# WishOfTeen小程序文档介绍

#### appid：wx28eb07c7948167e7

**组队情况：个人组队**



## 应用场景分析与拟实现的功能介绍

* 应用场景：众所周知，在基层党员干部人力严重不足的农村社会，众多相应党号召的活动、检测、监督、建设、扶贫扶弱行为都是依靠热心的志愿者朋友们帮助完成的，但受农村信息渠道限制，志愿力量往往不能与志愿需求紧密贴合，出现资源与需求不平衡的问题，而一款能够协助志愿供需双方的小程序无疑能够为农村志愿事业的发光发热助力。

* 拟实现功能
  * 迭代一（已实现）：
    * 微信账号授权登录
    * 业务账号信息展示
    * 虚拟用户志愿时长排行榜
  * 迭代二：(已实现)
    * 志愿活动招募发布
    * 主页志愿活动列表展示
  * 迭代三：(已实现)
    * 志愿活动领取
    * 已发布志愿详情
    * 已接受志愿详情
  * 迭代四：(已实现)
    * 布局优化
    * 业务逻辑优化



## 采用的技术与方法

* 前端：微信小程序
* 后端：微信云开发
* 数据库：微信云开发
* 第三方库：axios

* 登录验证：微信小程序api、axios
  * `getUserProfile`获取用户微信头像、昵称、openid授权
  * `getStorageSync`等api缓存用户sessionID及过期时间，从而实现一定时间内再使用小程序时无需登录
  * 云函数使用axios库进行http访问微信开放接口
* 页面管理
  * 详情页、列表页：已报名志愿、已发布志愿、主页志愿的**列表**及**详情**页使用同一页面代码，在路由时传入不同参数进行不同布局、样式的展示及特有元素节点的显示/隐藏
  * 登录页面：由于采用云函数及微信开放接口的方式进行用户认证，故不提供登录、注册页面，只需要授权登录即可使用，优化业务逻辑

## 产品功能展示和使用方法

* 无需注册，授权微信账号头像、昵称、微信openid使用即可登录
* 首页展示待领取的支援招募信息
* 个人主页可发布招募、查看个人志愿时长等信息
* 排行榜根据用户支援总时长及近期志愿时长进行排名
* 首页点击进度各志愿活动详情页并接取志愿
* 个人主页可查看已发布和已接取的志愿详情
* 志愿详情页可点击完成已发布的志愿，将会给所有接取志愿的用户增加志愿时长
* 支持重复点击底部tabbar进行页面刷新


**详细使用方法见演示视频**
