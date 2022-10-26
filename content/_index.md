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

## Problemstellung

- Vertrauenswürdige Datensicherung zwischen mehreren Parteien

![alt text](/images/distrust_homer.gif)

---

## Problemstellung

- Vertrauenswürdige Datensicherung zwischen mehreren Parteien
    - Kassenbuch (Ledger)
    - Versorgungskette (Supply Chain)
    - Schadensfälle bei Versicherungen
- Anspruch: Byzantinische Fehlertoleranz
    - Problem der byzantinischen Generäle
    --> Konsens über die Wahrheit eines Sachverhalts

---

## Distributed-Ledger-Technologie (DLT)

- *Verteiltes Kassenbuch*
- Public-Key-Kryptographie: Nicht fälschbare digitale Signaturen.
- Konsensmechanismen zur Einigung auf eine Wahrheit
- Implementierungen: 
    - **Blockchain**
        - Bitcoin, Ethereum, Hyperledger Fabric
    - **DAG** (directed acyclic Graph/gerichteter azyklischer Graph)
        - IOTA, Hashgraph

---

## Blockchain-Technologie
- Meistverbreiteste Implementierung von DLT
- Unveränderbare Verkettung von Datensätzen in kryptografisch signierten *Datenblöcken*
- Erstellen neuer Blöcke mittels Konsensalgorithmen
- (Bild hier)


{{% /section %}}

---

{{% section %}}

## Blockaufbau
- Blockchain: Liste von Datensätzen (Blocks)
- Block:
  - Kryptographisches Hash des letzten Blocks (chaining)
  - Zeitstempel
  - Transaktionsdaten (i.d.R. eine Baumstruktur)
- Jeder Block referenziert den vorherigen Block ==> Blöcke formen eine "Kette"
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
- Verschiedene Nodes akzeptieren teils unterschiedliche Blöcke "zeitgleich"
    - Temporärer Fork
    - Blockchain, die als erstes weiterwächst, wird zur neuen Wahrheit

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

--- 

{{% section %}}

## Mining Blocks 1

![alt text](/images/mining_blocks.png)

---

## Mining Blocks 2

![alt text](/images/mining_blocks_2.png)

---

## Mining Blocks 3

![alt text](/images/mining_blocks_3.png)

{{% /section %}}

---

## TODO: 
- Smart Contracts (Ethereum, Cardano live Beispiel)
- "Orakel"
- Hyperledger pluggable Konsens (mit Bild)
