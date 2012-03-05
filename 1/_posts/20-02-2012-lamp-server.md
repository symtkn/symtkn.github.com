---
layout: post
title: Lamp Server Kurulumu
---
###
    Linux’ta yaptığımız web sitelerini yayınlamak için bildiğimiz üzere Apache+PHP+MySql üçlüsü kurulur. Bunları ayrı ayrı kurmak mümkünken Linux’ta hepsini tek bir satır komutla da yapabiliriz. Ubuntu’ da ve diğer bir çok Linux dağıtımlarında bu iş için LAMP (Linux, Apache, Mysql, Php) paketi geliştirilmiştir.

    İlk olarak LAMP Linux, Apache, Mysql, Php (Perl,Python) 'nin başharflerinden oluşan bir kısaltmadır. İçerisinde tüm modüllerin olduğu bir setup dosyasıdırda denilebilir. 

    7.04 sürümünden itibaren Ubuntu temel sistemi Taksel içermektedir.Lamp-server'ı ister taksel ile ister gerekli paketleri kurarak sistemimize yükleyebiliriz. Ben burada taksel kullanarak kurulumu anlatacağım. Terminal penceresini açalım:

<code>sudo apt-get install tasksel</code>
<code>sudo tasksel install lamp-server</code>

Vazgeçilmez web tabanlı MYSQL veritabanı yönetim aracı olan phpmyadmin'i kurmak içinde aşağıdaki kod işimizi görücektir.

<code>sudo apt-get install phpmyadmin</code>

Son olarak localhostumuza ait olan dizine erişim yetkimizi ayarlıyalım.

<code>sudo chmod 0777 /var/www/</code>

Lamp server kurulumunu kontrol etmek için /var/www/ (localhost klasörü) altına deneme.php adlı yeni bir belge açalım ve içerisine şunları yazalım:
<code><?php</code><br>
    <code>echo  "Hello world!";</code><br>
    <code>?></code>

Yazıp kaydettikten sonra web tarayıcınız da http://localhost/deneme.php yazın.Eğer sayfanız açılıyorsa LAMP server başarıyla kurulmuş demektir.

