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

## Der Anfang
### Exkurs in die Historie von Git
- Entwicklung des Linux-Kernels benötigte ein **Versionskontrollsystem** (Version Control System, ***VCS***)
- 2002: Lösung -- Bitkeeper, ein proprietäres **verteiltes VCS** (Distributed VCS, ***DVCS***)
- 2005: Widerrufen der Erlaubnis, Bitkeeper kostenlos zu verwenden
- 2005: Linus Torvalds entwickelt als Lösung das DVCS Git

---

### *I’m an egotistical bastard, and I name all my projects after myself. First ‘Linux’, now ‘Git’.*
<div style="text-align: right;">
— Linus Torvalds
</div>

<br>
<br>
<br>

- Kontext: "Git" bedeutet im britischen Englisch umgangssprachlich so viel wie "Blödmann".
{ class="fragment" style="display: list-item"}

---

## Was macht Git aus?

- **Verteiltes** Versionsverwaltungssystem (Version Control System, *VCS*)
{ class="fragment" style="display: list-item"}
- Im Gegensatz zu anderen VCS: **Schnappschüsse** (***Snapshots***) statt Unterschiede
{ class="fragment" style="display: list-item"}
- Kernkonzept: **Lokale** Abzweigungen (*Branches*)
    - Interaktion mit dem Server erst wenn erwünscht
    - Lokale Branches sind leichtgewichtig
{ class="fragment" style="display: list-item"}
- Zusammenführung (*Merging*) **ganzer Branches**, nicht einzelner Änderungen (*Commits*)
    - Ausnahme: *Cherry-Picking* (dazu später mehr)
{ class="fragment" style="display: list-item"}
- Hohe **Performance** durch lokale Verarbeitung
{ class="fragment" style="display: list-item"}

---

## VCS vor Git

<image src="/images/vcs-deltas.png" width="800em" class="plain">

Frühere VCS: Speichern der Änderungen (*Deltas*) von Dateien

---

## Git VCS

<image src="/images/vcs-snapshots.png" width="800em" class="plain">

Git: Speichern von Snapshots des Dateisystems (*Tree*)

{{% /section %}}

---

{{% section %}}

## Git Grundlagen

---

## Git Branching
### Git Commit Struktur
- Commit ***Hash***
- **Autor** des Commits
- Zeiger auf einen **Snapshot** des Dateisystems (*Tree*)
- Zeiger auf **0..n Vorgänger**
    - 0: Initialer Commit
    - 1: Folgende Commits
    - n: Commit, der aus Merge resultiert

---

## Git Commit Struktur (2)

<image src="/images/branching-001-commit-and-tree.png" width="600em" class="plain">

Initialer Commit aus drei Dateien. Commit zeigt auf den *Tree* der Dateien (*Blobs*).

---

## Git Commit Struktur (3)

<image src="/images/branching-002-commits-and-parents.png" width="600em" class="plain">

Weitere Commits folgen. Jeder Commit zeigt auf den Tree sowie auf den vorhergehenden Commit.

---

## Git Branching
### Git Branch Struktur
- Branch: Leichtgewichtiger, **beweglicher** Zeiger auf einen Commit.
- Bei jedem weiteren Commit **wandert der Zeiger** auf den neuen Commit.
- Git merkt sich den ausgecheckten Branch: **Spezieller Zeiger *HEAD***.
- "Haupt-Branch" ist meist *master* oder *main*. Dies ist für Git bedeutungslos.

---

## Git Branch Struktur (1)

<image src="/images/branching-003-branch-and-history.png" width="600em" class="plain">

- Erstellung der Branches *master* sowie *v1.0* auf dem aktuellsten Commit. Branches sind nur Referenzen/Zeiger auf den Commit.
- Zeiger HEAD markiert den derzeitigen Branch.

---

## Git Branch Struktur (2)

<image src="/images/branching-004-head-to-master.png" width="600em" class="plain">

Erstellung des Branch *testing* auf dem derzeiten Branch *master*. Er zeigt nun auf den selben Commit wie *master*.

---

## Git Branch Struktur (3)

<image src="/images/branching-005-advance-testing.png" width="600em" class="plain">

- Wechsel auf Branch *testing* sowie Commit einer neuen Änderung.
- Zeiger HEAD wandert auf *testing*. Zeiger von *testing* wandert auf den neuen Commit.

---

## Git Branch Struktur (4)

<image src="/images/branching-007-advance-master.png" width="600em" class="plain">

- Wechsel auf Branch *master* sowie Commit einer neuen Änderung.
- Zeiger HEAD wandert auf *master*. Zeiger von *master* wandert auf den neuen Commit

---

## Git Merge
- **Zusammenführung** von zwei Branches mit gemeinsamem Vorgänger
- Neuer Commit wird erstellt (Merge-Commit), mit **beiden Branches** als Vorgänger
- Die Snapshots der Trees beider Commits werden **in einem neuen Tree zusammengeführt**
- Der neue Merge-Commit zeigt auf den zusammengführten Tree

---

## Git Merge (2)
<image src="/images/merging-001-basic-branching.png" width="600em" class="plain">

Branch *iss53* soll in Branch *master* gemergt werden.

---

## Git Merge (3)
<image src="/images/merging-002-basic-merging.png" width="600em" class="plain">

Three-Way-Merge mit C4 (*master*), C5 (*iss53*) sowie C2 (gemeinsamer Vorgänger).

---

## Git Merge (3)
<image src="/images/merging-003-basic-merging.png" width="600em" class="plain">

- Es resultiert ein neuer Commit C6, der einen zusammengeführten Tree aus C4, C5 und C2 enthält.
- Zeiger von *master* wandert auf den neuen Commit C6.

---

## Git Grundlagen
### Zusammenfassung

- Commit:
    - Zeiger auf einen **Snapshot** des Dateisystems (*Tree*)
    - Zeiger auf **0..n Vorgänger**
- Branch:
    - Leichtgewichtiger, **beweglicher** Zeiger auf einen Commit.
    - Bei jedem weiteren Commit **wandert der Zeiger** auf den neuen Commit.
    - Git merkt sich den ausgecheckten Branch: **Spezieller Zeiger *HEAD***.
- Merge:
    - **Zusammenführung** von zwei Branches mit gemeinsamem Vorgänger
    - Die Snapshots der Trees beider Commits werden **in einem neuen Tree zusammengeführt**

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
