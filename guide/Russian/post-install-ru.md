<img align="right" src="https://raw.githubusercontent.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/main/cepheus.png" width="425" alt="Windows 11 Running On A Xiaomi Mi 9">

# Запуск Windows 11 на Xiaomi Mi 9

## Дополнительные возможности после установки

### Отключение USB Хост 
> [!Important]
> Если вы используете usb хаб с внешним питанием, то отключите этот режим чтобы избежать повреждение телефона

Чтобы отключить USB Хост скачайте и запустить [restore_default_usb.reg](https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/blob/main/guide/tools/restore_default_usb.reg). Затем перезагрузите.

Чтобы включить USB Хост опять сделайте тоже самое, но с  [force_usb_host.reg](https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/blob/main/guide/tools/force_usb_host.reg).

## Готово!



### Скрытие D: тома (раздел модема)
> [!NOTE]
> Это рекомендуется сделать чтобы раздел не подвёргся модификации после которой некоторые приложения откажутся работать

- Откройте cmd и напишите ```diskpart```
- Затем ```list volume``` чтобы посмотреть доступные разделы
- Выберите диск D с помощью ```select volume $```, заменив "$" с цифрой тома
- Уберите букву ```remove letter d```
- Теперь выйдите из diskpart ```exit```

## Готово!
