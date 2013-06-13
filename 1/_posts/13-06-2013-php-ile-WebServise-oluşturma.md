---
layout: post
title: PHP İle Web Servisi Oluşturmak
---
###KONU BAŞLIKLARI

<li><a href="#web-service"> Web Servisi Nedir?</a></li><br>
<li><a href="#soap"> SOAP(Simple Object Access Protocol – Basit Nesne Erişim Protokolü)</a></li><br>
<li><a href="#wsdl"> WSDL(Web Service Description Language – Web Servisleri Tanımlama Dili)</a></li><br>
<li><a href="#nusoap"> NuSOAP Ne İşe Yarar?</a></li><br>
<li><a href="#sample"> Örnek Bir Uygulama</a></li><br>

###<a id="web-service"> Web Servisi Nedir? </a>
  Web servisler modern internet döneminin XML mesajlaşma tabanlı entegrasyon yöntemi ya da diğer bir deyişle api’leridir. 
Web servis ile internet üzerinde herhangi bir platformdaki herhangi bir dille yazılmış bir uygulama ile veri alışverişi
gerçekleştirebilriz. Örneğin bir siteniz var ve bu sitenizden kullanıcılarınız üyelik sistemiyle yararlanabiliyor. 
Bu sistemde kullanıcılarınıza SMS ile bilgi vermeye yarayan bir özellik aktif etmek istiyorsunuz. Ama bu servisi kontrol 
etmek elimizde değil; bu yüzden SMS servisini başka bir yerden alırız. Gerekli işlemleri kendi uygulamamızda gerçekleştirebilmemiz
için bir API(Application Programming Interface – Uygulama Geliştirme Arayüzü) sunar. İşte bu API’lerin iletişim yöntemlerinden
biride web servisleridir. Kısaca iki farklı uygulama arasında köprü görevi görmektedir.
<br>
  Farklı platformlarımız var ve bunların birbirleri ile anlaşması gerekir. İşte bu noktada SOAP devreye girer. Şöyle ki PHP ile
web servisi yazabilmek veya başka servislerle haberleşebilmek için dört ayrı kütüphane(protokol) mevcuttur. Bunlar OAuth, SCA,
SOAP, XML-RPC. Burada üzerinde duracağım kısım SOAP standartıdır.

###<a id="soap"> SOAP(Simple Object Access Protocol – Basit Nesne Erişim Protokolü) </a>
  SOAP, web üzerinden fonksiyonları kullanmak için geliştirilmiş bri sistemin XML tabanlı kurallar topluluğudur. SOAP kullanarak nesne transferi yapmak için, herhangi bir XML web servisi oluşturulur. SOAP ve HTML birbirini tamamlayan iki teknolojidir. Bilindiği üzre HTML “hypertext” transfer etmek amacıyla oluşturulmuş bir yapıdır; nesne transfer edemez, bu eksikliği SOAP kapatmaktadır.
<br><br>
Bir web servisinin genel yapısı :
<br>
<img src="/images/php_webService/runtime.gif"></a>
<br>
  <b>SOAP Server</b>, gelen SOAP isteklerini karşılayıp önceden belirtilmiş olan fonksiyon ya da metodlara yönlendiren bir dosyadır.
PHP Soap kütüphanesinde SOAPServer, SOAPClient, SOAPFault, SOAPHeader, SOAPParams, SOAPVar sınıfları bulunmaktadır. <br>
SoapServer sınıfının yöntemleri :<br>

<b>SoapServer:: addFunction</b> : Yazdığımız yöntemleri servise ekler. SOAP_FUNCTIONS_ALL ile bütün metotları ekleyebiliyoruz.<br>
<b>SoapServer:: __construct</b> : SoapServer Sınıfı kurucu yöntemi.<br>
<b>SoapServer:: getFunctions</b> : Tanımlı yöntemlerin listesini döndürür.<br>
<b>SoapServer:: handle</b> : Web Servisinin isteklere hazır halde bekletir.<br>
<b>SoapServer:: setClass</b> : addFunction yönteminin benzeridir.<br>
<br><br>
SoapClient sınıfının yöntemleri :<br>

<b>SoapClient::__call</b> : soap sunucusundan tanımlı bir metota çağrı yapar. aldığı iki değer vardır birincisi metot ismi ikincisi gönderikecek değerler.<br>
<b>SoapClient::__getFunctions</b> : Kullanılabilir metotların listesini<br>
<b>SoapClient::__getLastRequest</b> : Son isteklerin döndürür.<br>
<b>SoapClient::__getLastResponse</b> : Son gönderilen cevaplar.<br>


