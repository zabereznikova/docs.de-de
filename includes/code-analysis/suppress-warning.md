---
ms.openlocfilehash: b26e346f7076a57aef8ae7587ab1222b4100a323
ms.sourcegitcommit: 7e42488c2f8f63f6d499b5f8fb1dec5bac9ad254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957935"
---
## <a name="suppress-a-warning"></a><span data-ttu-id="6cbdb-101">Unterdrücken einer Warnung</span><span class="sxs-lookup"><span data-stu-id="6cbdb-101">Suppress a warning</span></span>

<span data-ttu-id="6cbdb-102">Um einen Regelverstoß zu unterdrücken, legen Sie die Option Schweregrad für die jeweilige Regel-ID `none` in einer Editor config-Datei auf fest.</span><span class="sxs-lookup"><span data-stu-id="6cbdb-102">To suppress a rule violation, set the severity option for the specific rule ID to `none` in an EditorConfig file.</span></span> <span data-ttu-id="6cbdb-103">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6cbdb-103">For example:</span></span>

```ini
[*.{cs,vb}]
dotnet_diagnostic.CA1822.severity = none
```

<span data-ttu-id="6cbdb-104">Visual Studio bietet zusätzliche Möglichkeiten, Warnungen von Code Analyse Regeln zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="6cbdb-104">Visual Studio provides additional ways to suppress warnings from code analysis rules.</span></span> <span data-ttu-id="6cbdb-105">Weitere Informationen finden Sie unter unter [drücken von Verletzungen](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations).</span><span class="sxs-lookup"><span data-stu-id="6cbdb-105">For more information, see [Suppress violations](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations).</span></span>

<span data-ttu-id="6cbdb-106">Weitere Informationen zu Schweregraden von Regeln finden Sie unter [Konfigurieren des Regel schwere](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level)Grads.</span><span class="sxs-lookup"><span data-stu-id="6cbdb-106">For more information about rule severities, see [Configure rule severity](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level).</span></span>
