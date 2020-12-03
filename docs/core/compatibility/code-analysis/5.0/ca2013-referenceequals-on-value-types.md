---
title: 'Breaking Change: CA2013: Verwenden Sie ReferenceEquals nicht mit Werttypen.'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, der durch die Aktivierung der Codeanalyseregel „CA2013“ ausgelöst wird.
ms.date: 09/03/2020
ms.openlocfilehash: ca2b845427eff547b996b577394c6859e30f50bf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759192"
---
# <a name="warning-ca2013-do-not-use-referenceequals-with-value-types"></a>Warnung CA2013: Verwenden Sie ReferenceEquals nicht mit Werttypen.

Die .NET-Codeanalyseregel [CA2013](/visualstudio/code-quality/ca2013) wird ab .NET 5.0 standardmäßig aktiviert. Sie erzeugt eine Buildwarnung für Code, in dem <xref:System.Object.ReferenceEquals(System.Object,System.Object)> verwendet wird, um einen oder mehrere Werttypen auf Gleichheit zu überprüfen.

## <a name="change-description"></a>Änderungsbeschreibung

Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../fundamentals/code-analysis/overview.md). Einige dieser Regeln, darunter [CA2013](/visualstudio/code-quality/ca2013), sind standardmäßig aktiviert. Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.

Die Regel CA2013 ermittelt Instanzen, bei denen <xref:System.Object.ReferenceEquals(System.Object,System.Object)> verwendet wird, um einen oder mehrere Werttypen auf Gleichheit zu überprüfen. Das Überprüfen von Werttypen auf Gleichheit auf diese Weise kann zu falschen Ergebnissen führen, da die Werte vor dem Vergleich geschachtelt werden. <xref:System.Object.ReferenceEquals(System.Object,System.Object)> gibt `false` zurück, auch wenn die verglichenen Werte dieselbe Instanz eines Werttyps darstellen.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

- Ändern Sie den Code so, dass ein geeigneter Gleichheitsoperator verwendet wird, z. B. `==`. Sie sollten diese Warnung nicht unterdrücken.

- Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren. Weitere Informationen finden unter [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

### Category

Code analysis

-->
