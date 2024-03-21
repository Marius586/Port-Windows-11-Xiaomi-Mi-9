<img align="right" src="https://raw.githubusercontent.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/main/cepheus.png" width="425" alt="Windows 11 Çalıştıran bir Mi 9">

# Xiaomi Mi 9'da Windows Çalıştırma

## Kurulum

## Windows Kurulumu

### Gerekenler
- [Windows on ARM sistem dosyası](https://worproject.com/esd)
- [UEFI imajı](https://github.com/qaz6750/XiaoMi9-Drivers/releases)
- [Sürücüler](https://github.com/qaz6750/XiaoMi9-Drivers/releases)
- [Modifiyeli TWRP](https://github.com/woacepheus/Port-Windows-11-Xiaomi-Mi-9/releases/download/1.4/recovery-cepheus.img) (Zaten kurulu olması lazım)

### Modifiyeli TWRP'ye geçin
> Eğer önceki sayfadaki son adım kurtarma bölümünü sıfırladıysa aşağıdaki komutla yeniden yükleyin:
```cmd
fastboot flash dosyaya\giden\yol\recovery-cepheus.img reboot recovery
```

#### Depolama Komutunu çalıştırın
> Eğer yeniden çalıştırın derse çalıştırın
```cmd
adb shell msc
```

### Bölmelere harf atama
  
#### Windows Disk Yöneticisi ile başlayın
> Xiaomi Mi 9 telefonuz bilgisayarda gözüktüğü anda
```cmd
diskpart
```

### Windows Bölümüne `X` Harfini Atayın

#### Telefondaki Windows bölümünü seçin
> Bölüm sayısını bulmak için Diskpart'a `list volume` yazın, adı "WINCEPHEUS" olarak çıkacaktır

```diskpart
select volume <bölüm sayısı>
```

#### X Harfini Atayın
```diskpart
assign letter x
```

### ESP Bölümüne `Y` Harfini Atayın

#### Telefondaki ESP Bölümünü seçin
> Bölüm sayısını bulmak için Diskpart'a `list volume` yazın, adı "ESPCEPHEUS" olarak çıkacaktır

```diskpart
select volume <bölüm sayısı>
```

#### Y Harfini Atayın
```diskpart
assign letter y
```

#### Diskpart'tan çıkın
```diskpart
exit
```

### Windows'un kurulumu
> `dosyaya\giden\yol\install.esd`'u install.esd dosyasına giden yol ile değiştirin.

> ISO dosyası indirdiyseniz .esd dosyası ISO içinde sources klasöründe olmalı. ISO'ya Explorer'da (Dosya Gezgini) çift tıklayarak bağlayın ve .esd dosyasını oradan kopyalayın.

> Dosyanızı verdiğimiz linkten almadıysanız `index:6`'yı `index:1` olarak değiştirin.

```cmd
dism /apply-image /ImageFile:dosyaya\giden\yol\install.esd /index:6 /ApplyDir:X:\
```

### Sürücülerin Kurulumu
> Sürücülerin olduğu sıkıştırılmış dosyayı ayıklayın 'OfflineUpdater.cmd' dosyasını çalıştırın. WINCEPHEUS Bölmesinin harfini (X olmalı) girin ve Enter'a basın.

### Windows EFI Önyükleyici dosyalarını oluşturun
```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

### Harf atamasını kaldırın
> Diskpart ile ESPCEPHEUS'un harfini kaldırın, yoksa bilgisayarı yeniden başlatana kadar dosya gezgininde boş sürücü olarak gözükecektir.

> ESPCEPHEUS'un numarasını bulmak için `list volume` kullanın, `select volume <numara>` ile seçin, son olarak `remove letter y` ile kaldırın

## Önyükleme İmajlarının yedeklerini alma

##### Kurtarma moduna yeniden girin
> MSC komutunu durdurmak için
- Telefonu yeniden başlatıp Kurtarma moduna girin veya bilgisayardan şu komutu yazın:
```cmd
adb reboot recovery
```

##### Android Önyükleyici imajının yedeğini alma
> TWRP Yedekleme aleti ile (ana menüde Backup olarak çıkar) Boot/Önyükleyici Bölümünün yedeğini alın ve adını "Android" yapın

##### UEFI imajını telefona atın
> MuCepheusSecureBoot.img dosyasını telefonun dahili depolamasına sürükleyin

##### UEFI imajını yükleme
> TWRP Kurulum aleti'ne (Install) girin, aşağıdan `Install Image`ı seçin ve UEFI imajını bulun
##### Windows Önyükleyici imajının yedeğini alma
> TWRP Yedekleme aleti ile (ana menüde Backup olarak çıkar) Boot/Önyükleyici Bölümünün yedeğini alın ve adını "Windows" yapın

## Windows'a girin
> UEFI imajını yükledikten sonra telefonu yeniden başladı

* Artık cihazınız Windows'u kurmaya başlayacaktır. Uzun sürmesi normaldir, lütfen sabırla bekleyin. Sonra yeniden başlayıp kurulum sonrası menüsüne (OOBE) gelecektir


## Hazırsınız!

### [Son Adım: Çift Sistem Kurulumu](dualboot-tr.md)
