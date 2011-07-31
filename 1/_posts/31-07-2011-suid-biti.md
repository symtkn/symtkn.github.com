---
layout: post
title: Suid-Sgid Bitleri
---
####KONU ANALİZİ
<li> <a href="#suid-bit"> Suid Biti </a> </li>
<li> <a href="#sgid-bit"> Sgid Biti </a> </li>
<li> <a href="#suid-sgid-degistirme"> Suid Ve Sgid Bitlerinin Değiştirilmesi </a> </li>

Oturum açtığımızda yeni bir kabuk süreci başlar. Her yeni kabuk süreci(bash) bizim kullanıcı bilgimizle çalışır. Böylece bizim sahip olduğumuz dosya ve dizinlere ulaşılır. Kullanıcı bilgilerini verdiğimiz programlar,dosya sisteminde bizim iznimizin olmadığı herhangi bir neseneye ulaşamayacaktır.<br>

Örneğin; normal kullanıcılar <u>passwd</u> dosyasına yazma hakkına sahip değildirler. 
<code> ls -l /etc/passwd</code><br>
<code>-rw-r--r-- 1 root root 1673 2010-12-09 14:43 /etc/passwd</code>

Oysa ki normal kullanıcılarında dolaylı olarak bu dosya üzerinde değişiklik yapmaya ihtiyaçları olabilir.Mesela şifrelerini değiştirecekleri zaman...

Linux izin modelinde "suid" ve "sgid" isimli iki özel bit vardır.

###<a id="suid-bit"> Suid Biti </a>

Eğer çalıştırılabilir bir dosyanın suid biti ayarlanmışsa o dosya o anda çalıştıran kullanıcı değilde ,asıl sahibi olan kuyllanıcının adıyla çalışıyormuş gibi olur.
Örneğin: passwd çalıştırılabilir dosyasına baktığımızda;

<code> ls -l /usr/bin/passwd</code><br>
<code>-rwsr-xr-x 1 root root 42824 2011-02-21 02:18 /usr/bin/passwd</code>

Burada dosya sahibinin izinlerini ifade eden üçlüde "x" yerine "s" var.
Bu "s" harfi; suid ve çalıştırılabilirlik bitlerinin ayarlandığını belirtir.Böylece <u>passwd komutu</u> çalıştığında, o anda çalıştıran kullanıcı değilde root kullanıcısı tarafından  çalıştırılıyormuş gibi olacaktır.
Ve passwd komutu root haklarıyla çalışınca, /etc/shadow dosyasınıda bir problem olmadan düzenleyebilecektir.Tabiki geçici olarak. =)

<b>EK BİLGİ:</b> 
/etc/passwd 'de kullanıcı hesapları vardır.<br>
/etc/shadow 'da şifreler saklıdır.

###<a id="sgid-bit"> Sgid Biti </a>

Programların o anda çalışan kullanıcıya göre değilde programın üzerindeki <u>grup</u> haklarına göre çalışmasına dayanır.

ls -l listelemesinde suid ve sgid bitleri "x" harfinin (yani çalıştırma/erişim yetkisinin) olduğu yerdedir.
Eğer hem "x" hemde suid/sgid bitleri aktifse listede "s" (küçük harf) olacaktır."x" biti aktif değilse "S" (büyük harf) olarak görülür.

###<a id="suid-sgid-degistirme"> Suid Ve Sgid Bitlerinin Değiştirilmesi </a>
u : user
g : group
+ : yetki verme
- : yetkiyi kaldırma

<code>chmod u+s /usr/bin/program_adi</code> 

<code>chmod g-s /home/grup_adi</code>

Buradaki +/- kısımlarını yapmak istediğiniz işleme göre değiştirebilirsiniz.






