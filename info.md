**ROV23**
---
- [**1. Kontrol Sistemleri**](#1-kontrol-sistemleri)
  - [1.1 Kontrol Sistem Secenekleri](#11-kontrol-sistem-secenekleri)
    - [ROS](#ros)
    - [Ardusub](#ardusub)
    - [Linux kernel + servisler](#linux-kernel--servisler)
  - [1.2 Kontrol bilgisayari](#12-kontrol-bilgisayari)
    - [Raspberry Pi](#raspberry-pi)
    - [Nvidia Jetson (Nano & Xaiver)](#nvidia-jetson-nano--xaiver)
    - [Pixhawk (Ardusub)](#pixhawk-ardusub)
  - [1.3 Yer istasyonu](#13-yer-istasyonu)
    - [ROSRemote](#rosremote)
    - [Web server](#web-server)
    - [QGround](#qground)
- [**2. Hareket Sistemleri**](#2-hareket-sistemleri)
  - [2.1 Motor konumlandirma](#21-motor-konumlandirma)
  - [2.2 Thruster alternatifleri](#22-thruster-alternatifleri)
    - [Hazır seçenekler](#hazır-seçenekler)
    - [Motor alternatifleri](#motor-alternatifleri)
    - [Ekstra](#ekstra)
- [**3. Tasarim**](#3-tasarim)
  - [3.1 Tüp Tasarımı](#31-tüp-tasarımı)
  - [3.2 Tüp Uretimi](#32-tüp-uretimi)
  - [3.3 Tüp Arka Kapak](#33-tüp-arka-kapak)
  - [3.4 Konnektor Alternatifleri](#34-konnektor-alternatifleri)
  - [3.5 Konnektor Uretimi](#35-konnektor-uretimi)
- [**4. Alt-sistemler**](#4-alt-sistemler)
  - [4.1 Goruntu Isleme](#41-goruntu-isleme)
  - [4.2 GPS ve konum tahmin metodlari](#42-gps-ve-konum-tahmin-metodlari)
  - [4.3 Ultrasonik sistemler](#43-ultrasonik-sistemler)
    - [Sensör Seçenekleri](#sensör-seçenekleri)
      - [25/45khz Ultrasonic Transducers](#2545khz-ultrasonic-transducers)
      - [Piezo](#piezo)
      - [Commercial ROV sensors](#commercial-rov-sensors)
---

# **1. Kontrol Sistemleri**

## 1.1 Kontrol Sistem Secenekleri
Seçebileceğimiz hazır kontrol sistemleri olduğu gibi her bir seçenek için önümüzde büyük sınırlandırmalar veya kendimizin yapmasını gerektirecek yapılar ile karşılacağız. Bu seçimde göz önünde bulundurmamız gereken temel faktör zaman kısıtlamamız, bu yüzden ilk alternatif ROS'un sınırlandırmalarını ve özelliklerini karşılaştırmamız gerek.

### ROS
ROS temel işlevli robotlar ve kontrolleri için gerekli tüm paketleri yüklü gelen bir middleware. Hazır servisler işimizi kolaylaştırabileceği gibi kendi modelimizi tam olarak konfigüre etmek mümkün olmayabilir.

### Ardusub
Her ne kadar tam olarak bizim amacımıza yönelik bir sistem olsa da malesef sınırlandırmalar oldukça fazla ve tüm hareket ve otonom için Pixhawk gerektiriyor.

### Linux kernel + servisler
En çok zaman alacak seçenek gibi dursa da sunduğu özgürlük nedeniyle tasarladığımız sistemi tam anlamıyla yürür şekile getirmek için en doğru seçenek.
Özet olarak bir linux sisteminin çalışması için en temel gereksinimi kernel'in üstüne yalnızca gerek duyduğumuz paket ve servisleri yükleyerek oluşturacağımız neredeyse kendi işletim sistemimiz olarak tanımlanabilir. Sistem mühendisliği açısından en fazla bilgi ve deneyim edinebileceğimiz seçenek olarak da bir artısı bulunuyor.


## 1.2 Kontrol bilgisayari

### Raspberry Pi
### Nvidia Jetson (Nano & Xaiver)
### Pixhawk (Ardusub)

## 1.3 Yer istasyonu

### ROSRemote
ROS ile yüklü gelen ve herhangi bir linux bilgisayarda (Raspberry Pi) yer istasyonu olarak çalıştırabileceğimiz hazır bir servis.

### Web server
Hazır bir sistem kullanmamamız durumunda, yine kontrol bilgisayarında hostlayabileceğimiz basit bir web server ve kendi event sistemimizi ROS'a benzer şekilde oluşturmamız mümkün. Ekstra bir kişi komut satırı kontrolünün yanında kullanıcı paneli üzerine çalışabilir.

### QGround
Ardusub kullanmamız durumunda ise QGround kullanabileceğimiz gibi QGround'u kendi amacımıza yönelik modifiye edebiliriz.

# **2. Hareket Sistemleri**

## 2.1 Motor konumlandirma
> motor konumlandırma alternatifleri

## 2.2 Thruster alternatifleri
### Hazır seçenekler
### Motor alternatifleri
- F2838 350KW
    - [Aliexpress](https://www.aliexpress.com/item/1005004303565052.html?spm=a2g0o.productlist.0.0.687761edfKZp29&algo_pvid=b23721b8-060c-4fb4-a19a-a571b01e4a74&algo_exp_id=b23721b8-060c-4fb4-a19a-a571b01e4a74-1&pdp_ext_f=%7B%22sku_id%22%3A%2212000028689508334%22%7D&pdp_npi=2%40dis%21TRY%21497.6%21368.21%21%21%2116.89%21%21%402101fd4b16612530564114403e4b44%2112000028689508334%21sea&curPageLogUid=kmBrn56H0XRc)
    - [Aliexpress](https://www.aliexpress.com/item/1005003908184896.html?spm=a2g0o.productlist.0.0.687761edfKZp29&algo_pvid=b23721b8-060c-4fb4-a19a-a571b01e4a74&algo_exp_id=b23721b8-060c-4fb4-a19a-a571b01e4a74-9&pdp_ext_f=%7B%22sku_id%22%3A%2212000027440102040%22%7D&pdp_npi=2%40dis%21TRY%21487.23%21331.35%21%21%2171.61%21%21%402101fd4b16612530564114403e4b44%2112000027440102040%21sea&curPageLogUid=CqwdbwjyX44P&gatewayAdapt=glo2tur)
    - [F1Depo](https://www.f1depo.com/urun/ipx8-su-gecirmez-fircasiz-motor-f2838-cw-350kv)
    - [Amazon](https://www.amazon.com/VGEBY1-Brushless-F2838-350KV-Underwater-Waterproof/dp/B07W8TXD7L)
- F2838 560KW
    - [Aliexpress](https://www.aliexpress.com/item/4001065199650.html?spm=a2g0o.productlist.0.0.687761edfKZp29&algo_pvid=b23721b8-060c-4fb4-a19a-a571b01e4a74&algo_exp_id=b23721b8-060c-4fb4-a19a-a571b01e4a74-5&pdp_ext_f=%7B%22sku_id%22%3A%2210000014000174833%22%7D&pdp_npi=2%40dis%21TRY%21532.15%21377.81%21%21%216.72%21%21%402101fd4b16612530564114403e4b44%2110000014000174833%21sea&curPageLogUid=KsplPoywlvjo)
- BRF4125
    - [Banggood](https://www.banggood.com/DXW-BRF4125-300KV-350KV-3-6S-Waterproof-Brushless-Motor-for-RC-Drone-FPV-Racing-Multirotor-p-1380283.html?imageAb=2&cur_warehouse=CN&ID=517076&rmmds=search&a=1661253501.4779&DCC=TR&currency=EUR&akmClientCountry=TR)

### Ekstra
> Dışarıdan yalnızca motorları alarak thruster tasarımını kendimiz yapmamız durumunda basit CFD simülasyonları ile tasarım raporu için içerik sağlayanabilir.

# **3. Tasarim**

## 3.1 Tüp Tasarımı
>tbd

## 3.2 Tüp Uretimi
>tbd

## 3.3 Tüp Arka Kapak
>tbd

## 3.4 Konnektor Alternatifleri
>tbd

## 3.5 Konnektor Uretimi
>tbd

# **4. Alt-sistemler**

## 4.1 Goruntu Isleme
>tbd

## 4.2 GPS ve konum tahmin metodlari
>tbd

## 4.3 Ultrasonik sistemler
### Sensör Seçenekleri
#### 25/45khz Ultrasonic Transducers
- [25KHZ And 45KHZ Double Frequency Sensor Cleaner Pzt Ultrasonic Transducers](https://www.alibaba.com/product-detail/25KHZ-And-45KHZ-Double-Frequency-Sensor_60788959520.html)
- [25/45khz two frequency ultrasonic sonic transducer/sensor](https://www.alibaba.com/product-detail/25-45khz-two-frequency-ultrasonic-sonic_60308262261.html)
#### Piezo
- [Ultrasonic Air Transducer 45 KHz](https://www.steminc.com/PZT/fr/ultrasonic-air-transducer-45-khz)
#### Commercial ROV sensors
- [VADR-6000M Subsea Vehicle Acoustic Receiver](https://www.rjeint.com/portfolio/vadr-6000m-subsea-vehicle-acoustic-receivers/)