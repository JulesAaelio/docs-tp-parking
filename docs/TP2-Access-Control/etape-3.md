# Etape 3 : Ajouter un contrôle d'accès RFID

## Objectifs 
Lorsqu'un badge d'accès est présenté. On affiche son UID. 

## Matériel nécéssaire
- [RC522 RFID Module](https://leony.ydayslyon.fr/consumables/152)

## Ressources documentaires
- [RC522 RFID Guide](https://joy-it.net/files/files/Produkte/SBC-RFID-RC522/SBC-RFID-RC522-Manual-09-06-2020.pdf)

## Schéma de branchement
TODO

## Extrait de code 
### Afficher l'UID

```
void printUid(MFRC522::Uid *uid) { 
  Serial.print(F("Card UID:"));
  for (byte i = 0; i < uid->size; i++) {
    if(uid->uidByte[i] < 0x10)
      Serial.print(F(" 0"));
    else
      Serial.print(F(" "));
    Serial.print(uid->uidByte[i], HEX);
  } 
  Serial.println();
}
```