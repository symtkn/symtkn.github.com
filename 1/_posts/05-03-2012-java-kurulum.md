---
layout: post
title: Ubuntu Üzerine Java Kurulumu
---
####KONU ANALİZİ
<ol type="I">
<li> <a href="#indirme"> JDK(Java Development Kit) paketi indirme </a> </li>
<li> <a href="#kurulum"> Kurulum </a> </li> 
<li> <a href="#yapilandirma"> Yapılandırma </a> </li>
</ol><br>
 
###<a id="indirme"> JDK(Java Development Kit) paketi indirme </a>
	
    Java yeni sürümü ile Oracle firmasının şemsiyesi altına girmiştir. Jdk paketini `tar.gz` uzantılı olarak bu <a href="http://www.oracle.com/technetwork/java/javase/downloads/index.html"> siteden </a>indirebiliriz.

###< a id="kurulum"> Kurulum </a>

    Başlangıç dizinimizin altında `java` adlı bir klasör oluşturalım. Bu klasör içerisinede indirmiş olduğumuz jdk paketini yerleştirelim. Sırasıyla aşağıdaki komutları uygularsak:
<b><>br
<code>$ cd ~/java</code><br>
<code>$ tar zxvf jdk*</code><br>
<code>$ sudo mv jdk1.7.0/ /usr/lib/jvm/</code><br>
</b>
   Şimdiki komutlarlada sistem java kaynaklarını yeni yüklediğimiz 1.7 versiyonuna bağlıyoruz.<br>
<b>
<code> $ sudo update-alternatives --install "/usr/bin/java" "java" "/usr/lib/jvm/jdk1.7.0/bin/java" 1</code><br>
<code>$ sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/lib/jvm/jdk1.7.0/bin/javac" 1</code><br>
<code>$ sudo update-alternatives --install "/usr/bin/javaws" "javaws" "/usr/lib/jvm/jdk1.7.0/bin/javaws" 1</code>
</b>
Böylece kurulum tamamlanmış bulunmaktadır.

###<a id="yapilandirma"> Yapılandırma </a>

Sistemdeki Javalardan hangisini kullanacağımızı seçerken şu komutu kullanırız:
<br><b>
<code>$ sudo update-alternatives --config java</code><br>
Bu işlemlerden sonra java'nın sağlıklı çalışması için sistemi reboot etmenizi tavsiye ederim :-)

