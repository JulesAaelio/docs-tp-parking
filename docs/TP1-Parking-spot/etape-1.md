# Etape 1 : Faire clignoter les LEDS

## Objectifs 
Utiliser un capteur de présence pour détécter la présence d'un véhicule sur la place de parking. 
Lorsque la place est occupée, on éclaira une LED de couleur rouge. 
Lorsque la place est libre, on éclairera une LED de couleur verte. 

## Matériel nécéssaire
- [Carte NodeMCU Lua Amica Module V2](https://leony.ydayslyon.fr/consumables/284)
- [Breaboard](https://leony.ydayslyon.fr/consumables/291)
- [LED Rouge](https://leony.ydayslyon.fr/consumables/80)
- [LED Verte](https://leony.ydayslyon.fr/consumables/88)

## Ressources documentaires
N/A

## Schéma de branchement
![branchements](../images/step-1.png)


## Extrait de code 
1 - Allumer et éteindre une LED
```c
int LED = 13;
void setup() {
  // Configurer le port LED en mode sortie. 
  pinMode(LED, OUTPUT);

}

void loop() {
  // Envoyer du courant dans le port LED. 
  digitalWrite(LED, HIGH);
  delay(500);

  // Ne plus envoyer de courant dans le port LED.
  digitalWrite(LED, LOW);
  delay(500);
}

```