###<a id="wsdl"> WSDL(Web Service Description Language – Web Servisleri Tanımlama Dili)</a>

  WSDL ile web servisinin metodları ve adresleri belirtilir.
<ul type="circle"> 
<li>Web servisin adı</li>
<li>Yapılabilecek yordam çağrıları</li>
<li>Bu yordam çağrılarının alabileceği parametreler</li>
<li>Parametrelerin tipleri</li>
<li>Döndürülecek cevap ve biçimi</li>
<li>Hata zamanında döndürülecek mesaj -sonuç (Fault)</li>
<li>Web servis çağrılarının yapılacağı adresi (EndpointURI)</li>
</ul>
tanımlamayı sağlar. 

WSDL'in Temel Bileşenleri :
<br>
<textarea rows="16" cols="30"> 
&ltdefinitions&gt
     &lttypes&gt
     Türlerin tanımlaması
     &lt/types&gt
     &ltmessage&gt
     Mesajın açıklaması
     &lt/message&gt
     &ltportType&gt
     Bir portun tanımlanması
     &lt/portType&gt
     &ltbinding&gt
     definition of a binding
     &lt/binding&gt 
&lt/definitions&gt
</textarea>
<br>
 - Sunucu tarafında da istemci tarafında da aynı wsdl kullanılır. Çünkü wsdl’in temel amacı budur. Yani ortak bir yapı kurarak
servisler arası iletişimi sağlamak.
 - İstemci wsdl dosyasına bakarak hangi metodu nasıl , ne parametreler ile çağıracağını ve ne sonuç döneceğini bilir.
 - Sunucu ise hangi servisi çalıştıracağını ve ne sonuç döndüreceğini wsdl yardımı ile bilir.


###<a id="nusoap"> NuSOAP Ne İşe Yarar?</a>

  NuSOAP, PHP web servislerinde SOAP’ın hızlı bir şekilde geliştirilmesine olanak sağlayan class kütüphanesidir.  Basit object-oriented interface(nesne yönemli arayüz), service için WSDL dosyasını otomatik olarak yaratabilir ya a WSDL kullanmadan çalışabilir. PHP dosyaları içerisine (istemci ya da sunucu) import edilir . <br>
   <b>require_once(‘lib/nusoap.php’);</b><br>
<br>
  Yaygın olarak basit tipler kullanılır. NuSOAP kütüphanesi Complex  Types(kompleks tipler) ide destekler. Basit tipler xsd, kompleks türler için tns etiketi kullanılır.
Ardışıl complex ya da basit/ilkel(primitive) tipler PHP de array veya struct lar kullanılarak oluşturulurlar. Şöyleki,
<br>
<textarea rows="15" cols="75"> 
$server->wsdl->addComplexType
        (
        'UyeGetirSonuc',  //Classın Adı
        'complexType', 
        'struct', 
        'all', 
        '',        // İçinde 2. bir sınıf çağırılacaksa adı buraya yazılır.
        array(  
              'Success'=> array('name'=>'Success','type' => 'xsd:boolean'),
              'Id' => array('name' => 'Id', 'type' => 'xsd:integer'),
              'Adi' => array('name' => 'Adi', 'type' => 'xsd:string'),
              'Soyadi'=> array('name' => 'Soyadi', 'type' => 'xsd:string'),
              'Uyeler'=> array('name' => 'Uyeler', 'type' => 'tns:UyeGetirSonuclar[]')
        )
);  
</textarea>

<br><br>
###<a id="sample"> Örnek Bir Uygulama</a>
NuSOAP yapısını kullanarak bir örnek üzerinde inceleme yaparsak;

Öncelikle NuSOAP'a ait php dosyasını <a href="https://www.dropbox.com/s/p77xw1bxottyadg/nusoap.php" target="_blank">buradan </a>   indirebilirsiniz.

Bu projede kullanılan dizinler :
- /lotus/client.php (SOAP istemci dosyası)
- /lotus/helloworld.php (SOAP sunucu dosyası)
- /lib/nusoap.php (NuSOAP kütüphanesi)<br>

