# ML-Book-Rating-Predictor

Bu proje, Goodreads 100K kitap veri seti kullanılarak, kitapların sayfa sayısı, yorum sayısı ve toplam oy sayısı gibi sayısal özelliklerine göre **yüksek puan (rating ≥ 4.0)** alıp almayacağını tahmin etmeyi amaçlamaktadır. Projede gözetimli öğrenme algoritmalarından **Logistic Regression** ve **Random Forest** kullanılmış, hiperparametre optimizasyonu için **GridSearchCV** uygulanmıştır.


## Giriş

Projede kullanılan veri seti Kaggle üzerinde yayınlanan bir veri seti olup, kitaplara ait sayısal özellikler temel alınarak bir sınıflandırma problemi çözülmüştür.

Başlıca adımlar şunlardır:

- Verinin yüklenmesi ve ön analizi  
- Etiketleme işlemi (rating ≥ 4.0 ise 1, değilse 0)  
- Logistic Regression ile temel performans değerlendirmesi  
- Random Forest ile gelişmiş modelleme ve hiperparametre ayarı  
- Model çıktılarının confusion matrix, classification report, ROC eğrisi ve feature importance ile değerlendirilmesi  
- EDA kapsamında tür, sayfa sayısı, yorum ve puan dağılımı görselleştirilmiştir


## Metrikler

Model başarıları aşağıdaki metriklerle değerlendirilmiştir:

- **Logistic Regression** modeli sınıf dengesizliği nedeniyle label=1 için zayıf performans göstermiştir (F1: ~0.08).
- **Random Forest** modeli GridSearchCV ile optimize edildiğinde label=1 için F1 skoru **0.53** seviyelerine çıkarılmıştır.
- Genel doğruluk **%62** olarak elde edilmiştir.

Ayrıca ROC eğrisi, karışıklık matrisi ve değişken önem sıralaması ile modelin davranışı detaylı analiz edilmiştir.


## Yorum ve Analiz

Bu proje sadece doğruluk metriklerine değil, aynı zamanda modelin sınıflar arasındaki dengeyi ne kadar iyi kurduğuna ve hangi değişkenlere ne derece ağırlık verdiğine odaklanmaktadır. Özellikle `totalratings` ve `reviews` değişkenlerinin model üzerindeki baskın etkisi öne çıkmıştır.

Proje kapsamında yapılan analizlerde şu değerlendirmeler öne çıkmıştır:

- Sayfa sayısı ve puan dağılımı dengesizdir ancak model için anlamlı sinyaller üretmektedir.
- Kategorik ve metinsel veriler henüz kullanılmamıştır, gelecekte model iyileştirmesi için bu veriler entegre edilebilir.


## Sonuç ve Gelecek Çalışmalar

Bu proje, gözetimli öğrenme yöntemleriyle kitapların kullanıcı puanlarını sınıflandırmak amacıyla güçlü bir temel sunmuştur. Veri ön işleme, modelleme, hiperparametre optimizasyonu ve model değerlendirme adımları sistemli biçimde uygulanmıştır.

Bundan sonraki aşamalarda aşağıdaki geliştirmeler yapılabilir:

- `desc`, `genre` gibi metinsel sütunların işlenip TF-IDF gibi tekniklerle modele dahil edilmesi  
- SMOTE gibi örnekleme teknikleriyle sınıf dengesizliğinin farklı yöntemlerle ele alınması  
- XGBoost, LightGBM gibi daha gelişmiş algoritmalarla model karşılaştırmaları yapılması  
- Streamlit gibi araçlar kullanılarak modele arayüz eklenmesi

### Gelişmiş Uygulama Fikri:

Proje, sadece sınıflandırma başarımıyla sınırlı kalmayıp bir **kitap öneri uygulaması** haline getirilebilir.  
Örneğin; kullanıcıya belirli sayfa aralığı, tür ve popülariteye göre yüksek puan alma olasılığı yüksek kitaplar öneren bir sistem geliştirilebilir.  
Bu sistem, eğitilen modelin çıktılarıyla kişiselleştirilmiş öneriler sunabilir ve bir web arayüzü ile erişilebilir hale getirilebilir.

Bu yöndeki çalışmalar, projeyi gerçek dünya kullanımına daha da yaklaştıracak ve ileri düzey uygulamalara geçiş için güçlü bir zemin oluşturacaktır.


## Linkler

[- [Kaggle Notebook - ml-book-rating-predictor](https://www.kaggle.com/code/evvalerel/ml-book-rating-predictor)  ](https://www.kaggle.com/code/evvalerel/ml-book-rating-predictor)

[- [Veri Seti - GoodReads 100k Books](https://www.kaggle.com/datasets/meetnaren/goodreads-best-books)](https://www.kaggle.com/datasets/mdhamani/goodreads-books-100k)

