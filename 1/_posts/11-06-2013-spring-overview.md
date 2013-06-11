---
layout: post
title: Spring Framework
---
###KONU BAŞLIKLARI

<li><a href="#spring_explain"> Spring Framework Nedir?</a></li><br>
<li><a href="#_container"> Inversion of Control (IoC)</a></li><br>
<li><a href="#di"> Dependency Injection (DI)</a></li><br>
<li><a href="#aop"> Aspect Oriented Programming (AOP)</a></li><br>
<li><a href="#reasons"> Neden Spring Framework?</a></li><br>
<li><a href="#xml_konfigurasyon"> XML Konfigürasyon Kullanımı</a></li><br>
<li><a href="#xml_file"> Spring XML Dosyasını Tanıyalım</a></li><br>
<li><a href="#data_type"> Değişkenleri Data Tiplerine Bağlama</a></li><br>
<li><a href="#collections"> Java Collections Kullanımı</a></li><br>
<li><a href="#web_scope"> Web Scopes</a></li><br>
<li><a href="#annotation"> Temel Anotasyonlar</a></li><br>

###<a id="spring_explain"> Spring Framework Nedir? </a>

  Spring, J2EE uygulamaları geliştirmede kullanılan uygulama çatılarından (application framework) biridir.

<b>Amaç:</b> Ağır olan uygulama geliştirme yükünü hafifletmektir.
<ul>
<li>Programcı için bir çok işlemi basitleştirir.</li>
<li>Kullanımını kolaylaştırır.</li>
<li>Açık kaynak kodludur.</li>
<li>Mimarisi Rod Johson’dır.</li>
<li>Nesne tabanlıdır. Yani POJO tabanlıdır.</li>
<li>Kullanım özgürlüğü tanır.(Parçalar birbirinden bağımsız şekilde kullanılabilir. Örneğin: Modüler yapı)</li>
</ul>

<b>Spring Framework Modüler Yapısı</b>
<img src="/images/spring/branch.png"></a>
<br><br>
<font color="red">Spring Core:</font>
Spring core paketi, Spring’in temelini olusturur. Bağlaşım kesme gibi temel fonksiyonlar Spring Core içinde implemente edilmiştir.<br>
<font color="red">Spring AOP:</font>
Spring’in AOP özellikleri direk kullanılmasada, deklaratif transaksiyon ve güvenlik uygulamalarında Spring AOP , Spring Core tarafından dolaylı olarak kullanılır.<br>
<font color="red">Spring MVC:</font>
Spring MVC (Model-View-Controller) Spring baz alınarak web tabanlı programlar oluşturulabilir. Spring MVC bir web frameworküdür.<br>
<font color="red">Spring Context:</font>
ApplicationContext ve WebApplicationContext gibi sınıflar bu modülde implemente edilmiştir. XML dosyalarından bulunan Spring bean tanımlamalarını okumak ve Spring bean nesnelerini oluşturmak için kullanılırlar.<br>
<font color="red">Spring DAO (Database Access Object):</font>
Bilgi bankaları üzerinde işlem yapmak için kullanılan JDBC teknolojisini kullanımda daha basit hale getiren sınıflar bu modül içinde yeralır.<br>
<font color="red">Spring ORM (Object Relational Mapping):</font>
Bu modül Hibernate, JDO, TopLink ve IBatis gibi popüler ORM frameworkler ile entegrasyonu sağlamaktır.<br>

###<a id="ioc_container"> Inversion of Control (IoC)</a>

   Kontrolün tersine çevrilmesi manasına gelir.
   IoC için güvenli bir container gerekir.(org.springframework.beans.factory.BeanFactory )
   Spring IoC container sayesinde nesnelerin hayat döngüsü yönetimi, bağımlılıkların yönetimi, konfigürasyonu (bir bütün halinde çalışma),
tasarım kalıplarının kullanımı sağlar.

###<a id="di"> Dependency Injection (DI)</a>
 Bağımlılıkları ortadan kaldırmak şeklinde ifade edilebilir.
 Nesneler arası bağlar XML konfigürasyon dosyaları üzerinden otomatik gerçekleştirilir.
