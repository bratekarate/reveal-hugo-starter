+++
title = "Crypto"
outputs = ["Reveal"]
[logo]
src = "/images/itf_logo_white_bg.png"
+++

# Blockchain

![blockchain](/images/csm_Blockchain-slide_dc0a04ac4a.png)

---

{{% section %}}

## Problemstellung

- Vertrauenswürdige Datensicherung zwischen mehreren Parteien

![distrust homer](/images/distrust_homer.gif)

---

## Problemstellung

- Vertrauenswürdige Datensicherung zwischen mehreren Parteien
    - Kassenbuch (Ledger)
    - Versorgungskette (Supply Chain)
    - Schadensfälle bei Versicherungen
- Anspruch: Byzantinische Fehlertoleranz
    - Problem der byzantinischen Generäle
    --> Konsens über die Wahrheit eines Sachverhalts
- Vermeidung eines "Single-Point-Of-Failure"

---

## Distributed-Ledger-Technologie (DLT)

![dlt](/images/dlt.png)

---

## DLT (2)

- ***Verteiltes Kassenbuch***: repliziert, geteilt und synchronisiert
- Public-Key-Kryptographie: Nicht fälschbare digitale Signaturen.
- Konsensmechanismen zur Einigung auf eine Wahrheit
- I.d.R. P2P-Netzwerk mit mehreren Knotenpunkten (Nodes)
- Implementierungen:
    - **Blockchain**
        - Bitcoin, Ethereum, Hyperledger Fabric
    - **DAG** (directed acyclic Graph/gerichteter azyklischer Graph)
        - IOTA, Hashgraph

---

## Blockchain-Technologie

![blockchain](/images/blockchain.png)
 
---

## Blockchain-Technologie
- Meistverbreiteste Implementierung von DLT
- Unveränderbare kryptografische Verkettung von Datensätzen in signierten *Datenblöcken*
- Vgl. *Linked List*
- Erstellen neuer Blöcke mittels Konsensalgorithmen
- Wie die meisten DLT: Replizierung auf Nodes im P2P-Netzwerk
- Bei Uneinigkeit im Netzwerk entstehen "Forks" der Blockchain

{{% /section %}}

---

{{% section %}}

## Blockchain: Aufbau
- Blockchain: Liste von Datensätzen (Blocks)
- Block:
  - Kryptographisches Hash des letzten Blocks (chaining)
  - Zeitstempel
  - Transaktionsdaten (i.d.R. eine Baumstruktur)
- Jeder Block referenziert den vorherigen Block ==> Blöcke formen eine "Kette"
- Blockchain ist unveränderbar: Blöcke können nur angehängt werden

---

## Block (Bitcoin)
![bitcoin block data](/images/Bitcoin_Block_Data.svg.png)

- Vgl. Ethereum-Block: Erweiterung des hier gezeigten Bitcoin-Blocks.

---

## Permissioned vs permissionless
- Blockchains können *permissioned* oder *permissionless* umgesetzt werden.
- Permissioned Blockchain
    - Private Netzwerke
    - Zentrale Autorität (CA) über Teilnehmer
    - Volle Kontrolle über Anzahl der Nodes im Netzwerk
    - *Bsp: Hyperledger Fabric*
- Permissionless Blockchain
    - Öffentliche Netzwerke
    - Keine zentrale Autorität (CA) über Mitglieder
    - Keinerlei Kontrolle über Anzahl der Nodes im Netzwerk
    - *Bsp: Bitcoin Blockchain*

{{% /section %}}

---

{{% section %}}

## Konsensalgorithmen

![agreement](/images/agree2.jpg)

---

## Konsensalgorithmen
- Verteiltes System ==> Viele Transaktionslisten (Blockchains) existieren im Netzwerk.
- Es muss sich automatisiert geeinigt werden, ob eine Liste integer ist.
  ==> Konsensalgorithmen
- Algorithmen mit Byzantine-Fault-Tolerance (BFT)
    - Permissioned (privat)
        - Proof-of-Authority (PoA)
        - Proof-of-elapsed-Time (PoET)
    - Permissionless (öffentlich)
        - Proof-of-Work (PoW)
        - Proof-of-Stake (PoS)

---

## Proof-of-Work (PoW)

![pow](/images/pow2.png)

---

## Proof-of-Work (PoW)
  - Absichtlich rechenaufwendige Aufgaben, um eine Transaktion zu validieren
  - Erstellen falscher Transaktionen wäre kostenaufwendig und nicht rentabel
  - Je älter ein Block ist desto schwerer umzuschreiben: Alle folgenden Blöcke müssten umgeschrieben werden.
  - Es gibt eine Belohnung für die erfolgreiche Validierung. So wird eine
    Cryptowährung regelrecht "geschürft" daher als "Mining" bezeichnet.

---

## Proof-of-Work (PoW)

![mining rig](/images/mining_rig2.jpg)

---

## Proof-of-Stake (PoS)

![pos](/images/pos2.png)

---

## Proof-of-Stake (PoS)
  - "Validierungsknoten" ersetzen die Miner
  - Statt Rechenaufwand muss ein Anteil ("Stake") in Cryptowährung festgesetzt werden
  - Halten sich Validatoren nicht an die Regeln des Netzwerks drohen hohe Verluste
  - Es gibt also keinen Anreiz, sich nicht an die Validierungsregeln zu halten.

---

## Proof-of-Stake (PoS)

![validator node](/images/valid_node.avif)

---

## PoW vs PoS
- PoW sorgt für hohen Energieaufwand: Es wird Energie "für nichts" verschwendet.
- PoS ist weit weniger Energieaufwändig. Allerdings nocht nicht so etabliert.

---

## PoW-Beispiel

![block mining 1](/images/mining_blocks.png)

---

## Streitfall statt Konsens

- Verschiedene Nodes akzeptieren teils unterschiedliche Blöcke "zeitgleich"
    - Temporärer Fork
    - Blockchain, die als erstes weiterwächst, wird zur neuen Wahrheit
- Permanente Uneinigkeit oder geplante Protokolländerungen
    - Soft Fork *(Abwärtskompatible Änderungen)*
        - Bitcoin Segregated Witness
    - Hard Fork *("Breaking Changes")*
        - Bitcoin, Bitcoin XT & Bitcoin Classic
        - Ethereum & Ethereum Classic

---

## Temporärer Fork (1)

![block mining 2](/images/mining_blocks_2.png)

---

## Temporärer Fork (2)

![block mining 3](/images/mining_blocks_3.png)

---

## Hyperledger Fabric Ordering

![ordering](/images/ordering.webp)

## Hyperledger Fabric Ordering

- Kein dedizierter Konsensmechanismus für alle Hyperledger Blockchains
- Konsensmechanismus ist je nach Anwendungsfall konfigurierbar
- Hyperledger Fabric Blockchains sind permissioned:
--> Geringere Anforderungen für byzantinische Fehlertoleranz
- Konsensalgorithmen:
    - PoeT (BFT)
    - Raft (CFT)
    - Kafka (deprecated)

{{% /section %}}

--- 

{{% section %}}

## Geschäftliche Anwendung

---

## Smart-Contracts

---

## Orakel

{{% /section %}}

---
