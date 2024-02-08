# KAFKA-DEBEZIUM

## Compose Ayağa Kaldırma

Projenizi ayağa kaldırmak için aşağıdaki adımları takip edin:

 **Docker Compose Kullanarak Konteynerları Başlatın:**
   Proje dizinindeki `docker-compose.yml` dosyasının bulunduğu dizinde terminali açın ve aşağıdaki komutu kullanarak konteynerları başlatın:

   ```bash
   docker-compose up -d


	Konteynerları başlattıktan sonra, aynı dizinde terminali açın ve aşağıdaki curl komutunu kullanarak bir POST isteği gönderin:


		```bash
		curl -i -X POST -H "Accept:application/json" -H "Content-Type:application/json" 		127.0.0.1:8083/connectors/ --data "@debezium.json"

		Not: Eğer bu istek sonucunda "400" hata kodu alıyorsanız, debezium.json dosyasındaki veritabanı bilgilerini kullanılacak olan veritabanınıza göre düzenlemeyi unutmayın.
	

Bu isteği başarıyla tamamladıktan sonra ("201") , Kafka UI'ı incelemek için tarayıcınızı açın ve localhost:8090 adresine gidin.