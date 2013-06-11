---
layout: post
title: Spring Ve Hibernate Entegrasyonu
---
   Bu yazımda web tabanlı, Spring Framework ve Hibernate Framework'u kullanarak geliştirmiş olduğum bir pojenin tanıtımını yapacağım. 
Eğer daha Spring ve Hibernate Framework'leri ile ilgili daha fazla bilgi edinmek isterseniz daha önceden bu konulara yer vermiş olduğum konu başlıklarını inceleyebilirsiniz. 
(<a href="http://symtkn.github.io/106/hibernate-overview/">Hibernate Framework</a> ve <a href="http://symtkn.github.io/106/spring-overview/">Spring Framework</a>)<br>

  Gelelim asıl konumuza, projenin kaynak kodlarına <a href="https://github.com/symtkn/J2EE/tree/master/FrameworkApplications" target="_blank"> buradaki Github adresinden</a> erişebilirsiniz.<br>

   Projenin amacı bir login form tasarlamaktır. Kullanıcıdan bazı bilgileri alarak veritabanına kaydeder ve kullanıcının ana sayfaya geçmesini(login olmasını) sağlar. Ve her kayıt işleminden sonra veritabındaki üye kayıt bilgilerini görebilmemiz için veritabanından gerekli bilgileri çeker; ekranda tablo şeklinde gösterir.
  Program çalıştırıldığın anda üretilen örnek çıktılara <a href="https://github.com/symtkn/J2EE/issues/1" target="_blank">şuradan</a> bakabilirsiniz.
