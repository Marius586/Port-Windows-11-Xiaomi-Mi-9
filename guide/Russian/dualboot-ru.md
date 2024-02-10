<img align="right" src="https://raw.githubusercontent.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/main/cepheus.png" width="425" alt="Windows 11 Running On A Xiaomi Mi 9">

# Windows на Xiaomi Mi 9

## Двойная загрузка Android и Windows

### Требования
- [Magisk](https://github.com/topjohnwu/Magisk/releases/latest)
- [UEFI](https://github.com/qaz6750/XiaoMi9-Drivers/releases)
- [Windows on Android Helper APK (test version)](https://t.me/WinOnMi9/328)
- [StA Installer](https://github.com/woa-vayu/Port-Windows-11-POCO-X3-Pro/releases/dualboot)

#### Настройка приложения
> [!Important]
>
> Чтобы смонтировать Windows во время загрузки Android, вам необходимо правильно «выключить» Windows. Для этого перезагрузите Windows, а затем загрузитесь в TWRP, когда экран станет черным. Отсюда вы можете вернуться на Android, используя резервную копию, сделанную ранее.
- Загрузите установщик StA и APK-файл WOA Helper, затем установите APK.
- Дайте ему рут права если он потребует.
- Скопируйте образ UEFI в папку UEFI в внутренней памяти. Создайте папку если её нету.
- Выберите «Backup to Android», а затем закройте всплывающее окно.
- Сделайте то же самое, но выберете «Backup to Windows» 
- Нажмите кнопку «Mount Windows» чтобы смонтировать Windows в папку Windows которая находится в вашей внутренней памяти.

- Скопируйте StA Installer.exe в корень папки Windows
- Вернитесь в вспомогательное приложение WOA и нажмите «Quickboot to windows»
- После загрузки Windows запустите установщик StA в каталоге C:\


#### Загрузка в Android
  
  - Запустите новый ярлык на рабочем столе от имени **АДМИНИСТРАТОР**.

#### Загрузка в Windows 

 - Нажмите "Quickboot to windows", или воспользуйтесь переключателем на панели быстрых настроек.

> Если быстрая загрузка не работает, возможно, вы неправильно завершили работу Windows. Если это произойдет, используйте кнопку «Прошить UEFI» и вручную перезагрузите телефон.

## Готово!
