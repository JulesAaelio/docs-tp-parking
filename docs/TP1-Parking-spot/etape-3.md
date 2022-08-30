# Etape 3 : Envoyer l'information au serveur

## Objectifs
Envoyer l'information au serveur

## Matériel nécéssaire 
N/A

## Branchements
N/A

## Ressources 
- [ArduinoMqqtClient](https://github.com/arduino-libraries/ArduinoMqttClient)
- [ArduinoWifi]()
## Extraits de code 

```c
float readDistanceCM() {
  digitalWrite(TRIG_PIN, LOW);
  delayMicroseconds(2);
  digitalWrite(TRIG_PIN, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIG_PIN, LOW);
  int duration = pulseIn(ECHO_PIN, HIGH);
  return duration * 0.034 / 2;
}
```