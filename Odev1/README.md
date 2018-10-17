İstanbul Ün. Bilgisayar Mühendisliği Bölümü
Bilgisayar Mühendisliğine Giriş, Güz 2018, Atakan KURT
ÖDEV 1: Veritabanı-SQL, Teslim tarihi: 16 Ekim Salı

Ödev materyali: Bu ödev için “www.w3schools.com/SQL” tutorial’ini “SQL Inner Join”e kadar, bu tutorial’in “SQL Database” bölümünü de “SQL Views” adımına kadar çalışmış olmanız gerekmektedir.
Geç teslim uyarısı: Geç ödev kabul edilmez. Teslim gününden sonra ödev getirmeyiniz. 
Kopya uyarısı: Bu ödev tek kişilik ödevdir. Kısmen de olsa başkasının çözümünü almayınız. Internetten bulduğunuz çözümler kopya kabul edilecektir. Ödevinizi başkasıyla paylaşmayınız. Ödev veya sınavlarda kopya çekenler disipline sevkedilecektir.
Teslim şekli: Aşağıdaki soruları MySQL veritabanında çalıştırarak çıktılarını bir düz metin (TXT) dosyasına veya bir MS World (DOCX) dosyasına saklayıp, o dosyayı yazdırarak çıktısını teslim günü ders asistanına veya bana teslim ediniz. Eğer odamızda değilsek ödevinizi kapının altından atabilirsiniz.
Ödev bilgisi: Ödevin ilk sayfasına ödevin numarasını (kaçıncı ödev olduğunu), adınızı, numaranızı, ders adı ve kodunu yazınız. Ayrı bir ödev kapak sayfası kullanmayınız. Ödevi poşet dosyaya koymayınız. Sayfaları zımbayla veya ataçla tutturabilirsiniz. Sayfaların tamamını kullanmaya çalışınız (her sayfaya sadece bir soru-cevap şeklinde yerleştirip, sayfada kullanılmamış alan bırakmayınız). Ödevi önlü arkalı yazdırınız. Ödevde soruyu ve cevabın kaçıncı sorunun cevabı olduğunu belirtiniz. Siyah ekran çıktılarını yazdırarak toner harcamayınız.
Hata düzeltme: Hata aldığınızda hata mesajını dikkatlice okuyarak hatanızı düzeltmeye çalışınız. Düzeltemezseniz hata mesajını Google’da arama yaparak çözüm bulmaya çalışınız. Çoğu zaman karşınıza stackoverflow.com’dan bir çözüm çıkacaktır. SQL sözdizimi için Mysql.com/doc adresindeki dokümanatasyon sayfalarını incemeniz de gerekebilir. Çözüm bulamadığınız takdirde yazdığınız sorgunun ve aldığınız hata mesajının ekran görüntülerini epostayla bana atakan.kurt@stanbul.edu.tr veya ders asistanına (Ramiz Birdal http://profil.istanbul.edu.tr/tr/p/ramiz.birdal) göndererek sorabilirsiniz.
SORULAR: (Aşağıdaki soruları hem MySQL ile hem de Relational Algebra ile yazınız)
Bir restorandaki müşteriler, siparişler, yemekler, yemeklerde kullanılan malzemeler aşağıdaki gibi bir veritabanında tutulmaktadır. Bu veri tabanı şemasını kullanarak aşağıdaki sorguları istenilen dilde ifade ediniz. [İpucu: Restoran ve Okul veritabanı arasındaki benzerlik: Müşteriler öğrencilere, yemekler derslere, siparişler ders almaya, malzeme hocalara, kullanma ise ders vermeye benzemektedir.]
•	Musteri(mno, madi, msoyadi, mtelefon) // müşterinin no’su adi, soyadı, telefonu
•	Yemek(yno, yadi, ykalori, yfiyati, yturu) // yemeğin no’su, adı, kalorisi, fiyatı ve türü
•	Malzeme(zno, zadi, ztipi) // malzemenin no’su, adı ve tipi
•	Siparis(mno, yno, tarihsaat) // hangi müşterinin hangi yemeği hangi tarih-saatte sipariş ettiği
•	Kullan(yno, zno, miktar) // hangi yemekte hangi malzemenin hangi miktarda kullanıldığı

•	Ödevi yapabilmek için önce mysql sunucusunu Xampp Control uygulamasından çalıştırınız
•	Sonra xampp/mysql/bin klasörüne gidiniz. 
•	Orada Shift + FareSağTuş’una birlikte basarak karşınıza çıkan menüden bir “command window” açınız. [Bilgisayarınızda Window 8/10 varsa “command window” yerine “Powershell window” çıkabilir. O zaman “Powershell window” açınız. “Powershell window” açılınca “cmd” yazıp Enter’a basınız. Böylece “command window” açmış olacaksınız]
•	“Command window” içinde “mysql –u root –p” komutunu giriniz (yani: “mysql –u root –p” yazıp Enter’a basınız. Tırnak işaretlerini yazmıyorsunuz ) Böylece mysql sunucusuna mysql DOS client’ıyla bağlanmış olacaksınız.
•	Mysql’de yazdığınız tüm komutları ve bu komutlarını cevap/çıktılarını odev1.sql diye bir metin dosyasına kaydetmeye başlamak için ‘TEE odev1.sql;’ komutunu yazıp Enter’a basınız. (Bundan sonra mysql’de yazdığınız tüm komutlar ve o komutların ekranda görülen çıktıları otomatik olarak odev1.sql metin dosyasının için mysql client’ı tarafından saklanacaktır.) 

1.	‘Ali’ ‘KURT’ müşterisinin sipariş verdiği yemeklerde kullanılan malzemelerin adlarını listeyiniz
2.	‘Kuru fasulye’ yemeğinde kullanılmayan malzemelerden yapılan yemeklerin kayıtlarını listeleyiniz
3.	‘domates’ ve ‘kereviz’ (hem domates hem dem de kereviz) malzemelerinin kullanıldığı yemeklerden sipariş veren müşterilerin kayıtlarını listeleyiniz.
4.	‘domates’ kullanılan tüm yemekleri sipariş eden müşterilerin isim ve soyisimlerini listeleyiniz
5.	En az 3 farklı yemekte kullanılan malzemeler için, her malzemenin hangi sayıda yemekte kullanıldığını, ortalama ne miktarda kullanıldığını listeleyiniz.

•	“Exit” yazarak mysql’den çıkınız.
•	Odev1.mysql dosyasını notepad ile açıp kontrol ediniz. Ödev bilgisi ve soru numaralarını bu dosyanın içine uygun yerlere yazınız ki, hangi komutun hangi sorunun cevabı olduğunu ödevi değerlendirirken kolayca görelim.
•	Odev1.sql dosyasının son şeklini yazdırıp ödevi teslim ediniz. 
•	Relational algebra çözümlerini kalem kağıt ile yaparak veriniz.

 