<b>***</b> Kullanılan dizin yapısını kendi projenize göre değiştirebilirsiniz. Eğer bir değişiklik söz konusu ise burada dikkat etmeniz gereken SOAP istemci dosyasının dizin yapısını, SOAP server dosyası içerisinde de enpoint güncellemeniz gerekmektedir.<br>
SOAP server dosyasının içeriği :
<br>
<textarea rows="15" cols="60"> 
&lt?php
require_once('/lib/nusoap.php');
// Server(sunucu) örneği yaratılır
$server = new nusoap_server;
// Kullanılacak method register(kayıt) edilir
$server->register('hello');
// Bir PHP fonksiyonu gibi method tanımlanır
function hello($name) {
    return 'Hello, ' . $name;
}
// Bilgi alışverişini sağlamak için bu kod kullanılır
$HTTP_RAW_POST_DATA = isset($HTTP_RAW_POST_DATA) ? $HTTP_RAW_POST_DATA : '';
$server->service($HTTP_RAW_POST_DATA);
?&gt
</textarea>
<br>
Burada <b>$server</b>  SOAP server işlevselliği için özel bir değişkendir.<br>
<b>$server->register('myFunction');</b> satırı servis fonksiyonunu tanımlar.<br>

Bu satırlarda da servis fonksiyonu implement edilir.<br>
<b>
function hello($parameters) {
. . .
    return $result;
}</b>
SOAP girdileri doğrudan fonksiyon parametreleri olarak alır.<br>
SOAP otomatik bir değer döner.<br>

<b>$HTTP_RAW_POST_DATA</b> XML SOAP isteklerini içermelidir.<br>
<b>$server->service</b> XML analizi yapar. Fonksiyon çağrıları yapar ve XML istekleri yaratır.<br>

<u>SOAP client dosyası :</u>
<br>
<textarea rows="10" cols="80"> 
&lt?php 
require_once('/lib/nusoap.php');
// client örneği yaratılır
$client = new nusoap_client('http://localhost/lotus/helloworld.php', false); // false : WSDL gereksiz
// SOAP methodu çağrılır 
$result = $client->call('hello', array('name' => 'symtkn'));
// sonuç gösterilir
print_r($result);
?&gt
</textarea>
<br>
<b>$client</b> SOAP client’ın işlevselliği yönünden özel bir değişkendir.<br>
<b>$client = new nusoap_client('http://localhost/lotus/helloworld.php', false);</b><br>
İlk parametre bir web servis endpoint URL dir.<br>
İkinci parametre false, WSDL’e ihtiyaç olmadığını belirtir.<br>
<b>$result = $client->call('hello', array('name' => 'symtkn'));</b><br>

İlk parametre çağırılacak fonksiyonun ismi, ikinci parametre SOAP girdilerinin listesini tutan bir array. <br>
Bu array “parametre ismi => parametre değeri” şeklinde key-value çiftleri halinde bulunur.<br>

Localhost’unuzda  client.php dosyası ile sunucuya http isteği (http://localhost/lotus/client.php) gönderirsek sunucu bize şöyle bir çıktı ile isteğimizi yanıtlar :
<br><code>
Hello, symtkn
</code><br>

Bu örnek projeyi yaparken karşılaştığım birkaç hata var; bunlarla eğer sizde karşılaşırsanız aşağıdaki adımları izleyebilirsiniz.
<b>Projeyi çalıştırma aşamasında karşılaşabileceğiniz hatalar  :</b>
<br>
1-) Cannot load php_soap.dll<br>
<b>Çözüm :</b>
php.ini dosyasında extension=php_soap.dll satırını başındaki noktalı virgülü kaldırın ve tüm servisleri restart yapın.<br>
Ve “PHP extentions” kısmından php_soap’, SOAP uzantısının (extention) etkinleştirilmiş olması gerekir.

2-) Warning: require_once(lib/nusoap.php) [function.require-once]: failed to open stream: No such file or directory in C:\wamp\www\lotus\client.php on line 4

Fatal error: require_once() [function.require]: Failed opening required 'lib/nusoap.php' (include_path='C:\wamp\www\lotus \include/..;.;C:\php5\pear') in C:\wamp\www\lotus\client.php on line 4<br>

<b>Çözüm :</b>
Php.ini dosyasında   include_path = ".;c:\wamp\www\" satırının başındaki noktalı virgülü kaldırarak restart yapın. Eğer eşitliğin sağ tarafı istenilen dizin yapısına uymuyorsa düzenleme yapabilirsiniz. Benim include edeceğim dosyalar www dizininin altında yer aldığı için bu yolu(path) yazdım.


