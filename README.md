# pyrus_modified

Репа создана для модификации APK Pyrus - после версии 239 сломали deeplink. Ну мы починим 

0 SET VERSION=242
1 download from apkpure new version https://apkpure.com/pyrus/net.papirus.androidclient
2 apktool.bat d Pyrus_4.242.011_APKPure.xapk -o %VERSION%
3 apktool.bat d .\%VERSION%\unknown\net.papirus.androidclient.apk -o %VERSION%_apk
4 notepad net.papirus.androidclient\AndroidManifest.xml

5 search string  "android.intent.category.BROWSABLE"

5 replace inside

<data android:host="pyrus.com" android:pathPrefix="/rd/signin" android:scheme="https"/>
<data android:host="*.pyrus.com" android:pathPrefix="/rd/signin" android:scheme="https"/>

6 apktool b %VERSION%_apk -o net.papirus.androidclient.apk
7 copy /Y net.papirus.androidclient.apk .\%VERSION%\unknown\
8 apktool b %VERSION% -o Pyrus_%VERSION%_Modified.xapk

