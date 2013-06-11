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
<li>Programcı için bir çok işlemi basitleştirir.
<li>Kullanımını kolaylaştırır.
<li>Açık kaynak kodludur.
<li>Mimarisi Rod Johson’dır.
<li>Nesne tabanlıdır. Yani POJO tabanlıdır.
<li>Kullanım özgürlüğü tanır.(Parçalar birbirinden bağımsız şekilde kullanılabilir. Örneğin: Modüler yapı)
</ul>

<b><u>Spring Framework Modüler Yapısı</u></b>
<img src="/images/spring/branch.png"></a>

<font color="red">Spring Core:</font>
Spring core paketi, Spring’in temelini olusturur. Bağlaşım kesme gibi temel fonksiyonlar Spring Core içinde implemente edilmiştir.
<font color="red">Spring AOP:</font>
Spring’in AOP özellikleri direk kullanılmasada, deklaratif transaksiyon ve güvenlik uygulamalarında Spring AOP , Spring Core tarafından dolaylı olarak kullanılır.
<font color="red">Spring MVC:</font>
Spring MVC (Model-View-Controller) Spring baz alınarak web tabanlı programlar oluşturulabilir. Spring MVC bir web frameworküdür.
<font color="red">Spring Context:</font>
ApplicationContext ve WebApplicationContext gibi sınıflar bu modülde implemente edilmiştir. XML dosyalarından bulunan Spring bean tanımlamalarını okumak ve Spring bean nesnelerini oluşturmak için kullanılırlar.
<font color="red">Spring DAO (Database Access Object):</font>
Bilgi bankaları üzerinde işlem yapmak için kullanılan JDBC teknolojisini kullanımda daha basit hale getiren sınıflar bu modül içinde yeralır.
<font color="red">Spring ORM (Object Relational Mapping):</font>
Bu modül Hibernate, JDO, TopLink ve IBatis gibi popüler ORM frameworkler ile entegrasyonu sağlamaktır.

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
<ol>
<li><b>Spring IoC çalışma şekli :</b></li>
<img src="/images/spring/Ioc_scheme.png"></a>

<li><b>Metadata Konfigürasyon Seçenekleri :</b>
	<lo>
	<li>XML kullanımı (Sınıf dosyaları değişmez.)</li>
	<li>Java kullanımı (Sınıf dosyaları değişmez fakat ek konfigürasyon dosyaları gerekir.)</li>
	<li>Anotasyonlar (Sınıf dosyaları değişmez.)</li>
	</lo>
</li>
</ol>

###<a id="xml_file"> Spring XML Dosyasını Tanıyalım</a>
  -Birden fazla bean kullanılabilir. Aynı XML dosyasında aynı bean id birden fazla kullanılamaz. 
   Tüm beanler default olarak <b>Singleton</b> olarak oluşturulur.
  -<u>Spring IoC container nesneleri oluştururken 3 teknik kullanır.</u>
     <ol>
     <li>Constructor kullanarak</li>
     <li>Static Factory metodu</li>
     <li>Instance Factory</li>
     </ol>
  -<u>Spring IoC Dependency Injection Teknikleri:</u>
     <ol>
     <li>Constructor kullanarak</li>
     <li>Setter metodu yardımıyla</li>
     </ol>

Genel bir örnek üzerinde bu yapıları incelersek;

<code>
<bean id="company" class="examples.Company">
    <constructor-arg name="customer" ref= "myCustomer"/><
    <constructor-arg name="since" value="1992"/>
</bean>

<bean id="myCustomer" class="examples.Customer">
    <property name="name" value="Symtkn"/>
    <property name="years" value="20"/>
    <proparty name="address" value="myAddress"/>
</bean>
<bean id="myAddress" class="examples.Address"/>
</code> 
<br>
Kodu açıklarsak; İlk olarak "constructor" kullanarak, "Company" adlı classdan id'si "company" olan bir Ioc nesnesi oluşturduk. Ve bu sınıfın yapıcı metoduna(constructor) parametre olarak başka bir bean id'yi(id="myCustomer" olan sınıfı) referans verdik. İkinci parametre olarakta parametre ismi "since" olan argümana value olarak belirtilen değeri atadık.
 "myCustomer" id'sine sahip "Customer" sınıfının sahip olduğu setter metodları kullanılarak sınıf içerisindeki instance variables değerini <u><property><u> tagı ile belirtmiş olduk."Address" sınıfı cinsindeki "address" değişkenine bean id'si "myAddress" olan nesneyi injection ettik.
 "Address" sınıfı bir yapıcı metoda sahip fakat bu seferen parametre almamaktadır. Bu yüzden constructor yöntemi kullanılarak nesnesini oluşturmamız yeterli oldu.
Gerekli class kodları aşağıdaki şekilde yaratılabilir.
<br><br>
<code>
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
</code>
<br>
###<a id="data_type"> Değişkenleri Data Tiplerine Bağlama</a>
   Temel tipler için otomatik değer çevirme mevcuttur.
<b>P-namespace :</b>
    Daha kısa bir Spring dosyası elde etmemizi sağlar.
    p:degiskenAdi= "value"
<b>C-namespace :</b>
    Constructor içindir. P-namespace ile aynı şekilde kullanılır.
###<a id="collections"> Java Collections Kullanımı</a>
<list>,  <map>, <set>  içerisinde List, Set, Map, Properties data tipleri kullanılabilir.
<b>List :</b>
<img src="/images/spring/list_collection.png"></a>
<b>Map :</b>
<img src="/images/spring/map_collection.png"></a>
<b>Set :</b>
<img src="/images/spring/set_collection.png"></a>
<font color="red">Lazy kullanımı :</font>
Metadata bilgisinde <b>‘lazy-init=true’</b> ifadesi bulunan bean ler program içerisinde ne zaman gerekli olursa o zaman nesnesi yaratılır. 
<font color="red">Scope :</font>
Bean lerin kapsam, faaliyet ve kullanım alanlarını belirtir.
<u>Singleton Scope:</u> Bean nesne sadece bir kere oluşturulur ve her sorgulamada bu nesne kullanılır.
<u>Prototype Scope:</u> Bean nesnesi her sorgulamada oluşturulur ve aynı nesne kullanılmaz.

###<a id="web_scope"> Web Scopes</a>
<ol>Temel 3 web scopes vardır.
<li>Request</li>
<li>Session</li>
<li>Global Session</li>

***<b>‘web.xml’</b> dosyası içerisinde, kullandığımız web servlet container sürümüne göre değişiklikler yapmalıyız.
Örneğin Servlet 2.4 ve daha yeni web container için:

<code>
<web-app>
  <listener>
    <listener-class>
      org.springframework.context.request.RequestContextListener
    </listener-class>
  </listener>
</web-app>
</code>
<br>
###<a id="annotation"> Temel Anotasyonlar</a>

<b>@Configuration :</b>
    Spring, sınıf ve içindeki tüm metotları container olarak görür.
<b>@Bean :</b>
    Her bir metodun bean olarak gözükmesini sağlar.
<b>@Autowired :</b>
    Gerekli olan bean i otomatik olarak bulur.
<b>@Resource :</b>
    Autowired anotasyonu ile aynıdır. Ek olarak kullanılmasını istediğimiz bean ismini belirtebiliriz.
<b>@ImportResource :</b>
    Xml dosyası ile configuration dosyasını birleştirir.
<b>@Value :</b>
    Properties dosyası içerisindeki verileri otomatik olarak almamızı sağlar.
Örneğin: @Value("${variableName}")

