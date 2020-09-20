---
ms.openlocfilehash: b01424c63d6e7956127bf889c53422b60ba2f219
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065163"
---
### <a name="ca2013-do-not-use-referenceequals-with-value-types"></a>CA2013: Verwenden Sie ReferenceEquals nicht mit Werttypen.

Die .NET-Codeanalyseregel [CA2013](/visualstudio/code-quality/ca2013) wird ab .NET 5.0 standardmäßig aktiviert. Sie erzeugt eine Buildwarnung für Code, in dem <xref:System.Object.ReferenceEquals(System.Object,System.Object)> verwendet wird, um einen oder mehrere Werttypen auf Gleichheit zu überprüfen.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../docs/fundamentals/productivity/code-analysis.md). Einige dieser Regeln, darunter [CA2013](/visualstudio/code-quality/ca2013), sind standardmäßig aktiviert. Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.

Die Regel CA2013 ermittelt Instanzen, bei denen <xref:System.Object.ReferenceEquals(System.Object,System.Object)> verwendet wird, um einen oder mehrere Werttypen auf Gleichheit zu überprüfen. Das Überprüfen von Werttypen auf Gleichheit auf diese Weise kann zu falschen Ergebnissen führen, da die Werte vor dem Vergleich geschachtelt werden. <xref:System.Object.ReferenceEquals(System.Object,System.Object)> gibt `false` zurück, auch wenn die verglichenen Werte dieselbe Instanz eines Werttyps darstellen.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 8

#### <a name="recommended-action"></a>Empfohlene Aktion

- Ändern Sie den Code so, dass ein geeigneter Gleichheitsoperator verwendet wird, z. B. `==`. Sie sollten diese Warnung nicht unterdrücken.

- Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren. Weitere Informationen finden unter [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Category

Codeanalyse

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

-->
