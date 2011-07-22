---
layout: post
title: VirtualBox İle OS Kurulumu
---
####KONU BAŞLIKLARI

<li><a href="virtual-kurulum"> Ubuntu Üzerinde VirtualBox-OSE Kurulumu </a><li><br>
<li><a href="virtualbox-kullanım"> VirtualBox-OSE Kullanımı </a><li><br>
<br>

  VirtualBox bilgisayarınızdaki işletim sistemi üzerinde sanal olarak bir bilgisayar daha oluşturup farklı işletim sistemlerini kullanmanızı sağlar.

###<a id="virtual-kurulum"> Ubuntu Üzerinde VirtualBox Kurulumu </a>
 
 <u>Ubuntu Yazılım Merkezinden</u>  yazılım edin kısmının arama motoruna virtualbox yazarak aratın.Ve kur diyerek kurulumu başalatın.Kurulmasını bekleyin,kurulum bittikten sonra <u>donatılar</u> menüsünde göreceksiniz.Virtualbox OSE diye...
 Artık indirdiğiniz iso dosyalarını, elinizdeki linux sürümünü makinanıza kurabilirsiniz.Rahat bir şekilde tüm işlemleri gerçekleştirebilirsiniz nasıl olsa sanal pc çöksede yeniden yapabilirsiniz. :)


###<a id="virtualbox-kullanım"> VirtualBox-OSE kullanımı </a>

Uygulamalar > Donatılar > VirtualBox OSE yolunu izleyerek sanal makinamızı açarız.Karşımıza aşağıda birinci resimdeki gibi bir arayüz çıkıcak.Bu ekranın, sol tarafında kurulu olan sanal OS'lerinizi görürsünüz.Şu an için boş çünkü şimdilik hiç bir işletim sistemi kurulu değil.Artık makinamızı çalıştırmaya başlıyalım.

<img src="http://github.com/symtkn/sym.github.com/blob/master/images/sanalmakina/sanal.png?raw=true"/>
<code>yeni</code> kısmını tıklayarak yeni bir sanal makina oluşturuyoruz.

<img src="http://github.com/symtkn/sym.github.com/blob/master/images/sanalmakina/sanal1.png?raw=true"/>

Sanal makinamıza bir isim veriyoruz ve işletim sistemimizi seçiyoruz.Ben burada sanal makinamın adını "new" yaptım ve elimde ubuntu iso dosyası olduğundan işletim sistemi açılır menüsünden Linux'u,versiyon açılır menüsünden ise Ubuntu'yu seçelim ve ileri diyelim.

<img src="http://github.com/symtkn/sym.github.com/blob/master/images/sanalmakina/sanal2.png?raw=true"/>

İşletim sistemimiz için ne kadar bellek(RAM) ayıracağımız belirliyoruz.Benim 2GB RAM'im var o yüzden sanal Ubuntu için 512MB'lık RAM ayırdım.Ayıracağınız RAM miktarı toplam RAM kapasitesine bağlıdır.İleri diyerek devam edin.

<ul type=square><li><b>NOT:</b>Virtualbox için ayırmış olduğunuz RAM,bilgisayarınızın RAM'inden ayrılıp Virtualbox için kullanılacaktır.Örneğin ben her sanal Ubuntu'yu açtığımda 2GB RAM den 512MB'ını normal işletim sisteminde kullanamaz hale geliyorum.Sanal OS(operating system) için ayırdığınız RAM miktarı sadece Vİrtualbox çalıştığı zaman geçerli. </li></ul> 

<img src="http://github.com/symtkn/sym.github.com/blob/master/images/sanalmakina/sanal3.png?raw=true"/>

Sabit diskimizin depolama tipini seçiyoruz.Eğer sadece deneyip kapatıcam diyorsanız dinamik olarak genişleyen kalıp sanal OS için uygundur.Yani yapacağımız eklentiler veya sonradan kuracağımız programlara uyumluluk olması açısındanda idealdir.

<img src="http://github.com/symtkn/sym.github.com/blob/master/images/sanalmakina/sanal4.png?raw=true"/>

Dizin yolunu değiştirmek istemezseniz ön tanımlı olarak /home/kullanıcıadı/VirtualBoxVMs/sanal makinamıza vermiş olduğumuz ad olarak komum adı oluşur.Ben sanal sabit disk için 16GB'lık bir alan ayırıyorum.Bu alan sizin bilgisayarınızın HDD kapasitesine veya keyfinize göre değişebilir.Ancak bu boyut en az 8GB olmalıdır.

<img src="http://github.com/symtkn/sym.github.com/blob/master/images/sanalmakina/sanal5.png?raw=true"/>

İleri dediğimizde karşımıza kurulumun özeti çıkar.Bitir diyerek ekranın sol tarafında sanal OS'mizi görebiliriz. 

<img src="http://github.com/symtkn/sym.github.com/blob/master/images/sanalmakina/sanal6.png?raw=true"/>

Artık Ubuntuyu kurabiliriz.Bunu iki şekilde yapabiliriz.İnternetten indirip CD'ye yazdırdığımız.iso dosyasını kullanabiliriz ya da hiç CD ye yazdırmadan direk bilgisyarımızda kayıtlı olan .iso dosyasını kullanarak yükleme yapabiliriz.Ben CD'ye yazdırmadan masaüstüme kayıt ettiğim Ubuntu 10.iso dosyasınından kuracağım.

<img src="http://github.com/symtkn/sym.github.com/blob/master/images/sanalmakina/sanal7.png?raw=true"/>

Asıl önemli noktaya geldik.Ortam tipi CD/DVD ROM sürüsü olarak kalsın.Fakat <u>Ortam kaynağını</u> masaüstümdeki .iso dosyası olarak gösteririz.Ve bundan sonra karşımıza çıkcak olan pencereler de gerekli dil ayarını,klavye türünü kendi isteğimize göre belirleyerek Ubuntu'yu kurmaya başlıyoruz.Zaten geri kalan işlemler bildiğimiz klasik Ubuntu kurulum aşamalarıdır.

<img src="http://github.com/symtkn/sym.github.com/blob/master/images/sanalmakina/sanal8.png?raw=input"/>
 
Görüldüğü gibi kendi masaüstümüzde VirtualBox ile Ubuntu var artık...

<img src="http://github.com/symtkn/sym.github.com/blob/master/images/sanalmakina/sanal9.png?raw=true"/>










  


