# MobileAppSecurity

Original Link: https://infosecwriteups.com/hail-frida-the-universal-ssl-pinning-bypass-for-android-e9e1d733d29

* [Tools](#tools)



<h1 id="tools">Tools</h1>

* [Genymotion](https://www.genymotion.com/fun-zone/)

* [Python]()

	pip install Frida
	pip install objection
	pip install frida-tools

* [Platform Tools]()

* [Universal bypass](./fridascript.js)

<h1 id="setup">Setup</h1>

	adb connect 192.168.1.190:5555
	adb devices

* [Frida](https://github.com/frida/frida/releases/)

	adb shell getprop ro.product.cpu.abi

<h1 id="frida">Frida Setup</h1>

	adb push C:\ADB\frida-server /data/local/tmp
	adb shell chmod 777 /data/local/tmp/frida-server

<h1 id="burp">Burpsuite</h1>

	Setup Burp
	
<h1 id="inject">Inject Script</h1>

	adb push cacert.der /data/local/tmp/cert-der.crt
	adb shell /data/local/tmp/frida-server &
	frida-ps -U
	frida -U -f com.twitter.android -l D:\frida\fridascript.js --no-paus
