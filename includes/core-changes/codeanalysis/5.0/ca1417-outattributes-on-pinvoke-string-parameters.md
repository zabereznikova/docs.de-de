---
ms.openlocfilehash: ada458ffeeba95d4989507f90c789b159f359797
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065157"
---
### <a name="ca1417-outattribute-on-string-parameter-for-pinvoke"></a>CA1417: OutAttribute für Zeichenfolgenparameter für P/Invoke

Die .NET-Codeanalyseregel [CA1417](/visualstudio/code-quality/ca1417) ist ab .NET 5.0 standardmäßig aktiviert. Sie erzeugt eine Buildwarnung für alle Methodendefinitionen für [Plattformaufrufe (P/Invoke)](../../../../docs/standard/native-interop/pinvoke.md), bei denen ein <xref:System.String>-Parameter im Wert übergeben und mit <xref:System.Runtime.InteropServices.OutAttribute> gekennzeichnet wird.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../docs/fundamentals/productivity/code-analysis.md). Einige dieser Regeln, darunter [CA1417](/visualstudio/code-quality/ca1417), sind standardmäßig aktiviert. Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.

Die Regel CA1417 kennzeichnet [P/Invoke](../../../../docs/standard/native-interop/pinvoke.md)-Methodendefinitionen, bei denen ein <xref:System.String>-Parameter mit dem Attribut <xref:System.Runtime.InteropServices.OutAttribute> gekennzeichnet und im Wert übergeben wird. Beispiel:

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

Die .NET-Runtime verwaltet eine als Internpool bezeichnete Tabelle, die einen einzelnen Verweis auf jedes eindeutige Zeichenfolgenliteral in einem Programm enthält. Wenn eine mit <xref:System.Runtime.InteropServices.OutAttribute> gekennzeichnete internalisierte Zeichenfolge im Wert an eine P/Invoke-Methode übergeben wird, kann die Runtime destabilisiert werden. Weitere Informationen zur Internalisierung von Zeichenfolgen finden Sie in den Hinweisen zu <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 8

#### <a name="recommended-action"></a>Empfohlene Aktion

- Wenn Sie geänderte Zeichenfolgendaten zurück zum Aufrufer marshallen müssen, übergeben Sie die Zeichenfolge stattdessen in einem Verweis.

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(out string s);
  ```

- Wenn Sie geänderte Zeichenfolgendaten nicht zurück zum Aufrufer marshallen müssen, entfernen Sie einfach <xref:System.Runtime.InteropServices.OutAttribute>.

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(string s);
  ```

  Weitere Informationen finden Sie unter [CA1417](/visualstudio/code-quality/ca1417).

- Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren. Weitere Informationen finden unter [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Category

Codeanalyse

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