Örneğin: ClassA sınıfı ClassB tipinde bir değişkene sahip olsun. Bu bağımlılık Spring tarafından ClassA dan nesne oluşturulurken göz önünde bulundurulur. Spring otomatik olarak ClassB sınıfından nesne oluşturarak ClassA sınıfından oluşturduğu nesneye enjekte eder.

 Bağımlılık tanımları kod bölümünden çıkarılarak IoC prensibini kullanan container’a sunulur.
 Uygulamayı tekrardan derlemeden değişiklikler ele alınabilir.
 Bileşenler çalışma anında elde edilerek, bileşenler arası ilişkiler dinamik bir yapı kazanır.

###<a id="aop"> Aspect Oriented Programming (AOP)</a>
  Kesim yönelimli programlama olarak türkçeye çevirebiliriz.
<b>Amaç: </b>Uygulamalara modülerlik kazandırmak.

Program çerçevesinde yer almak zorunda olmayan bazı metot (transaction, logging vb.) ve modülleri bir yerde toplayarak programdan bağımsız bir yerde implemente eder.

###<a id="reasons"> Neden Spring Framework?</a>
<ul type="circle"> 
<li>Kendini ispatlamış; dünya çapında milyonlarca kullanıcısı vardır.</li>
<li>IoC prensibini kullanıyor ve bu sayede çok güçlü bir container haline geldi.</li>
<li>Kolay test edilebilir kod verir. (Sebep, nesne tabanlı olmasıdır.)</li>
<li>Gereksiz Exception sınıflarını gizler. Daha sade uygulama ortamı yaratılır.</li>
<li>Diğer API ve frameworkler için işimizi kolaylaştıracak bir çok araca sahiptir.</li>
<li>En önemli sebep AOP entegrasyonu desteklemesidir.</li>
</ul>

###<a id="xml_konfigurasyon"> XML Konfigürasyon Kullanımı</a>
IoC container’ a bir şeyler yaptırmak için ‘Metadata Konfigürasyon’ u gerekir.
<ul>
<li><b>Spring IoC çalışma şekli :</b></li>
<img src="/images/spring/Ioc_scheme.png"></a>

<li><b>Metadata Konfigürasyon Seçenekleri :</b></li>
	<lu>
	<li>XML kullanımı (Sınıf dosyaları değişmez.)</li>
	<li>Java kullanımı (Sınıf dosyaları değişmez fakat ek konfigürasyon dosyaları gerekir.)</li>
	<li>Anotasyonlar (Sınıf dosyaları değişmez.)</li>
	</lu>
</ul>

###<a id="xml_file"> Spring XML Dosyasını Tanıyalım</a>
  -Birden fazla bean kullanılabilir. Aynı XML dosyasında aynı bean id birden fazla kullanılamaz. 
   Tüm beanler default olarak <b>Singleton</b> olarak oluşturulur.<br><br>
  -<u>Spring IoC container nesneleri oluştururken 3 teknik kullanır.</u>
     <ol>
     <li>Constructor kullanarak</li>
     <li>Static Factory metodu</li>
     <li>Instance Factory</li>
     </ol><br>
  -<u>Spring IoC Dependency Injection Teknikleri:</u>
     <ol>
     <li>Constructor kullanarak</li>
     <li>Setter metodu yardımıyla</li>
     </ol>

Genel bir örnek üzerinde bu yapıları incelersek;

<textarea>
&ltbean id="company" class="examples.Company"&gt
    &ltconstructor-arg name="customer" ref= "myCustomer"/&gt
    &ltconstructor-arg name="since" value="1992"/&gt
&lt/bean&gt

&ltbean id="myCustomer" class="examples.Customer"&gt
    &ltproperty name="name" value="Symtkn"/&gt
    &ltproperty name="years" value="20"/&gt
    &ltproparty name="address" value="myAddress"/&gt
&lt/bean&gt
&ltbean id="myAddress" class="examples.Address"/&gt
</textarea>

<br>
Kodu açıklarsak; İlk olarak "constructor" kullanarak, "Company" adlı classdan id'si "company" olan bir Ioc nesnesi oluşturduk. Ve bu sınıfın yapıcı metoduna(constructor) parametre olarak başka bir bean id'yi(id="myCustomer" olan sınıfı) referans verdik. İkinci parametre olarakta parametre ismi "since" olan argümana value olarak belirtilen değeri atadık.<br>
 "myCustomer" id'sine sahip "Customer" sınıfının sahip olduğu setter metodları kullanılarak sınıf içerisindeki instance variables değerini &ltproperty&gt tagı ile belirtmiş olduk."Address" sınıfı cinsindeki "address" değişkenine bean id'si "myAddress" olan nesneyi injection ettik.<br>
 "Address" sınıfı bir yapıcı metoda sahip fakat bu seferen parametre almamaktadır. Bu yüzden constructor yöntemi kullanılarak nesnesini oluşturmamız yeterli oldu.
