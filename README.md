# Robots.txt
Robots.txt



Arama motoru botlarının asli görevi web sitelerinin sayfalarını taramak ve arşivlemektir. Bazı durumlarda web sitemizin önemli bilgiler içeren bazı bölümlerini arama motoru botlarının erişimine kapatmak isteriz. İşte robots.txt dosyası bu amaç için kullandığımız yöntemlerden birisidir. Yanlış oluşturduğumuz bir robots.txt dosyası sitemizin önemli bölümlerinin arama motorlarının erişimine kapanması anlamına gelebilir.
Yani robots.txt arama motorlarının sitemizin hangi bölümlerini dizine ekleyeceğini, hangi dizini taraması gerektiğini ve hangi arama motorunun giriş izni olduğunu veya olmadığı kontrol ettiğimiz basit komut dosyalarıdır. Arama motorları sitemize geldiğinde ilk olarak bu dosyayı tarar ve dosyadaki komutlara göre sitenin izin verilen bölümlerini dizine ekler.
</br></br>
Bilinmesi gereken bazı bilgiler
</br></br>
 - Robots.txt dosyamızın sitemizin kök dizininde bulunuyor olması gerekir.
 - Robots.txt dosyamızın UTF-8 karakter kodlamasına uygun şekilde hazırlanmış olmalıdır.
 - www.sitemiz.com/robots.txt dizininde bulunmalıdır.
 
 ### User-agent
Sitemize hangi arama motoru robotunun gelebileceğini ya da gelemeyeceğini belirtmenizi sağlar. Örneğin arama motorlarının sitemizi taramasını istemiyorsak, user-agent komutunu kullanırız.
</br></br>
user-agent:*  &nbsp;&nbsp;&nbsp;=> &nbsp;&nbsp;&nbsp; Tüm arama motoru robotlarına izin vermek için tek başına kullanırız.
</br></br>
Tüm arama motorlarının sitemizi taramasını engellemek istiyorsak şöyle kullanırız;</br>
user-agent: *</br>
disallow: /
</br></br>
Sadece google bot'un private dizinine erişimini engelleyelim. Diğer tarayıcılara sitemizin tamamına erişimi engelleyelim.</br></br>
User-agent: googlebot</br>
Disallow: /private/</br>
User-agent: *</br>
Disallow: /</br>


### Allow ve Disallow
Allow ya da Disallow komutlarını kullanarak sitemizdeki belirli dizinlere/sayfalara erişim izni verebilir ya da sınırlama koyabiliriz. Bu bölümde yapacağımız değişiklik sadece arama motoru robotuna özeldir. Kullanıcılar komut verdiğimiz dizine/sayfaya erişmeye devam edebileceklerdir. Örneğin, aşağıdaki kod ile index sayfamıza izin verdik, özel sayfamıza ise taramayı engelledik.</br></br>
user-agent: *</br>
allow: /Home/Index</br>
disallow: /Admin/privatePage/</br>


### sitemap.xml komutu
sitemap.xml dosyasının URL’sinin doğru şekilde yazılmış olması gerekmektedir. Sitemap.xml dosyası, sitemizin taranması konusunda arama motoru robotlarına en önemli bilgileri vereceği için, mutlaka kullanılmalıdır. Arama motoru robotu sitemizi tararken ilk olarak robots.txt dosyasına göz atmaktadır ve bu dosyada ve sitede sitemap.xml dosyasına dair herhangi bir içerik bulunmaması bir dezavantaj yaratabilir.</br></br>
user-agent: *</br>
Sitemap: http://www.sitemiz.com/sitemap.xml

### Özel komut
Robots.txt dosyasına ekleyeceğimiz özel komutlarla, belli bir karakteri içeren ya da belli bir URL uzantısını içeren sayfaları bütünüyle arama motoru robotlarının erişimine kapatabiliriz. Örnek olarak url içerisinde ? olan tüm url'ler arama motoru robotlarının erişimine kapatmak;
</br></br>
user-agent: *</br>
Disallow: /*?
