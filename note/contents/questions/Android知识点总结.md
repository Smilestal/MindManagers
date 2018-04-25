# Android面试题
https://hit-alibaba.github.io/interview/Android/basic/Android-LaunchMode.html

Android面试题除了Android基础之外，更多的问的是一些源码级别的、原理这些等。所以想去大公司面试，一定要多看看源码和实现方式，常用框架可以试试自己能不能手写实现一下，锻炼一下自己。

### 一、Android基础知识点

* 四大组件是什么
    Activity、Service、BroadcastReceiver、ContentProvider

* 四大组件的生命周期和简单用法
    Activity：
        生命周期：onCreate、onStart、onResume、onPause、onStop、onRestart、onDestroy

    Service：
        生命周期：
            手动方法：startService、bindService、unbindService、stopService
            自动方法：onCreate、onStartCommand、onBind、onUnBind、onDestroy

    BroadcastReceiver：
        生命周期：onReceiver


* Activity之间的通信方式
    Intent
    借助类的静态变量
    借助全局变量/Application
    借助外部工具
    – 借助SharedPreference
    – 使用Android数据库SQLite
    – 赤裸裸的使用File
    – Android剪切板
    借助Service

* Activity各种情况下的生命周期
* 横竖屏切换的时候，Activity 各种情况下的生命周期
* Activity上有Dialog的时候按Home键时的生命周期
* 两个Activity 之间跳转时必然会执行的是哪几个方法？
* 前台切换到后台，然后再回到前台，Activity生命周期回调方法。弹出Dialog，生命值周期回调方法。

* Activity与Fragment之间生命周期比较
    Fragment生命周期：
        被创建：
            onAttach、onCreate、onCreateView、onActivityCreated
        对用户可见：
            onStart、onResume
        进入后台模式：
            onPause、onStop
        被销毁：
            onDestroyView、onDestroy、onDetach

    fragments的大部分状态都和activitie很相似，但fragment有一些新的状态。

    onAttached() —— 当fragment被加入到activity时调用（在这个方法中可以获得所在的activity）。
    onCreateView() —— 当activity要得到fragment的layout时，调用此方法，fragment在其中创建自己的layout(界面)。
    onActivityCreated() —— 当activity的onCreated()方法返回后调用此方法
    onDestroyView() —— 当fragment中的视图被移除的时候，调用这个方法。
    onDetach() —— 当fragment和activity分离的时候，调用这个方法。
    一旦activity进入resumed状态（也就是running状态），你就可以自由地添加和删除fragment了。因此，只有当activity在resumed状态时，fragment的生命周期才能独立的运转，其它时候是依赖于activity的生命周期变化的。


* Activity的四种启动模式对比
    standard：每次启动Activity都会创建一个新的Activity实例
    singleTop：每次扫描栈顶，如果在任务栈顶发现了相同的实例则重用，否则新建并压入栈顶。
    singleTask：与singleTop的区别是singleTask会扫描整个任务栈，如果任务栈中存在相同的实例，则将其上层的实例全部移除，再重用，否则新建实例。
    singleInstance：Activity的实例在一个独立的任务栈中，当不同应用交替调用次实例时，只要该任务栈中存在该实例，都重用。

* Activity状态保存于恢复
    什么时候需要保持数据
        正常销毁时不需要保存数据
            按back键或者Activity调用finish销毁时
        非正常销毁时需要保存数据
            被停止或长期未使用，或者前台Activity需要更多资源以致该Activity被系统关闭
            屏幕旋转、键盘可用性改变、 语言改变
            如果需要模拟这种情况的Activity销毁，可以打开开发者选项，选择不保留活动（英文为Do not keep activities），即可模拟内存不足时的系统行为。

    什么时候调用onSaveInstanceState
        屏幕旋转重建会调用onSaveInstanceState()
        启动另一个activity: 当前activity在离开前会调用onSaveInstanceState()
        按Home键的情形和启动另一个activity一样, 当前activity在离开前会onSaveInstanceState()

    什么时候调用onRestoreInstanceState
        保存的情况下重新回到该界面时，恢复数据调用此方法


* fragment各种情况下的生命周期
* Fragment状态保存startActivityForResult是哪个类的方法，在什么情况下使用？

* 如何实现Fragment的滑动？
* fragment之间传递数据的方式？

* Activity 怎么和Service 绑定？
* 怎么在Activity 中启动自己对应的Service？
* service和activity怎么进行数据交互？
* Service的开启方式
* 请描述一下Service 的生命周期

* 谈谈你对ContentProvider的理解
* 说说ContentProvider、ContentResolver、ContentObserver 之间的关系

* 请描述一下广播BroadcastReceiver的理解
* 广播的分类
* 广播使用的方式和场景
* 在manifest 和代码中如何注册和使用BroadcastReceiver?
* 本地广播和全局广播有什么差别？
* BroadcastReceiver，LocalBroadcastReceiver 区别

* AlertDialog,popupWindow,Activity区别
* Application 和 Activity 的 Context 对象的区别

