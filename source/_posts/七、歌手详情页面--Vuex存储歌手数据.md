---
title: 七、歌手详情页面--Vuex存储歌手数据
date: 2019-01-19 00:00
updata: 2019-08-11 19:45
categories:
- Vue2.0开发企业级移动音乐APP
tags: 移动音乐APP
---
#### 本节总览
---
> 本节代码提交至：[chapter7](https://github.com/liugezhou/liugezhou_music/tree/chapter7)
#### 效果预览：
![singer-detail.png](http://img.liugezhou.online/Vue2-07.png)

>本节实现点击歌手提交mutation，将歌手数据存储在store中，涉及到整个Vuex技术栈。
本节主要代码开发是singer-detail组件。
singer-detail调用开发的music-list组件：将歌手歌曲数据、背景图片以及歌手姓名传入到music-list组件中。
music-list组件中分为上半部分与下半部分两块，下半部分的歌曲列表再分离成song-list组件。
即总共包含三个组件的开发，还有一些酷炫、美丽的花朵、图片拖拽等的效果。

#### 代码更新
---
>`主要`更新代码列表如下：
 ```
   /src/components/singer-detail/singer-detail.vue
   /src/store  //文件夹下包含多个文件
   /src/api/singer.js
   /src/components/music-list/music-list.vue
   /src/base/song-list/song-list.vue
```

### 本节代码开发知识点及代码思路：
---
####  一、`transition` | 进入/离开 & 列表过渡

>官方学习：https://cn.vuejs.org/v2/guide/transitions.html
小结：
1.transition标签包裹
2.进入时：`name-enter`与`name-enter-active`
3.离开时：`name-leave-to`与`name-leave-active`
4.CSS3-3D转换(`translate3d`)
关于Vue的动画效果与CSS3动画效果的学习，一定要去Vue的官方文档进行一个系统的学习。

#### 二、Vuex

>官方学习：https://vuex.vuejs.org/zh/
>小结：
>1.Vuex 是一个专为 Vue.js 应用程序开发的`状态管理模式`。
>2.Vuex 背后的基本思想，借鉴了 [Flux](https://facebook.github.io/flux/docs/overview.html)、[Redux](http://redux.js.org/)、和 [The Elm Architecture](https://guide.elm-lang.org/architecture/)
>3.Vuex 和单纯的全局对象有两点不同:
   1️⃣、Vuex 的状态存储是响应式的
   2️⃣、你不能直接改变` store `中的状态。改变 `store `中的状态的唯一途径就是显式地提交 `(commit) mutation`。
>4.可以通过 `store.state.count` 来获取状态对象，以及通过` store.commit` 方法触发状态变更.
>5.强调:我们通过提交` mutation `的方式，而非直接改变` store.state.count`，是因为我们想要更明确地追踪到状态的变化.
>6.`mapState `辅助函数| `对象展开运算符`
>7.`Getter`:从 `store `中的 `state` 中派生出一些状态:[详请](https://vuex.vuejs.org/zh/guide/getters.html)
>8.[mapGetters 辅助函数](https://vuex.vuejs.org/zh/guide/getters.html#mapgetters-%E8%BE%85%E5%8A%A9%E5%87%BD%E6%95%B0)
>9.[Mutation](https://vuex.vuejs.org/zh/guide/mutations.html)
>>1️⃣、接受 state 作为第一个参数
>>2️⃣、可以向 `store.commit `传入额外的参数，即 `mutation `的 载荷（payload）
>>3️⃣、使用常量替代 Mutation 事件类型（本节使用）
>>4️⃣、Mutation 必须是同步函数
>
> 10.[Action](https://vuex.vuejs.org/zh/guide/actions.html)
>> `Action `类似于` mutation`，不同在于：
>>①、`Action` 提交的是 `mutation`，而不是直接变更状态。
>>②、`Action` 可以包含任意`异步`操作。
>
>11.[Module](https://vuex.vuejs.org/zh/guide/modules.html)
为了解决store 对象可能变得相当臃肿的问题。
……
#### 三、通过jsonp--以singer.id为参数，获取歌手详情数据
>在`api/singer.js`中添加`getSingerDetail(singerId)`方法。
api中的诸多方法都是通过jsonp方式获取数据，不再赘述。
#### 四、歌手详情数据处理和song类的封装
>通过jsonp获取到了歌手详情的数据后，需要对详情数据进行优化，将优化的数据进行存储。
>在`common/js`中新建`song.js`，开发song类 ，避免代码冗余----[小拓展：ES6-Class基本语法](https://www.jianshu.com/p/0743e31cd911)
#### 五、music-list组件开发

> 新建文件`/src/components/music-list/music-list.vue`  
> musicl-list布局，在之前也对歌手的song数据进行了封装存储后，我们继续分析需求，我们发现多个页面与歌手详情页面是类似的（头部的大图片与歌曲list区块），于是开发song-list组件（下半部分的歌曲列表），方便各个地方进行使用。

#### 后面的代码暂时就不分析了，直接github上clone下chapter7分支代码即可，这个歌手详情页真是美的不像话。

#### 20190823代码分析更新
> 1. 添加路由子路由(children),点击歌手列表中某歌手跳转至某歌手页面，代码修改的地方：[戳这里](https://github.com/liugezhou/liugezhou_music/blob/chapter7/src/router/index.js)。 
> 
> 2. 开发歌手详情页面，代码查看：[戳这里](https://github.com/liugezhou/liugezhou_music/blob/chapter7/src/components/singer-detail/singer-detail.vue). --这里使用了transition动画.  
> 
> 3. 使用Vuex，在store下新建一系列文件，可直接查看代码。这里的代码规范也可以让我们在使用到Vuex的时候按这种方式进行代码管理。
>  
> 4. 写获取歌手歌曲列表的方法：[代码在这里](https://github.com/liugezhou/liugezhou_music/blob/chapter7/src/api/singer.js)
>   
> 5. 构建一个song类，用来处理需要的song的数据：[代码在这里](https://github.com/liugezhou/liugezhou_music/blob/chapter7/src/common/js/song.js) ,这个很重要是为了在上面的第二步骤处理获得到的song数据--song数据的二次封装。
> 
> 6. music-list组件开发：[代码](https://github.com/liugezhou/liugezhou_music/blob/chapter7/src/components/music-list/music-list.vue)。
>
> 7. 基础组件song-list组件开发：[代码](https://github.com/liugezhou/liugezhou_music/blob/chapter7/src/base/song-list/song-list.vue)--包含酷炫的上滑下拉的效果。

>关于本节如果你有任何问题可以在下方留言。
>如有疑问请添加我的微信号：18231133236。欢迎交流！  
>更多内容，请访问的我的个人博客：[https://www.liugezhou.online](https://links.jianshu.com/go?to=https%3A%2F%2Fwww.liugezhou.online).