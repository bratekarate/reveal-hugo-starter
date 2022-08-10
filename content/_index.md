+++
title = "Crypto"
outputs = ["Reveal"]
[logo]
src = "/images/itf_logo_white_bg.png"
+++

# Blockchain

![alt text](/images/csm_Blockchain-slide_dc0a04ac4a.png)

Technische Betrachtung

---

{{% section %}}

## Aufbau
- Blockchain: Liste von Datensätzen (Blocks)
- Block:
  - Kryptographisches Hash des letzten Blocks (chaining)
  - Zeitstempel
  - Transaktionsdaten (i.d.R. eine Baumstruktur)
- Jeder Block refernziert den letzten Block ==> Blöcke formen eine "Kette"
- Blockchain ist unveränderbar: Blöcke können nur angehängt werden

---

## Block
![alt text](/images/Bitcoin_Block_Data.svg.png)

{{% /section %}}

---

{{% section %}}
## Konsensalgorithmen
- Verteiltes System ==> Viele Transaktionslisten (Blockchains) existieren im Netzwerk.
- Es muss sich automatisiert geeinigt werden, ob eine Liste integer ist.
  ==> Konsensalgorithmen

---

## Proof-of-Work
  - Absichtlich rechenaufwendige Aufgaben, um eine Transaktion zu validieren
  - Erstellen falscher Transaktionen wäre kostenaufwendig und nicht rentabel
  - Je älter ein Block ist desto schwerer umzuschreiben: Alle folgenden Blöcke müssten umgeschrieben werden.
  - Es gibt eine Belohnung für die erfolgreiche Validierung. So wird eine
    Cryptowährung regelrecht "geschürft" daher als "Mining" bezeichnet.

---

## Proof-of-Stake
  - "Validierungsknoten" ersetzen die Miner
  - Statt Rechenaufwand muss ein Anteil ("Stake") in Cryptowährung festgesetzt werden
  - Halten sich Validatoren nicht an die Regeln des Netzwerks drohen hohe Verluste
  - Es gibt also keinen Anreiz, sich nicht an die Validierungsregeln zu halten.

---

## Proof-of-Stake vs Proof-of-Work
- Proof-of-Work sort für hohen Energieaufwand: Es wird Energie "für nichts" verschwendet.
- Proof-of-Stake ist weit weniger Energieaufwändig. Allerdings nocht nicht so etabliert.

{{% /section %}}
