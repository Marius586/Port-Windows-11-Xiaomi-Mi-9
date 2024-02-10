<img align="right" src="https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/blob/main/cepheus.png" width="425">


# Windows на Xiaomi Mi 9

## Двойная загрузка Android и Windows

### Требования
- [Magisk](https://github.com/topjohnwu/Magisk/releases/latest)
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
- [Модифицированное TWRP](https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/releases)
- [NTFS Android Magisk Модуль](https://github.com/woa-vayu/Port-Windows-11-POCO-X3-Pro/releases/ntfsdroid)
- [UEFI](https://github.com/qaz6750/XiaoMi9-Drivers/releases)
- [Windows on Android Helper APK (test version)](https://t.me/WinOnMi9/328)
- [StA Installer](https://github.com/woa-vayu/Port-Windows-11-POCO-X3-Pro/releases/dualboot)

### Настройка телефона

#### Добавление поддержки NTFS в Android
- Установите Magisk, если вы еще этого не сделали
- Установите модуль magisk NTFS Android через менеджер Magisk.

#### Настройка приложения
> [!Примичание]
>
> Чтобы смонтировать Windows во время загрузки Android, вам необходимо правильно «выключить» Windows. Для этого перезагрузите Windows, а затем загрузитесь в TWRP, когда экран станет черным. Отсюда вы можете вернуться на Android, используя резервную копию, сделанную ранее.
- Загрузите установщик StA и APK-файл Windows on Android Helper, затем установите APK
- Создайте папку с именем «UEFI» во внутренней памяти
- Скопируйте образ UEFI в папку UEFI
- Откройте приложение и разрешите любой root-доступ, который он хочет
- Нажмите кнопку «BACKUP ANDROID BOOT», затем закройте всплывающее окно
- Нажмите кнопку «Подключить/Отключить Windows», затем закройте всплывающее окно
- Перейдите в проводник, и Windows должна быть смонтирована на SD-карте/Windows (ваше внутреннее хранилище). Переместите установщик StA и резервную копию boot.img в эту папку
- Вернитесь в вспомогательное приложение WOA и нажмите «Быстрая загрузка в Windows»
- После загрузки Windows запустите установщик StA в каталоге C:\

#### Загрузка в Android
  
  - Запустите новый ярлык на рабочем столе от имени **АДМИНИСТРАТОР**.

#### Загрузка в Windows 

 - Запустите программу
 - Нажмите "Quickboot to windows"

> Если быстрая загрузка не работает, возможно, вы неправильно завершили работу Windows. Если это произойдет, используйте кнопку «Прошить UEFI» и вручную перезагрузите телефон.

## Готово!