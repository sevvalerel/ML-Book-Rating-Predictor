# 📚 ML-Book-Rating-Predictor

Bu proje, Goodreads 100K kitap veri seti kullanılarak; kitapların sayfa sayısı, yorum sayısı ve toplam oy sayısı gibi **sayısal özelliklerine** göre yüksek puan (rating ≥ 4.0) alıp almayacağını tahmin etmeyi amaçlamaktadır.

Projede gözetimli öğrenme algoritmalarından **Logistic Regression** ve **Random Forest** kullanılmış; **hiperparametre optimizasyonu** için `GridSearchCV` uygulanmıştır.

---

## Giriş

Kaggle'da yayınlanan veri seti kullanılarak kitaplara ait **sayısal özellikler** temel alınmış ve bir **sınıflandırma problemi** çözülmüştür.

### Başlıca Adımlar:

- Verinin yüklenmesi ve ön analizi  
- Etiketleme işlemi (`rating ≥ 4.0` → 1, değilse → 0)  
- Logistic Regression ile temel performans değerlendirmesi  
- Random Forest ile gelişmiş modelleme ve hiperparametre ayarı  
- Model çıktılarının confusion matrix, classification report, ROC eğrisi ve feature importance ile değerlendirilmesi  
- EDA kapsamında tür, sayfa sayısı, yorum ve puan dağılımı görselleştirilmesi  

---

## Metrikler ve Performans

| Model              | F1 Skoru (Label=1) | Doğruluk (%) |
|--------------------|--------------------|--------------|
| Logistic Regression| ~0.08              | 60-62        |
| Random Forest      | 0.53 (GridSearch)  | 62           |

- Logistic Regression sınıf dengesizliği nedeniyle zayıf performans göstermiştir.
- Random Forest ile optimizasyon sonrası daha dengeli ve başarılı sonuçlar elde edilmiştir.
- ROC eğrisi, karışıklık matrisi ve feature importance gibi metriklerle model detaylıca analiz edilmiştir.

---

## Yorum ve Analiz

- `totalratings` ve `reviews` değişkenleri model başarısına en fazla katkı sağlayan özellikler olmuştur.
- Sayfa sayısı ve puan dağılımı dengesiz olsa da model için anlamlı sinyaller üretmektedir.
- Kategorik ve metinsel veriler henüz kullanılmamıştır; bu da modelin iyileştirme potansiyelini göstermektedir.

---

## 🔧 Gelecek Geliştirmeler

- `desc`, `genre` gibi **metinsel sütunların** işlenmesi ve modele TF-IDF gibi tekniklerle dahil edilmesi  
- **SMOTE** gibi örnekleme teknikleriyle sınıf dengesizliğinin ele alınması  
- **XGBoost**, **LightGBM** gibi gelişmiş algoritmalarla model karşılaştırmaları  
- **Streamlit** gibi araçlarla modele web arayüzü eklenmesi  

---

## Gelişmiş Uygulama Fikri

Proje, sadece sınıflandırma başarımıyla sınırlı kalmayıp bir **kitap öneri sistemi** olarak geliştirilebilir:

> Kullanıcıya belirli sayfa aralığı, tür ve popülariteye göre **yüksek puan alma olasılığı yüksek** kitaplar önerilebilir.

Bu sistem, eğitilen modelin çıktılarıyla kişiselleştirilmiş öneriler sunabilir ve bir web arayüzü üzerinden erişilebilir hale getirilebilir. Böylece proje, **gerçek dünya kullanımına** daha çok yaklaşır ve ileri düzey uygulamalara geçiş için zemin hazırlar.

---

## Linkler

- [Kaggle Notebook – ml-book-rating-predictor](https://www.kaggle.com/code/evvalerel/ml-book-rating-predictor)  
- [Veri Seti – Goodreads 100K Books](https://www.kaggle.com/datasets/arashnic/goodreads-books)

---

> Bu proje, Akbank ML Bootcamp kapsamında gerçekleştirilmiş olup, gözetimli öğrenme alanında veri analizi, modelleme ve değerlendirme becerilerini pekiştirmek amacıyla hazırladığım projedir.
