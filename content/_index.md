+++
title = "Crypto"
outputs = ["Reveal"]
[logo]
src = "/images/Secondary_Black.svg"
width = "4%"
top = "3%"
left = "48%"
+++

# Git Training
<br>

<div>

### Collaboration Betters The World &nbsp;&nbsp;&nbsp;<image src="/images/dot.svg" width="50em" class="plain" style="display: inline-block; vertical-align: middle;padding-bottom: 10px;" >
</div>
Referent: Felix Jian, Full Stack Engineer

---

{{% section %}}

## Organisatorisches

---

## Schulungsziele 

- Verwendung von Git über die **Kommandozeile** 
- **Pull-Requests** und **direktes Einchecken** mit Git 
- Umgang mit rückständigen **Remote-Branches**
- Vermeidung von Fehlern mit **Git-Rebase**
- Anwendung von **Cherry-Picking**-Techniken 
- Zielgerichtete Untersuchung der **Git-Historie**
- Nutzung von **Bitbucket** als zentrales Repository der Commerzbank 
- *(Besonderheiten bei der Verwendung von **Git auf Windows**)*

---

## Ablauf

| Uhrzeit | Thema | 
| ----- | -------------  |
| 09:00 | Kennenlernen && Einführung in Git |
| 10:15 | Pause |
| 10:30 | Lokales Arbeiten mit Git |
| 12:00 | Mittagspause |
| 13:00 | Fortgeschrittene Git-Techniken (Rebase, History, Cherry-Pick) |
| 15:15 | Pause |
| 15:30 | Git in der Technologielandschaft der Commerzbank |
| 17:00 | Schulungsende |

{{% /section %}}

---

## Git, bedeutet das nicht...?

<image src="/images/git-merge.gif" width="800em" class="plain fragment">

---

{{% section %}}

## Git Grundlagen

---

### *I’m an egotistical bastard, and I name all my projects after myself. First ‘Linux’, now ‘Git’.*
<div style="text-align: right;">
— Linus Torvalds
</div>

<br>
<br>
<br>

- Kontext: "Git" bedeutet im britischen Englisch umgangssprachlich so viel wie "Blödmann".

---

## Der Anfang
### Exkurs in die Historie von Git
- Entwicklung des Linux-Kernels benötigte ein **Versionskontrollsystem** (Version Control System, ***VCS***)
- 2002: Lösung -- Bitkeeper, ein proprietäres **verteiltes VCS** (Distributed VCS, ***DVCS***)
- 2005: Widerrufen der Erlaubnis, Bitkeeper kostenlos zu verwenden
- 2005: Linus Torvalds entwickelt als Lösung das DVCS Git

---

## Auffrischung
### Was ist Git?

- **Verteiltes** Versionsverwaltungssystem (Version Control System, *VCS*)
- Im Gegensatz zu anderen VCS: **Schnappschüsse** (***Commits***) statt Unterschiede
- Kernkonzept: **Lokale** Abzweigungen (*Branches*)
    - Interaktion mit dem Server erst wenn erwünscht
    - Lokale Branches sind leichtgewichtig
- Zusammenführung (*Merging*) **ganzer Branches**, nicht einzelner Änderungen (*Commits*)
    - Ausnahme: *Cherry-Picking* (dazu später mehr)
- Hohe **Performance** durch lokale Verarbeitung

---

## VCS vor Git

<image src="/images/vcs-deltas.png" width="800em" class="plain">

Frühere VCS: Speichern der Änderungen (*Deltas*) von Dateien

---

## Git VCS

<image src="/images/vcs-snapshots.png" width="800em" class="plain">

Git: Speichern von Schnappschüssen des Dateisystems

---

## Git Branching
### Git Commit Struktur
- Commit ***Hash***
- **Autor** des Commits
- Zeiger auf einen **Schnappschuss** des Dateisystems
- Zeiger auf **0..n Vorgänger**
    - 0: Initialer Commit
    - 1: Folgende Commits
    - n: Commit, der aus Merge resultiert
 
---

## Git Branching
### Git Commit Struktur


 
---

## Test

- xyz
- testas askldjaskldjaskldjaskldjaklsdjasjlkdsakljaskdasjkl lkas djkalsj askl 
- [http://maps.google.com](google.com)
{ class="fragment" style="display: list-item"}

- <div class="line">test</div>
{ class="fragment" style="display: list-item"}

<div class="fragment">

```sh{}
git commit -m 'test'
git commit -m 'test'
```

</div>

---

## Grundlagen 2

---

## Grundlagen 3

{{% /section %}}

---

{{% section %}}

## Rebase etc
 
---

## Rebase 2

---

## Rebase 3

---

## Rebase 4

{{% /section %}}
