---
title: Code Analyse in .net
titleSuffix: ''
description: Erfahren Sie mehr über die Quell Code Analyse im .NET SDK.
ms.date: 08/22/2020
ms.topic: overview
ms.custom: updateeachrelease
helpviewer_keywords:
- code analysis
- code analyzers
ms.openlocfilehash: ca3a9cb914befbc8e0982070b818b27ee3143793
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "96592013"
---
# <a name="overview-of-net-source-code-analysis"></a>Übersicht über die Analyse von .NET-Quellcode

Die Analysetools für die .NET-Compilerplattform (Roslyn) untersuchen Ihren C#- oder Visual Basic-Code auf Probleme hinsichtlich Codequalität und Codeformat. Ab .NET 5.0 sind diese Analysetools im .NET SDK enthalten. (Bisher haben Sie Code Qualitätsanalysen als [nuget-Paket](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers)installiert, und Codestil-Analysen wurden mit Visual Studio installiert.)

- [Code Qualitätsanalyse ("CAXXXX"-Regeln)](#code-quality-analysis)
- [Code Format Analyse ("idexxxx"-Regeln)](#code-style-analysis)

Wenn Regelverstöße von einem Analyzer gefunden werden, werden Sie abhängig von der [Konfiguration](configuration-options.md)der einzelnen Regeln als Vorschlag, Warnung oder Fehler gemeldet. Code Analyse Verstöße werden mit dem Präfix "ca" oder "IDE" angezeigt, um Sie von Compilerfehlern zu unterscheiden.

> [!TIP]
>
> - Sie können auch Analysemodule von Drittanbietern installieren, z. b. [StyleCop](https://www.nuget.org/packages/StyleCop.Analyzers/), [roslynator](https://www.nuget.org/packages/Roslynator.Analyzers/), [xUnit](https://www.nuget.org/packages/xunit.analyzers/) [Analyzer und Sonar Analyzer](https://www.nuget.org/packages/SonarAnalyzer.CSharp/).
> - Wenn Sie Visual Studio verwenden, verfügen viele Analyzer-Regeln über zugeordnete *Code Korrekturen* , die Sie anwenden können, um das Problem zu beheben. Code Korrekturen werden im Glühbirnen Symbol-Menü angezeigt.

## <a name="code-quality-analysis"></a>Analyse der Codequalität

_Regeln für die Code Qualitätsanalyse ("ca")_ untersuchen ihren c#-oder Visual Basic-Code auf Sicherheit, Leistung, Entwurf und andere Probleme. Die Analyse ist standardmäßig für Projekte aktiviert, die auf .net 5,0 oder höher ausgerichtet sind. Sie können die Code Analyse für Projekte aktivieren, die auf frühere .NET-Versionen abzielen, indem Sie die [enablenetanalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) -Eigenschaft auf festlegen `true` . Sie können die Code Analyse für Ihr Projekt auch deaktivieren, indem Sie `EnableNETAnalyzers` auf festlegen `false` .

> [!TIP]
> In Visual Studio können Sie die Code Analyse mithilfe der Projekt Eigenschaftenfenster aktivieren oder deaktivieren. Um auf das Projekt Eigenschaftenfenster zuzugreifen, klicken Sie mit der rechten Maustaste auf ein Projekt in Projektmappen-Explorer, und wählen Sie **Eigenschaften** aus. Wählen Sie als nächstes die Registerkarte **Code Analyse** aus, und aktivieren oder deaktivieren Sie dann das Kontrollkästchen, um **.net-Analysen zu aktivieren**.

### <a name="enabled-rules"></a>Aktivierte Regeln

Die folgenden Regeln sind standardmäßig in .net 5,0 Preview 8 aktiviert.

| Diagnose-ID | Category | Schweregrad | BESCHREIBUNG |
| - | - | - | - |
| [CA1416](/visualstudio/code-quality/ca1416) | Interoperabilität | Warnung | Analysetool für die Plattformkompatibilität |
| [CA1417](/visualstudio/code-quality/ca1417) | Interoperabilität | Warnung | Nicht `OutAttribute` für Zeichen folgen Parameter für P/Aufrufe verwenden |
| [CA1831](/visualstudio/code-quality/ca1831) | Leistung | Warnung | Verwenden Sie `AsSpan` anstelle von Bereichs basierten indexatoren für Zeichen folgen, wenn dies angebracht ist. |
| [CA2013](/visualstudio/code-quality/ca2013) | Zuverlässigkeit | Warnung | Nicht `ReferenceEquals` mit Werttypen verwenden |
| [CA2014](/visualstudio/code-quality/ca2014) | Zuverlässigkeit | Warnung | Nicht `stackalloc` in Schleifen verwenden |
| [CA2015](/visualstudio/code-quality/ca2015) | Zuverlässigkeit | Warnung | Finalizer nicht für Typen definieren, die von abgeleitet sind <xref:System.Buffers.MemoryManager%601> |
| [CA2200](/visualstudio/code-quality/ca2200) | Verbrauch | Warnung | Erneut ausführen, um Stapeldetails beizubehalten.
| [CA2247](/visualstudio/code-quality/ca2247) | Verbrauch | Warnung | Argument, das an den TaskCompletionSource-Konstruktor übergeben wurde, sollte <xref:System.Threading.Tasks.TaskCreationOptions> Enumeration anstelle von <xref:System.Threading.Tasks.TaskContinuationOptions> |

Sie können den Schweregrad dieser Regeln ändern, um Sie zu deaktivieren oder auf Fehler zu erhöhen.

Eine vollständige Liste der verfügbaren Code Qualitätsregeln finden Sie unter [Code Qualitätsregeln](quality-rules/index.md).

### <a name="enable-additional-rules"></a>Aktivieren zusätzlicher Regeln

Ab .NET 5.0 RC2 umfasst das .NET SDK alle [Codequalitätsregeln für Zertifizierungsstellen](/visualstudio/code-quality/code-analysis-for-managed-code-warnings). Eine vollständige Liste der Regeln, die in jeder .NET SDK-Version enthalten sind, finden Sie unter [Analyzer Releases](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md).

#### <a name="default-analysis-mode"></a>Standardanalyse Modus

Im Standardanalyse Modus sind einige Regeln [standardmäßig](#enabled-rules) als Buildwarnungen aktiviert. Einige andere Regeln sind standardmäßig nur als Visual Studio-IDE-Vorschläge mit entsprechenden Code Korrekturen aktiviert. Die übrigen Regeln sind standardmäßig deaktiviert. Die [vollständige Liste der Regeln](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md) schließt den Standard Schweregrad jeder Regel ein und gibt an, ob die Regel standardmäßig im Standardanalyse Modus aktiviert ist.

#### <a name="custom-analysis-mode"></a>Benutzerdefinierter Analysemodus

Sie können [Code Analyse Regeln konfigurieren](configuration-options.md) , um eine einzelne Regel oder eine Kategorie von Regeln zu aktivieren oder zu deaktivieren. Außerdem können Sie die [analysismode](../../core/project-sdk/msbuild-props.md#analysismode) -Eigenschaft verwenden, um zu einem der folgenden benutzerdefinierten Analyse Modi zu wechseln:

- _Aggressiver_ oder _Opt-out-_ Modus: alle Regeln sind standardmäßig als Buildwarnungen aktiviert. Sie können einzelne Regeln [deaktivieren](configuration-options.md).
- _Konservativer_ oder _Opt-in-_ Modus: alle Regeln sind standardmäßig deaktiviert. Sie können einzelne Regeln [aktivieren](configuration-options.md).

### <a name="treat-warnings-as-errors"></a>Warnungen als Fehler behandeln

Wenn Sie das- `-warnaserror` Flag verwenden, wenn Sie die Projekte erstellen, werden alle Code Analyse Warnungen auch als Fehler behandelt. Wenn Sie nicht möchten, dass Code Qualitäts Warnungen (CAXXXX) als Fehler behandelt werden `-warnaserror` , können Sie die `CodeAnalysisTreatWarningsAsErrors` MSBuild-Eigenschaft `false` in der Projektdatei auf festlegen.

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

Sie sehen weiterhin alle Code Analyse Warnungen, aber Sie werden Ihren Build nicht unterbrechen.

### <a name="latest-updates"></a>Neueste Updates

Standardmäßig erhalten Sie die neuesten Code Analyse Regeln und Standardregel Schweregrade, wenn Sie ein Upgrade auf neuere Versionen des .NET SDK durchführen. Wenn Sie dieses Verhalten nicht wünschen, z. b. Wenn Sie sicherstellen möchten, dass keine neuen Regeln aktiviert oder deaktiviert sind, können Sie es mit einer der folgenden Methoden außer Kraft setzen:

- Legen Sie die `AnalysisLevel` MSBuild-Eigenschaft auf einen bestimmten Wert fest, um die Warnungen für diese Gruppe zu sperren. Wenn Sie ein Upgrade auf ein neueres SDK durchführen, erhalten Sie weiterhin Fehlerbehebungen für diese Warnungen, aber es werden keine neuen Warnungen aktiviert, und vorhandene Warnungen werden nicht deaktiviert. Fügen Sie z. b. den folgenden Eintrag in die Projektdatei ein, um den Satz von Regeln für die zu sperren, die mit Version 5,0 des .NET SDK ausgeliefert werden.

  ```xml
  <PropertyGroup>
    <AnalysisLevel>5.0</AnalysisLevel>
  </PropertyGroup>
  ```

  > [!TIP]
  > Der Standardwert für die- `AnalysisLevel` Eigenschaft ist. dies `latest` bedeutet, dass Sie immer die neuesten Code Analyse Regeln erhalten, wenn Sie zu neueren Versionen des .NET SDK wechseln.

  Weitere Informationen und eine Liste möglicher Werte finden Sie unter [analysislevel](../../core/project-sdk/msbuild-props.md#analysislevel).

- Installieren Sie das [nuget-Paket Microsoft. Code Analysis. netanalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) , um Regel Updates von .NET SDK-Updates zu entkoppeln. Durch das Installieren des Pakets werden die integrierten SDK-Analysen deaktiviert, und es wird eine Buildwarnung generiert, wenn das SDK eine neuere Analyzer-Assemblyversion enthält, als das nuget-Paket.

## <a name="code-style-analysis"></a>Code Format Analyse

[Code Format Analyse](/visualstudio/ide/editorconfig-code-style-settings-reference) ("idexxxx"-Regeln) ermöglicht es Ihnen, konsistentes Codeformat in Ihrer Codebasis zu definieren und zu verwalten. Im folgenden sind die Standardeinstellungen aufgeführt:

- Befehlszeilenbuild: die Code Format Analyse ist standardmäßig für alle .net-Projekte in Befehlszeilenbuilds deaktiviert.
- Visual Studio: die Code Format Analyse ist standardmäßig für alle .net-Projekte in Visual Studio aktiviert, wenn [schnelle Aktionen im Code umgestaltet](/visualstudio/ide/code-generation-in-visual-studio)werden.

Ab .net 5,0 rc2 können Sie die Code Format Analyse für den Build aktivieren, sowohl in der Befehlszeile als auch in Visual Studio. Code Format Verletzungen werden als Warnungen oder Fehler mit einem Präfix "IDE" angezeigt. Dies ermöglicht es Ihnen, konsistente Code Stile zum Zeitpunkt der Erstellung zu erzwingen.

> [!NOTE]
> Die Funktion zur Analyse des Code Stils ist experimentell und kann sich zwischen den Versionen von .net 5 und .net 6 ändern.

Schritte zum Aktivieren der Code Format Analyse bei Build:

1. Legen Sie die MSBuild-Eigenschaft [enforcecodestyleinbuild](../../core/project-sdk/msbuild-props.md#enforcecodestyleinbuild) auf fest `true` .

1. [Konfigurieren](configuration-options.md) Sie in einer *Editor config* -Datei jede "IDE"-codestilregel, die Sie auf dem Build ausführen möchten, als Warnung oder Fehler. Zum Beispiel:

   ```ini
   [*.{cs,vb}]
   # IDE0040: Accessibility modifiers required (escalated to a build warning)
   dotnet_diagnostic.IDE0040.severity = warning
   ```

   Alternativ können Sie die gesamte Kategorie "Style" standardmäßig als Warnung oder Fehler konfigurieren und dann selektiv Regeln deaktivieren, die Sie nicht bei Build ausführen möchten. Zum Beispiel:

   ```ini
   [*.{cs,vb}]

   # Default severity for analyzer diagnostics with category 'Style' (escalated to build warnings)
   dotnet_analyzer_diagnostic.category-Style.severity = warning

   # IDE0040: Accessibility modifiers required (disabled on build)
   dotnet_diagnostic.IDE0040.severity = silent
   ```

## <a name="suppress-a-warning"></a>Unterdrücken einer Warnung

Legen Sie die Option Schweregrad für diese Regel-ID `none` in einer Editor config-Datei auf fest, um eine Regelverletzung zu unterdrücken. Zum Beispiel:

```ini
dotnet_diagnostic.CA1822.severity = none
```

Visual Studio bietet zusätzliche Möglichkeiten, Warnungen von Code Analyse Regeln zu unterdrücken. Weitere Informationen finden Sie unter unter [drücken von Verletzungen](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations).

Weitere Informationen zu Schweregraden von Regeln finden Sie unter [Konfigurieren des Regel schwere](configuration-options.md#severity-level)Grads.

## <a name="see-also"></a>Siehe auch

- [Referenz zur Code Qualitätsanalyse Regel](quality-rules/index.md)
- [Regel Referenz für Code Format Analyse](style-rules/index.md)
- [Codeanalyse in Visual Studio](/visualstudio/code-quality/roslyn-analyzers-overview)
- [.NET Compiler Platform SDK](../../csharp/roslyn-sdk/index.md)
- [Tutorial: Schreiben Ihres ersten Analysetools und Codefixes](../../csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix.md)
