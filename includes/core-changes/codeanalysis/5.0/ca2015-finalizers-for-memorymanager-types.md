---
ms.openlocfilehash: 4fc31f75e8f8cdd50abebd399d9749688e6faa5a
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065158"
---
### <a name="ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a>CA2015: Keine Finalizer für von MemoryManager abgeleitete Typen definieren\<T>

Die .NET-Codeanalyseregel [CA2015](/visualstudio/code-quality/ca2015) wird ab .NET 5.0 standardmäßig aktiviert. Sie erzeugt eine Buildwarnung für alle Typen, die von <xref:System.Buffers.MemoryManager%601> abgeleitet werden und einen Finalizer definieren.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../docs/fundamentals/productivity/code-analysis.md). Mehrere dieser Regeln, einschließlich [CA2015](/visualstudio/code-quality/ca2015), werden standardmäßig aktiviert. Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.

Mithilfe der Regel CA2015 werden Typen gekennzeichnet, die von <xref:System.Buffers.MemoryManager%601> abgeleitet werden und einen Finalizer definieren. Wenn ein Finalizer zu einem von <xref:System.Buffers.MemoryManager%601> abgeleiteten Typen hinzugefügt wird, liegt wahrscheinlich ein Fehler vor. Dieser deutet darauf hin, dass eine native Ressource, die in einer <xref:System.Span%601>-Struktur abgerufen werden könnte, bereinigt wird, während sie möglicherweise noch von <xref:System.Span%601> verwendet wird.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 8

#### <a name="recommended-action"></a>Empfohlene Aktion

- Entfernen Sie die Definition des Finalizers. Weitere Informationen finden Sie unter [CA2015](/visualstudio/code-quality/ca2015).

- Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren. Weitere Informationen finden unter [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Category

Codeanalyse

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
