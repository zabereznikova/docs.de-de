---
ms.openlocfilehash: 6bb3b11ef4e4cb6f6a039c97911b0acca862fe6f
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065160"
---
### <a name="ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a>CA2247: Das Argument für den Konstruktor „TaskCompletionSource“ muss ein TaskCreationOptions-Wert sein

Die .NET-Codeanalyseregel [CA2247](/visualstudio/code-quality/ca2247) wird ab .NET 5.0 standardmäßig aktiviert. Sie erzeugt eine Buildwarnung für Aufrufe des Konstruktors <xref:System.Threading.Tasks.TaskCompletionSource%601>, die ein Argument des Typs <xref:System.Threading.Tasks.TaskContinuationOptions> übergeben.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../docs/fundamentals/productivity/code-analysis.md). Mehrere dieser Regeln, einschließlich [CA2247](/visualstudio/code-quality/ca2247), werden standardmäßig aktiviert. Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.

Die Regel CA2247 findet Aufrufe des Konstruktors <xref:System.Threading.Tasks.TaskCompletionSource%601>, die ein Argument des Typs <xref:System.Threading.Tasks.TaskContinuationOptions> übergeben. Der Typ <xref:System.Threading.Tasks.TaskCompletionSource%601> verfügt über einen Konstruktor, der einen <xref:System.Threading.Tasks.TaskCreationOptions>-Wert annimmt, und einen weiteren Konstruktor, der eine <xref:System.Object>-Klasse akzeptiert. Wenn Sie versehentlich einen <xref:System.Threading.Tasks.TaskContinuationOptions>-Wert anstelle eines <xref:System.Threading.Tasks.TaskCreationOptions>-Werts übergeben, wird der Konstruktor mit dem <xref:System.Object>-Parameter zur Laufzeit aufgerufen. Ihr Code wird kompiliert und ausgeführt, später jedoch nicht das beabsichtigte Verhalten aufweisen.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 8

#### <a name="recommended-action"></a>Empfohlene Aktion

- Ersetzen Sie das Argument <xref:System.Threading.Tasks.TaskContinuationOptions> durch den entsprechenden <xref:System.Threading.Tasks.TaskCreationOptions>-Wert. Unterdrücken Sie diese Warnung nicht, da sie fast immer auf einen Fehler in Ihrem Code hinweist. Weitere Informationen finden Sie unter [CA2247](/visualstudio/code-quality/ca2247).

- Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren. Weitere Informationen finden unter [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Category

Codeanalyse

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

#### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

-->
