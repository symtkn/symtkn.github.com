---
layout: post
title: Root Şifresi
---
#### KONU ANALİZİ

<li> <a href="#password-degisim"> Root Şifresinin Değişimi </a> </li><br>
<li> <a href="#unutulan-password"> Ubuntu'da Unutulan Root Şifresini Değiştirme </a> </li><br>
<br><br><br><br>

###<a id="password-degisim"> Root Şifresinin Değişimi </a>

Uçbirimde sırasıyla yapmamız gereken işlemler:
<ol type="I">
<li> Root olarak sisteme giriniz.("\" yazıp Enter'a basmanız  yeterli.) </li><br>
<li> <code>passwd</code> yazın ve Enter'a basın.</li><br>
<li> Şimdi kullandığınız şifrenizi giriniz. </li><br>
<li> İki sefer yeni şifrenizi giriniz. </li><br>
</ol>
   Sonuç olarak şifreniz başarıyla değiştirildi,mesajını görürüz.
<br><br><br>

###<a id="unutulan-password"> Ubuntu'da Unutulan Root Şifresini Değiştirme </a>

Öncelikle Linux'u tek kullanıcı modunda yeniden başlatmalıyız.
<ol>
<li>Makineyi yeniden başlatın.(Terminal penceresinden <code>sudo reboot</code> ile yapabilirsiniz.)</li><br>
<li>GRUB yüklenirken ESC'e basın.Böylece menüye gireceksiniz.</li><br>
<li>Eğer kurtarma modu diye bir seçenek varsa seçin ve B'yi tuşalayın.Makineyı tek kullanıcı modunda başlatmış olcaksınız.</li><br>
<li>Böyle bir seçenek yoksa, varsayılan açılış yapılandırılması seçili olmalıdır.Düzenlemek için E'yi tuşlayın. </li><br>
<li>"<u>kernel</u>" ile başlayan satıra gelin ve o satırı düzenlemek için E'yi tuşlayın.</li><br>
<li>Satırın sonuna ilave bir değer olarak <code>single</code> yazın.Enter'a basın be B'yi tuşlayınız.</li><br>

Sistem tek kullanıcılı modda açılmış olmalı.Açıldığında otomatik olarak giriş yapmış ve komut satırına gelmiş olacaksız.

-->Şifrenizi değiştirmek için <code>passwd</code> yazın.

-->Root hesabının şifresini değiştirmek için, <code>passwd root</code> yazın.Böylelikle root şifresini tekrardan tanımlamış olacaksınız.

