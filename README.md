# TestBugly
bugly热更新
测试 腾讯的bugly热更新
demo运行通过
加固工具:360加固保
我的360加固只是为了打多渠道包，统计数据。所以加固后的apk不需要再重签名，就可以实现热更新。
Android Studio有两种打包方式:手动打包，自动打包
手动打包:就是Build->Generate Signed Bundle/APK 
自动打包:进入tinker-support.gradle 页面，右边有Gradle 预览 ，点击build->assembleRelease，打包前需要在build.gradle配置签名文件

这两种打包方式最后得到的apk是一样的，就是我们要的基准包，如果你的360加固只是为了统计数据，那么直接加固不影响热更新的功能
补丁包:同样的页面 ,右边Gradle预览，点击tinker-support->buildTinkerPatchRelease，这个就是补丁包，打包前需要修改tinker-support.gradle的tinkerId，这个tinkerId不能与基准包的id相同，baseApkDir这个是你生成基准包apk的目录。
更详细的可以去看
https://bugly.qq.com/docs/user-guide/instruction-manual-android-hotfix/?v=20181014122344
官方文档的tinker-support.gradle 缺少 tinkerEnable = true
