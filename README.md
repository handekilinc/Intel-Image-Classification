# 🖼️ Intel Image Classification

![0_S4LF1ObkVh2ke-I-](https://github.com/user-attachments/assets/c76dbd9a-828d-4f97-b8a5-4964093b2bbe)

## 📌 Proje Kaggle Linki

[Intel Image Classification Dataset](https://www.kaggle.com/code/handekln/intel-image-classification)


📂 Dataset Information

Bu proje, Intel tarafından sağlanan sahne sınıflandırma veri seti kullanılarak gerçekleştirilmiştir. Veri seti, farklı sahne türlerini temsil eden görsellerden oluşur ve 6 ana sınıfa ayrılmıştır:

![1_hacj-pIrC_lOesy4hObdWQ](https://github.com/user-attachments/assets/98ff73e8-865c-4621-8548-57b592317286)

Buildings: Bina ve şehir yapıları

Forest: Orman ve ağaç manzaraları

Glacier: Buzullar ve karlı dağlık bölgeler

Mountain: Dağlar ve yüksek araziler

Sea: Deniz ve sahil görüntüleri

Street: Sokak ve kentsel manzaralar

<img width="600" height="420" alt="intel-image-classification-dataset-images" src="https://github.com/user-attachments/assets/7fcd1a66-b0bb-46c7-97a0-bc8eaa285d8f" />




Intel Görüntü Sınıflandırma Veri Seti Hakkında:

Her biri 150 piksel * 150 piksel boyutunda yaklaşık 25.000 görüntü
Altı kategori vardır: Binalar(0), Orman(1), Buzul(2), Dağ(3), Deniz(4) ve Sokak(5).

![1_7Bjr3Pu4N-n-LwmmFju83Q](https://github.com/user-attachments/assets/256475ae-e8bd-4fc9-afe2-4be108f0fa61)

Tüm eğitim verileri klasörlere ayrılmıştır.
Dizin 3 klasörden oluşur: Seq_train(14k örnek), Seq_test(7k örnek) ve Seq_pred(3k örnek).

Eğitim seti: 14.899 görsel

Test seti: 3.732 görsel

Toplam sınıf sayısı: 6

Bu veri seti, sahne sınıflandırma problemleri için zengin ve çeşitlilik sağlayan bir kaynak sunmaktadır.

🎯 Proje Hedefleri

Projenin temel amaçları şunlardır:

Sahne görsellerini doğru bir şekilde sınıflandırmak.

Önceden eğitilmiş bir EfficientNetB0 modeli kullanarak yüksek doğruluk (%85+) elde etmek.

Veri artırma (augmentation) ve mixed precision teknikleri ile model eğitimini hızlandırmak ve genelleme performansını artırmak.

Modelin farklı sınıflarda yüksek doğruluk sağlayabilmesini sağlamak ve overfitting’i önlemek.

<img width="1024" height="576" alt="best-image-classification-models-1" src="https://github.com/user-attachments/assets/d0ee70ea-e350-4086-a693-31645187abc7" />


📝 Proje Özeti

Intel Image Classification projesi, sahne görselleri üzerinde derin öğrenme temelli bir sınıflandırma sistemi geliştirmeyi amaçlamaktadır. Proje adımları aşağıdaki gibidir:

1️⃣ Veri Hazırlama ve Artırma

Görseller, modelin input boyutuna uygun olarak yeniden boyutlandırılmıştır (224x224 piksel).

Veri artırma teknikleri kullanılmıştır: döndürme, yatay kaydırma, yakınlaştırma ve yatay çevirme gibi yöntemlerle eğitim verisinin çeşitliliği artırılmıştır.

Bu sayede model, sınıf varyasyonlarını daha iyi öğrenmiş ve overfitting riski azaltılmıştır.

2️⃣ Model Mimarisi

![1__8ACmO8lDanToRVTc1yemg](https://github.com/user-attachments/assets/34caffa3-f811-48d5-8367-4ec2a3b3c1df)

Base Model: EfficientNetB0, ImageNet üzerinde önceden eğitilmiş olarak kullanılmıştır.

Dense Katmanlar: 256 ve 256 nöronlu iki katman eklenmiştir.

Dropout: %40 ve %30 oranlarında iki dropout katmanı ile overfitting önlenmiştir.

Output Katmanı: 6 sınıf için softmax aktivasyonu kullanılmıştır.

3️⃣ Eğitim Stratejisi

1. Aşama: Son katmanlar eğitilmiş, base model dondurulmuştur. Bu sayede model, önceden öğrenilmiş özellikleri koruyarak sınıf özel bilgileri öğrenmiştir.

2. Aşama: Fine-tuning yapılmış, tüm EfficientNet katmanları açılmıştır. Bu sayede modelin genel performansı artırılmıştır.

Optimizer: Adam kullanılmış, learning rate stage1 için 0.001 ve stage2 için 0.00001 olarak ayarlanmıştır.

Mixed Precision: FP16 kullanılarak TPU/GPU hızlandırması sağlanmıştır.

4️⃣ Eğitim Sürecini İzleme

Model eğitimi sırasında performans takibi için şu callback’ler kullanılmıştır:

EarlyStopping → Val accuracy gelişmediğinde erken durdurma.

ReduceLROnPlateau → Öğrenme oranını dinamik düşürme.

ModelCheckpoint → En iyi val accuracy’ye sahip modeli kaydetme.

Ayrıca, eğitim sonrası accuracy/loss grafiklerinin çizdirilmesi ile modelin öğrenme eğrileri incelenmiştir.

5️⃣ Performans ve Değerlendirme

Model, validation set üzerinde %85’in üzerinde doğruluk elde etmiştir.

Eğitim ve doğrulama sürecinde accuracy ve loss grafikleri ile performans takip edilmiştir.

Veri artırma sayesinde model, özellikle sınıflar arası benzerliklerde daha doğru tahminler yapabilmiştir.

<img width="794" height="812" alt="__results___19_0" src="https://github.com/user-attachments/assets/fcc921dd-f435-4f7f-a5db-b1eaeb13f94e" />

## 🚀 Nasıl Çalıştırılır?

1. Projeyi **Kaggle** veya **Google Colab** üzerinde açabilirsiniz.
2. Dataset'i yükleyin: [Intel Image Classification Dataset](https://www.kaggle.com/datasets/puneet6060/intel-image-classification)
3. Gerekli kütüphanelerin yüklü olduğundan emin olun:
   ```python
   import tensorflow as tf
   import numpy as np
   import matplotlib.pyplot as plt
   from tensorflow.keras.preprocessing.image import ImageDataGenerator

Dataset yolunu ayarlayın ve train_generator ile val_generator oluşturun. Modeli eğitin.

Eğitim tamamlandıktan sonra en iyi model final_efficientnet.h5 dosyası olarak kaydedilecektir.

 📊 Test Seti Performansı ve Sınıf Bazlı Değerlendirme

Model, test setinde %85 doğruluk ile tahmin yapabilmektedir. Bu, Intel Image Classification veri seti gibi karmaşık ve çeşitlilik gösteren sahne görselleri üzerinde oldukça güçlü bir performans olarak değerlendirilebilir.

Sınıf	Precision	Recall	F1-Score	Destek
Buildings	0.84	0.88	0.86	437
Forest	0.96	0.98	0.97	474
Glacier	0.82	0.81	0.82	553
Mountain	0.87	0.67	0.76	525
Sea	0.75	0.91	0.82	510
Street	0.89	0.87	0.88	501

Accuracy: 0.85 → Test setinde model genel olarak %85 doğru tahmin yapıyor.

Macro & Weighted Avg: Precision, recall ve F1-score da yaklaşık 0.85. Bu, modelin sınıflar arasında dengeli performans gösterdiğini ortaya koyuyor.

Gözlem: Mountain sınıfında recall biraz düşük (%67), bu nedenle model bazı mountain görsellerini diğer sınıflarla karıştırabiliyor. Glacier ve Sea sınıflarında ise yüksek doğruluk elde edilmiştir.

👉 Veri artırma (augmentation) sayesinde model, özellikle forest ve mountain gibi sınıflarda daha başarılı sonuçlar elde etmiştir.

📌 Örnek Çıktılar
Eğitim sırasında accuracy ve loss grafikleri incelenmiştir.

Ayrıca confusion matrix kullanılarak modelin en çok karıştırdığı sınıflar gözlemlenmiştir.

<img width="788" height="701" alt="confusion matrix" src="https://github.com/user-attachments/assets/5b2b8993-fd21-4e0d-b942-589911556585" />


📊 Veri Analizi ve Gözlemler

Eğitim sırasında veri artırmanın etkisi gözlemlenmiş ve bazı sınıflarda daha yüksek doğruluk sağlanmıştır (özellikle “forest” ve “mountain” gibi doğal manzaralarda).

Overfitting’i önlemek için dropout katmanları ve batch normalization gibi yöntemler kullanılmıştır.

Model, her bir sahne sınıfını yüksek doğrulukla ayırt edebilmiştir.

🔮 Gelecek Çalışmalar

Daha derin EfficientNet varyantları kullanılarak model doğruluğunun artırılması.

Grad-CAM ve diğer explainability teknikleri ile modelin karar mekanizmasının görselleştirilmesi.

Gerçek zamanlı sahne sınıflandırma uygulamaları (örneğin bir mobil veya web uygulaması).

Farklı data augmentation yöntemleri ve adversarial örneklerle modelin dayanıklılığının artırılması.

✅ Sonuç

Intel Image Classification projesi, sahne sınıflandırma problemini çözmek için güçlü bir hibrit yaklaşım geliştirmiştir.

Mixed precision ve veri artırma ile modelin eğitim süresi optimize edilmiştir.

Fine-tuning ile modelin genelleme performansı artırılmış ve %88,5 doğruluk sağlanmıştır.

Bu proje, transfer learning ve modern CNN mimarilerinin sahne sınıflandırma görevlerinde ne kadar etkili olduğunu göstermektedir.

![License](https://img.shields.io/badge/license-MIT-blue.svg)

📌 Referanslar

**Dataset:** [Intel Image Classification](https://www.kaggle.com/datasets/puneet6060/intel-image-classification)

**Reference Paper:** _Tan, M., Le, Q.V. EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks. ICML 2019_

