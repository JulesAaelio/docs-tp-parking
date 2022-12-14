# Etape 3 : Envoyer l'information au serveur

## Objectifs
Se connecter au réseau WiFi
Envoyer le statut (occupé / libre) au serveur. 
On enverra un entier binaire : 

occupé = 1   
libre = 0

## Matériel nécéssaire 
N/A

## Branchements
N/A

## Ressources 
- [Librairie PubSubClient](https://www.arduino.cc/reference/en/libraries/pubsubclient/)
- [Librairie ArduinoWifi](https://www.arduino.cc/reference/en/libraries/wifi/)
- [Librairie ESP8266WifiExample](https://github.com/esp8266/Arduino/blob/master/libraries/ESP8266WiFi/examples/WiFiClient/WiFiClient.ino)

## Extrait de code 
### Connexion à un réseau wifi et envoi d'un message mqtt

https://github.com/knolleary/pubsubclient/blob/master/examples/mqtt_esp8266/mqtt_esp8266.ino

### Intégrer des données dans une chaîne de caractères 
```c
  float data = 10.0;
  char message[100];
  sprintf(message, "mydata=%f",data);
```

## Pour envoyer l'information au serveur
Pour envoyer l'information au serveur, on utilise le protocole [MQTT](https://en.wikipedia.org/wiki/MQTT)   
On enverra toutes les informations sur le topic `parking`

### Adresse et port
|   |   |
|---|---|
| **Adresse** | srv2.juleslaurent.fr | 
| **Port**    | 1883                 |


### Format des messages 
Le serveur s'attend à recevoir des informations au format [InfluxDB inline protocol](https://docs.influxdata.com/influxdb/v1.8/write_protocols/line_protocol_tutorial/)

> Chaque message que vous enverez au serveur doit contenir le tag `spot` contenant votre numéro de place. 

> Le timestamp n'est pas obligatoire. Il sera automatiquement ajouté par le serveur. 

Pour l'occupation de la place, le message doit contenir les éléments suivants :

measurement = status   
fields : status (int)  

Exemple de message : 
```
temperature,spot=1 temperature=37.6
```

### Troubleshooting
Vous ne voyez pas vos informations s'afficher à l'écran ? 
Vous pouvez vous connecter au serveur MQTT en tant que subscriber pour vérifier que les informations que vous envoyez sont correctement formattées / reçues par le serveur. 

Installez [Mosquitto](https://mosquitto.org/download/)
Et lancez la commande suivante : 
```
mosquitto_sub -h srv2.juleslaurent.fr -t "parking"
```

ou via docker 

```
docker run -it eclipse-mosquitto mosquitto_sub -h srv2.juleslaurent.fr -t "parking"
```