### 房智汇 Android开发工程师面试问卷：
- 在5天内尽量完成，如果时间安排有冲突，请告知完成时间
- 可以上网查资料，问问题，问人，但必须自己动手完成
- 测试题比实际项目代码容易很多
- 对问题有不确定的地方及时发邮件 yuerengui（at）housesigma.com，tanwei（at）housesigma.com，reed（at）housesigma.com
- 远程面试本身就是对远程工作能力的测试，请当成正常工作交流
- 答案请发回： 
```
To: reed（at）housesigma.com
cc: yuerengui（at）housesigma.com, tanwei（at）housesigma.com
Subject: Android开发面试问卷回复 （姓名，城市）
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
Android APK：https://housesigma.com/static/housesigma-2.13.0-prd.apk    

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
### 问题0，写在最前面的问题
> 我们是个小团队，花费时间招人不易，能提供的岗位也有限。希望尽量多了解申请人，力争每个成员都可以安心的在这里工作。    
> 无需担心个人生活安排会影响面试结果。有孩子，不能加班 在我们这里不是减分项。    

- 目前是否在职，为什么会想来房智汇做远程职位？这个工作对你来说有哪些好处和不便的地方？
- 未来2年有打算常住哪个城市？
- 如果将来的5年都在我们公司工作，对职位，收入，工作内容有什么期待？（最理想的状况）
- 团队会议时间外，平时的工作日打算怎么安排时间？
- 有什么想问的问题？

---
### 问题1 Google map 相关
> 此题为代码相关面试题，UI美观会加分，但是基础样式的UI并不是减分项 
- 根据下图完成相关demo，必须包含的功能有
    - 使用Google map sdk开发可交互地图
    - 在地图指定坐标上放置marker
    - 点击marker可以弹出下图中底部的浮层，展示可左右滚动切换的视图
- 渲染内容相关的数据在 mapdata.json 中
- 兼容安卓版本>=9

![图2](https://user-images.githubusercontent.com/8005462/148961361-aebc3563-82ac-4505-8cd5-19252fb9b7f8.png)

**答案格式**
- 源代码上传github（或者打包）
- 编译好的 apk

---
### 问题2 请描述一下你对Android App Bundle的理解
- 

---
### 问题3
#### 3.1 需实现一个超大滚动列表，具体需求如下：
- 总数据超过一万条，后端api接口可以根据参数size、page返回相应页面与数据
```
size = 10, page = 1，即每页返回10条记录，当前为第1页
size = 100, page = 4，即每页返回100条记录，当前为第4页....依次类推
```
- 每条记录为ID与简单文本。

- 需用户可以顺滑的上下滚动查看内容，尽可能少的占用内存。
- 写出关键的代码，并阐述原理。

#### 3.2 若上一问题中返回的数据中每条记录均包含图片并需要展示：
- 在处理上与之前是否有不同？是否有什么需要注意的地方？
- 可以写出关键代码或阐述实现方案。

---
### 问题4 用户在实际使用App的过程中偶尔会出现Crash的情况
- 我们应该如何知晓Crash的信息，分享你实际处理过的方案。
- 同时我们又可以进行那些处理，以保证用户有最佳的体验。

#### 4.2
- H5混编app报以下崩溃错误，应该怎样处理？
```
Caused by java.lang.RuntimeException
Using WebView from more than one process at once with the same data directory is not supported. https://crbug.com/558377 
```


---
### 问题5
- 你认为App绘制的关键性能指标是哪些，分别应该如何获取与监测？


