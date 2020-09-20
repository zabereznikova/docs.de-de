---
ms.openlocfilehash: 4e937f56f6315ce2abf76dd56989f4d2c4059f22
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065161"
---
### <a name="ca1831-use-asspan-instead-of-range-based-indexers-for-string"></a>CA1831: Anstelle von bereichsbasierten Indexern AsSpan für Zeichenfolgen verwenden

Die .NET-Codeanalyseregel [CA1831](/visualstudio/code-quality/ca1831) wird ab .NET 5.0 standardmäßig aktiviert. Sie erzeugt eine Buildwarnung für Code, bei dem ein auf <xref:System.Range> basierender Indexer für eine Zeichenfolge verwendet wird, aber keine Kopie vorgesehen war.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../docs/fundamentals/productivity/code-analysis.md). Mehrere dieser Regeln, einschließlich [CA1831](/visualstudio/code-quality/ca1831), werden standardmäßig aktiviert. Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.

Die Regel CA1831 ermittelt Instanzen, bei denen ein auf <xref:System.Range> basierender Indexer für eine Zeichenfolge verwendet wird, aber keine Kopie vorgesehen war. Wenn der auf <xref:System.Range> basierende Indexer direkt für eine Zeichenfolge verwendet wird, um eine implizite Umwandlung durchzuführen, wird eine überflüssige Kopie des angeforderten Zeichenfolgenabschnitts erstellt. Beispiel:

```csharp
ReadOnlySpan<char> slice = str[1..3];
```

Laut CA1831 soll der auf <xref:System.Range> basierende Indexer stattdessen für eine *Spanne* der Zeichenfolge verwendet werden. Zum Beispiel:

```csharp
ReadOnlySpan<char> slice = str.AsSpan()[1..3];
```

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 8

#### <a name="recommended-action"></a>Empfohlene Aktion

- Rufen Sie <xref:System.MemoryExtensions.AsSpan(System.String)> oder <xref:System.MemoryExtensions.AsMemory(System.String)> vor dem auf <xref:System.Range> basierenden Indexer auf, um Ihren Code zu korrigieren und unnötige Zuteilungen zu vermeiden. Beispiel:

  ```csharp
  ReadOnlySpan<char> slice = str.AsSpan()[1..3];
  ```

- Wenn Sie Ihren Code nicht ändern möchten, können Sie die Regel deaktivieren, indem Sie ihren Schweregrad auf `suggestion` oder `none` festlegen. Weitere Informationen finden Sie unter [Konfigurieren von Codeanalyseregeln](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md).

- Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren. Weitere Informationen finden unter [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Category

Codeanalyse

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Range?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Range`

-->
