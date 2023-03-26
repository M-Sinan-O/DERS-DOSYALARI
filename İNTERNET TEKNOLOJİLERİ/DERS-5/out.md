# Ağ Katmanları

# Uzaktan Ders-I

23.03.2020

M.Sinan Oruç

# OSI Modeli

![](img%5Cag0.png)

![](img%5Cag1.png)

# OSI Başvuru Modeli

İki bilgisayar arasındaki iletişimi biçimsel olarak tanımlayan ilk kuruluşlardan birisi ISO\(International Organization for Standardization\) dur\.

ISO uluslararası veri iletişimini geliştiren kuruluşlardan biridir\.

Farklı bilgisayarların ve standartların gelişmesi ile sorunların ortaya çıkması nedeniyle ISO \(International Organization for Standardization\)\, OSI \(Open Systems Interconnection\) modelini 1984’te geliştirdi\.

# 

OSI ağ katman yapısından önce her donanım üreticisi kendine özgü bir ağ politikası izlediğinden\, aynı ağda farklı üreticilerin donanımları çalışamamaktaydı\.

OSI yapısı ile beraber farklı üreticilere ait donanımların uyumsuzlukları kaldırılarak aynı ağda uyumlu şekilde çalışmasına olanak sağlanmıştır\.

OSI yapısı ağı yedi katmana ayrılmıştır\.

Bu katmanlarda haberleşme esnasında kullanılan protokoller ve donanımlar bulunur\.

Bu katman birbirine bağımlıdır\.

Veri gönderimi yapılırken veri gönderici tarafında en üst katmandan yola çıkarak alıcının ise en alt katmanından başlayarak yukarı doğru tırmanır\.

![](img%5Cag2.png)

![](img%5Cag3.png)

En üst katman veriyi temsil ederken\, en alttaki katman bit seviyesindeki veriyi temsil etmektedir\.

# Fiziksel Katman(Physical Layer)

Bu katman verinin kablolar ile iletiminden sorumludur\.

Verinin elektrik\, ışık veya radyo sinyallerine çevrim şekli ve aktarımını tanımlar\.

Veri gönderen taraf dijital sinyalleri 1 ve 0 lardan oluşan veriyi analog sinyaller \(ışık\,elektrik veya radyo\) sinyallerinden birine çevirerek iletimini sağlar\.

Veriyi alan taraf ise analog sinyalleri\, dijital sinyallere çevirir\.

Ağ katmanındaki HUB’lar fiziksel katman tanımıdır\. Fiziksel katman iletişim türleri RS\-232\, 10Base\-T\, 1000Base\-TX\,DSL vb\.

# 

![](img%5Cag4.png)

# Veri Bağı Katmanı(Data Link Layer)

Fiziksel katmana erişim ile ilgili kuralları düzenler\.

Bu katmanda işlerin çoğunluğu ağ arayüz kartı içerisinde gerçekleşmektedir\.

Bu katman ağdaki cihazların tanımlanması\, veri hattının hangi cihaz tarafından kullanıldığının belirlenmesinde ve fiziksel katmandan gelen verinin hata denetimini yapar\.

Veriyi ağ katmanından alıp fiziksel katmana iletmek için kullanılan katmandır\.

Eğer veri ağ katmanından geliyorsa ve hata tespit edilirse veriye hata bitleri eklenir ve fiziksel katmana aktarılır\, bu katmanda tekrar gözden geçirilen veri ve hata bitlerinde gerçek bir hata görülürse veri iletimi tekrar yapılır\.

Ethernet\, Frame Relay\, ISDN\, Switch ve Bridge

# 

![](img%5Cag5.png)

Veri bağı katmanı LLC\(Logical Link Control\) ve MAC\(Media Access Control\) alt katmanları olmak üzere iki bölüme ayrılmaktadır\.

MAC alt katmanı ağ katmanından veri gönderiminde hata bitleri ve alıcı\, verici adreslerin ekleyerek fiziksel katmana geçiş yönünde denetimi gerçekleştirir\.

Aynı şekilde ağ katmanı tarafından gelen veriye ise bu işlemlerin tersini yapar\, veriyi LLC katmanına aktarır\.

LLC alt katmanı ise alıcı\-gönderici bilgisayarda aynı protokollerin kullanılması ve bozuk paketlerin tekrar gönderilmesini sağlar\.

LLC alt katmanı bir üst katman olan ağ katmanı için geçiş görevi görür\.

