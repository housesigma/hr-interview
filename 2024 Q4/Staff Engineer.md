> 请在收到后的一周内完成   
> 如果有任何疑问，欢迎随时来信联系   
> 难免谬误，敬请指正，友好交流   
>   
> 完成后请发送到下面邮箱：   
```
Subject: 2024Q4 资深工程师 笔试回复 | {姓名}
To: hr-china@housesigma.com
```

一、使用PHP语言实现一个灵活可扩展的API请求限流器 [RateLimiter]，要求如下：
  - 支持对不同请求对象进行限流控制，可以是全局限流（所有用户共享限额）或针对特定对象（例如，根据用户ID进行限流）
  - 至少实现两种常见的限流策略（如漏桶算法、令牌桶算法），并且能够方便地扩展更多限流策略
  - 默认使用Redis作为限流数据的存储系统，同时支持轻松切换或扩展为其他存储系统（如数据库、内存等）
  - 提供详细的使用文档和类库的结构设计图，帮助开发者快速理解和上手使用;

二、通过数据库的慢日志，我们发现了一个慢请求[执行时间 > 1s]，原始SQL和Explain分析结果如下
```
SELECT 
    filed_a
FROM table_l 
JOIN table_d on table_l.id = table_d.id
WHERE
    table_l.date_end >= DATE('2019-07-01')
    AND table_l.date_end < (DATE('2019-07-01') + INTERVAL 1 month)
    AND table_l.date_end >= table_l.date_start
    AND table_l.flag = 1
    AND table_l.type = "S"
    AND table_d.id_m = 1234
```

| id  | select_type | table   | partitions | type   | possible_keys                             | key            | key_len | ref        | rows  | filtered | Extra                    |
| --- | ----------- | ------- | ---------- | ------ | ----------------------------------------- | -------------- | ------- | ---------- | ----- | -------- | ------------------------ |
| 1   | SIMPLE      | table_l |            | range  | PRIMARY,flag,date_end,type,flag_type_date | flag_type_date | 40      |            | 61708 | 33.33    | Using where; Using index |
| 1   | SIMPLE      | table_d |            | eq_ref | PRIMARY,id_m                              | PRIMARY        | 4       | table_l.id | 1     | 5.00     | Using where              |

- table_l是主表、table_d是副表，总数据量接近1KW
- 其中 flag_type_date 为组合索引  KEY flag_type_date (flag,type,date_end,date_start)
- DATE('2019-07-01')、flag = 1、'S'、1234 这几个参数值都会根据场景而不同
- 请根据上述信息，给出可能的优化办法并说明原因 


三、你在工作中一定遇到过许多技术挑战和有趣的项目。请描述一个给你留下深刻印象的工程实现或项目开发经历。
  - 简要介绍项目的背景、目标和重要性; 
  - 项目团队的组成和你在项目中扮演的角色;
  - 详细说明在项目中遇到的一个主要技术挑战或难题;
  - 请通过图文方式描述实现解决方案的过程和细节;
