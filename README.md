
# KAFKA - DEBEZIUM

### Kafka Nedir?
Kafka, yüksek performanslı, ölçeklenebilir ve dayanıklı bir veri akışı platformudur. Apache Kafka, büyük ölçekli veri akışlarını işlemek ve farklı sistemler arasında güvenilir bir şekilde iletişim kurmak için tasarlanmıştır. Olay temelli (event-driven) mimarilere uygun olarak çalışan Kafka, veri üreticileri ile tüketici uygulamaları arasında güvenilir, hızlı ve ölçeklenebilir bir iletişim sağlar. Bu özellikleri sayesinde, Kafka, modern veri entegrasyonu, akış işleme ve gerçek zamanlı analitik uygulamalar için popüler bir tercih haline gelmiştir.
### 
### Debezium Nedir?
Debezium, veritabanlarında gerçekleşen değişiklikleri izlemek ve bu değişiklikleri güvenilir bir şekilde Kafka üzerinden iletmek için tasarlanmış bir açık kaynak projedir. Debezium, veritabanlarındaki tablo değişikliklerini yakalar, bu değişiklikleri Kafka mesajlarına dönüştürür ve ardından bu mesajları Kafka broker'ı üzerinden tüketici uygulamalara ileterek gerçek zamanlı veri akışını sağlar. Veritabanı değişikliklerini yakalamak için veritabanı loglarına (binlog) dayanır ve bu sayede veri güvenilir bir şekilde aktarılabilir.Bu proje, Kafka ve Debezium'u kullanarak veri akışını yönetmek için bir örnek sunmaktadır. Proje, Docker Compose kullanarak Kafka ve Debezium konteynerlarını ayağa kaldırmak ve bir veritabanındaki değişiklikleri Kafka üzerinden izlemek için adımları içermektedir.

### 

#### Docker Compose Dosyasını Ayağa Kaldırma

Proje dizinindeki `docker-compose.yml` dosyasının bulunduğu dizinde terminali açın ve aşağıdaki komutu kullanarak konteynerları başlatın

```bash
  docker-compose up -d
```


Konteynerları başlattıktan sonra, aynı dizinde terminali açın ve aşağıdaki curl komutunu kullanarak bir POST isteği gönderin.

```bash
  curl -i -X POST -H "Accept:application/json" -H "Content-Type:application/json" 		127.0.0.1:8083/connectors/ --data "@debezium.json"
```


### KAFKA UI

Kafka UI'ı incelemek için tarayıcınızı açın ve localhost:8090 adresine gidin.

```bash
  http://localhost:8090
```
    

  #### ATILAN İSTEK SONUCUNDA

**201:** İstek başarılı bir şekilde gönderildi.

**400:** İstek gönderilemedi. `debezium.json` dosyasındaki DB configini kontrol edin.
