# 🖼️ Intel Image Classification

![0_S4LF1ObkVh2ke-I-](https://github.com/user-attachments/assets/c76dbd9a-828d-4f97-b8a5-4964093b2bbe)

Proje Kaggle Linki: Intel Image Classification Dataset

📂 Dataset Information

Bu proje, Intel tarafından sağlanan sahne sınıflandırma veri seti kullanılarak gerçekleştirilmiştir. Veri seti, farklı sahne türlerini temsil eden görsellerden oluşur ve 6 ana sınıfa ayrılmıştır:

![1_hacj-pIrC_lOesy4hObdWQ](https://github.com/user-attachments/assets/98ff73e8-865c-4621-8548-57b592317286)

Buildings: Bina ve şehir yapıları

Forest: Orman ve ağaç manzaraları

Glacier: Buzullar ve karlı dağlık bölgeler

Mountain: Dağlar ve yüksek araziler

Sea: Deniz ve sahil görüntüleri

Street: Sokak ve kentsel manzaralar

Intel Görüntü Sınıflandırma Veri Seti Hakkında:

Her biri 150 piksel * 150 piksel boyutunda yaklaşık 25.000 görüntü
Altı kategori vardır: Binalar(0), Orman(1), Buzul(2), Dağ(3), Deniz(4) ve Sokak(5).

Tüm eğitim verileri klasörlere ayrılmıştır.
Dizin 3 klasörden oluşur: Seq_train(14k örnek), Seq_test(7k örnek) ve Seq_pred(3k örnek).

Eğitim seti: 14.899 görsel

Test seti: 3.732 görsel

Toplam sınıf sayısı: 6

Bu veri seti, sahne sınıflandırma problemleri için zengin ve çeşitlilik sağlayan bir kaynak sunmaktadır.

🎯 Proje Hedefleri

Projenin temel amaçları şunlardır:

Sahne görsellerini doğru bir şekilde sınıflandırmak.

Önceden eğitilmiş bir EfficientNetB0 modeli kullanarak yüksek doğruluk (%95+) elde etmek.

Veri artırma (augmentation) ve mixed precision teknikleri ile model eğitimini hızlandırmak ve genelleme performansını artırmak.

Modelin farklı sınıflarda yüksek doğruluk sağlayabilmesini sağlamak ve overfitting’i önlemek.

📝 Proje Özeti

Intel Image Classification projesi, sahne görselleri üzerinde derin öğrenme temelli bir sınıflandırma sistemi geliştirmeyi amaçlamaktadır. Proje adımları aşağıdaki gibidir:

1️⃣ Veri Hazırlama ve Artırma

Görseller, modelin input boyutuna uygun olarak yeniden boyutlandırılmıştır (224x224 piksel).

Veri artırma teknikleri kullanılmıştır: döndürme, yatay kaydırma, yakınlaştırma ve yatay çevirme gibi yöntemlerle eğitim verisinin çeşitliliği artırılmıştır.

Bu sayede model, sınıf varyasyonlarını daha iyi öğrenmiş ve overfitting riski azaltılmıştır.

2️⃣ Model Mimarisi

Base Model: EfficientNetB0, ImageNet üzerinde önceden eğitilmiş olarak kullanılmıştır.

Dense Katmanlar: 256 ve 256 nöronlu iki katman eklenmiştir.

Dropout: %40 ve %30 oranlarında iki dropout katmanı ile overfitting önlenmiştir.

Output Katmanı: 6 sınıf için softmax aktivasyonu kullanılmıştır.

3️⃣ Eğitim Stratejisi

1. Aşama: Son katmanlar eğitilmiş, base model dondurulmuştur. Bu sayede model, önceden öğrenilmiş özellikleri koruyarak sınıf özel bilgileri öğrenmiştir.

2. Aşama: Fine-tuning yapılmış, tüm EfficientNet katmanları açılmıştır. Bu sayede modelin genel performansı artırılmıştır.

Optimizer: Adam kullanılmış, learning rate stage1 için 0.001 ve stage2 için 0.00001 olarak ayarlanmıştır.

Mixed Precision: FP16 kullanılarak TPU/GPU hızlandırması sağlanmıştır.

4️⃣ Performans ve Değerlendirme

Model, validation set üzerinde %95’in üzerinde doğruluk elde etmiştir.

Eğitim ve doğrulama sürecinde accuracy ve loss grafikleri ile performans takip edilmiştir.

Veri artırma sayesinde model, özellikle sınıflar arası benzerliklerde daha doğru tahminler yapabilmiştir.

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

Fine-tuning ile modelin genelleme performansı artırılmış ve %95+ doğruluk sağlanmıştır.

Bu proje, transfer learning ve modern CNN mimarilerinin sahne sınıflandırma görevlerinde ne kadar etkili olduğunu göstermektedir.

📌 Referanslar

**Dataset:** [Intel Image Classification](https://www.kaggle.com/datasets/puneet6060/intel-image-classification)

**Reference Paper:** _Tan, M., Le, Q.V. EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks. ICML 2019_

