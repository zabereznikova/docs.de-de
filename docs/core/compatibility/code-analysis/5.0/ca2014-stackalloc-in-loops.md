---
title: 'Breaking Change: CA2014: Verwenden Sie stackalloc nicht in Schleifen.'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, der durch die Aktivierung der Codeanalyseregel „CA2014“ ausgelöst wird.
ms.date: 09/03/2020
ms.openlocfilehash: 7ad6203c0edd930bbbe43cdb8df0413cba833d8e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759191"
---
# <a name="warning-ca2014-do-not-use-stackalloc-in-loops"></a>Warnung CA2014: Verwenden Sie stackalloc nicht in Schleifen.

Die .NET-Codeanalyseregel [CA2014](/visualstudio/code-quality/ca2014) wird ab .NET 5.0 standardmäßig aktiviert. Sie erzeugt eine Buildwarnung für jeden C#-Code, in dem ein [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md)-Ausdruck innerhalb einer Schleife verwendet wird.

## <a name="change-description"></a>Änderungsbeschreibung

Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../fundamentals/code-analysis/overview.md). Mehrere dieser Regeln, einschließlich [CA2014](/visualstudio/code-quality/ca2014), werden standardmäßig aktiviert. Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.

Die Regel CA2014 sucht nach C#-Code, in dem ein [stackalloc-Ausdruck](../../../../csharp/language-reference/operators/stackalloc.md) innerhalb einer Schleife verwendet wird. Mit [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) wird Speicher aus dem aktuellen Stapelrahmen belegt. Der Speicher wird erst wieder freigegeben, wenn der aktuelle Methodenaufruf zurückgegeben wird. Dies kann zu Stapelüberläufen führen. Da Ausnahmen von Stapelüberläufen nicht abgefangen werden können, wird die App im Falle eines Stapelüberlaufs beendet.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

- Verwenden Sie [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) nicht innerhalb von Schleifen. Weisen Sie den Speicherblock außerhalb der Schleife zu, und verwenden Sie ihn innerhalb der Schleife wieder. Weitere Informationen finden Sie unter [CA2014](/visualstudio/code-quality/ca2014).

- Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren. Weitere Informationen finden unter [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
