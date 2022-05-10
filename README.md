# PRÀCTICA 6: LECTOR RFID + LECTOR SD + DISPLAY

En aquesta pràctica he après a utilitzar diversos dispositius en un sol SPI. Per fer-ho, entre els dispositius es comparteixen els senyals CLK/SCK, MOSI i MISO. El pin restant, el CS/SS, és independent per cada dispositiu i a l'hora de dissenyar el software indiquem a quin pin tenim connectat el CS/SS de cada dispositiu.

## Requeriments

Pel muntatge que he fet (adjunto vídeo més abaix) he necessitat el següent material:

* ESP32
* Display I2C SSD1306
* Lector RFID SPI MF522-AN
* Lector SD SPI HW-125
* Targeta SD
* 2 diodes LED
* 1 Buzzer actiu

Si es vol deixar registrada la data i hora de lectura de la targeta RFID, també es necessita una connexió wifi per tal de poder connectar-se a un servidor NTP i sincronitzar la data i hora actual.

## Funcionament

Primer, apareix un missatge a la pantalla de "Connectant...", per tant, això vol dir que la placa està connectant-se amb la xarxa wifi i poder sincronitzar la data i hora actual. Un cop fet això, el dispositiu estarà llest per llegir targetes RFID.

Quan es passa una targeta RFID, la pantalla mostrarà el seu ID, s'encendrà un LED verd durant uns segons i el buzzer farà un soroll indicant que s'ha passat la targeta. A més a més, es deixarà registrat dins d'un fitxer de la targeta SD el ID de la targeta RFID i l'hora i data de lectura.

[Vídeo del funcionament](https://drive.google.com/file/d/1hG5x8pjVVlt_VaDnJqXITv0x0OJ5dK5H/view?usp=sharing) (s'ha de tenir iniciada la sessió amb un usuari acabat en "upc.edu").
