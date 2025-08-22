# Gezinomi Kural Tabanlı Sınıflandırma Projesi

Bu proje, **MIUUL - Python Programming for Data Science** eğitimi kapsamında gerçekleştirilmiştir.  
Amacımız, **Gezinomi** adlı turizm şirketinin satış verilerini kullanarak **kural tabanlı sınıflandırma** yöntemiyle müşteri segmentleri oluşturmak ve yeni müşterilerin şirkete ortalama ne kadar gelir getirebileceğini tahmin etmektir.  

## Proje Amacı
- Satış verilerinden seviye tabanlı müşteri tanımları (persona) oluşturmak  
- Bu personeları segmentlere ayırmak  
- Yeni gelen müşterileri uygun segmente sınıflandırmak  
- Her segmentin şirkete sağlayacağı ortalama gelir tahminini yapmak  

Örneğin:  
Antalya’da her şey dahil, yüksek sezonda tatil yapmak isteyen bir müşterinin şirkete ortalama ne kadar kazandırabileceği hesaplanabilmektedir.  

---

## Veri Seti
Veri seti, Gezinomi şirketinin yaptığı satış kayıtlarından oluşmaktadır.  

- **SaleId** : Satış ID’si  
- **SaleDate** : Satış tarihi  
- **CheckInDate** : Otele giriş tarihi  
- **Price** : Satış fiyatı  
- **ConceptName** : Otel konsepti (Herşey Dahil, Yarım Pansiyon vb.)  
- **SaleCityName** : Otelin bulunduğu şehir  
- **CInDay** : Müşterinin otele giriş günü  
- **SaleCheckInDayDiff** : Satış ile giriş tarihi arasındaki gün farkı  
- **Season** : Sezon bilgisi (High / Low)  

> Veri seti tekilleştirilmemiştir. Yani bir müşteri birden fazla satış işlemi yapmış olabilir.
  
Not: Bu projede kullanılan veri seti, MIUUL eğitim materyali kapsamında sağlanmıştır ve gizlilik nedeniyle repoya eklenmemiştir. Projeyi çalıştırmak isteyen kullanıcıların kendi data/ klasörüne gezinomi_miuul.xlsx dosyasını eklemeleri gerekmektedir. 

---

## Proje Adımları
Proje kapsamında aşağıdaki görevler gerçekleştirilmiştir:  

1. **Veri Keşfi (Exploratory Data Analysis)**  
   - Şehir, konsept ve sezon bazında satışların incelenmesi  
   - Fiyat ortalamalarının ve toplam gelirlerin hesaplanması  

2. **Özellik Mühendisliği (Feature Engineering)**  
   - Satın alma zamanlamasına göre kategorik değişkenler oluşturuldu  
     - Last Minuters, Potential Planners, Planners, Early Bookers  
   - Seviye tabanlı müşteri tanımları (persona) oluşturuldu  

3. **Segmentasyon**  
   - Personalar ortalama fiyata göre 4 segmente ayrıldı  
   - Segmentlerin ortalama, maksimum ve toplam gelirleri hesaplandı  

4. **Kural Tabanlı Sınıflandırma**  
   - Yeni müşteriler segmentlere atanarak, şirkete getirecekleri tahmini gelir hesaplandı  

---

## Örnek Çıktılar

- **Seviye Tabanlı Persona Örneği**  
```
SaleCityName   ConceptName     Season    Price      sales_level_based
Girne          Herşey Dahil    High      103.93     GIRNE_HERŞEY_DAHIL_HIGH
```

- **Segment Örneği**  
```
SEGMENT    Price_Mean   Price_Max   Price_Sum
A          95.4         210.7       12000
B          75.3         180.2       9500
...
```

- **Yeni Müşteri Örneği**  
Antalya’da yüksek sezonda, Herşey Dahil tatil yapmak isteyen bir müşteri **A segmentinde** yer almakta ve ortalama **103.9 birim gelir** getirmesi beklenmektedir.  

---

## Kullanılan Teknolojiler
- Python  
- Pandas  
- NumPy  

---

## Notlar
- Bu proje, **MIUUL Python Programming for Data Science** eğitimi kapsamında yapılmıştır.  
- Veri seti MIUUL tarafından sağlanmıştır.  
