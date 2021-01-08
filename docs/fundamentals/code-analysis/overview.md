---
title: Code Analyse in .net
titleSuffix: ''
description: Erfahren Sie mehr über die Quell Code Analyse im .NET SDK.
ms.date: 12/04/2020
ms.topic: overview
ms.custom: updateeachrelease
helpviewer_keywords:
- code analysis
- code analyzers
ms.openlocfilehash: 80815b5913ad72756de503209b52e8848dd708bf
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025080"
---
# <a name="overview-of-net-source-code-analysis"></a>Übersicht über die Analyse von .NET-Quellcode

Die Analysetools für die .NET-Compilerplattform (Roslyn) untersuchen Ihren C#- oder Visual Basic-Code auf Probleme hinsichtlich Codequalität und Codeformat. Ab .net 5,0 sind diese Analysen im .NET SDK enthalten und müssen nicht separat installiert werden. Wenn Ihr Projekt auf .net 5 oder höher ausgerichtet ist, ist die Code Analyse standardmäßig aktiviert. Wenn das Projekt eine andere .NET-Implementierung als Ziel hat, z. b. .net Core, .NET Standard oder .NET Framework, müssen Sie die Code Analyse manuell aktivieren, indem Sie die [enablenetanalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) -Eigenschaft auf festlegen `true` .

Wenn Sie nicht zum .net 5 + SDK wechseln möchten oder wenn Sie ein auf einem nuget-Paket basierendes Modell bevorzugen, sind die Analysetools auch im [nuget-Paket Microsoft. Code Analysis. netanalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.NetAnalyzers)verfügbar. Möglicherweise bevorzugen Sie ein Paket basiertes Modell für Bedarfs gesteuerte Versions Aktualisierungen.

> [!NOTE]
> .Net-Analysen sind Ziel Framework-agnostisch. Das heißt, das Projekt muss keine bestimmte .NET-Implementierung als Ziel haben. Die Analysen funktionieren für Projekte, die auf `net5.0` und frühere Versionen von .net abzielen, z `netcoreapp3.1` `net472` . b. und.

Wenn Regelverstöße von einem Analyzer gefunden werden, werden Sie abhängig von der [Konfiguration](configuration-options.md)der einzelnen Regeln als Vorschlag, Warnung oder Fehler gemeldet. Code Analyse Verstöße werden mit dem Präfix "ca" oder "IDE" angezeigt, um Sie von Compilerfehlern zu unterscheiden.

## <a name="code-quality-analysis"></a>Analyse der Codequalität

Regeln für die *Code Qualitätsanalyse* ("CAXXXX") untersuchen ihren c#-oder Visual Basic-Code auf Sicherheit, Leistung, Entwurf und andere Probleme. Die Analyse ist standardmäßig für Projekte aktiviert, die auf .net 5,0 oder höher ausgerichtet sind. Sie können die Code Analyse für Projekte aktivieren, die auf frühere .NET-Versionen abzielen, indem Sie die [enablenetanalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) -Eigenschaft auf festlegen `true` . Sie können die Code Analyse für Ihr Projekt auch deaktivieren, indem Sie `EnableNETAnalyzers` auf festlegen `false` .

> [!TIP]
> Wenn Sie Visual Studio verwenden:
>
> - Viele Analyzer-Regeln verfügen über zugeordnete *Code Korrekturen* , die Sie anwenden können, um das Problem zu beheben. Code Korrekturen werden im Glühbirnen Symbol-Menü angezeigt.
> - Sie können die Code Analyse aktivieren oder deaktivieren, indem Sie in Projektmappen-Explorer mit der rechten Maustaste auf ein Projekt klicken und **Eigenschaften** der  >  Registerkarte "**Code Analyse** " auswählen > die **.net-Analysen aktivieren**

### <a name="enabled-rules"></a>Aktivierte Regeln

Die folgenden Regeln sind standardmäßig in .net 5,0 aktiviert.

