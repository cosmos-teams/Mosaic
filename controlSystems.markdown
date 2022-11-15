---
layout: page
title: Kontrol Sistemleri
permalink: /control/
nav_order: 2
---

# **Kontrol Sistem Secenekleri**
---

Seçebileceğimiz hazır kontrol sistemleri olduğu gibi her bir seçenek için önümüzde büyük sınırlandırmalar veya kendimizin yapmasını gerektirecek yapılar ile karşılaşacağız. Bu seçimde göz önünde bulundurmamız gereken temel faktör zaman kısıtlamamız, bu yüzden ilk alternatif ROS'un sınırlandırmalarını ve özelliklerini karşılaştırmamız gerek.

### 1.1 ROS
ROS temel işlevli robotlar ve kontrolleri için gerekli tüm paketleri yüklü gelen bir middleware. Hazır servisler işimizi kolaylaştırabileceği gibi kendi modelimizi tam olarak konfigüre etmek mümkün olmayabilir.

### 1.2 Ardusub
Her ne kadar tam olarak bizim amacımıza yönelik bir sistem olsa da malesef sınırlandırmalar oldukça fazla ve tüm hareket ve otonom için Pixhawk gerektiriyor.

### 1.3 Linux kernel + servisler
En çok zaman alacak seçenek gibi dursa da sunduğu özgürlük nedeniyle tasarladığımız sistemi tam anlamıyla yürür şekile getirmek için en doğru seçenek.
Özet olarak bir linux sisteminin çalışması için en temel gereksinimi kernel'in üstüne yalnızca gerek duyduğumuz paket ve servisleri yükleyerek oluşturacağımız neredeyse kendi işletim sistemimiz olarak tanımlanabilir. Sistem mühendisliği açısından en fazla bilgi ve deneyim edinebileceğimiz seçenek olarak da bir artısı bulunuyor.


# **Kontrol bilgisayari**
---

### 2.1 Raspberry Pi
### 2.2 Nvidia Jetson (Nano & Xaiver)
### 2.3 Pixhawk (Ardusub)

# **Yer istasyonu**
---

### 3.1 ROSRemote
ROS ile yüklü gelen ve herhangi bir linux bilgisayarda (Raspberry Pi) yer istasyonu olarak çalıştırabileceğimiz hazır bir servis.

### 3.2 Web server
Hazır bir sistem kullanmamamız durumunda, yine kontrol bilgisayarında hostlayabileceğimiz basit bir web server ve kendi event sistemimizi ROS'a benzer şekilde oluşturmamız mümkün. Ekstra bir kişi komut satırı kontrolünün yanında kullanıcı paneli üzerine çalışabilir.

### 3.3 QGround
Ardusub kullanmamız durumunda ise QGround kullanabileceğimiz gibi QGround'u kendi amacımıza yönelik modifiye edebiliriz.

### Three.js Point Cloud
PCL ile olusturabilecegimiz point cloud'u baglanti saglandiginda host'a gonderip three.js ile renderlayabiliriz. Tahmini konum ve hesaplanan rotalar gibi verileri de bu veri ile birlikte gosterip kendi arayuzumuzu olusturabiliriz.

# **Kontrol Sistem Yapısı**
---

>tbd