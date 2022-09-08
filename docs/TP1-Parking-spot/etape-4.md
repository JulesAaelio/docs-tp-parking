# Etape 4 : Ajouter le capteur de température

## Objectifs
Mesurer la température et envoyer l'information au serveur

## Matériel nécéssaire 
- [Capteur de température 18B20 prémonté](https://leony.ydayslyon.fr/consumables/194)  

OU
- [Capteur de température DS18B20](https://leony.ydayslyon.fr/consumables/194) + [Résistance 4.7K ](https://leony.ydayslyon.fr/consumables/96)

## Branchements
> ATTENTION : Si le capteur est branché à l'envers, il chauffe fortement.
Si votre capteur devient chaud, débranchez le fil relié au 3V3 et laissez le refroidir. 

## Envoie de l'information au serveur

Pour la température, le message doit contenir les éléments suivants : 

measurement = temperature   
fields : temperature (float)

## Ressources 
- [DS18B20 Datasheet](https://datasheets.maximintegrated.com/en/ds/DS18B20.pdf)
- [Librairie DallasTemperature](https://www.arduino.cc/reference/en/libraries/dallastemperature/)
- [Librairie OneWire](https://www.arduino.cc/reference/en/libraries/onewire/) 

## Extraits de code 
Les librairies mentionnées fournissent des exemples. 