LLC ayrıca veri paketlerinden bozuk gidenlerin \(veya karşı taraf için alınanların\) tekrar gönderilmesinden sorumludur\.

_Flow_  _ Control _ yani alıcının işleyebileğinden fazla veri paketi gönderilerek boğulmasının engellenmesi de LLC'nin görevidir\.

# Ağ Katmanı(Network Katmanı)

Bu katman gelen veri paketlerinin ağ adreslerini kullanarak uygun ağlara yönlendirilmesini sağlar\.

Ağdaki cihazların adresleme işlemlerini gerçekleştirir\.

Router ve yönlendirilebilir switch bu katmanda yer alır\.

Adresleme işlemlerini \(Mantıksal adres ve fiziksel adres çevrimleri\) yürütür\.

Görevi taşıma katmanından gelen isteklere cevap vermek ve veriyi veri bağı katmanına iletmektir\. IP\, IPsec\.

# Taşıma Katmanı (Transport Katmanı)

Üst katmandan aldığı verileri bölümlere \(segment\) ayırarak bir alt katmana iletir\.

Bir üst katmana bu bölümleri birleştirerek sunar\.

İki düğüm arasında mantıksal bir bağlantının kurulmasını sağlar\.

Aynı zamanda akış kontrolü \(flow control\) kullanarak karşı tarafa gönderilen verinin yerine ulaşıp ulaşmadığını kontrol eder\.

Karşı tarafa gönderilen bölümlerin gönderilen sırayla birleştirilmesini sağlar\.

TCP\, UDP \(User Datagram Protocol\)\, SPX

# Oturum Katmanı(Session Katmanı)

* İki cihaz arasındaki Oturumun kurulması\, yönetilmesi ve sonlandırılmasını sağlar\.
* Haberleşmenin organize ve senkronize edilmesini sağlar\. Örneğin üçüncü bilgisayar iletişime dahil olduğunda oturum katmanı bu iletişimi organize eder\.
* Cihazlar arasında iletişim türüne de \(simplex\, half duplex\, full duplex\)  yine bu katmanda karar verilir\.
* Eğer veri iletiminde hata oluşmuş ise tekrar gönderilmesine karar verir\.
* Verinin güvenliğini sağlar\.
* Bu katmanda çalışan protokollere örnek;
  * NetBIOS \(Ağa bağlı cihazların birbiri ile haberleşmesini sağlayan uygulama\)
  * SSL\(İnternet üzerinden güvenli iletişim sağlayan bir yapıdadır\.\)

# Sunum Katmanı(Presentation Layer)

* Bu katmanın temel amacı verinin uygulama katmanı tarafından anlaşılabilir hale gelmesini sağlamaktır\.
* Bu katman verileri\, uygulama katmanına sunarken veri üzerinde kodlama ve dönüştürme işlemlerini yapar\.
* Örneğin farklı işletim sistemlerine aynı veriyi anlamlı kılabilmek için veriyi makine diline çevirmek zorundadır\. Bu işletim sistemlerinden birinde veri 8 bit ile anlam kazanırken diğerinde 16 bit ile anlam kazanabilir\. Bu sebeple veri genelleştirilmelidir\.
* Ayrıca bu katmanda;
  * veriyi sıkıştırma/açma\,
  * şifreleme/şifre çözme\,
  * Unicode’den ASCII’ye veya tam tersi yönde bir dönüşüm işlemlerini de yerine getirir\.
* PICT \,TIFF \,JPEG \,MIDI \,MPEG\, HTML\.

# Unicode

![](img%5Cag6.png)

# EBCDIC(Extended Binary Coded Decimal Interchange Code =Genişletilmiş İkilik Kodlu Ondalık Değişim Kodu)

![](img%5Cag7.png)

# ASCII

![](img%5Cag8.png)

# Uygulama Katmanı(Application Katmanı)

Kullanıcıya en yakın katmandır\.

Kullanıcı tarafından çalıştırılan tüm uygulamalar bu katmandadır\.

Uygulamalar ile ağ arasındaki geçiş birimidir\.

Dosya paylaşımı\, e\-mail\, veritabanı gibi işlemlerin gerçekleştirildiği katmandır\.

HTTP\, FTP\, SMTP – E\-mail \(Simple Mail Transfer Protocol\)\,  DNS

# 

<span style="color:#FF0000">Uzaktan Eğitim Dönemince Lütfen Evinizden Çıkmayın\!\!</span>

