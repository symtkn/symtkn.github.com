---
layout: post
title: Hibernate Framework
---
###KONU BAŞLIKLARI

<li><a href="#hb-tanım"> Neden Hibernate?</a></li><br>
<li><a href="#hb-mimari"> Mimari Yapısı</a></li><br>
<li><a href="#hb-yapılandırma"> Yapılandırması</a></li><br>
<li><a href="#xml-tabanlı-ayarlar"> Ayarlar Yapılırken XML Tabanlı Dosya Kullanmak</a></li><br>
<li><a href="#pojo"> Kalıcı Sınıflar</a></li><br>

###<a id="hb-tanım"> 1- Neden Hibernate?</a>

  Nesne İlişkisel Eşleme (ORM / Object-Relational Mapping ), İlişkisel Veri tabanı ile Nesneler arasında çevirme yapma 
ve bağlantı kurma işlemidir. Küçük nesnelerle bu işlemi yapmak kolay iken nesnelerin, verilerin ve birleştirmemiz gereken 
tabloların sayısı arttıkça bu işleminin yapılması oldukça zor bir hal alır.

  Karmaşıklaşan nesne modeli ve ilişkileri karşımıza sorun olarak çıkar. Hibernate bu nokta da bu işlemleri en başarılı 
şekilde yerine getirmemizde bize büyük kolaylık, rahatlık ve başarım sağlar. 
Hibernate Java'da kalıcı veri yönetimine bütün bir çözüm getiren bir projedir. Java için bir ORM Kitaplığı yani bir Nesne-İlişkisel
Eşleme aracıdır.
    
  Uygulamaların, ilişkisel veri tabanı ile etkileşimine aracılık eder. Basit bir Java nesnesinin kalıcı hale gelmesini
ve kaydedilmiş kalıcı nesneyi geri yüklememizi basit komutlarla sağlar. Bu da geliştiricinin <font color="red">sadece iş 
mantığına</font> odaklanmasını sağlar. Takip edilmesini gerektiren belli katı kuralları yoktur. Bu sayede hem yeni hem de var olan projelere herhangi bir değişiklik gerektirmeden başarılı bir şekilde uyum sağlar.
Geliştiricisi Gavin King'e göre kalıcı nesneler, başka bir nesneden türetilmeyen basit Java nesneleri POJO(Plan Old Java Object) olmalıydı. Belirli katı standartları olmamalı ve güçlü bir sorgulama dilini desteklemeliydi. Ve bunların hepsi açık kaynak kodlu olmalıydı.

###<a id="hb-mimari"> 2- Mimari Yapısı</a>

<b>Genel Görünüm</b>
Aşağıda ki diyagram da Hibernate’in uygulamaya veri kalıcılığı sağlamak için veri tabanı ve yapılandırma kütüklerini kullandığı görülmektedir.

<img src="/images/hibernate/mimari.png"></a> </br></br>
</br></br>
<b> -->Daha detaylı gösterimi</b>
</br></br>
<img src="/images/hibernate/alt_yapi.png"></a> </br>

   Bu mimari uygulamayı altta yatan JDBC/JTA/JNDI katmanlarından soyutlar ve detayları Hibernate’e bırakır.

<font color="red"> SessionFactory : </font>
SessionFactory derlenmiş basit bir veri tabanı adreslemelerinin tutulduğu alan olarak tanımlanabilir.

<font color="red"> Session : </font>
Uygulama ve kalıcı veriler arasında ki tek iş parçacıklı kısa süreli bir görüşmeyi temsil eder.

<font color="red"> Persistent objects and collections : </font>
İş methodları içerebilen kalıcı durumlu tek iş parçacıklı, kısa ömürlü nesnelerdir. Bu nesneler belli bir anda tek bir oturumla
(Session nesnesiyle) ilişkili olup oturum sonlandığında nesneler serbest kalır ve herhangi bir uygulama katmanı tarafından kullanıma
hazır hale gelirler.

<font color="red"> Transient Objects and Collections : </font>
Bir oturumla(Session nesnesiyle) ilişkilendirilmemiş kalıcı sınıf nesneleridir.

<font color="red"> Transaction : </font>
Uygulama tarafından işin atomik birimlerini belirtmek amacıyla kullanılan tek iş parçacıklı,kısa ömürlü nesnelerdir. Bir Session 
belli koşullarda birden çok transactiona yayılabilmektedir. Transactionlar uygulamayı JDBC, JTA ya da CORBA alt katmanlarından yalıtır.

<font color="red"> ConnectionProvider : </font>
JDBC bağlantılarının tutulur ve JDBC bağlantıları üretmektedir. Uygulamayı altta yatan Datasource ve DriverManager katmanlarından soyutlar.

<font color="red"> TransactionFactory : </font>
Transactionlar için bir fabrika işlevi görür.

###<a id="hb-yapılandırma"> 3- Yapılandırması</a>

  Bir sessionFactory nesnesi yaratabilmek için ilk önce uygulama yüklenirken eşleme(mapping) dosyalarının yerlerini
ayarlamak amacıyla Configuration sınıfının bir kopyasını oluşturmamız gerekmektedir.
  Hibernate’ te XML eşleme dosyaları <b>.hbm.xml</b> uzantılı olmak zorundadır ve bunlar her bir sınıf için hepsi bir
XML eşleme dosyası yerine ayrı ayrı oluşturulmalıdır.

<b>NOT : </b>
Her kalıcı sınıf için oluşturulan bu XML eşleme dosyası aynı dizine konulmalıdır.

###<a id="xml-tabanlı-ayarlar"> 4- Ayarlar Yapılırken XML Tabanlı Dosya Kullanmak</a>

<font color="blue">hibernate.cfg.xml :</font>

  <p>Veritabanı ile ilgili bilgiler bu XML dosyasına yazılır. Dolayısıyla kod içerisinde veritabanı işlemleri için herhangi
bir ayar yapmamıza gerek kalmaz.Tüm ayarlar bu XML dosyası kullanılarak yapılacaktır.
  Ayrıca kalıcı sınıfların eşleme dosyalarının bulundukları yerlerde bu XML dosyasına eklenir.</p>

###<a id="pojo"> 5- Kalıcı Sınıflar</a>

  Kalıcı sınıflar yapılacak işe ait varlıklara karşılık gelirler. Kalıcılık, verinin herhangi bir veri saklama
ortamında (veri tabanı, kütükler) saklanmasıyla sağlanır.

  Hibernate kalıcı sınıfların <font color="red">Plain Old Java Objects (POJO)</font> denilen programlama modeline
uymasını bekler.
  Kalıcı sınıflar "java bean" tarzında yazılmalıdır. Çünkü Hibernate verilerin Javabean tarzında yazılmış olduğunu varsayar. 
 <b>JavaBean</b> tarzı sınıf demek tüm nitelikleri private olan, belirleyici niteliği sıralı(serialized) olan, niteliklerine 
ulaşmak için get/set methodları tanımlayan ve boş bir yapıcısı bulunan sınıf demektir. Tüm kalıcı sınıfların public olan bir 
önbelirli yapılandırıcısının olması gerekir. Bu Hibernate’in <code>Constructor.newInstance()</code> methodunu kullanmasını sağlar.
