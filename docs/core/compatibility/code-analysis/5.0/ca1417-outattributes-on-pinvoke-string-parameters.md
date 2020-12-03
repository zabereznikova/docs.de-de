---
title: 'Breaking Change: CA1417: OutAttribute für Zeichenfolgenparameter für P/Invoke'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, der durch die Aktivierung der Codeanalyseregel „CA1417“ ausgelöst wird.
ms.date: 09/29/2020
ms.openlocfilehash: 3316d07108ec7f9da985494413336cba6d560dc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759196"
---
# <a name="warning-ca1417-outattribute-on-string-parameter-for-pinvoke"></a>Warnung CA1417: OutAttribute für Zeichenfolgenparameter für P/Invoke

Die .NET-Codeanalyseregel [CA1417](/visualstudio/code-quality/ca1417) ist ab .NET 5.0 standardmäßig aktiviert. Sie erzeugt eine Buildwarnung für alle Methodendefinitionen für [Plattformaufrufe (P/Invoke)](../../../../standard/native-interop/pinvoke.md), bei denen ein <xref:System.String>-Parameter im Wert übergeben und mit <xref:System.Runtime.InteropServices.OutAttribute> gekennzeichnet wird.

## <a name="change-description"></a>Änderungsbeschreibung

Ab .NET 5.0 umfasst das .NET SDK [.NET-Quellcodeanalysen](../../../../fundamentals/code-analysis/overview.md). Einige dieser Regeln, darunter [CA1417](/visualstudio/code-quality/ca1417), sind standardmäßig aktiviert. Wenn Ihr Projekt Code enthält, der gegen diese Regel verstößt und dafür konfiguriert ist, Warnungen als Fehler zu interpretieren, könnte es sich hierbei um einen Breaking Change für Ihr Build handeln.

Die Regel CA1417 kennzeichnet [P/Invoke](../../../../standard/native-interop/pinvoke.md)-Methodendefinitionen, bei denen ein <xref:System.String>-Parameter mit dem Attribut <xref:System.Runtime.InteropServices.OutAttribute> gekennzeichnet und im Wert übergeben wird. Beispiel:

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

Die .NET-Runtime verwaltet eine als Internpool bezeichnete Tabelle, die einen einzelnen Verweis auf jedes eindeutige Zeichenfolgenliteral in einem Programm enthält. Wenn eine mit <xref:System.Runtime.InteropServices.OutAttribute> gekennzeichnete internalisierte Zeichenfolge im Wert an eine P/Invoke-Methode übergeben wird, kann die Runtime destabilisiert werden. Weitere Informationen zur Internalisierung von Zeichenfolgen finden Sie in den Hinweisen zu <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

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

- Legen Sie `EnableNETAnalyzers` in Ihrer Projektdatei auf `false` fest, um die Codeanalyse vollständig zu deaktivieren. Weitere Informationen finden unter [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
