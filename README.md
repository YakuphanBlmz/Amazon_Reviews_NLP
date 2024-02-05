#  Natural Language Processing 

## Doğal Dil İşleme Nedir?

NLP, "Natural Language Processing" (Doğal Dil İşleme) ifadesinin kısaltmasıdır. NLP, bilgisayarların insan dilini anlaması, yorumlaması, üretmesi ve cevap vermesi gibi görevleri gerçekleştirmek için kullanılan bir disiplindir. Bu alandaki temel amaç, bilgisayarların insanlar gibi dil ile etkileşim kurabilmesini sağlamaktır.

NLP'nin birçok uygulama alanı vardır. Bazı örnekler şunlardır:

* Metin Madenciliği (Text Mining): Büyük metin verilerini analiz ederek anlamlı bilgiler çıkarmak.
* Konuşma Tanıma (Speech Recognition): Sesli komutları anlamak ve yazıya dönüştürmek.
* Çeviri Sistemleri: Bir dilde yazılmış metinleri başka bir dile çevirmek.
* Chatbotlar ve Sanal Asistanlar: Kullanıcılarla doğal bir dilde etkileşim kurabilen bilgisayar programları.
* Duygu Analizi (Sentiment Analysis): Metinlerdeki duygusal tonları belirleyerek kullanıcı duygularını anlamak.
* Kelime Dağarcığı ve Anlam Çıkarma: Kelimelerin anlamlarını anlama ve bağlamı çıkarma.

NLP, makine öğrenimi, dilbilimi ve bilgisayar bilimleri alanlarının kesişiminde yer alır. Bu alandaki gelişmeler, otomatik metin anlama, dil tabanlı arama ve birçok uygulama için yeni olanaklar sunmaktadır.
Metinleri analiz ederek çok değerli veriler elde edebiliriz.

**Bu yazımda sizlere NLP'yi bir örnek üzerinde anlatmaya çalışacağım.**

Bahsettiğimiz gibi NLP'nin bir çok farklı alanı vardır. Ben ise bu aşamada "Metin Sınıflandırma" ve "Duygu Analizi" konusuna odaklanacağım. Ele aldığımız bu konuları uçtan uca bir gerçek bir Amazon verisi üzerinden gerçekleştireceğiz. Projemizin sonunda elde ettiğimiz çıktı bir duygu analizi(Sentiment Analysis) ve duygu modellemesi(Sentiment Modeling) olacaktır. Amazondaki bir ürünün yorumlarına odaklanarak bu çıkarımlarda bulunacağız.

### Süreç 
Bir metin sınıflandırma süreci, veri bilimi sürecine oldukça benzerdir. Veriyi elde etme aşamasından sonra, metinler ön işleme aşamasından geçirilir. Ardından metin görselleştirme işlemleri yapılır ve ilgili konudaki analiz uygulanır. Bir makine öğrenmesi veya bir modelleme süreci varsa özellik mühendisliği yapılır ve neticesinde modelleme yapılır. Bu adımları maddeler halinde listelemek istersek :

1. **Text Preprocessing**
2. **Text Visualization**
3. **Sentiment Analysis**
4. **Feature Engineering**
5. **Sentiment Modeling**

Projeye başlayabilmemiz adına, doğal dil işlemede kullanılan yaygınca kütüphanelerin indirilmesi gerekiyor. Bu kütüphaneleri indirmek için dosyanın olduğu konumda, terminali açıp aşağıdaki komutları yazmanız yeterli olacaktır. 

* ```pip install nltk```
* ```pip install textblob```
* ```pip install wordcloud```
* ```pip install -U scikit-learn```
* ```pip install pyarrow``` *(Gerekebilir)*


Her projede kütüphaneler eklenir fakat bu kütüphanelerin içeriğini bilmek de önemlidir. Dilerseniz eklediğimiz kütüphanelerin ne olduğuna bir bakalım.

