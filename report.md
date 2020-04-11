# Отчет #

### Установка дистрибутивов ПО в ос Windows с помощью скрипта *.bat ###

- архиватор [7-zip](https://www.7-zip.org/a/7z1900-x64.msi): `msiexec /i 7z1900-x64.msi`
    - `/passive` автоматический режим - только указатель хода выполнения,
    - `/norestart` без перезагрузки,
    - `/le 7zip-log.txt` вести журнал установки с отображением все сообщений об ошибках в файл 7zip-log.txt,
    - `TARGETDIR="C:\Program Files\7-Zip"` каталог для установки указать явно "C:\Program Files\7-Zip";
- графический редактор [Paint.Net](http://dl2.topfiles.net/files/2/61/670/NU1iN2LEDEQzK2FrWVRqcDlTS2dBeDhKSnIyWXREbFo5bjJUWWIxZkVRblNpbz06OifR1qa1AtBWueFZ0M8kpE4/paintnet_4.2.10.exe): `paintnet_4.2.10.exe`
    - `/auto` полностью автоматическая установка (в том числе и согласие с лицензией),
    - `DESKTOPSHORTCUT=1` на рабочий стол вывести ярлык для запуска приложения,
    - `TARGETDIR="C:\Program Files\Graphics\Paint"`каталог для установки — "C:\Program Files\Graphics\Paint";
- векторный графический редактор [Inkscape](https://inkscape.org/ru/release/inkscape-0.92.4/windows/64-bit/msi/dl/): `msiexec /i inkscape-0.92.4-x64.msi`
    - `/qr` установка с сокращенным интерфейсом,
    - `/norestart` без перезапуска,
    - `/le inkscape-log.txt` вести журнал установки с отображением всех сообщений об устранимых ошибках в файл inkscape-log.txt,
    - `INSTALLDIR="C:\Program Files\Graphics\Inkscape"` каталог для установки указать явно "C:\Program Files\Graphics\Inkscape";
- офисный редактор [LibreOffice](http://download.documentfoundation.org/libreoffice/stable/6.4.2/win/x86_64/LibreOffice_6.4.2_Win_x64.msi): `msiexec /i LibreOffice_6.4.2_Win_x64.msi`
    - `/passive` автоматический режим - только указатель хода выполнения,
    - `/norestart` без перезагрузки после установки,
    - `/le libreoffice-install-log.txt` вести журнал установки с отображением всех сообщений об ошибках в файл libreoffice-install-log.txt,
- дополнение к LibreOffice [русское языковое расширение](http://download.documentfoundation.org/libreoffice/stable/6.4.2/win/x86_64/LibreOffice_6.4.2_Win_x64_helppack_ru.msi): `msiexec /i LibreOffice_6.4.2_Win_x64_helppack_ru.msi`
    - `/passive` автоматический режим - только указатель хода выполнения,
    - `/forcerestart` с перезагрузкой после установки,
    - `/le+ libreoffice-install-log.txt` вести журнал установки с отображением всех сообщений об ошибках в файл libreoffice-install-log.txt,
- текстовый редактор [Notepad++](https://github.com/notepad-plus-plus/notepad-plus-plus/releases/download/v7.8.5/npp.7.8.5.Installer.x64.exe): `npp.7.8.5.Installer.x64.exe`
    - `/S` полностью автоматическая установка,
- Java Runtime Environment [JRE 8](https://www.oracle.com/webapps/redirect/signon?nexturl=https://download.oracle.com/otn/java/jdk/8u241-b07/1f5b5a70bf22433b84d0e960903adac8/jre-8u241-windows-x64.exe): `jre-8u241-windows-x64.exe`
    - `INSTALLCFG=%cd%\jre-cfg.txt` использование конфигурационного файла,
        - `INSTALL_SILENT=Enable` автономный режим установки (без задания вопросов пользователю),
        - `INSTALLDIR=C:\Java\JRE` каталог для установки java: "C:\Java\JRE",
        - `WEB_ANALYTICS=Disable` отключить отправку веб-аналитики на сервера Oracle,
        - `WEB_JAVA=Enable` разрешить запуск веб-приложений Java в браузере,
    - `/L %cd%\jre-log.txt` создание лог-файла с результатами установки (имя лог-файла в текущей директории: jre-log.txt).
    
Процесс установки:
1. Скачиваем установщик
2. Кладем *.bat-файл (при установке JRE 8 еще конфигурационный файл) в одну папку с установщиком
3. Запускаем *.bat-файл