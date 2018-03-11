# Android面试题全集（上）

### **1.如何将activity设置成窗口模式**

答：一共两种方式。  
1.在AndroidManifest.xml清单配置文件中修改当前Activity的theme属性。
```java
android:theme="@style/Theme.AppCompat.Light.Dialog"
```
2.自定义主题，也就是在styles.xml自定义代码，代码示例如下。
```java
 <style name="Theme.MainActivity" parent="Theme.AppCompat.Light.Dialog">  
        <item name="android:windowBackground">@drawable/xxxxxx</item>  
 </style> 
  ....
  应用主题：
 android:theme="@style/Theme.MainActivity" 
```
### **2.为什么要在主线程中创建AsyncTask**

答：这个要看Android版本，在4.1版本之前，一定要在主线程中创建AsyncTask,但是在4.1及其以上版本并没有这个限制。以前版本需要在UI线程创建，因为需要在主线程创建InternalHandler，以便onProgressUpdate， onPostExecute ， onCancelled 可以正常更新UI。

### **3.Android线程之间通信有几种方式**

答：1.runOnUiThread()；2.post()和postDelay()；
3.Handler + Message或者Handler + Thread + Message；
4.Broadcast；5.AsyncTask；
6.EventBus；7.rxjava；8.共享变量；

### **4.解析XMl有几种方式**

答：1.[SAX](https://baike.baidu.com/item/sax/3006235?fr=aladdin)使用流式处理的方式，它并不记录所读内容的相关信息。它是一种以事件为驱动的XML API，解析速度快，占用内存少。使用回调函数来实现。 缺点是不能倒退。  

2.[DOM](https://baike.baidu.com/item/DOM/50288)是一种用于XML文档的对象模型，可用于直接访问XML文档的各个部分。它是一次性全部将内容加载在内存中，生成一个树状结构,它没有涉及回调和复杂的状态管理。 缺点是加载大文档时效率低下。  

3.[Pull]()内置于Android系统中。也是官方解析布局文件所使用的方式。Pull与SAX有点类似，都提供了类似的事件，如开始元素和结束元素。不同的是，SAX的事件驱动是回调相应方法，需要提供回调的方法，而后在SAX内部自动调用相应的方法。而Pull解析器并没有强制要求提供触发的方法。因为他触发的事件不是一个方法，而是一个数字。它使用方便，效率高。

### **5.同一个程序，不同Activity是否可以放在不同任务栈中**

答：可以放在不同的Task中。需要为不同的activity设置不同的taskaffinity属性，启动activity的Intent需要包含FLAG_ACTIVITY_NEW_TASK标记，或者指定清单文件中启动模式为singleInstance。

### **6.横竖屏时候Activity的生命周期**

### **7.Android中进程与进程之间如何通信**

### **8.如何安全退出当前应用**

### **9.service是否在UI线程中执行**

### **10.service是否能执行耗时操作**

### **11.横竖屏时候Activity的生命周期**

### **12.service中是否可以弹吐司**

### **13.软键盘是如果适配的**

### **14.如何优化Android中的界面布局**

### **15.如何保存Activity状态**

### **16.Servcice、Activity如何进行数据传递**

### **17.如何解决AS中jar包冲突**

### **18.Android中的动画有哪几类，请简要说说**

### **19.如何解决AS中jar包冲突**

### **20.LruCache原理**

### **21.动画插值器**

### **22.SurfaceView有什么特点**

### **23.Fragment中replace和add方法区别**

### **24.Activity中的生命周期**

### **25.Fragment中的生命周期**

### **26.两个Activity之间跳转必然会执行那几个方法**

答：回答之前最好先回答Activity生命周期，假如A跳转到B分两种情况。  
1.A会调用onPause()，然后B调用onCreate()->onStart()->onResume()，A调用onStop()。  
2.假如B是透明对话框样式，A不会调用onStop()。

### **27.Activity管理机制**

### **28.为什么Timer比Alarmanager实现心跳更耗电**

### **28.为什么Timer比Alarmanager实现心跳更耗电**

### **29.Service的开启方式**

### **30.请描述一下Service 的生命周期### **

### **31.请说说view绘制流程**

### **32.如何适配字体**

### **33.广播的分类**

### ** 四大组件是什么**

### ** 四大组件的生命周期和简单用法**

### ** ScrollView中嵌套会引发什么问题，如何解决**

### ** 四大组件的生命周期和简单用法**

### ** 如何设置前台进程**

### ** 三级缓存**

### ** 禁止viewpager滑动**

### ** Servializable和Parcelable区别**

### ** 简述Activity、View、Window三者问题**

### **自定义控件MeasureSpec测量模式**

### **如何自定义控件**

### **Android中如何调用C语言**

### **多渠道打包**

### **微信扫码登录**

### **okhttp底层原理**

### **Android数字签名**

### **谈谈你对ContentProvider的理解**

### **说说ContentProvider、ContentResolver、ContentObserver 之间的关系**

### **mvvm、mvp、mvc理解**

### **Android NDK理解**

### **如何捕获崩溃异常**

### **热修复原理**

### **组件化原理**

### **插件化原理**

### **DexClassLoader和PathClassLoader区别**

### **Context和ApplicationContext区别**

### **padding和margin区别**

### **如何与js互调**

### **Framework工作方式以及原理**

### **Activity生成view**

### **如何与js互调**

### **能不能在子线程中实例化Handler**

### **Fragment如何实现类Activity任务栈**

### **自定义View注意线程问题有哪些**

### **如何与js互调**

### **事件分发机制**

### **如何保存Activity的状态**

### **如何与js互调**

### **Android数据存储有哪几种方式**

### **如何防止进程（app）被杀掉**

### **getX()和getRawX()有啥区别**

### **service生命周期**

### **如何与js互调**

### **AIDL**

### **如何与js互调**

### **Service和IntentService有啥区别**

### **如何与js互调**

### **JVM和Dalvik有啥区别**

### **如何与js互调**