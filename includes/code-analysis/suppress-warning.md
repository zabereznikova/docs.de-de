---
ms.openlocfilehash: b26e346f7076a57aef8ae7587ab1222b4100a323
ms.sourcegitcommit: 7e42488c2f8f63f6d499b5f8fb1dec5bac9ad254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957935"
---
## <a name="suppress-a-warning"></a>Unterdrücken einer Warnung

Um einen Regelverstoß zu unterdrücken, legen Sie die Option Schweregrad für die jeweilige Regel-ID `none` in einer Editor config-Datei auf fest. Beispiel:

```ini
[*.{cs,vb}]
dotnet_diagnostic.CA1822.severity = none
```

Visual Studio bietet zusätzliche Möglichkeiten, Warnungen von Code Analyse Regeln zu unterdrücken. Weitere Informationen finden Sie unter unter [drücken von Verletzungen](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations).

Weitere Informationen zu Schweregraden von Regeln finden Sie unter [Konfigurieren des Regel schwere](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level)Grads.
