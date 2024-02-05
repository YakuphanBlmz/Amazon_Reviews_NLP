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
Bir metin sınıflandırma süreci, veri bilimi sürecine oldukça benzerdir. Veriyi elde etme aşamasından sonra, metinler ön işleme aşamasından geçirilir. Ardından metin görselleştirme işlemleri yapılır ve ilgili konudaki analiz uygulanır. Bir makine öğrenmesi veya bir modelleme süreci varsa özellik mühendisliği yapılır ve sonrasında neticesinde modelleme yapılır. Bu adımları maddeler halinde listelemek istersek :

1. Text Preprocessing
2. Text Visualization
3. Sentiment Analysis
4. Feature Engineering
5. Sentiment Modeling

Projeye başlayabilmemiz adına, doğal dil işlemede kullanılan yaygınca kütüphanelerin indirilmesi gerekiyor. Bu kütüphaneleri indirmek için dosyanın olduğu konumda, terminali açıp aşağıdaki komutları yazmanız yeterli olacaktır. 

!pip install nltk
!pip install textblob
!pip install wordcloud

Her projede kütüphaneler eklenir fakat bu kütüphanelerin içeriğini bilmek de önemlidir. Dilerseniz eklediğimiz kütüphanelerin ne olduğuna bir bakalım.