### NLTK (Natural Language Toolkit)
NLTK (Natural Language Toolkit), doğal dil işleme (NLP) uygulamaları geliştirmek için kullanılan bir Python kütüphanesidir. NLTK, dil analizi, metin madenciliği, konuşma tanıma, çeviri ve daha birçok NLP görevi için araçlar ve kaynaklar sunar. İşte NLTK'nin temel özellikleri ve neden kullanılması gerektiğiyle ilgili bazı nedenler:

* **Çok Kapsamlı Dil Veritabanı:** NLTK, dilbilimi ve dil işleme araştırmalarında kullanılan geniş bir dil veritabanına sahiptir. Bu, dil analizi ve işleme görevlerinde kullanılan modellerin ve kaynakların geniş bir yelpazesine erişim sağlar.
* **Metin Madenciliği ve Analizi:** NLTK, metin madenciliği uygulamaları için özellikle güçlüdür. Metin içindeki kelime frekansı analizi, kelime bulutları oluşturma, belirli kelime türlerini ayıklama ve metin madenciliği uygulamalarında kullanılan birçok aracı içerir.
* **Konuşma Tanıma:** NLTK, konuşma tanıma uygulamalarında kullanılmak üzere bir dizi araç ve algoritma içerir. Sesli komutları anlamak, sesli metinleri yazıya dönüştürmek gibi görevleri gerçekleştirebilir.
* **Çeviri Sistemleri:** NLTK, dil çevirisi uygulamalarında kullanılabilecek çeşitli çeviri modellerini içerir. Özellikle dilbilim temelli çeviri uygulamaları için kullanışlıdır.
* **Dil İstatistikleri ve Sınıflandırma:** NLTK, dilin istatistiksel özelliklerini analiz etmek ve metin sınıflandırma gibi görevlerde kullanılan makine öğrenimi modellerini uygulamak için araçlar içerir.
* **Eğitim ve Öğrenme Kaynakları:** NLTK, dil işleme ve makine öğrenimi konularında eğitim ve öğrenme kaynakları içerir. Bu kaynaklar, NLP konusundaki temel kavramları öğrenmek ve uygulamak için kullanışlıdır.

NLTK, geniş bir topluluk tarafından desteklenmekte ve sürekli olarak güncellenmektedir. Bu nedenle, NLP uygulamaları geliştirmek isteyen geliştiriciler için güvenilir bir kaynaktır. Ancak, son dönemde diğer popüler NLP kütüphaneleri de gelişmiş ve kullanım açısından daha kolay hale gelmiştir, bu yüzden projenin ihtiyaçlarına en uygun kütüphaneyi seçmek önemlidir. Gereksiz yere kütüphane kullanmanın da olumsuz etkileri vardır.

