---
layout: default
title: Goruntu Isleme
parent: Alt-Sistemler
nav_order: 1
---

## 4.1 Goruntu Isleme

### 4.1.1 Kamera & Yontem Secimi
- Kullanmayi planladigimiz kameraya bagli olarak suan ideal 3 farkli goruntu isleme metod alternatifimiz bulunyor;

#### OpenCV ORB Keypoint Detection
- Tek bir kaynaktan elde ettigimiz kareden cesitli metodlar ile (ORB, SIFT) goruntudeki ayristirilabilecek ozellikleri arayip bunlari sonradan kareler arasinda karsilastirarak tamamen OpenCV bazli bir feature detection metodu kullanabiliriz. Bu metod hem tek goruntu kaynagi hem de pixel bazli isleme yaptigindan limitasyonlari en fazla olan ve bize en dusuk hassasiyeti sunan yontem.

#### Stereo pair
- Ozellikle bizim kullanim alanimizda Jetson gibi CUDA cekirdegi iceren bir donanim ve Nvidia'nin hazir modelleri ile bize iki farkli sensor kullanarak derinlik haritasi saglayabilecek bir yontem. Derinlik haritasi pixel bazli goruntu islemeden ustun olsa da calistirmak icin jetson gibi cuda cekirdegi olan bir donanimda calistirma zorunlulugu karar asamasinda dusunmemiz gereken limitasyonlari arasinda.

#### Intel RealSense
- Tum yontemlerin arasinda kullandigi sensor nedeniyle en guclu olan alternatifimiz. Daha once sualti kullanimi hakkinda uzun bir github issue thread'i bulunuyor ve sualtinda oldukca yuksek verimde calisabiliyor. Kendi SDK'i ile birlikte Raspberry Pi ile kullanabilecegimiz gibi Jetson gibi bir kart ile kullanmanin avantajlarini da degerlendirebiliriz. Alternatifler arasinda bu amaca yonelik oldugu icin point cloud cikarmada en hassas veri sunabilecek secenegimiz.

### 4.1.2 Sistemlerin ornek kullanimlari

#### Jetson + stereo pair
- [Nvidia'nin kendi modeli ile stereo pair kullanimi](https://github.com/NVIDIA-AI-IOT/jetson-stereo-depth)

#### Intel RealSense
- [RealSense'in kendi forumunda sualti kullanim](https://support.intelrealsense.com/hc/en-us/community/posts/5418070547731-Underwater-usage-)
  
- [D435 sualti kullanimi Github thread'i](https://github.com/IntelRealSense/realsense-ros/issues/1723)

- FishSense (Ornek kullanim)
- - [Website](https://e4e.ucsd.edu/fishsense)
- - [YouTube](https://www.youtube.com/watch?v=KA_x03_Aru8)