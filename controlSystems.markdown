---
layout: page
title: Kontrol Sistemleri
permalink: /controlsystems/
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

## 1.4 Kontrol Sistem Yapısı
>tbd