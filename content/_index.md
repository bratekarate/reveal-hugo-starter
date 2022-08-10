+++
title = "Living Styleguide"
outputs = ["Reveal"]
+++

# Living Styleguide

Design-Richtlinien und Komponentenbibliothek der Commerzbank

---

{{% section %}}

{{< slide background-image="/images/thinking.gif" >}}
## Wieso?

---

## Motivation
- **Qualitätsstandard** für
    - Brand-Awareness
    - User-Experience
    - Usabiltity
    - Accessability
- **Geteiltes Know-How** statt **Inselwissen** einzelner Teams.

{{% /section %}}

---

{{% section %}}

## Kurzbeschreibung

- Der Living Styleguide (LSG) ist ein *Designsystem* zur **Vereinfachung** und **Standardisierung** der Entwicklung *webbasierter Nutzeroberflächen* innerhalb der Commerzbank.

---

## Struktur

- Sammlung von Design-Richtlinien
- Komponentenbibliothek aus LSG-Standardkomponenten in React und HTML
- Komponentenbibliothek wächst stetig und wird angepasst ==> System ist ein “Living” Styleguide

{{% /section %}}

---

{{% section %}}

## Beispiel
![coba portal](/images/portal.png)

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
{{% /section %}}

---

{{% section %}}

## Tätigkeiten

- Frontendentwicklung mit React
  - Wartung und Weiterentwicklung von UI-Komponenten
  - Entwicklung neuer UI-Komponenten
  - Refaktorisierung und Vereinheitlichung alter Programmlogik zur Nutzung modernerer React-Features

---

## Tätigkeiten (2)

- Tooling für die Entwicklung
  - Linting
  - Git Pre-commit Hooks

---

## Tätigkeiten (3)

- Testing
  - Regressionstests
  - Storybook reporting
- CI
  - OpenShift Buildoptimierung/Bugfixing
  - Umsetzung neuer OpenShift CI-Features
    - Fail-fast
    - Konfiguration über Umgebungsvariablen

{{% /section %}}

---

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
Don't forget to thank the audience.
{{% /note %}}

