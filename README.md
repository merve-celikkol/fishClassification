# Fish Classification(Balık Türü Sınıflandırma Projesi)

TensorFlow/Keras ile oluşturulan bir derin öğrenme modelini kullanarak farklı balık türlerini görüntü verilerine göre sınıflandırmayı amaçlamaktadır. Projede kullanılan veri kümesi, büyük ölçekli bir balık veri kümesidir ve model, etiketlenmiş balık görüntüleri üzerinde eğitilmiştir.

## Veri Kümesi
Farklı balık türlerine ait görüntülerden oluşmaktadır. Görüntüler etiketlenmiş olup, her sınıf bir balık türünü temsil eder.
Veri setinde 9 farklı balık türüne ait fotoğraflar bulunmaktadır. Bu 9 balık türü şöyledir:
•	Yaldızlı Çipura

•	Kızıl Çipura

•	Levrek

•	Barbunya

•	İstarvit

•	Karadeniz Çaça

•	Çizgili Barbunya

•	Alabalık

•	Karides 

Dizin: /kaggle/input/a-large-scale-fish dataset/Fish_Dataset/Fish_Dataset
Görüntüler .png formatında bulunmaktadır.
Veri kümesi, çeşitli balık türlerini içeren birden fazla sınıfa sahiptir.

## Eğitim Parametreleri

•	Epoch: Model tüm veri kümesini birden çok kez (50 epoch'a kadar) taradı, ancak erken durdurma (early stopping) kullanılarak eğitim erken sonlandırılabiliyor.

•	Batch Size: Her adımda 64 görüntü kullanılarak model eğitildi.

•	Doğruluk: Eğitim sırasında modelin başarı oranı doğruluk (accuracy) metriği ile ölçüldü.

## Model Mimarisi

Aşırı öğrenmeyi önlemek amacıyla dropout ve L2 regularizasyonu gibi yöntemler uygulanmıştır.
Modelin ana bileşenleri şunlardır:
•	Girdi Katmanı: Girdi görüntüleri (28, 28, 3) boyutunda yeniden boyutlandırılır ve düzleştirilir.

•	Gizli Katmanlar:

o	  ReLU aktivasyon fonksiyonuna sahip yoğun katmanlar.

o  	Daha hızlı yakınsama için batch normalization.

o	  Aşırı öğrenmeyi önlemek için dropout katmanları.

•  	Çıkış Katmanı: Çok sınıflı sınıflandırma için softmax aktivasyonuna sahip bir yoğun katman.

Her görüntü 28x28 piksel olacak şekilde boyutlandırılır. Renkli oldukları için rgb olarak ayarlanır. Batch size her işlemde modele kaç görüntü gönderileceğini, her bir adımda işlenecek görüntü sayısını belirtir. Bu projede 64 olarak seçilmiştir.
Kullanılan ana kütüphaneler:

•	TensorFlow

•	Keras

•	Pandas

•	Matplotlib

•	Seaborn

•	Scikit-learn

Hesaplanan metrikler şunlardır:

•	Doğruluk

•	Hassasiyet

•	Geri çağırma

•	F1 Skoru

Modeli eğitmek için fit fonksiyonu kullanılmıştır. early_stopping, lr_scheduler_callback ile eğitim sürecinde kullanılacak callback fonksiyonlarıdır.
Epoch sayısı 50 olarak belirlenmiştir.

Model, doğruluk, kayıp (loss) ve diğer metrikler açısından eğitim ve doğrulama performansını görselleştiren grafikler oluşturur. Bu grafikler, modelin ne kadar başarılı olduğunu ve aşırı öğrenme olup olmadığını gösterir.
Ayrıca, modelin doğru ve yanlış tahminlerini gösteren örnek görseller de sunulmaktadır. Örneğin, doğru tahminler yeşil ile işaretlenirken, yanlış tahminler kırmızı ile işaretlenir.

## Sonuçlar 

•	Doğruluk: Model, eğitim ve test veri setlerinde yüksek doğruluk elde etti.

•	Model Performansı: Eğitim sırasında kayıp ve doğruluk grafikleri incelenerek modelin genel performansı değerlendirildi.

•	Tahminler: Doğru ve yanlış tahminler görselleştirilerek modelin ne kadar başarılı olduğu analiz edildi.

https://www.kaggle.com/code/mervecelikkol/fish-class

