# pyrus_modified

Репа создана для модификации APK Pyrus - после версии 239 сломали deeplink. Ну мы починим 
##Вариант 1 - вручную

1 на vscode установить apklab

2 скачать from apkpure new version  https://apkpure.com/pyrus/net.papirus.androidclient

3 распаковать через 7zip

4 запустить vscode

5 ctrl-shift-p ввести APKLab: Open an APK и выбрать файл net.papirus.androidclient.apk

6 выбрать галочки что бы не декомпилить всякое, нажать Enter

7 Найти в манифесте "android.intent.category.BROWSABLE"

+ добавить там (в 2 места)
+ 
<data android:host="*.pyrus.com"/>

и сохранить

8 ткнуть на apktool.yml выбрать APKLab: Rebuild the APK

9 Повторить с файлом config.arm64_v8a.apk пункты 5,6,8

10 запустить CMD, пойти в папку куда распаковак xapk

11 adb install-multiple net.papirus.androidclient\dist\net.papirus.androidclient.apk  config.arm64_v8a\dist\config.arm64_v8a.apk

##Вариант 2 - Скачать 

1 скачиваем файлы dist.zip.001 dist.zip.002

2 через 7-zip распаковываем

3 запускаем в этой папке cmd

4 adb install-multiple net.papirus.androidclient.apk  config.arm64_v8a.apk

