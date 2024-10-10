> 请在收到后的一周内完成   
> 如果有任何疑问，欢迎随时来信联系   
> 难免谬误，敬请指正，友好交流   
>   
> 完成后请发送到下面邮箱：   
```
Subject: 2024Q4 资深工程师 笔试回复 | {姓名}
To: hr-china@housesigma.com
```

一、使用PHP语言, 实现一个API请求限流器[RateLimiter]，要求如下:
  - 限制的请求对象可以是全局或者某一特定对象，比如根据用户ID或全部用户;
  - 至少实现两种常见的限流策略，并支持继续扩展;
  - 默认使用redis作为存储系统，并支持扩展为其它存储系统;
  - 交付内容需要包括该类库的用法文档和结构设计图;

三、通过数据库的慢日志，我们发现了一个慢请求，SQL和Explain分析结果如下
```
SELECT 
    filed_a
FROM table_l 
JOIN table_d on table_l.id = table_d.id
WHERE
    table_l.date_end >= DATE('2019-07-01' )
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
`其中 flag_type_date 为组合索引  KEY flag_type_date (flag,type,date_end,date_start)`
- 请根据上述信息，给出可能的优化办法并说明原因 


二、你在工作中一定遇到过许多技术挑战和有趣的项目。请描述一个给你留下深刻印象的工程实现或项目开发经历。
  - 简要介绍项目的背景、目标和重要性; 
  - 项目团队的组成和你在项目中扮演的角色;
  - 详细说明在项目中遇到的一个主要技术挑战或难题;
  - 请通过图文方式描述实现解决方案的过程和细节;