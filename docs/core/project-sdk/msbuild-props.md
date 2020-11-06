---
title: MSBuild-Eigenschaften für Microsoft.NET.Sdk
description: Referenz für MSBuild-Eigenschaften und -Elemente, die vom .NET SDK verstanden werden.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: 463e2a163e6a20f5631b0ab82462614834156ae3
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063227"
---
# <a name="msbuild-reference-for-net-sdk-projects"></a>MSBuild-Referenz für .NET SDK-Projekte

Diese Seite ist eine Referenz für die MSBuild-Eigenschaften und -Elemente, mit denen Sie .NET-Projekte konfigurieren können.

> [!NOTE]
> Diese Seite befindet sich noch in Bearbeitung und führt nicht sämtlich nützlichen MSBuild-Eigenschaften für das .NET SDK auf. Eine Liste der gängigen MSBuild-Eigenschaften finden Sie unter [Gemeinsame MSBuild-Projekteigenschaften](/visualstudio/msbuild/common-msbuild-project-properties).

## <a name="framework-properties"></a>Frameworkeigenschaften

- [TargetFramework](#targetframework)
- [TargetFrameworks](#targetframeworks)
- [NetStandardImplicitPackageVersion](#netstandardimplicitpackageversion)

### <a name="targetframework"></a>TargetFramework

Die Eigenschaft `TargetFramework` gibt die Zielframeworkversion für die App an. Eine Liste gültiger Zielframeworkmoniker finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md#supported-target-frameworks).

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

Weitere Informationen finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md).

### <a name="targetframeworks"></a>TargetFrameworks

Verwenden Sie die Eigenschaft `TargetFrameworks`, wenn Sie Ihre App für mehrere Zielplattformen entwickeln möchten. Eine Liste gültiger Zielframeworkmoniker finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md#supported-target-frameworks).

> [!NOTE]
> Diese Eigenschaft wird ignoriert, wenn `TargetFramework` (Singular) angegeben ist.

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

Weitere Informationen finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md).

### <a name="netstandardimplicitpackageversion"></a>NetStandardImplicitPackageVersion

> [!NOTE]
> Diese Eigenschaft gilt nur für Projekte, die `netstandard1.x` verwenden. Sie gilt nicht für Projekte, die `netstandard2.x` verwenden.

Verwenden Sie die Eigenschaft `NetStandardImplicitPackageVersion`, wenn Sie eine Frameworkversion angeben möchten, die niedriger ist als die Metapaketversion. Die Projektdatei im folgenden Beispiel gilt für `netstandard1.3`, verwendet aber Version 1.6.0 von `NETStandard.Library`.

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a>Paketeigenschaften

Sie können Eigenschaften wie `PackageId`, `PackageVersion`, `PackageIcon`, `Title` und `Description` angeben, um das Paket zu beschreiben, das aus Ihrem Projekt erstellt wird. Informationen zu diesen und anderen Eigenschaften finden Sie unter [Paketziel](/nuget/reference/msbuild-targets#pack-target).

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a>Veröffentlichen von Eigenschaften und Elementen

- [RuntimeIdentifier](#runtimeidentifier)
- [RuntimeIdentifiers](#runtimeidentifiers)
- [TrimmerRootAssembly](#trimmerrootassembly)
- [UseAppHost](#useapphost)

### <a name="runtimeidentifier"></a>RuntimeIdentifier

Mit der Eigenschaft `RuntimeIdentifier` können Sie eine einzelne [Runtime-ID (RID)](../rid-catalog.md) für das Projekt angeben. RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung.

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers

Mit der Eigenschaft `RuntimeIdentifiers` können Sie eine durch Semikolons getrennte Liste von [Runtime-IDs (RIDs)](../rid-catalog.md) für das Projekt angeben. Verwenden Sie diese Eigenschaft, wenn die Veröffentlichung für mehrere Runtimes erfolgen muss. `RuntimeIdentifiers` wird zur Wiederherstellungszeit verwendet, um sicherzustellen, dass sich die richtigen Assets im Graph befinden.

> [!TIP]
> `RuntimeIdentifier` (Singular) kann schnellere Builds bereitstellen, wenn nur eine einzige Runtime erforderlich ist.

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a>TrimmerRootAssembly

Mit dem `TrimmerRootAssembly`-Element können Sie eine Assembly aus der [*Kürzung*](../deploying/trim-self-contained.md) ausschließen. Die Kürzung ist der Prozess, bei dem nicht verwendete Teile der Runtime aus einer gepackten Anwendung entfernt werden. In einigen Fällen können die erforderlichen Verweise durch eine Kürzung fälschlicherweise entfernt werden.

Der folgende XML-Code schließt die `System.Security`-Assembly aus der Kürzung aus.

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a>UseAppHost

Die Eigenschaft `UseAppHost` wurde in Version 2.1.400 des .NET SDK eingeführt. Sie steuert, ob eine native ausführbare Datei für eine Bereitstellung erstellt wird. Eine native ausführbare Datei ist für eigenständige Bereitstellungen erforderlich.

In .NET Core 3.0 und höheren Versionen wird standardmäßig eine frameworkabhängige ausführbare Datei erstellt. Legen Sie die Eigenschaft `UseAppHost` auf `false` fest, um die Erzeugung der ausführbaren Datei zu deaktivieren.

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

Weitere Informationen zur Bereitstellung finden Sie unter [.NET-Anwendungsbereitstellung](../deploying/index.md).

## <a name="compile-properties"></a>Kompilierungseigenschaften

- [EmbeddedResourceUseDependentUponConvention](#embeddedresourceusedependentuponconvention)
- [LangVersion](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a>EmbeddedResourceUseDependentUponConvention

Die `EmbeddedResourceUseDependentUponConvention`-Eigenschaft definiert, ob Ressourcenmanifest-Dateinamen aus Typinformationen in Quelldateien generiert werden, die mit Ressourcendateien angeordnet werden. Wenn sich beispielsweise *Form1.resx* im selben Ordner wie *Form1.cs* befindet und `EmbeddedResourceUseDependentUponConvention` auf `true` festgelegt ist, nimmt die generierte *.resources* -Datei den Namen des ersten Typs an, der in *Form1.cs* definiert ist. Wenn z. B. `MyNamespace.Form1` der erste in *Form1.cs* definierte Typ ist, lautet der generierte Dateiname *MyNamespace.Form1.resources*.

> [!NOTE]
> Wenn `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten für ein `EmbeddedResource`-Element angegeben werden, basiert der generierte Manifestdateiname für diese Ressourcendatei stattdessen auf diesen Metadaten.

Standardmäßig ist diese Eigenschaft in einem neuen .NET-Projekt auf `true` festgelegt. Wenn bei Festlegung auf `false` keine `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten für das `EmbeddedResource`-Element in der Projektdatei angegeben werden, basiert der Ressourcenmanifest-Dateiname auf dem Stammnamespace für das Projekt und dem relativen Dateipfad zur *.resx* -Datei. Weitere Informationen finden Sie unter [Benennung von Ressourcenmanifestdateien](../resources/manifest-file-names.md).

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a>LangVersion

Mit der Eigenschaft `LangVersion` können Sie eine bestimmte Version der Programmiersprache angeben. Wenn Sie beispielsweise auf C#-Vorschaufeatures zugreifen möchten, legen Sie `LangVersion` auf `preview` fest.

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

Weitere Informationen finden Sie unter [C#-Sprachversionsverwaltung](../../csharp/language-reference/configure-language-version.md#override-a-default).

## <a name="code-analysis-properties"></a>Codeanalyseeigenschaften

### <a name="analysislevel"></a>AnalysisLevel-Eigenschaft

Mit der `AnalysisLevel`-Eigenschaft können Sie eine Codeanalyseebene angeben. Wenn Sie beispielsweise auf Analysetools für Vorschaucode zugreifen möchten, legen Sie `AnalysisLevel` auf `preview` fest. Standardwert: `latest`.

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

Die verfügbaren Optionen sind in der nachfolgenden Tabelle aufgeführt.

| Wert | Bedeutung |
|-|-|
| `latest` | Die neuesten Codeanalysen, die veröffentlicht wurden, werden verwendet. Dies ist die Standardoption. |
| `preview` | Die neuesten Codeanalysetools werden verwendet, auch wenn sie sich in der Vorschau befinden. |
| `5.0` | Die Regeln, die für das .NET 5.0-Release aktiviert wurden, werden verwendet, auch wenn neuere Regeln verfügbar sind. |
| `5` | Die Regeln, die für das .NET 5.0-Release aktiviert wurden, werden verwendet, auch wenn neuere Regeln verfügbar sind. |

### <a name="analysismode"></a>AnalysisMode

Ab .NET 5.0 RC2 umfasst das .NET SDK alle [Codequalitätsregeln für Zertifizierungsstellen](../../fundamentals/code-analysis/quality-rules/index.md). Standardmäßig werden nur [einige Regeln als Buildwarnungen aktiviert](../../fundamentals/code-analysis/overview.md#enabled-rules). Mit der `AnalysisMode`-Eigenschaft können Sie die Regeln anpassen, die standardmäßig aktiviert sind. Sie können entweder zu einem aggressiveren Analysemodus (Deaktivierung) oder zu einem konservativeren Analysemodus (Aktivierung) wechseln. Wenn Sie beispielsweise alle Regeln standardmäßig als Buildwarnungen aktivieren möchten, legen Sie den Wert auf `AllEnabledByDefault` fest.

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
</PropertyGroup>
```

Die verfügbaren Optionen sind in der nachfolgenden Tabelle aufgeführt.

| Wert | Bedeutung |
|-|-|
| `Default` | Dies ist der Standardmodus, in dem bestimmte Regeln als Buildwarnungen bzw. Visual Studio-IDE-Vorschläge aktiviert sind und der Rest deaktiviert ist. |
| `AllEnabledByDefault` | Dies ist der aggressive Modus (Deaktivierung), in dem alle Regeln als Buildwarnungen aktiviert sind. Sie können einzelne Regeln [deaktivieren](../../fundamentals/code-analysis/configuration-options.md). |
| `AllDisabledByDefault` | Dies ist der konservative Modus (Aktivierung), in dem alle Regeln standardmäßig deaktiviert sind. Sie können einzelne Regeln [aktivieren](../../fundamentals/code-analysis/configuration-options.md). |

### <a name="codeanalysistreatwarningsaserrors"></a>CodeAnalysisTreatWarningsAsErrors-Eigenschaft

Mit der `CodeAnalysisTreatWarningsAsErrors`-Eigenschaft können Sie konfigurieren, ob Warnungen im Rahmen der Codequalitätsanalyse (CAxxxx) als Warnungen behandelt werden und den Build unterbrechen sollen. Wenn Sie beim Erstellen von Projekten das `-warnaserror`-Flag verwenden, werden [Warnungen im Rahmen der .NET-Codequalitätsanalyse](../../fundamentals/code-analysis/overview.md#code-quality-analysis) ebenfalls als Fehler behandelt. Wenn Warnungen bei der Codequalitätsanalyse nicht als Fehler behandelt werden sollen, können Sie die MSBuild-Eigenschaft `CodeAnalysisTreatWarningsAsErrors` in Ihrer Projektdatei auf `false` festlegen.

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a>EnableNETAnalyzers-Eigenschaft

Die [.NET-Codequalitätsanalyse](../../fundamentals/code-analysis/overview.md#code-quality-analysis) ist für Projekte, die auf .NET 5.0 oder höher ausgerichtet sind, standardmäßig aktiviert. Sie können die .NET-Codeanalyse für Projekte aktivieren, die auf frühere Versionen von .NET abzielen, indem Sie die Eigenschaft `EnableNETAnalyzers` auf `true` festlegen. Legen Sie diese Eigenschaft auf `false` fest, um die Codeanalyse in einem beliebigen Projekt zu deaktivieren.

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!TIP]
> Eine andere Möglichkeit, die .NET-Codeanalyse für Projekte zu aktivieren, die auf .NET-Versionen vor .NET 5.0 abzielen, besteht darin, die [AnalysisLevel](#analysislevel)-Eigenschaft auf `latest` festzulegen.

### <a name="enforcecodestyleinbuild"></a>EnforceCodeStyleInBuild

> [!NOTE]
> Hierbei handelt es sich aktuell um ein experimentelles Feature, das möglicherweise in den Versionen zwischen .NET 5 und .NET 6 geändert wird.

Die [.NET-Codeformatsanalyse](../../fundamentals/code-analysis/overview.md#code-style-analysis) ist beim Build für alle .NET-Projekte standardmäßig deaktiviert. Sie können die Codeformatsanalyse für .NET-Projekte aktivieren, indem Sie die `EnforceCodeStyleInBuild`-Eigenschaft auf `true` festlegen.

```xml
<PropertyGroup>
  <EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>
</PropertyGroup>
```

Alle Codeformatregeln, die als Warnungen oder Fehler [konfiguriert](../../fundamentals/code-analysis/overview.md#code-style-analysis) sind, werden beim Build ausgeführt und melden Verstöße.

## <a name="run-time-configuration-properties"></a>Runtimekonfigurationseigenschaften

Sie können manche Verhaltensweisen der Runtime konfigurieren, indem Sie die MSBuild-Eigenschaften in der Projektdatei der App angeben. Informationen zu anderen Konfigurationsmöglichkeiten für das Runtimeverhalten finden Sie unter [Konfigurationseinstellungen für die Runtime](../run-time-config/index.md).

- [ConcurrentGarbageCollection](#concurrentgarbagecollection)
- [InvariantGlobalization](#invariantglobalization)
- [RetainVMGarbageCollection](#retainvmgarbagecollection)
- [ServerGarbageCollection](#servergarbagecollection)
- [ThreadPoolMaxThreads](#threadpoolmaxthreads)
- [ThreadPoolMinThreads](#threadpoolminthreads)
- [TieredCompilation](#tieredcompilation)
- [TieredCompilationQuickJit](#tieredcompilationquickjit)
- [TieredCompilationQuickJitForLoops](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a>ConcurrentGarbageCollection

Mit der `ConcurrentGarbageCollection`-Eigenschaft wird konfiguriert, ob [die Garbage Collection im Hintergrund (parallele GC)](../../standard/garbage-collection/background-gc.md) aktiviert ist. Legen Sie den Wert auf `false` fest, um die Garbage Collection im Hintergrund zu deaktivieren. Weitere Informationen finden Sie unter [Garbage Collection im Hintergrund](../run-time-config/garbage-collector.md#background-gc).

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a>InvariantGlobalization

Mit der `InvariantGlobalization`-Eigenschaft wird konfiguriert, ob die App im *globalisierungsinvarianten Modus* ausgeführt wird, was bedeutet, dass sie keinen Zugriff auf kulturspezifische Daten hat. Legen Sie den Wert auf `true` fest, um die Ausführung im globalisierungsinvarianten Modus zu konfigurieren. Weitere Informationen finden Sie unter [Invarianter Modus](../run-time-config/globalization.md#invariant-mode).

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a>RetainVMGarbageCollection

Mit der `RetainVMGarbageCollection`-Eigenschaft wird der Garbage Collector so konfiguriert, dass gelöschte Speichersegmente in eine Standbyliste eingefügt werden, damit Sie diese zukünftig verwenden oder freigeben können. Wenn der Wert auf `true` festgelegt wird, wird der Garbage Collector angewiesen, die Segmente in eine Standbyliste einzufügen. Weitere Informationen finden Sie unter [Beibehalten der VM](../run-time-config/garbage-collector.md#retain-vm).

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a>ServerGarbageCollection

Mit der `ServerGarbageCollection`-Eigenschaft wird konfiguriert, ob die Anwendung die [Garbage Collection für Arbeitsstationen oder für Server](../../standard/garbage-collection/workstation-server-gc.md) verwendet. Legen Sie den Wert auf `true` fest, um die Garbage Collection für Server zu verwenden. Weitere Informationen finden Sie unter [Workstation und Server im Vergleich](../run-time-config/garbage-collector.md#workstation-vs-server).

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a>ThreadPoolMaxThreads

Mit der `ThreadPoolMaxThreads`-Eigenschaft wird die maximale Threadanzahl für den Arbeitsthreadpool konfiguriert. Weitere Informationen finden Sie unter [Maximale Threadanzahl](../run-time-config/threading.md#maximum-threads).

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a>ThreadPoolMinThreads

Mit der `ThreadPoolMinThreads`-Eigenschaft wird die minimale Threadanzahl für den Arbeitsthreadpool konfiguriert. Weitere Informationen finden Sie unter [Minimale Threadanzahl](../run-time-config/threading.md#minimum-threads).

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a>TieredCompilation

Mit der `TieredCompilation`-Eigenschaft wird konfiguriert, ob der JIT-Compiler (Just-in-Time) die [mehrstufige Kompilierung](../whats-new/dotnet-core-3-0.md#tiered-compilation) verwendet. Legen Sie den Wert auf `false` fest, um die mehrstufige Kompilierung zu deaktivieren. Weitere Informationen finden Sie unter [Mehrstufige Kompilierung](../run-time-config/compilation.md#tiered-compilation).

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a>TieredCompilationQuickJit

Mit der `TieredCompilationQuickJit`-Eigenschaft wird konfiguriert, ob der JIT-Compiler Quick JIT verwendet. Legen Sie den Wert auf `false` fest, um Quick JIT zu deaktivieren. Weitere Informationen finden Sie unter [Quick JIT](../run-time-config/compilation.md#quick-jit).

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a>TieredCompilationQuickJitForLoops

Mit der `TieredCompilationQuickJitForLoops`-Eigenschaft wird konfiguriert, ob der JIT-Compiler Quick JIT für Methoden mit Schleifen verwendet. Legen Sie den Wert auf `true` fest, um Quick JIT für Methoden mit Schleifen zu aktivieren. Weitere Informationen finden Sie unter [Quick JIT für Schleifen](../run-time-config/compilation.md#quick-jit-for-loops).

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a>Referenz für Eigenschaften und Elemente

- [AssetTargetFallback](#assettargetfallback)
- [PackageReference](#packagereference)
- [ProjectReference](#projectreference)
- [Verweis](#reference)
- [Wiederherstellen von Eigenschaften](#restore-properties)

### <a name="assettargetfallback"></a>AssetTargetFallback

Mit der Eigenschaft `AssetTargetFallback` können Sie zusätzliche kompatible Frameworkversionen für Projektverweise und NuGet-Pakete angeben. Wenn Sie z. B. mit `PackageReference` eine Paketabhängigkeit angeben, aber das entsprechende Paket keine Assets enthält, die mit dem `TargetFramework` Ihres Projekts kompatibel sind, kommt die Eigenschaft `AssetTargetFallback` ins Spiel. Die Kompatibilität des referenzierten Pakets wird erneut anhand jedes Zielframeworks überprüft, das in `AssetTargetFallback` angegeben ist.

Sie können die Eigenschaft `AssetTargetFallback` auf eine oder mehrere [Zielframeworkversionen](../../standard/frameworks.md#supported-target-frameworks) festlegen.

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a>PackageReference

Das `PackageReference`-Element definiert einen Verweis auf ein NuGet-Paket.

Das `Include`-Attribut gibt die Paket-ID an. Das `Version`-Attribut gibt die Version oder den Versionsbereich an. Informationen, wie Sie eine Mindestversion, Maximalversion, einen Versionsbereich oder eine exakte Versionsübereinstimmung angeben, finden Sie unter [Versionsbereiche](/nuget/concepts/package-versioning#version-ranges). Sie können auch die folgenden Metadaten zu einem Projektverweis hinzufügen: `IncludeAssets`, `ExcludeAssets` und `PrivateAssets`.

Der Codeausschnitt für die Projektdatei im folgenden Beispiel verweist auf das Paket [System.Runtime](https://www.nuget.org/packages/System.Runtime/).

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

Weitere Informationen finden Sie unter [Paketverweis in Projektdateien](/nuget/consume-packages/package-references-in-project-files).

### <a name="projectreference"></a>ProjectReference

Das `ProjectReference`-Element definiert einen Verweis auf ein anderes Projekt. Das referenzierte Projekt wird als NuGet-Paketabhängigkeit hinzugefügt, d. h., es wird genauso wie eine `PackageReference` behandelt.

Das Attribut `Include` gibt den Pfad zu dem Projekt an. Sie können auch die folgenden Metadaten zu einem Projektverweis hinzufügen: `IncludeAssets`, `ExcludeAssets` und `PrivateAssets`.

Der Codeausschnitt für die Projektdatei im folgenden Beispiel verweist auf ein Projekt namens `Project2`.

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a>Referenz

Das `Reference`-Element definiert einen Verweis auf eine Assemblydatei.

Das `Include`-Attribut gibt den Namen der Datei an, und die `HintPath`-Metadaten geben den Pfad zu der Assembly an.

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a>Wiederherstellen von Eigenschaften

Durch das Wiederherstellen eines referenzierten Pakets werden alle seine direkten Abhängigkeiten sowie alle Abhängigkeiten dieser Abhängigkeiten installiert. Sie können die Paketwiederherstellung anpassen, indem Sie Eigenschaften wie `RestorePackagesPath` und `RestoreIgnoreFailedSources` angeben. Weitere Informationen zu diesen und anderen Eigenschaften finden Sie unter [Wiederherstellungsziel](/nuget/reference/msbuild-targets#restore-target).

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a>Siehe auch

- [MSBuild-Schemareferenz](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [Gemeinsame MSBuild-Eigenschaften](/visualstudio/msbuild/common-msbuild-project-properties)
- [MSBuild-Eigenschaften für NuGet-Ziel „pack“](/nuget/reference/msbuild-targets#pack-target)
- [MSBuild-Eigenschaften für NuGet-Ziel „restore“](/nuget/reference/msbuild-targets#restore-properties)
- [Anpassen eines Builds](/visualstudio/msbuild/customize-your-build)
