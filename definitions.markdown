---
layout: page
title: Tanımlamalar
permalink: /definition/
nav_order: 5
---

## 3.3 **Elektronik Tasarım, Algoritma ve Yazılım Tasarımı**

```
{Bu kısımda:
- Aracın elektronik ile ilgili önemli görülen kısımları,
- Aracın kontrol/navigasyon/güdüm algoritma ile ilgili önemli görülen kısımları, 
- Aracın arayüzleri, bu arayüzlerde kullanılması planlanan alt bileşenler, mesaj arayüzleri, 
aracın kontrolünde kullanılması - planlanan su üstü kontrol istasyonunun arayüzü, 
görüntü ve veri aktarımı ile ilgili önemli görülen kısımlar anlatılır}
```

### 3.3.1 Elektronik Tasarim

Araçtaki sensörlerden aldığımız verileri ortak kullanarak hesapladığımız konum vektörümüz ile birlikte kendi yazdığımız ve Raspberry Pi üzerinde çalışan güdüm kontrol algoritmalarımızın çıkışları sonucunu Raspberry Pi'ın pinlerinden pwm çıkışı olarak alıp esc'lere göndererek iticilerimizin kontrolünü sağlıyoruz.

Tüm görüntü işleme işlemlerimiz için CUDA çekirdeği barındırdığından Jetson Nano kullanmayı tercih ettik. Kullandığımız 2 eş kamera ile derinlik verisi hesaplarken ilk görevde hedefe kararlı bir şekilde iniş sağlamak için üçüncü yere dik bakan bir usb kamera yedek bulunduruyoruz.

Aracımız içindeki tüm gücü tüp içerisindeki 5S Li-po bataryadan alarak elektronik kartlarımıza regülatör ile güç sağladığımız gibi esc'lere batarya çıkışımızdan güç dağıtım kartı ile güç sağlıyoruz.


Kontrol bilgisayarımız olan raspberry pi ile yer istasyonumuzdaki wifi modem ile ssh üzerinden haberleşme sağlıyoruz. _Bu yöntem ile su altında haberleşme kapabiliyetimiz olmadığından test süreci için kablolu bir sistem kullanabiliriz._


### 3.3.2 Algoritma Tasarimi

Güdüm/navigasyon/kontrol algoritmalarımızı motor sürücümüzün direk bağlı olduğu kontrol bilgisayarımız Raspberry Pi ile sağlıyoruz. İvme sensörlerimiz ve basınç sensörlerimizi ortak kullanarak elde ettiğimiz veriyi kalman filtrelerimiz ile işledikten sonra nokta bulutumuzda işaretleyerek hedefe olan nihayi rotamızı hedefi algıladıktan sonra sabit hızlanma & yavaşlama hızlarımızı s-eğrisi hareket modeline göre hesaplayarak stabil bir güdüm rotası elde ediyoruz.

Görüntü işleme için çift kamera kullanarak Nvidia stero depth kullanarak bulunuduğumuz konumumuzda algıladığımız yakın mesafeleri aynı şekilde nokta bulutumuza projekte ederek bulunduğumuz ortamın üç boyutlu bir modelini çıkarıyoruz. Saptayabildiğimiz tüm hedefleri kontrol algoritmamız için girdi olarak kullanıp bize verilen görevi tamamlamayı amaçlıyoruz.

Rotamızı kontrol teorisine uygun şekilde en optimal olarak hesapladıktan sonra motorlarımıza PWM değeri olarak yazabilmek için her motor için tersine kinematik formülümüz ile hesapladığımız itki kuvvetimizi motor sürücülerimize iletiyoruz. Bu adımdan emin olmak için PID algoritmaları kullandığımız gibi, önceden her motor için hesaplamış olduğumuz vektör bileşen katsayılarımızı kullanarak tersine kinematik ile motorlarımıza iletmemiz gereken itki kuvvetimizi elde ediyoruz.


### 3.3.3 Yazilim Tasarim

Tüm yarışma sürecinin gerektirdiği stabil ve yedekli sistem tasarımı adına ana kontrol bilgisarımız Raspberry Pi üzerinde Buildroot kullanarak çapraz-derlediğimiz (cross-compile) Linux ortamında, kendi yazdığımız C++ kodlarımız ile tüm güdüm ve kontrolümüzü sağlıyoruz. 

Aynı şekilde görüntü işleme için gerek duyduğumuz sürücüleri Jetson Nano ile kullanabilmek adına görüntü işleme algoritmalarımızı Jetson Linux kullanarak çalıştırıyoruz. İki bilgisayarımız arasında stabil bir haberleşme için LAN üzerinden web soketleri kullanarak iletişimi sağlıyoruz.

Kontrol algoritmalarımız için C++ kullanma amacımız aynı anda birden çok filtre, girdi ve çıktı operasyonlarını birbirlerini engellemeden eş zamanlı çalışmaları adına birden çok çekirdek üzerinde çalıştırarak sistemimizi en stabil şekilde çalıştırmayı amaçlıyoruz ve C++'ı bu amaca yönelik birden çok çekirdekli yazılım performansı için seçtiğimiz en uygun dil olarak değerlendirdik.

--

Kaynakca için wikipedia sayfarındaki açıklamalardaki yayınlar kullanılabilir;

- [Kontrol teorisi](https://en.wikipedia.org/wiki/Control_theory)
- [Kalman filtresi](https://en.wikipedia.org/wiki/Kalman_filter)
- C++ multi-thread performasi icin kaynak bulunabilir
- PID algoritmasi aciklamasi icin akademik kaynak olduguna eminim, onemli bir referans olabilir
- S-Curve (s-eğrisi) için kaynak bulamadım, aynı şekilde iyi bir referans olabilir