1. docker-compose.yml dosyasının bulunduğu dizinde ayağa kaldırıyoruz.

2. Containerları ayağa kaldırdıktan sonra aynı dizin içinde terminalde curl ile post isteği atıyoruz.

		curl -i -X POST -H "Accept:application/json" -H "Content-Type:application/json" 		127.0.0.1:8083/connectors/ --data "@debezium.json"
	
	** debezium.json dosyasında bulunan database bilgilerini kullanılacak olan database'mize göre düzenlemeyi unutmayın.

3. Attığımız curl isteği sonucu 201 döndükten sonra ' localhost:8090 ' adresine gidip kafka'yı ui üzerinden inceleyebiliriz.