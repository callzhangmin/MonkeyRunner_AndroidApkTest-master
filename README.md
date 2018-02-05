MonkeyRunner_AndroidAppTest
====================================
Python+MonkeyRunner 渠道包测试脚本程序
=============使用说明=================
1、将需要测试的Apk文件全部放在apk文件夹中
2、将基线图放在screenShot文件夹中，按照自己的功能需求命名基线图
3、将手机通过数据线连接上电脑
4、运行Start.bat即可开始测试，测试结果保存在log文件夹中

=======================注意=====================
1、电脑需配置好Android SDK环境变量。
2、该程序默认是我自己的渠道包自动化测试，若需要测试其他应用，可自行修改ApkTest.py文件里的应用包名和入口名。
3、如果手机比较卡，打开应用比较慢，导致截图失败，可以修改ApkTest.py里的APP启动时等待时间。
4、基线图的来源应该是被测手机的截图。
  基线图获得：
安装好应用，打开后，直接截图即可。PS：若打开应用后自动弹出输入法，则输入法也要截进来。

==================测其他应用时，需要更改的参数=============
  应用包名：pakageName；
  入口Activity名：componentName；


=======工具原理=======：
    通过MonkeyRunner遍历apk文件夹里的apk文件，实现自动安装应用，打开应用，截图，将截图与提前准备好的基线图做对比，对比相似度达到90%时，则对比通过，然后自动卸载应用，进入下一个APK文件的对比流程。
    当apk目录下所有apk都执行完操作后，自动退出。
