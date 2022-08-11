+++
title = "Living Styleguide"
outputs = ["Reveal"]
[logo]
src = "/images/itf_logo_white_bg.png"
+++

# Living Styleguide

Design-Richtlinien und Komponentenbibliothek der Commerzbank

{{% note %}}
Ich werde euch einen kurzen Einblick in das LSG Projekt geben.

Design-Richtlinien...
{{% /note %}}


---

{{% section %}}

{{< slide id="bgimg" background-image="/images/thinking.gif" >}}
## Wieso?

{{% note %}}
- Bevor ich darauf eingehe WAS der LSG ist:
- Wieso gibt es den LSG?
- Hintergründe, Existenzberechtigung
{{% /note %}}

---

## Motivation
- **Qualitätsstandard** für
    - Brand-Awareness
    - User-Experience
    - Usabiltity
    - Accessability
- **Geteiltes Know-How** statt **Inselwissen** einzelner Teams.

{{% note %}}
- Viele UI Projekte in der Bank
- Wildwuchs muss vermieden werden
- Qualitätsstandards sollen eingehalten werden
- Inselwissen kann Problem werden --> geteiltes Know-How angestrebt
{{% /note %}}

{{% /section %}}

---

{{% section %}}

## Kurzbeschreibung

- Der Living Styleguide (LSG) ist ein *Designsystem* zur **Vereinfachung** und **Standardisierung** der Entwicklung *webbasierter Nutzeroberflächen* innerhalb der Commerzbank.

{{% note %}}
- Aus diesen Gründen gibt es den LSG
- Vereinfachen --> Kosten reduzieren
- Standardisieren -> Qualitätsstandards
{{% /note %}}

---

## Struktur

- Sammlung von Design-Richtlinien
- Komponentenbibliothek aus LSG-Standardkomponenten in React und HTML
- Komponentenbibliothek wächst stetig und wird angepasst ==> System ist ein “Living” Styleguide

{{% note %}}
- Name LSG kann irreführend sein
- "Styleguide" -> Design-Richtlinien
- Aber: Komponentenbibliothek elementarer Bestandteil (Vereinfachung, Inselwissen)
{{% /note %}}

{{% /section %}}

---

{{% section %}}

## Beispiel
![coba portal](/images/portal.png)

{{% note %}}
- Homepage der Commerzbank
- LSG-Standardkomponenten: 
  - Productstage (Produktvorstellung, wie ein "Vorhang" verschwindet sie)
  - Button
- Kann in vielen Projekten eingesetzt werden
{{% /note %}}

Quelle: https://commerzbank.de

---

## Codebeispiel

```javascript{|2,8,10}
import React, { useState } from 'react';
import { Button } from '@lsg.components';

export function App() {
  const [count, setCount] = useState(0);

  return (
    <Button action={() => setCount(count + 1)}>
      Clicked {count} times
    </Button>
  );
}
```
(Kein Bezug zur vorherigen Beispielseite)

{{% note %}}
- Kein Bezug zur vorherigen Beispielseite --> Nur ein fiktives, simples Beispiel
- Typische React App mit funktionalen Components und Hooks
- Button wird vom LSG importiert und eingesetzt
{{% /note %}}

{{% /section %}}

---

{{% section %}}

## Tätigkeiten

- Frontendentwicklung mit React ![react logo](/images/react_logo.png)
  - Wartung und Weiterentwicklung von UI-Komponenten
  - Entwicklung neuer UI-Komponenten
  - Refaktorisierung und Vereinheitlichung alter Programmlogik zur Nutzung modernerer React-Features

{{% note %}}
- Tätigkeiten sind nicht alle zwingend erforderlich, je nach eigenem Interesse und Skills
- Sicher noch mehr Tätigkeiten relevant, dies ist meine Perspektive
- Vornehmlich React-Entwicklung
{{% /note %}}

---

## Tätigkeiten (2)

- Tooling für die Entwicklung ![tool icon](/images/tools.png)
  - Linting
  - Git Pre-commit Hooks

{{% note %}}
- Tooling immer wieder relevant
- Linting und Pre-Commit Hooks bereits eingebunden
- (Hier war ich selbst viel beteiligt)
- Aber: Es muss immer weiter optimiert und an neue Anforderungen angepasst werden.
{{% /note %}}

---

## Tätigkeiten (3)

- Testing ![test icon](/images/check.png)
  - Regressionstests
  - Storybook reporting
- CI/CD ![ci icon](/images/infinity.png)
  - OpenShift Buildoptimierung/Bugfixing
  - Umsetzung neuer OpenShift CI-Features
    - Fail-fast
    - Konfiguration über Umgebungsvariablen

{{% note %}}
- Tests wurden kürzlich erst aktiviert, viel Verbesserungspotential.
- CI ist derzeit "fertig", aber Anforderungen ändern sich.
{{% /note %}}

{{% /section %}}

---

{{% section %}}

## Technologien

- Javascript, Typescript, React
- HTML, CSS, SASS
- Nodejs, npm
- Rollup, Webpack, lerna
- Storybook, Styleguidist
- AVA, Jest
- (Stencil, Webcomponents)
- Shell, Bash, CLI
- Linux, OpenShift, Docker, TeamCity, nginx, CI/CD
{{% note %}}
- Typische Frontend-Technologien
- Bundling: Rollup relevanter, aber Webpack teils erforderlich (Storybook, Styleguidist)
- lerna für Monorepo Verwaltung
- AVA main test framework
- Shell, Bash, CLI, Linux: für OpenShift und Pre-Commit Hooks interessant
{{% /note %}}

{{% /section %}}
