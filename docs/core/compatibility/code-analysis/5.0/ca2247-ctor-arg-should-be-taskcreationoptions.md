---
title: 'Breaking Change: CA2247: Das Argument für den Konstruktor „TaskCompletionSource“ muss ein TaskCreationOptions-Wert sein'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, der durch die Aktivierung der Codeanalyseregel „CA2247“ ausgelöst wird.
ms.date: 09/03/2020
ms.openlocfilehash: 323fd5a05da4dfeb68ef75d88d5d293ba01c8ade
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759473"
---
# <a name="warning-ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a>Warnung CA2247: Das Argument für den Konstruktor „TaskCompletionSource“ muss ein TaskCreationOptions-Wert sein

Die .NET-Codeanalyseregel [CA2247](/visualstudio/code-quality/ca2247) wird ab .NET 5.0 standardmäßig aktiviert. Sie erzeugt eine Buildwarnung für Aufrufe des Konstruktors <xref:System.Threading.Tasks.TaskCompletionSource%601>, die ein Argument des Typs <xref:System.Threading.Tasks.TaskContinuationOptions> übergeben.

## <a name="change-description"></a>Änderungsbeschreibung

Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../fundamentals/code-analysis/overview.md). Mehrere dieser Regeln, einschließlich [CA2247](/visualstudio/code-quality/ca2247), werden standardmäßig aktiviert. Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.

Die Regel CA2247 findet Aufrufe des Konstruktors <xref:System.Threading.Tasks.TaskCompletionSource%601>, die ein Argument des Typs <xref:System.Threading.Tasks.TaskContinuationOptions> übergeben. Der Typ <xref:System.Threading.Tasks.TaskCompletionSource%601> verfügt über einen Konstruktor, der einen <xref:System.Threading.Tasks.TaskCreationOptions>-Wert annimmt, und einen weiteren Konstruktor, der eine <xref:System.Object>-Klasse akzeptiert. Wenn Sie versehentlich einen <xref:System.Threading.Tasks.TaskContinuationOptions>-Wert anstelle eines <xref:System.Threading.Tasks.TaskCreationOptions>-Werts übergeben, wird der Konstruktor mit dem <xref:System.Object>-Parameter zur Laufzeit aufgerufen. Ihr Code wird kompiliert und ausgeführt, später jedoch nicht das beabsichtigte Verhalten aufweisen.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

- Ersetzen Sie das Argument <xref:System.Threading.Tasks.TaskContinuationOptions> durch den entsprechenden <xref:System.Threading.Tasks.TaskCreationOptions>-Wert. Unterdrücken Sie diese Warnung nicht, da sie fast immer auf einen Fehler in Ihrem Code hinweist. Weitere Informationen finden Sie unter [CA2247](/visualstudio/code-quality/ca2247).

- Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren. Weitere Informationen finden unter [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

### Category

Code analysis

-->
