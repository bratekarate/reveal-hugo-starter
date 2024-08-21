+++
title = "Git Training"
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

---

## Git, bedeutet das nicht...?

<image src="/images/git-merge.gif" width="800em" class="plain fragment">

---

{{% section %}}

## Der Anfang
### Exkurs in die Historie von Git
- Entwicklung des Linux-Kernels benötigte ein **Versionskontrollsystem** (Version Control System, ***VCS***)
- 2002: Lösung -- BitKeeper, ein proprietäres **verteiltes VCS** (Distributed VCS, ***DVCS***)
- 2005: Widerrufen der Erlaubnis, BitKeeper kostenlos zu verwenden
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

{{% /section %}}

---

{{% section %}}

## Git Command Line

---

## Git Commands
<div class="fragment">

- **Porcelain**
    - *High-level*-Commands für typische Use-Cases
    - Beispiele:
        - git status
        - git add
        - git commit
        - git push
        - git pull
        - git log
        - git branch

</div>
<div class="fragment">

- **Plumbing**
    - *Low-level*-Commands für interne Inspektion und Manipulation
    - Beispiele:
        - git cat-file
        - git rev-parse
        - git name-rev
        - git hash-object

</div>

---

## Das .git Verzeichnis
- Git speichert interne Daten in einer Verzeichnisstruktur.
    - Mit Standardprogrammen wie `ls` erkundbar
    - Allerdings oft nicht lesbar, da binär
<div class="fragment">

- Einige wichtige Git-Verzeichnisse und Dateien:
   - `HEAD`: hält den Namen des aktuellen Branches
   - `objects`: enthält die binären Git-Objekte, nach Hash strukturiert
   - `refs`: bildet Branchnamen auf Hashes ab (lokal und remote)
   - `config`: bildet Branchnamen auf Hashes ab (lokal und remote)
   - `logs`: enthält die Logs der verschiedenen Branches

</div>

---

## Das .git Verzeichnis (2)
- Die grundlegendsten Analyseprogramme für Git: `ls` und `cat`

<div class="fragment">

- Aktuellen Branch ausgeben:
```sh
cat .git/HEAD
```
</div>
<div class="fragment">

- Commit mit dem Hash <HASH> finden:
```sh
ls .git/objects/<ERSTE_2_STELLEN_DES_HASHES>/<REST_DES_HASHES>
```
z.B.
```sh
ls .git/objects/25/be3b47e180f79e4e93d1f2af63a9d2401b92e1
```
</div>
<div class="fragment">

- Objekte lesen, z.B. mit `cat`: Nicht möglich, da binär
    - --> Hex-Dump wie z.B. `xxd` kann verwendet werden
    - Dennoch nicht wirklich menschenlesbar

</div>

<div class="fragment">

- Besser geeignet: *Plumbing* Commands wie `git cat-file` oder `git name-rev`.

</div>

---

## Porcelain Commands

```sh{}
# Abfragen
git status          # Status des Repositories zusammenfassen.
git log             # Historie des Repositories anzeigen. 

# Ändern
git add             # Lesbaren Namen aus Hash einer Revisionsspezifikation
git commit          # Lesbaren Namen aus Hash einer Revisionsspezifikation
git restore         # Hash aus einem Objekt (z.B. Datei) erzeugen.

# Abzweigen
git switch          # Hash aus einem Objekt (z.B. Datei) erzeugen.
git branch          # test

# Vereinigen
git merge           # test
git rebase          # test
git cherry-pick     # test

# Sync
git push            # Hash aus einem Objekt (z.B. Datei) erzeugen.
git fetch           # Hash aus einem Objekt (z.B. Datei) erzeugen.
git pull            # Hash aus einem Objekt (z.B. Datei) erzeugen.
```

---

## Porcelain Commands

|   |   |   |
| - | - | - |
| <span class="code-table-highlight">Abfragen</span> |
| `git status` | Status des Repositories zusammenfassen. |
| `git log` | Historie einer Revision (z.B. Branch oder Commit) anzeigen.  |
|
| <span class="code-table-highlight">Ändern</span> |
| `git add` | Lesbaren Namen aus Hash einer Revisionsspezifikation |
| `git commit` | Lesbaren Namen aus Hash einer Revisionsspezifikation |
| `git restore` | Hash aus einem Objekt (z.B. Datei) erzeugen. |
|
| <span class="code-table-highlight">Abzweigen</span> |
| `git switch` | Hash aus einem Objekt (z.B. Datei) erzeugen. |
| `git branch` | test |
|
| <span class="code-table-highlight">Vereinigen</span> |
| `git merge` | test |
| `git rebase` | test |
| `git cherry-pick` | test |
|
| <span class="code-table-highlight">Synchronisieren</span> |
| `git push` | Hash aus einem Objekt (z.B. Datei) erzeugen. |
| `git fetch` | Hash aus einem Objekt (z.B. Datei) erzeugen. |
| `git pull` | Hash aus einem Objekt (z.B. Datei) erzeugen. |
{ .code-table }

---
## Plumbing Commands

- Werden selten benötigt
- Einige jedoch hilfreich zum Verständnis:
```sh{1|2-4|5,6|7}
git cat-file        # Details eines Git-Objektes für ein Hash ausgeben.
git rev-parse       # Revisionsspezifikation (z.B. HEAD, master^, HEAD..master)
                    #   parsen und je nach Optionen als Hash oder
                    #   menschenlesbar ausgeben.
git name-rev        # Lesbaren Namen aus Hash einer Revisionsspezifikation
                    #   anzeigen.
git hash-object     # Hash aus einem Objekt (z.B. Datei) erzeugen.
```

{{% /section %}}
