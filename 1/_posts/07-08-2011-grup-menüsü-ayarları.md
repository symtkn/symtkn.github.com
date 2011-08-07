---
layout: post
title: Grup Menüsü Ayarları
---
Eğer bilgisyarınızda birden fazla işletim sistemi yüklü ise ve sizde devamlı olarak birini kullanıyorsanız, eminim her defasında grup menüsünden onu seçmekten sıkılmışsınızdır. Şimdi bunu ortadan kaldırmanın yollarına bakalım.

Öncelikle bize gereken ilk şey kaçıncı sıradaki şeçeneği default olarak belirleyeceğimizdir. Bunun için bilgisayar açılırken önümüze gelecek olan grup menüsünden istediğimiz işletim sisteminin kaçıncı sırada olduğunu tespit etmeliyiz.<br>

<b>NOT:</b>Eğer yeni bir Ubuntu sürümü yüklemiş iseniz Windows seçeneği grub menüsünde büyük ihtimalle 5.sırada olur.
<br><br>

<b>Default Olarak Menüdeki Bekleme Süresi Ayarı:</b>Normal şartlar altında 10 sn dir. Sizde istediğiniz kadar süre zarfı belirliyebilirisniz. Fakat unutmayın ki gireceğimiz değer saniye cinsinden olmalıdır.

Bilgisayarımızı ubuntu (ubuntunun herhangi versiyonu olabilir) ile başlatarak Uygulamalar(Applications) menüsünden > Donatılar(Accessories) > Uçbirim(Terminal)i çalıştırıyoruz. Daha sonra açmış olduğumuz terminal ekranına bu kodu yazıyoruz.
<br>
<code>sudo gedit /etc/default/grub</code>
<br>
Bu komutu yazdığınızda sizden şifre istiyecektir.Şayet şifereyi doğru girdiyseniz karşınıza bir pencere çıkacaktır. Burada değiştirmeniz gerekenler GRUB_DEFAULT=0 VE GRUB_TIMEOUT=10 değerleridir.
<br><br>
<b>GRUB_DEFAULT,</b>hangi şeçeneğin default olarak seçileceğini<br>
<b>GRUB_TIMEOUT,</b>kaç saniye sonra default olarak seçilmiş seçeneğin aktif olacağını belirtmektedir.<br><br>

Mesela bizim istediğimiz işletim sistemi 5. sırada olsun.Bu yüzden GRUB_DEFAULT 'a gireceğim değerin 4 olması gerekir. Çünkü ilk seçenek 0 dan başlamaktadır. Yani kısacası bulunduğu değerden bir eksiğini yazmalıyız. 

GRUB_TIMEOUT değeri ise istediğiniz şekilde süreyi saniye cinsinden kısaltıp uzatabilirsiniz.

Sonuç olarak dosyada yaptığımız değişikliklerden sonra dosyayı kaydedip kapatıyoruz ve konsola dönüyoruz. Bu değişiklilerin aktif olabilmesi için dosyanın içindeki verilerin güncellenmesi gerekir. Bu yüzdende son olarak aşağıdaki komutu yazıp girmiş olduğumuz verilerin aktif olmasını sağlıyoruz.
<br>
<code>sudo update-grub</code>
<br>
<br>
<b>NOT:</b>Komutu girdikten sonra grub menüsünün içeriğinin ekrana yazıldığını göreceksiniz.






