* Android属性动画特性
* 如何导入外部数据库?
* LinearLayout、RelativeLayout、FrameLayout的特性及对比，并介绍使用场景。

* 谈谈对接口与回调的理解
* 回调的原理
* 写一个回调demo
* 介绍下SurfView
* RecycleView的使用
* 序列化的作用，以及Android两种序列化的区别
* 差值器
* 估值器
* Android中数据存储方式
    网络
    文件
    SharedPerference
    ContentProvider
    SQLite数据库

### 二、Android源码相关分析

* Android动画框架实现原理
* Android各个版本API的区别
* Requestlayout，onlayout，onDraw，DrawChild区别与联系
* invalidate和postInvalidate的区别及使用
* Activity-Window-View三者的差别
* 谈谈对Volley的理解
* 如何优化自定义View
* 低版本SDK如何实现高版本api？
* 描述一次网络请求的流程
* HttpUrlConnection 和 okhttp关系
* Bitmap对象的理解
* looper架构
* ActivityThread，AMS，WMS的工作原理
* 自定义View如何考虑机型适配
* 自定义View的事件
* AstncTask+HttpClient 与 AsyncHttpClient有什么区别？
* LaunchMode应用场景
* AsyncTask 如何使用?
* SpareArray原理
* 请介绍下ContentProvider 是如何实现数据共享的？
* AndroidService与Activity之间通信的几种方式
* IntentService原理及作用是什么？
* 说说Activity、Intent、Service 是什么关系
* ApplicationContext和ActivityContext的区别
* SP是进程同步的吗?有什么方法做到同步？
* 谈谈多线程在Android中的使用
* 进程和 Application 的生命周期
* 封装View的时候怎么知道view的大小
* RecycleView原理
* AndroidManifest的作用与理解

### 三、常见的一些原理性问题

* Handler机制和底层实现
* Handler、Thread和HandlerThread的差别
* handler发消息给子线程，looper怎么启动？
* 关于Handler，在任何地方new Handler 都是什么线程下?
* ThreadLocal原理，实现及如何保证Local属性？
* 请解释下在单线程模型中Message、Handler、Message Queue、Looper之间的关系
* 请描述一下View事件传递分发机制
* Touch事件传递流程
* 事件分发中的onTouch 和onTouchEvent 有什么区别，又该如何使用？
* View和ViewGroup分别有哪些事件分发相关的回调方法
* View刷新机制
* View绘制流程
* 自定义控件原理
* 自定义View如何提供获取View属性的接口？
* Android代码中实现WAP方式联网
* AsyncTask机制
* AsyncTask原理及不足
* 如何取消AsyncTask？
* 为什么不能在子线程更新UI？
* ANR产生的原因是什么？
* ANR定位和修正
* oom是什么？
* 什么情况导致oom？
* 有什么解决方法可以避免OOM？
* Oom 是否可以try catch？为什么？
* 内存泄漏是什么？
* 什么情况导致内存泄漏？
* 如何防止线程的内存泄漏？
* 内存泄露场的解决方法
* 内存泄漏和内存溢出区别？
* LruCache默认缓存大小
* ContentProvider的权限管理(解答：读写分离，权限控制-精确到表级，URL控制)
* 如何通过广播拦截和abort一条短信？
* 广播是否可以请求网络？
* 广播引起anr的时间限制是多少？
* 计算一个view的嵌套层级
* Activity栈
* Android线程有没有上限？
* 线程池有没有上限？
* ListView重用的是什么？
* Android为什么引入Parcelable？
* 有没有尝试简化Parcelable的使用？

### 四、开发中常见的一些问题

* ListView 中图片错位的问题是如何产生的?
* 混合开发有了解吗？
* 知道哪些混合开发的方式？说出它们的优缺点和各自使用场景？（解答：比如:RN，weex，H5，小程序，WPA等。做Android的了解一些前端js等还是很有好处的)；
* 屏幕适配的处理技巧都有哪些?
* 服务器只提供数据接收接口，在多线程或多进程条件下，如何保证数据的有序到达？
* 动态布局的理解
* 怎么去除重复代码？
* 画出 Android 的大体架构图
* Recycleview和ListView的区别
* ListView图片加载错乱的原理和解决方案
* 动态权限适配方案，权限组的概念
* Android系统为什么会设计ContentProvider？
* 下拉状态栏是不是影响activity的生命周期
* 如果在onStop的时候做了网络请求，onResume的时候怎么恢复？
* Bitmap 使用时候注意什么？
* Bitmap的recycler()
* Android中开启摄像头的主要步骤
* ViewPager使用细节，如何设置成每次只初始化当前的Fragment，其他的不初始化？
* 点击事件被拦截，但是想传到下面的View，如何操作？
* 微信主页面的实现方式
* 微信上消息小红点的原理
* CAS介绍（这是阿里巴巴的面试题，我不是很了解，可以参考博客: [CAS简介](http://blog.csdn.net/jly4758/article/details/46673835)）