| Diagnose-ID | Kategorie | severity | BESCHREIBUNG |
| - | - | - | - |
| [CA1416](/visualstudio/code-quality/ca1416) | Interoperabilität | Warnung | Analysetool für die Plattformkompatibilität |
| [CA1417](/visualstudio/code-quality/ca1417) | Interoperabilität | Warnung | Nicht `OutAttribute` für Zeichen folgen Parameter für P/Aufrufe verwenden |
| [CA1831](/visualstudio/code-quality/ca1831) | Leistung | Warnung | Verwenden Sie `AsSpan` anstelle von Bereichs basierten indexatoren für Zeichen folgen, wenn dies angebracht ist. |
| [CA2013](/visualstudio/code-quality/ca2013) | Zuverlässigkeit | Warnung | Nicht `ReferenceEquals` mit Werttypen verwenden |
| [CA2014](/visualstudio/code-quality/ca2014) | Zuverlässigkeit | Warnung | Nicht `stackalloc` in Schleifen verwenden |
| [CA2015](/visualstudio/code-quality/ca2015) | Zuverlässigkeit | Warnung | Finalizer nicht für Typen definieren, die von abgeleitet sind <xref:System.Buffers.MemoryManager%601> |
| [CA2200](/visualstudio/code-quality/ca2200) | Usage | Warnung | Erneut ausführen, um Stapeldetails beizubehalten.
| [CA2247](/visualstudio/code-quality/ca2247) | Usage | Warnung | Argument, das an den TaskCompletionSource-Konstruktor übergeben wurde, sollte <xref:System.Threading.Tasks.TaskCreationOptions> Enumeration anstelle von <xref:System.Threading.Tasks.TaskContinuationOptions> |

