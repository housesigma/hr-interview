### 招聘流程：

![image](https://user-images.githubusercontent.com/16353524/170642451-221c799e-281b-4009-98c2-1f19b11fae20.png)


如果没有重大变化，我们就只看问卷答案。不会在语音面试前另外联络申请人。

--- 

# HouseSigma 前端开发面试问卷。

- 在5天内尽量完成，如果时间安排有冲突，请告知完成时间
- 可以上网查资料，问问题，问人，但必须自己动手完成
- 测试题比实际项目代码容易
- 对问题有不确定的地方及时发邮件 yuerengui（at）housesigma.com，tanwei（at）housesigma.com，reed（at）housesigma.com，jiangyilong（at）housesigma.com
- 远程面试本身就是对远程工作能力的测试，请当成正常工作交流
- 答案请发回： 
  ```
  To: reed（at）housesigma.com
  cc: yuerengui（at）housesigma.com, tanwei（at）housesigma.com，jiangyilong（at）housesigma.com
  Subject: VUE开发面试问卷回复 （姓名，城市）
  ```

---

#### 公司业务背景：

HouseSigma（房智汇）是面向加拿大-多伦多购房者的投资买房利器。

- 提供过去15年的房屋成交历史和价格。
- 多种数据图表
- 提供买卖房经纪服务
活动用户量，月pv 同行业排名前3（多伦多地区）。
用户集中在加拿大英文用户，中文版流量占不到4%

桌面版网站：https://housesigma.com/web/
移动版网站：https://housesigma.com/app/    
iOS App：https://itunes.apple.com/ca/app/housesigma-toronto-sold-price/id1255490256?mt=8    
Android App: https://play.google.com/store/apps/details?id=com.housesigma.android&hl=en_CA    
Android APK：https://static.housesigma.com/android_apk/housesigma-4.1.8-prd.apk 

---

### 工作时间安排

多伦多和中国有12小时时差（冬季13小时）我们的工作时间

- 每周 1，4 团队语音会议
  - 夏季: 北京时间早上9：00，相当于多伦多时间晚上9：00
  - 冬季: 北京时间早上9：00，相当于多伦多时间晚上8：00
- 其余时间灵活安排自己的工作进度，工作时间，休息时间。
- 工作内容在 issue tracker + 钉钉。有急事打电话。

我们平时的工作氛围比较轻松

- 极少出现加班的情况。（过去一年里大概有几次，紧急bug）
- 安静的在家钻研技术打磨产品。不搞那些有用没用的 work hard play hard
- 请假，调休提前说。急事就直接去, 钉钉给我留言。

期待每周5x8小时工作是有效率的工作。
不想看到的：

- 无故连续不能提交进度
- 工作时有紧急业务不响应
- 工作时不查看协作工具

---

### 写在最前面的问题

> 我们是个小团队，花费时间招人不易，能提供的岗位也有限。希望尽量多了解申请人，力争每个成员都可以安心的在这里工作。    
有孩子，不能加班 在我们这里不是减分项。正常情况也不要加班。    

- 目前是否在职，为什么会想来房智汇做远程职位？这个工作对你来说有哪些好处和不便的地方？
- 未来2年有打算常住哪个城市？
- 如果将来的5年都在我们公司工作，对职位，收入，工作内容有什么期待？（最理想的状况）
- 团队会议时间外，平时的工作日打算怎么安排时间？
- 有什么想问的问题？

---

### 面试问题 1 - coding

1. 请从0开始构建一个vue3脚手架
   1. 请使用Typescript，scss
   2. 包含状态管理（ pinia ）、路由等基础功能
   3. UI控件请使用纯css/scss，不引入第三方UI框架
2. 使用脚手架实现下面的页面
   - 设计稿：https://www.figma.com/file/3iBGSHYN255KPzhU7jwHyc/Reed-interview?node-id=0%3A1
   - 地图数据：https://github.com/housesigma/hr-interview/blob/main/Android/mapdata.json
     - 地图使用Google Map，测试Key请在邮件中查收
     - 数据中的地址在 加拿大-温哥华
   - 需求说明：
     - 按照设计稿实现所有的UI
       - 必须完成：加载地图，标记，filter 菜单
       - *可不完成：导航条，搜索框，watch按钮
     - 地图上根据提供的地图数据，显示标记
     - 【黄标1】筛选功能，只需要实现Filters按钮的功能
     - 【黄标2】多选，点击Any 清除其它选项
     - 【黄标3】单选
     - 【黄标4】单选
     - 点击clear按钮，清除所有选项，填充默认值
     - 点击apply按钮，隐藏filters弹窗，并在地图页上显示一个alert,显示接收到apply事件（alert内容可以简单写 “已完成过滤” 之类的就可以）。
     - 筛选的值保存状态到Pinia Store中，并同步更新到本地localstore或者indexdb作持久化存储，刷新页面后从本地存储取值填充回Pinia中，同步更新UI。
   - 
     - 导航条上的
![image](https://user-images.githubusercontent.com/16353524/170638274-0007dc47-c61c-4add-b233-cdbc417b7ae4.png)

---

### 面试问题2  - pagespeed

页面速度有2方面的考虑：

- 用户体验
- SEO

慢的页面不但影响用户，也会影响SEO排名。以下列出了我们的网站和竞品

```
桌面端
https://housesigma.com/web/
https://housesigma.com/web/en/house/aQmD7zn0LEM7J9Bo/10-Connaught-Ave-London-N5Y3A3-X5634582
手机端
https://housesigma.com/app/
https://housesigma.com/app/en/listing/aQmD7zn0LEM7J9Bo/10-Connaught-Ave-London-N5Y3A3-X5634582
```

```
竞品
https://www.zolo.ca/oakville-real-estate/467-hedgerow-lane
https://www.redfin.ca/on/toronto/116-Wheeler-Ave-M4L-3V2/home/151707805
```

1. 有哪些地方我们的网站做的不好，需要改善？
   1. 哪些问题是影响用户体验的，哪些是影响SEO的？    

2. 为了得到以上答案，使用了什么页面速度调试和报告工具？
   1. 为什么要使用这个（些）工具？    
   2. 不同的测试指标有什么意义？      

3. 需要怎样改善？

注1: 我们面向的是加拿大用户，暂不考虑中国大陆地区用户的访问体验。测试结果以海外版为基准。

注2: HouseSigma网站从中国IP访问，和用海外IP访问，是不一样的服务器。（GeoDNS）    
一般使用海外的测试网站（ https://pagespeed.web.dev/ ）， 测的是我们北美服务器（机器快，带宽大）    
如果从中国运行测试（Chrome dev），访问的是我们的亚洲镜像（带宽小）

#### 答案格式

- 请尽量完整的介绍解决思路, 有可能的排查方向|手段, 如果使用到某些工具也请一并列出

---

### 面试问题 3

用vue.js，angular（或类似框架）开发的SPA，运行时发现浏览器报告内存使用过高。很多iPhone X，XS 用户反馈使用时间长了容易崩溃

- 怎样调试判断是否有内存泄漏？
- 如果是内存泄漏通过哪些手段修复？
- 如果不是内存泄漏怎么办？

*结合自己曾经解决的案例说明。

---

### 面试问题 4

有一个项目，需要进行多端开发（桌面端、移动端），采用同一套后端API，前端决定使用vue 的情况下，如果才能最大化的做到代码复用？ 业界有没有什么成熟的方案？ 