Gerekli class kodları aşağıdaki şekilde yaratılabilir.
<br><br>

<textarea>
package examples;

public class Customer {

    private String name;
    private String years;
    private Address address;
    
    public void setName(String ValueName) {
	this.name =  ValueName;
    }
    public void setYears(int ValYears) {
         this.years =  ValYears;
    }
    public void setAddress(Address ValAddress) {
         this.address = ValAddress;
    }
    public Customer() {
   	System.out.println("Customer");
    }
}

package examples;

public class Company {

    private Customer customer;
    private int since;
  
    public Company(Customer ValCustomer, int VaSince) {
        System.out.println("Company constructor 2 arguments");
	this.customer = ValCustomer;
	this.since = ValSince;
    }
    public Company() {
        System.out.println("Company default constructor");
    }
}

package examples;

public class Address {

    public Address() {
	System.out.println("Address");
    }
}
</textarea>

<br>
<br>
###<a id="data_type"> Değişkenleri Data Tiplerine Bağlama</a>
   Temel tipler için otomatik değer çevirme mevcuttur.<br>
<b>P-namespace :</b>
    Daha kısa bir Spring dosyası elde etmemizi sağlar.
    p:degiskenAdi= "value"<br>
<b>C-namespace :</b>
    Constructor içindir. P-namespace ile aynı şekilde kullanılır.

###<a id="collections"> Java Collections Kullanımı</a>
&ltlist&gt,  &ltmap&gt, &ltset&gt tagları içerisinde List, Set, Map, Properties data tipleri kullanılabilir.
<b>List :</b><br>
<img src="/images/spring/list_collection.png"></a>
<br>
<b>Map :</b><br>
<img src="/images/spring/map_collection.png"></a>
<br>
<b>Set :</b><br>
<img src="/images/spring/set_collection.png"></a>
<br><br>
<font color="red">Lazy kullanımı :</font>
Metadata bilgisinde <b>‘lazy-init=true’</b> ifadesi bulunan bean ler program içerisinde ne zaman gerekli olursa o zaman nesnesi yaratılır. 
<br>
<font color="red">Scope :</font>
Bean lerin kapsam, faaliyet ve kullanım alanlarını belirtir.<br>
<u>Singleton Scope:</u> Bean nesne sadece bir kere oluşturulur ve her sorgulamada bu nesne kullanılır.<br>
<u>Prototype Scope:</u> Bean nesnesi her sorgulamada oluşturulur ve aynı nesne kullanılmaz.

###<a id="web_scope"> Web Scopes</a>
<ol>Temel 3 web scopes vardır.
<li>Request</li>
<li>Session</li>
<li>Global Session</li>
</ol>
*** <b>‘web.xml’</b> dosyası içerisinde, kullandığımız web servlet container sürümüne göre değişiklikler yapmalıyız.
Örneğin Servlet 2.4 ve daha yeni web container için:

<code>
&ltweb-app&gt
  &ltlistener&gt
    &ltlistener-class&gt
      org.springframework.context.request.RequestContextListener
    &lt/listener-class&gt
  &lt/listener&gt
&lt/web-app&gt
</code>
<br>
###<a id="annotation"> Temel Anotasyonlar</a>

<b>@Configuration :</b>
    Spring, sınıf ve içindeki tüm metotları container olarak görür.<br>
<b>@Bean :</b>
    Her bir metodun bean olarak gözükmesini sağlar.<br>
<b>@Autowired :</b>
    Gerekli olan bean i otomatik olarak bulur.<br>
<b>@Resource :</b>
    Autowired anotasyonu ile aynıdır. Ek olarak kullanılmasını istediğimiz bean ismini belirtebiliriz.<br>
<b>@ImportResource :</b>
    Xml dosyası ile configuration dosyasını birleştirir.<br>
<b>@Value :</b>
    Properties dosyası içerisindeki verileri otomatik olarak almamızı sağlar.<br>
Örneğin: @Value("${variableName}")