Sie können den Schweregrad dieser Regeln ändern, um Sie zu deaktivieren oder auf Fehler zu erhöhen. Sie können auch [Weitere Regeln aktivieren](#enable-additional-rules).

- Eine Liste der Regeln, die in jeder .NET SDK-Version enthalten sind, finden Sie unter [Analyzer Releases](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md).
- Eine Liste aller Code Qualitätsregeln finden Sie unter [Code Qualitätsregeln](quality-rules/index.md).

### <a name="enable-additional-rules"></a>Aktivieren zusätzlicher Regeln

Der *Analysemodus* verweist auf eine vordefinierte Konfiguration der Code Analyse, bei der keine, einige oder alle Regeln aktiviert sind. Im Standardanalyse Modus wird nur eine kleine Anzahl von Regeln [als Buildwarnungen aktiviert](#enabled-rules). Sie können den Analysemodus für Ihr Projekt ändern, indem Sie die [analysismode](../../core/project-sdk/msbuild-props.md#analysismode) -Eigenschaft in der Projektdatei festlegen. Folgende Werte sind zulässig:

| Wert | BESCHREIBUNG |
| - | - |
| `AllDisabledByDefault` | Dies ist der konservativste Modus. Alle Regeln sind standardmäßig deaktiviert. Sie können einzelne Regeln [aktivieren](configuration-options.md).<br /><br />`<AnalysisMode>AllDisabledByDefault</AnalysisMode>` |
| `AllEnabledByDefault` | Dies ist der aggressivste Modus. Alle Regeln werden als Buildwarnungen aktiviert. Sie [können einzelne Regeln selektiv deaktivieren, um](configuration-options.md) Sie zu deaktivieren.<br /><br />`<AnalysisMode>AllEnabledByDefault</AnalysisMode>` |
| `Default` | Der Standardmodus, in dem einige der Regeln als Warnungen aktiviert sind, sind andere nur als Visual Studio-IDE-Vorschläge mit entsprechenden Code Behebungen aktiviert, und der Rest wird vollständig deaktiviert. Sie können einzelne Regeln selektiv aktivieren [oder](configuration-options.md) deaktivieren, um Sie zu deaktivieren.<br /><br />`<AnalysisMode>Default</AnalysisMode>` |

Informationen zum Ermitteln des Standard schwere Grads für jede verfügbare Regel und unabhängig davon, ob die Regel im Standardanalyse Modus aktiviert ist, finden Sie in der [vollständigen Liste der Regeln](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md).

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

## <a name="code-style-analysis"></a>Analyse im Code Stil

*Code-Style-* Regeln ("idexxxx") ermöglichen es Ihnen, konsistentes Codeformat in Ihrer Codebasis zu definieren und zu verwalten. Die Standardeinstellungen für die Aktivierung lauten:

- Befehlszeilenbuild: die Analyse im Code Stil ist standardmäßig für alle .net-Projekte in Befehlszeilenbuilds deaktiviert.

  Ab .net 5,0 können Sie die [Analyse im Code Stil für den Build aktivieren](#enable-on-build), sowohl in der Befehlszeile als auch in Visual Studio. Code Format Verletzungen werden als Warnungen oder Fehler mit einem Präfix "IDE" angezeigt. Dies ermöglicht es Ihnen, konsistente Code Stile zum Zeitpunkt der Erstellung zu erzwingen.

- Visual Studio: die Analyse im Code Stil ist standardmäßig für alle .net-Projekte in Visual Studio aktiviert, wenn [schnelle Aktionen im Code umgestaltet](/visualstudio/ide/code-generation-in-visual-studio)werden.

Eine vollständige Liste der Code Analyse Regeln finden Sie unter Regeln für den [Code Stil](style-rules/index.md).

### <a name="enable-on-build"></a>Beim Build aktivieren

Mit dem .net 5,0 SDK und höheren Versionen können Sie die Code Analyse bei der Erstellung über die Befehlszeile und in Visual Studio aktivieren. (Aus Leistungsgründen gelten jedoch einige [Code Stilregeln](https://github.com/dotnet/roslyn/blob/9f87b444da9c48a4d492b19f8337339056bf2b95/src/Analyzers/Core/Analyzers/EnforceOnBuildValues.cs#L95) weiterhin nur in der Visual Studio-IDE.)

Führen Sie die folgenden Schritte aus, um die Code Analyse für den Build zu aktivieren:

1. Legen Sie die MSBuild-Eigenschaft [enforcecodestyleinbuild](../../core/project-sdk/msbuild-props.md#enforcecodestyleinbuild) auf fest `true` .

1. [Konfigurieren](configuration-options.md) Sie in einer *Editor config* -Datei jede "IDE"-codestilregel, die Sie auf dem Build ausführen möchten, als Warnung oder Fehler. Beispiel:

   ```ini
   [*.{cs,vb}]
   # IDE0040: Accessibility modifiers required (escalated to a build warning)
   dotnet_diagnostic.IDE0040.severity = warning
   ```

   Alternativ können Sie die gesamte Kategorie "Style" standardmäßig als Warnung oder Fehler konfigurieren und dann selektiv Regeln deaktivieren, die Sie nicht bei Build ausführen möchten. Beispiel:

   ```ini
   [*.{cs,vb}]

   # Default severity for analyzer diagnostics with category 'Style' (escalated to build warnings)
   dotnet_analyzer_diagnostic.category-Style.severity = warning

   # IDE0040: Accessibility modifiers required (disabled on build)
   dotnet_diagnostic.IDE0040.severity = silent
   ```

> [!NOTE]
> Das Code Analyse Feature ist experimentell und kann sich zwischen den Versionen von .net 5 und .net 6 ändern.

## <a name="suppress-a-warning"></a>Unterdrücken einer Warnung

Legen Sie die Option Schweregrad für diese Regel-ID `none` in einer Editor config-Datei auf fest, um eine Regelverletzung zu unterdrücken. Beispiel:

```ini
dotnet_diagnostic.CA1822.severity = none
```

Visual Studio bietet zusätzliche Möglichkeiten, Warnungen von Code Analyse Regeln zu unterdrücken. Weitere Informationen finden Sie unter unter [drücken von Verletzungen](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations).

Weitere Informationen zu Schweregraden von Regeln finden Sie unter [Konfigurieren des Regel schwere](configuration-options.md#severity-level)Grads.

## <a name="third-party-analyzers"></a>Analysetools von Drittanbietern

Zusätzlich zu den offiziellen .net-Analysemodulen können Sie auch Drittanbieter-Analyzers installieren, z. b. [StyleCop](https://www.nuget.org/packages/StyleCop.Analyzers/), [roslynator](https://www.nuget.org/packages/Roslynator.Analyzers/), [xUnit](https://www.nuget.org/packages/xunit.analyzers/)Analyzer und [Sonar Analyzer](https://www.nuget.org/packages/SonarAnalyzer.CSharp/).

## <a name="see-also"></a>Weitere Informationen

- [Referenz zur Code Qualitätsanalyse Regel](quality-rules/index.md)
- [Regel Referenz für Code Format Analyse](style-rules/index.md)
- [Codeanalyse in Visual Studio](/visualstudio/code-quality/roslyn-analyzers-overview)
- [.NET Compiler Platform SDK](../../csharp/roslyn-sdk/index.md)
- [Tutorial: Schreiben Ihres ersten Analysetools und Codefixes](../../csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix.md)