Daha fazla araştırma yapmak için [NLTK](https://www.nltk.org/index.html) sitesini ziyaret edebilirsiniz. 

#### EK BİLGİ : Gereksiz Kütüphane Kullanımı 
* **Proje Boyutu ve Performans:** Gereksiz kütüphaneleri projenize eklemek, proje boyutunu artırabilir ve gereksiz kaynak kullanımına yol açabilir. Bu durum, projenizin performansını etkileyebilir, özellikle de büyük veri setleri veya düşük kaynaklı cihazlarla çalışılıyorsa.

* **Bağımlılıklar ve Güvenlik Riskleri:** Gereksiz kütüphaneler, projenizin dış bağımlılıklarını artırabilir. Bu, projenizin güvenliği için bir risk oluşturabilir, çünkü her bağımlılık potansiyel bir güvenlik açığı içerebilir. Ayrıca, projenizi güncel tutmak ve bağımlılıkları yönetmek daha zor olabilir.

* **Geliştirme ve Bakım Zorluğu:** Gereksiz kütüphaneleri kullanmak, kodunuzu karmaşıklaştırabilir ve geliştirme sürecini zorlaştırabilir. Bu, ekibinizin veya gelecekteki geliştiricilerin projeyi anlamasını ve bakımını yapmasını zorlaştırabilir.

* **Kod Temizliği ve Anlaşılırlık:** Gereksiz kütüphaneleri kullanmak, projenizin kod temizliğini ve anlaşılırlığını azaltabilir. Bu da kodunuzu okumak, anlamak ve üzerine çalışmak için daha fazla zaman harcanmasına neden olabilir.

* **Gereksiz Özellikler:** Gereksiz kütüphaneler, projenizin ihtiyaçlarına uygun olmayan özellikleri içerebilir. Bu durum, projenizin gereksiz karmaşıklığı artırabilir ve kullanıcılara istemedikleri veya kullanmadıkları özelliklerle karşılaşma riski verebilir.




### TextBlob
TextBlob, Python dilinde doğal dil işleme (NLP) görevlerini gerçekleştirmek için kullanılan bir kütüphanedir. TextBlob, dil işleme görevlerini kolaylaştıran bir arayüz sağlar ve bir dizi özellik içerir. İşte TextBlob'un temel özellikleri:

* **Basit ve Kullanımı Kolay:** TextBlob, NLP görevlerini gerçekleştirmek için basit bir API sağlar. Bu sayede kullanıcılar, dil işleme işlemlerini daha hızlı ve daha az kodla gerçekleştirebilirler.

* **Metin Analizi:** TextBlob, metin analizi için bir dizi araç ve fonksiyon içerir. Metin analizi, metinlerdeki duyguları belirleme, cümle yapısı analizi, kelime frekansı ve sıklığı gibi görevleri kapsar.

* **Duygu Analizi:** TextBlob, metinlerdeki duygusal tonları analiz edebilir. Metin içindeki ifadeleri pozitif, negatif veya nötr olarak sınıflandırabilir.

* **Kelime Dağarcığı:** TextBlob, bir kelimenin anlamını, eşanlamlılarını ve kelime türünü belirleme gibi kelime düzeyinde analizler yapabilir.

* **Metin Sınıflandırma:** TextBlob, belirli bir metni önceden tanımlanmış kategorilere sınıflandırmak için kullanılabilir. Bu, spam filtreleme, duygu analizi ve konu sınıflandırma gibi uygulamalarda kullanışlıdır.

* **Konu Çıkarma:** TextBlob, bir metnin ana konularını çıkarma yeteneğine sahiptir. Bu, büyük metin koleksiyonları üzerinde önemli konuları belirlemek için kullanılabilir.

* **Dil Tanıma:** TextBlob, metnin hangi dilde olduğunu tanımlama yeteneğine sahiptir. Bu özellik, çok dilli uygulamalarda veya çok dilde veri üzerinde çalışırken kullanışlıdır.

Temel özellikleri bu şekilde. Peki iyi de neden kullanalım. Çünkü :

* **Hızlı Prototip Oluşturma:** TextBlob, NLP görevlerini hızlı bir şekilde prototip oluşturmak için idealdir. Basit bir API ve kullanımı kolay fonksiyonları, karmaşık dil işleme görevlerini hızlı bir şekilde uygulamanıza olanak tanır.

* **Başlangıç Seviyesi Kullanıcılar İçin Uygun:** TextBlob, özellikle dil işleme konusunda deneyimi olmayan veya başlangıç seviyesindeki kullanıcılar için uygundur. [Dökümantasyonu](https://textblob.readthedocs.io/en/dev/) açıklayıcıdır ve temel NLP görevlerini gerçekleştirmek için kullanıcı dostu bir arabirim sunar. 

* **Kolay Kurulum:** TextBlob, temel NLP işlevselliğini sağlamak için gerekli olan birçok dil işleme aracını içerir. Bu nedenle, kullanıcıların ayrı ayrı dil modelleri veya kaynakları indirmelerine gerek kalmadan kolayca kullanılabilir.

TextBlob'un bazı durumlarda daha spesifik veya gelişmiş NLP görevleri için yetersiz kalabilir(genelde de kalır). Projenizin ihtiyaçlarına bağlı olarak, daha spesifik veya özelleştirilebilir kütüphaneleri incelemek de faydalı olabilir.

### WordCloud
WordCloud, Python dilinde metin verilerinden kelime bulutları oluşturmak için kullanılan bir kütüphanedir. Bu kütüphane, metin içerisinde geçen kelimelerin frekansına göre görsel olarak temsil edilen bir kelime bulutu oluşturmak için kullanılır. 

<img src="https://miro.medium.com/v2/resize:fit:1358/0*1NkpAO55_vSV_vRF.jpeg" alt="Word Cloud" width="1024" height="562">

İşte WordCloud'un temel özellikleri ve kullanılmasının nedenleri:

* **Görsel Temsil:** WordCloud, metin içerisinde geçen kelimeleri bir görsel olarak temsil eder. Bu sayede metindeki önemli kelimelerin ve kelimeler arasındaki ilişkilerin hızlıca anlaşılmasını sağlar.

* **Frekans Analizi:** Kelime bulutları, metindeki kelimelerin frekanslarına göre büyüklükleri belirleyerek önem sırasına koymak için kullanılır. Bu, metindeki anahtar kelimeleri ve konuları hemen farkedebilmenizi sağlar.

* **Veri Görselleştirme:** WordCloud, metin madenciliği ve veri analizi uygulamalarında kullanılarak büyük metin verilerini hızlı bir şekilde görselleştirmenizi sağlar. Metindeki önemli kelimeleri belirlemek ve anlamak için güçlü bir araçtır.

* **Proje Analizi ve Raporlama:** WordCloud'lar, projelerinizde veya raporlarınızda metin verilerini görselleştirmek için kullanılabilir. Özellikle kelime bulutları, bir projenin ana temasını veya bir metnin öne çıkan konularını vurgulamak için kullanışlıdır.

* **Gelişmiş Özelleştirme:** WordCloud kütüphanesi, oluşturulan kelime bulutlarını özelleştirmek için bir dizi seçenek sunar. Renk paletleri, şekil seçenekleri, frekans filtreleme ve diğer özelliklerle kelime bulutları istenilen şekilde uyarlanabilir.

* **Dil Bağımsız:** WordCloud, birçok dilde metin verileriyle çalışabilir. Bu özellik, çok dilli projelerde veya çok dilli metin verileriyle çalışırken avantaj sağlar.

WordCloud için iki adet kaynak önerebilirim. Bunlar : 
* [PyPI](https://pypi.org/project/wordcloud/)
* [Andreas C. Müller Github](https://amueller.github.io/word_cloud/)

### Scikit-Learn 
scikit-learn, Python programlama dilinde kullanılan açık kaynaklı bir makine öğrenimi kütüphanesidir. Genellikle kısaltması olarak sklearn olarak da bilinir. scikit-learn, bir dizi makine öğrenimi algoritması, veri madenciliği ve veri analizi araçları içerir. İşte scikit-learn'ün temel özellikleri :

* **Basit ve Kullanımı Kolay:** scikit-learn, kullanımı kolay ve iyi belgelenmiş bir API'ye sahiptir. Bu, hem başlangıç seviyesindeki kullanıcılar hem de deneyimli makine öğrenimi uzmanları için uygun bir tercih yapılmasını sağlar.

* **Geniş Algoritma Desteği:** scikit-learn, sınıflandırma, regresyon, kümeleme, boyut azaltma ve model seçimi gibi çeşitli makine öğrenimi algoritmalarını içerir. Bu, projelerinizde farklı görevlere uygun algoritmalar seçmenizi sağlar.

* **Veri Ön İşleme ve Feature Engineering Araçları:** scikit-learn, veri ön işleme ve özellik mühendisliği konularında bir dizi araç sunar. Özellikle veri temizleme, ölçekleme, dönüştürme ve eksik veri yönetimi gibi işlemleri kolayca gerçekleştirebilirsiniz.

* **Model Seçimi ve Değerlendirme:** scikit-learn, farklı modelleri karşılaştırma ve en uygun modeli seçme konusunda yardımcı olan araçlar içerir. Ayrıca, çeşitli metrikler kullanarak modellerin performansını değerlendirmenizi sağlar.

* **Paralel İşleme ve Dağıtılmış Hesaplama Desteği:** Bazı algoritmalar, veri setinin büyüklüğü nedeniyle uzun sürebilir. scikit-learn'ün bazı bölümleri paralel işleme ve dağıtılmış hesaplama yeteneklerini destekler, bu da performansı artırabilir.

* **Topluluk Desteği ve Sürekli Gelişim:** scikit-learn, büyük bir açık kaynaklı topluluk tarafından desteklenir ve sürekli olarak geliştirilmektedir. Bu, kullanıcılar için güncel ve desteklenen bir kaynak olmasını sağlar.

Neden bu kütüphaneyi kullananayım ki? Çünkü :

* **Başlangıç Seviyesi İçin İdeal:** scikit-learn, makine öğrenimi konusunda yeni olanlar için ideal bir başlangıç noktasıdır. Basit ve tutarlı bir API, öğrenme sürecini kolaylaştırır.

* **Hızlı Prototip Oluşturma:** Projelerinizi hızlı bir şekilde prototiplemek ve farklı algoritmaları denemek için uygundur.

* **Endüstri Standartlarına Uygunluk:** scikit-learn, birçok endüstri standardına ve iyi kabul edilmiş makine öğrenimi yöntemlerine uygunluğu ile bilinir.

* **Esnek ve Genişletilebilir:** scikit-learn, kullanıcıların kendi algoritmalarını entegre etmelerine ve kütüphaneyi genişletmelerine olanak tanıyan bir yapı sunar.


## Veri Setimiz 
Veri setimiz Amazon'daki bir ürünün yorumlarıdır. Gerçek bir veri setidir. Bir örneğini incelediğimizde :  

![image](https://github.com/YakuphanBlmz/Amazon_Reviews_NLP/assets/106194461/5c1160d7-2206-4c65-9e84-d86dcc703e61)

Verileri yorumlamak istersek : 

* **reviewerID :** Yorum yapan kişileri ifade eden değişken
* **asin :** Ürünü ifade eden değişken
* **reviewerName :** Yorum yapan kişilerin isimleri ifade eden değişken
* **helpful :** Yorumların faydalı olup olmadığına dair değişken, soldaki değer faydalı bulmayı, sağdaki değer ise faydalı bulmamayı gösterir.
* **reviewText :** Yorumları ifade eden değişken (bizi ilgilendiren asıl kısım)
* **overall :** Verdiği puanı ifade eden değişken
* **summary :** Yorumların özeti niteliğinde tanımlanmış değişken
* **unixReviewTime :** Yorumun Unix zaman damgasını(timestamp) ifade eden değişken (Unix zaman damgası, 1970-01-01 00:00:00'den itibaren geçen saniye sayısını temsil eder. Bu tür bir zaman temsil biçimi genellikle hesaplama ve karşılaştırma işlemlerinde kullanılır. Bu sütundaki değerler, yorumun ne zaman yapıldığını gösterir.)
* **reviewTime :** Yorumun yazıldığı tarihi ifade eden  değişken
* **day_diff :** Yorumun yapıldığı tarih ile referans tarih arasındaki gün sayısını gösteren değişken (Genellikle, referans tarih, veri setinin incelendiği tarihi temsil eder.)
* helpful_yes : *helpful* değişkeninin açılmış halinden biridir. Faydalı yorumları gösteren değişken
* total_vote : *helpful* değişkeninde yer alan faydalı ve faydalı olmayan birimlerin toplanılmış halini gösterir.

Buradaki değişkenleri anlamadıysanız korkmayın. Bizim odak noktamız **reviewText** değişkeni olacaktır.  


