<h1 align="left">KAFKA - DEBEZIUM</h1>

###

<p align="left">Kafka ve Debezium İle Veri Akışını Yönetme</p>

###

<h2 align="left">Kafka Nedir?</h2>

###

<p align="left">Kafka, yüksek performanslı, ölçeklenebilir ve dayanıklı bir veri akışı platformudur. Apache Kafka, büyük ölçekli veri akışlarını işlemek ve farklı sistemler arasında güvenilir bir şekilde iletişim kurmak için tasarlanmıştır. Olay temelli (event-driven) mimarilere uygun olarak çalışan Kafka, veri üreticileri ile tüketici uygulamaları arasında güvenilir, hızlı ve ölçeklenebilir bir iletişim sağlar. Bu özellikleri sayesinde, Kafka, modern veri entegrasyonu, akış işleme ve gerçek zamanlı analitik uygulamalar için popüler bir tercih haline gelmiştir.</p>

###

<h2 align="left">Debezium Nedir?</h2>

###

<p align="left">Debezium, veritabanlarında gerçekleşen değişiklikleri izlemek ve bu değişiklikleri güvenilir bir şekilde Kafka üzerinden iletmek için tasarlanmış bir açık kaynak projedir. Debezium, veritabanlarındaki tablo değişikliklerini yakalar, bu değişiklikleri Kafka mesajlarına dönüştürür ve ardından bu mesajları Kafka broker'ı üzerinden tüketici uygulamalara ileterek gerçek zamanlı veri akışını sağlar. Veritabanı değişikliklerini yakalamak için veritabanı loglarına (binlog) dayanır ve bu sayede veri güvenilir bir şekilde aktarılabilir.<br><br>Bu proje, Kafka ve Debezium'u kullanarak veri akışını yönetmek için bir örnek sunmaktadır. Proje, Docker Compose kullanarak Kafka ve Debezium konteynerlarını ayağa kaldırmak ve bir veritabanındaki değişiklikleri Kafka üzerinden izlemek için adımları içermektedir.</p>

###

<h3 align="left">Docker Compose Dosyasını Ayağa Kaldırma</h3>

###

<p align="left">Proje dizinindeki `docker-compose.yml` dosyasının bulunduğu dizinde terminali açın ve aşağıdaki komutu kullanarak konteynerları başlatın<br><br>docker-compose up -d</p>

###

<h3 align="left">Konteynerları başlattıktan sonra, aynı dizinde terminali açın ve aşağıdaki curl komutunu kullanarak bir POST isteği gönderin</h3>

###

<p align="left">curl -i -X POST -H "Accept:application/json" -H "Content-Type:application/json" 		127.0.0.1:8083/connectors/ --data "@debezium.json"</p>

###

<h5 align="left">NOT !</h5>

###

<p align="left">Eğer bu istek sonucunda "400" hata kodu alıyorsanız, debezium.json dosyasındaki veritabanı bilgilerini kullanılacak olan veritabanınıza göre düzenlemeyi unutmayın.</p>

###

<p align="left">Bu isteği başarıyla tamamladıktan sonra ("201") , Kafka UI'ı incelemek için tarayıcınızı açın ve localhost:8090 adresine gidin.</p>

###