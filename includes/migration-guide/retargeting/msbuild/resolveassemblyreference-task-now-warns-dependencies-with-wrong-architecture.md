---
ms.openlocfilehash: 4d410811095786b33580d25f6c6eab3ac2f27148
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616063"
---
### <a name="resolveassemblyreference-task-now-warns-of-dependencies-with-the-wrong-architecture"></a>Die ResolveAssemblyReference-Aufgabe warnt jetzt vor Abhängigkeiten von der falschen Architektur

#### <a name="details"></a>Details

Die Aufgabe gibt die Warnung MSB3270 aus, die angibt, dass ein Verweis oder eine seiner Abhängigkeiten nicht der Architektur der App entspricht. Dies erfolgt z. B., wenn eine App, die mit der `AnyCPU`-Option kompiliert wurde, einen x86-Verweis enthält. Ein solches Szenario kann einen App-Fehler zur Laufzeit ergeben (in diesem Fall, wenn die App als x64-Prozess bereitgestellt wird).

#### <a name="suggestion"></a>Vorschlag

Es gibt zwei Bereiche mit Auswirkungen:

- Bei der Neukompilierung werden Warnungen generiert, die nicht angezeigt wurden, als die App mit einer früheren Version von MSBuild kompiliert wurde. Da die Warnung eine potenzielle Quelle des Laufzeitfehlers angibt, sollte sie untersucht werden.
- Wenn Warnungen wie Fehler behandelt werden, kann die Anwendung nicht kompiliert werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.5.1       |
| Typ    | Neuzuweisung |
