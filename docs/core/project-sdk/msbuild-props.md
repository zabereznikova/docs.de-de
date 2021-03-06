---
title: MSBuild-Eigenschaften für Microsoft.NET.Sdk
description: Referenz für MSBuild-Eigenschaften und -Elemente, die vom .NET SDK verstanden werden.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: 21bbe46cf60540c01344cc8fcb82c62ff0fbbee5
ms.sourcegitcommit: 4313614f57690f9a5119a37314f0a1fd738ebda2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "98692708"
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

## <a name="publish-properties-items-and-metadata"></a>Veröffentlichen von Eigenschaften, Elementen und Metadaten

- [AppendRuntimeIdentifierToOutputPath](#appendruntimeidentifiertooutputpath)
- [AppendTargetFrameworkToOutputPath](#appendtargetframeworktooutputpath)
- [CopyLocalLockFileAssemblies](#copylocallockfileassemblies)
- [CopyToPublishDirectory](#copytopublishdirectory)
- [LinkBase](#linkbase)
- [PreserveCompilationContext](#preservecompilationcontext)
- [PreserveCompilationReferences](#preservecompilationreferences)
- [RuntimeIdentifier](#runtimeidentifier)
- [RuntimeIdentifiers](#runtimeidentifiers)
- [TrimmerRootAssembly](#trimmerrootassembly)
- [UseAppHost](#useapphost)

### <a name="copytopublishdirectory"></a>CopyToPublishDirectory

Die `CopyToPublishDirectory`-Metadaten in einem MSBuild-Element steuern, wann das Element in das Veröffentlichungsverzeichnis kopiert wird. Zulässige Werte sind `PreserveNewest`, wodurch das Element nur kopiert wird, wenn es geändert wurde, `Always`, wodurch das Element immer kopiert wird, und `Never`, wodurch das Element nie kopiert wird. Aus Leistungssicht ist `PreserveNewest` zu bevorzugen, da so inkrementelle Builds ermöglicht werden.

```xml
<ItemGroup>
  <None Update="appsettings.Development.json" CopyToOutputDirectory="PreserveNewest" CopyToPublishDirectory="PreserveNewest" />
</ItemGroup>
```

### <a name="linkbase"></a>LinkBase

Wenn ein Element sich außerhalb des Projektverzeichnisses und dessen Unterverzeichnissen befindet, verwendet das Veröffentlichungsziel die [Link-Metadaten](/visualstudio/msbuild/common-msbuild-item-metadata) des Elements, um zu bestimmen, wohin es kopiert werden soll. `Link` legt auch fest, wie Elemente außerhalb der Projektstruktur im Projektmappen-Explorer von Visual Studio angezeigt werden.

Wenn `Link` für ein Element nicht angegeben ist, das sich außerhalb der Projektstruktur befindet, wird standardmäßig der Wert `%(LinkBase)\%(RecursiveDir)%(Filename)%(Extension)` festgelegt. Mit `LinkBase` können Sie einen sinnvollen Basisordner für Elemente außerhalb der Projektstruktur angeben. Die Ordnerhierarchie des Basisordners wird mit `RecursiveDir` beibehalten. Wenn `LinkBase` nicht angegeben wird, wird das Element im `Link`-Pfad weggelassen.

```xml
<ItemGroup>
  <Content Include="..\Extras\**\*.cs" LinkBase="Shared"/>
</ItemGroup>
```

Auf der folgenden Abbildung sehen Sie, wie eine Datei, die über das Globmuster des vorherigen Elements `Include` eingefügt wird, im Projektmappen-Explorer dargestellt wird.

:::image type="content" source="media/solution-explorer-linkbase.png" alt-text="Projektmappen-Explorer zeigt Element mit LinkBase-Metadaten":::

### <a name="appendtargetframeworktooutputpath"></a>AppendTargetFrameworkToOutputPath

Die `AppendTargetFrameworkToOutputPath`-Eigenschaft steuert, ob der [Zielframeworkmoniker (TFM, Target Framework Moniker)](../../standard/frameworks.md) an den Ausgabepfad angehängt wird, der durch [OutputPath](/visualstudio/msbuild/common-msbuild-project-properties#list-of-common-properties-and-parameters) definiert wird. Das .NET SDK fügt automatisch das Zielframework und, falls vorhanden, den Runtimebezeichner an den Ausgabepfad an. Wenn Sie `AppendTargetFrameworkToOutputPath` auf `false` festlegen, wird verhindert, dass der Zielframeworkmoniker an den Ausgabepfad angefügt wird. Jedoch überschreiben sich ohne den Zielframeworkmoniker im Ausgabepfad mehrere Buildartefakte gegenseitig.

Beispielsweise wird für eine .NET 5.0-App der Ausgabepfad von `bin\Debug\net5.0` in `bin\Debug` mit der folgenden Einstellung geändert:

```xml
<PropertyGroup>
  <AppendTargetFrameworkToOutputPath>false</AppendTargetFrameworkToOutputPath>
</PropertyGroup>
```

### <a name="appendruntimeidentifiertooutputpath"></a>AppendRuntimeIdentifierToOutputPath

Die `AppendRuntimeIdentifierToOutputPath`-Eigenschaft steuert, ob der [Runtimebezeichner (RID, Runtime Identifier)](../rid-catalog.md) an den Ausgabepfad angefügt wird. Das .NET SDK fügt automatisch das Zielframework und, falls vorhanden, den Runtimebezeichner an den Ausgabepfad an. Wenn Sie `AppendRuntimeIdentifierToOutputPath` auf `false` festlegen, wird verhindert, dass der Runtimebezeichner an den Ausgabepfad angefügt wird.

Beispielsweise wird für eine .NET 5.0-App und einen Runtimebezeichner von `win10-x64` der Ausgabepfad von `bin\Debug\net5.0\win10-x64` in `bin\Debug\net5.0` mit der folgenden Einstellung geändert:

```xml
<PropertyGroup>
  <AppendRuntimeIdentifierToOutputPath>false</AppendRuntimeIdentifierToOutputPath>
</PropertyGroup>
```

### <a name="copylocallockfileassemblies"></a>CopyLocalLockFileAssemblies

Die Eigenschaft `CopyLocalLockFileAssemblies` ist nützlich für Plug-In-Projekte, die von anderen Bibliotheken abhängig sind. Wenn Sie diese Eigenschaft auf `true` festlegen, werden alle Abhängigkeiten von NuGet-Paketen in das Ausgabeverzeichnis kopiert. Das bedeutet, dass Sie die Ausgabe von `dotnet build` verwenden können, um das Plug-In auf einem beliebigen Computer auszuführen.

```xml
<PropertyGroup>
  <CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>
</PropertyGroup>
```

> [!TIP]
> Alternativ können Sie auch `dotnet publish` verwenden, um die Klassenbibliothek zu veröffentlichen. Weitere Informationen finden Sie unter [dotnet publish](../tools/dotnet-publish.md).

### <a name="preservecompilationcontext"></a>PreserveCompilationContext

Die `PreserveCompilationContext`-Eigenschaft ermöglicht es einer erstellten oder veröffentlichten Anwendung, mehr Code zur Laufzeit mit denselben Einstellungen zu kompilieren, die zum Zeitpunkt der Erstellung verwendet wurden. Die Assemblys, auf die zur Buildzeit verwiesen wird, werden in das *ref*-Unterverzeichnis des Ausgabeverzeichnisses kopiert. Die Namen der Verweisassemblys werden in der *.deps.json*-Datei der Anwendung zusammen mit den Optionen gespeichert, die an den Compiler weitergeleitet werden. Sie können diese Informationen mithilfe der Eigenschaften <xref:Microsoft.Extensions.DependencyModel.DependencyContext.CompileLibraries?displayProperty=nameWithType> und <xref:Microsoft.Extensions.DependencyModel.DependencyContext.CompilationOptions?displayProperty=nameWithType> abrufen.

Diese Funktion wird hauptsächlich intern von ASP.NET Core MVC und Razor Pages verwendet, um die Runtime-Kompilierung von Razor-Dateien zu unterstützen.

```xml
<PropertyGroup>
  <PreserveCompilationContext>true</PreserveCompilationContext>
</PropertyGroup>
```

### <a name="preservecompilationreferences"></a>PreserveCompilationReferences

Die `PreserveCompilationReferences`-Eigenschaft ähnelt der [PreserveCompilationContext](#preservecompilationcontext)-Eigenschaft, mit der Ausnahme, dass sie nur die referenzierten Assemblys in das Veröffentlichungsverzeichnis kopiert, nicht die *.deps.json*-Datei.

```xml
<PropertyGroup>
  <PreserveCompilationReferences>true</PreserveCompilationReferences>
</PropertyGroup>
```

Weitere Informationen finden Sie unter [Razor SDK-Eigenschaften](/aspnet/core/razor-pages/sdk#properties).

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

Die `UseAppHost`-Eigenschaft steuert, ob eine native ausführbare Datei für eine Bereitstellung erstellt wird. Eine native ausführbare Datei ist für eigenständige Bereitstellungen erforderlich.

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

Die `EmbeddedResourceUseDependentUponConvention`-Eigenschaft definiert, ob Ressourcenmanifest-Dateinamen aus Typinformationen in Quelldateien generiert werden, die mit Ressourcendateien angeordnet werden. Wenn sich beispielsweise *Form1.resx* im selben Ordner wie *Form1.cs* befindet und `EmbeddedResourceUseDependentUponConvention` auf `true` festgelegt ist, nimmt die generierte *.resources*-Datei den Namen des ersten Typs an, der in *Form1.cs* definiert ist. Wenn z. B. `MyNamespace.Form1` der erste in *Form1.cs* definierte Typ ist, lautet der generierte Dateiname *MyNamespace.Form1.resources*.

> [!NOTE]
> Wenn `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten für ein `EmbeddedResource`-Element angegeben werden, basiert der generierte Manifestdateiname für diese Ressourcendatei stattdessen auf diesen Metadaten.

Standardmäßig ist diese Eigenschaft in einem neuen .NET-Projekt auf `true` festgelegt. Wenn bei Festlegung auf `false` keine `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten für das `EmbeddedResource`-Element in der Projektdatei angegeben werden, basiert der Ressourcenmanifest-Dateiname auf dem Stammnamespace für das Projekt und dem relativen Dateipfad zur *.resx*-Datei. Weitere Informationen finden Sie unter [Benennung von Ressourcenmanifestdateien](../resources/manifest-file-names.md).

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

## <a name="default-item-inclusion-properties"></a>Standardeigenschaften für den Elementeinschluss

- [DefaultExcludesInProjectFolder](#defaultexcludesinprojectfolder)
- [DefaultItemExcludes](#defaultitemexcludes)
- [EnableDefaultCompileItems](#enabledefaultcompileitems)
- [EnableDefaultEmbeddedResourceItems](#enabledefaultembeddedresourceitems)
- [EnableDefaultItems](#enabledefaultitems)
- [EnableDefaultNoneItems](#enabledefaultnoneitems)

Weitere Informationen finden Sie unter dem Abschnitt zu [standardmäßigen Include- und Excludedateien](overview.md#default-includes-and-excludes).

### <a name="defaultitemexcludes"></a>DefaultItemExcludes

Verwenden Sie die `DefaultItemExcludes`-Eigenschaft, um Globmuster für Dateien und Ordner zu definieren, die aus der Include- und Excludedatei sowie Remove-Globs ausgeschlossen werden sollen. Standardmäßig werden die Ordner *./bin* und *./obj* aus den Globmustern ausgeschlossen.

```xml
<PropertyGroup>
  <DefaultItemExcludes>$(DefaultItemExcludes);**/*.myextension</DefaultItemExcludes>
</PropertyGroup>
```

### <a name="defaultexcludesinprojectfolder"></a>DefaultExcludesInProjectFolder

Verwenden Sie die `DefaultExcludesInProjectFolder`-Eigenschaft, um Globmuster für Dateien und Ordner im Projektordner zu definieren, die aus der Include- und Excludedatei sowie Remove-Globs ausgeschlossen werden sollen. Standardmäßig werden Ordner, die mit einem Punkt (`.`) beginnen, z. B. *.git* und *.vs*, aus den Globmustern ausgeschlossen.

Diese Eigenschaft ähnelt der `DefaultItemExcludes`-Eigenschaft, mit der Ausnahme, dass sie nur Dateien und Ordner im Projektordner berücksichtigt. Wenn ein Globmuster versehentlich mit Elementen außerhalb des Projektordners mit einem relativen Pfad übereinstimmen würde, verwenden Sie die `DefaultExcludesInProjectFolder`-Eigenschaft anstelle der `DefaultItemExcludes`-Eigenschaft.

```xml
<PropertyGroup>
  <DefaultExcludesInProjectFolder>$(DefaultExcludesInProjectFolder);**/myprefix*/**</DefaultExcludesInProjectFolder>
</PropertyGroup>
```

### <a name="enabledefaultitems"></a>EnableDefaultItems

Die `EnableDefaultItems`-Eigenschaft steuert, ob Kompilierungselemente, eingebettete Ressourcenelemente und `None`-Elemente implizit in das Projekt eingeschlossen werden. Der Standardwert ist `true`. Um jedes implizite Einbeziehen von Dateien zu deaktivieren, legen Sie die `EnableDefaultItems`-Eigenschaft auf `false` fest.

```xml
<PropertyGroup>
  <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

### <a name="enabledefaultcompileitems"></a>EnableDefaultCompileItems

Die `EnableDefaultCompileItems`-Eigenschaft steuert, ob Kompilierungselemente implizit in das Projekt eingeschlossen werden. Der Standardwert ist `true`. Legen Sie die `EnableDefaultCompileItems`-Eigenschaft auf `false` fest, um die implizite Einbindung von *.cs-Dateien und anderen Spracherweiterungsdateien zu deaktivieren.

```xml
<PropertyGroup>
  <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

### <a name="enabledefaultembeddedresourceitems"></a>EnableDefaultEmbeddedResourceItems

Die `EnableDefaultEmbeddedResourceItems`-Eigenschaft steuert, ob eingebettete Ressourcenelemente implizit in das Projekt eingeschlossen werden. Der Standardwert ist `true`. Legen Sie die `EnableDefaultEmbeddedResourceItems`-Eigenschaft auf `false` fest, um die implizite Einbindung eingebetteter Ressourcendateien zu deaktivieren.

```xml
<PropertyGroup>
  <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
</PropertyGroup>
```

### <a name="enabledefaultnoneitems"></a>EnableDefaultNoneItems

Die `EnableDefaultNoneItems`-Eigenschaft steuert, ob `None`-Elemente (Dateien, die keine Rolle im Buildprozess aufweisen) implizit in das Projekt eingeschlossen werden. Standardwert: `true`. Legen Sie die `EnableDefaultNoneItems`-Eigenschaft auf `false` fest, um die implizite Einbindung von `None`-Elementen zu deaktivieren.

```xml
<PropertyGroup>
  <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

## <a name="code-analysis-properties"></a>Codeanalyseeigenschaften

- [AnalysisLevel-Eigenschaft](#analysislevel)
- [AnalysisMode](#analysismode)
- [CodeAnalysisTreatWarningsAsErrors-Eigenschaft](#codeanalysistreatwarningsaserrors)
- [EnableNETAnalyzers-Eigenschaft](#enablenetanalyzers)
- [EnforceCodeStyleInBuild](#enforcecodestyleinbuild)

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

Ab .NET 5.0, sind alle [Codequalitätsregeln für Zertifizierungsstellen](../../fundamentals/code-analysis/quality-rules/index.md) im .NET SDK enthalten. Standardmäßig werden nur [einige Regeln als Buildwarnungen aktiviert](../../fundamentals/code-analysis/overview.md#enabled-rules). Mit der `AnalysisMode`-Eigenschaft können Sie die Regeln anpassen, die standardmäßig aktiviert sind. Sie können entweder zu einem aggressiveren Analysemodus (Deaktivierung) oder zu einem konservativeren Analysemodus (Aktivierung) wechseln. Wenn Sie beispielsweise alle Regeln standardmäßig als Buildwarnungen aktivieren möchten, legen Sie den Wert auf `AllEnabledByDefault` fest.

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
- [DisableImplicitFrameworkReferences](#disableimplicitframeworkreferences)
- [PackageReference](#packagereference)
- [ProjectReference](#projectreference)
- [Verweis](#reference)
- [Wiederherstellungsbezogene Eigenschaften](#restore-related-properties)

### <a name="assettargetfallback"></a>AssetTargetFallback

Mit der Eigenschaft `AssetTargetFallback` können Sie zusätzliche kompatible Frameworkversionen für Projektverweise und NuGet-Pakete angeben. Wenn Sie z. B. mit `PackageReference` eine Paketabhängigkeit angeben, aber das entsprechende Paket keine Assets enthält, die mit dem `TargetFramework` Ihres Projekts kompatibel sind, kommt die Eigenschaft `AssetTargetFallback` ins Spiel. Die Kompatibilität des referenzierten Pakets wird erneut anhand jedes Zielframeworks überprüft, das in `AssetTargetFallback` angegeben ist. Diese Eigenschaft ersetzt die veraltete Eigenschaft `PackageTargetFallback`.

Sie können die Eigenschaft `AssetTargetFallback` auf eine oder mehrere [Zielframeworkversionen](../../standard/frameworks.md#supported-target-frameworks) festlegen.

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="disableimplicitframeworkreferences"></a>DisableImplicitFrameworkReferences

Die Eigenschaft `DisableImplicitFrameworkReferences` steuert `FrameworkReference`-Elemente implizit, wenn .NET Core 3.0 oder höher als Ziel verwendet wird. Wenn .NET Core 2.1 oder .NET Standard 2.0 oder niedriger als Ziel verwendet wird, steuert die Eigenschaft implizit [PackageReference](#packagereference)-Elemente für Pakete in einem Metapaket. Ein Metapaket ist ein frameworkbasiertes Paket, das nur aus Abhängigkeiten von anderen Paketen besteht. Diese Eigenschaft steuert ebenfalls implizite Verweise wie `System` und `System.Core`, wenn das .NET Framework als Ziel verwendet wird.

Legen Sie diese Eigenschaft auf `true` fest, um implizite `FrameworkReference`- oder [PackageReference](#packagereference)-Elemente zu deaktivieren. Wenn Sie diese Eigenschaft auf `true` festlegen, können Sie auf Framework- oder Paketebene je nach Bedarf explizite Verweise hinzufügen.

```xml
<PropertyGroup>
  <DisableImplicitFrameworkReferences>true</DisableImplicitFrameworkReferences>
</PropertyGroup>
```

### <a name="packagereference"></a>PackageReference

Das `PackageReference`-Element definiert einen Verweis auf ein NuGet-Paket.

Das `Include`-Attribut gibt die Paket-ID an. Das `Version`-Attribut gibt die Version oder den Versionsbereich an. Informationen, wie Sie eine Mindestversion, Maximalversion, einen Versionsbereich oder eine exakte Versionsübereinstimmung angeben, finden Sie unter [Versionsbereiche](/nuget/concepts/package-versioning#version-ranges). Sie können auch [Objektattribute](#asset-attributes) zu einem Paketverweis hinzufügen.

Der Codeausschnitt für die Projektdatei im folgenden Beispiel verweist auf das Paket [System.Runtime](https://www.nuget.org/packages/System.Runtime/).

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

Weitere Informationen finden Sie unter [Paketverweis in Projektdateien](/nuget/consume-packages/package-references-in-project-files).

#### <a name="asset-attributes"></a>Objektattribute

Die Metadaten von `IncludeAssets`, `ExcludeAssets` und `PrivateAssets` können zu einem Paketverweis hinzugefügt werden.

| Attribut | BESCHREIBUNG |
| - | - |
| `IncludeAssets` | Dieses Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt werden sollen. Standardmäßig sind alle Paketobjekte enthalten. |
| `ExcludeAssets`| Dieses Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, nicht genutzt werden sollen. |
| `PrivateAssets` | Dieses Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt, aber nicht an das nächste Projekt übertragen werden sollen. Die Objekte `Analyzers`, `Build` und `ContentFiles` sind standardmäßig privat, wenn dieses Attribut nicht vorhanden ist. |

Diese Attribute können die folgenden Elemente enthalten, die durch ein `;`-Zeichen getrennt werden, wenn mehr als eines enthalten ist:

- `Compile` gibt an, dass die Inhalte des Ordners *lib* zum Kompilieren verfügbar sind.
- `Runtime` gibt an, dass die Inhalte des Ordners *runtime* verteilt werden.
- `ContentFiles`: Gibt an, dass die Inhalte des *contentfiles*-Ordner verwendet werden.
- `Build` gibt an, dass die Eigenschaften/Ziele im Ordner *build* verwendet werden.
- `Native` gibt an, dass die Inhalte nativer Objekte für die Runtime in den *Ausgabeordner* kopiert werden.
- `Analyzers`: Gibt an, dass Analysen verwendet werden

Alternativ kann das Attribut Folgendes enthalten:

- `None`: Keines der Objekte wird verwendet.
- `All`: Alle Objekte werden verwendet.

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

### <a name="restore-related-properties"></a>Wiederherstellungsbezogene Eigenschaften

Durch das Wiederherstellen eines referenzierten Pakets werden alle seine direkten Abhängigkeiten sowie alle Abhängigkeiten dieser Abhängigkeiten installiert. Sie können die Paketwiederherstellung anpassen, indem Sie Eigenschaften wie `RestorePackagesPath` und `RestoreIgnoreFailedSources` angeben. Weitere Informationen zu diesen und anderen Eigenschaften finden Sie unter [Wiederherstellungsziel](/nuget/reference/msbuild-targets#restore-target).

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="run-properties"></a>Ausführungseigenschaften

Die folgenden Eigenschaften werden verwendet, um Apps mit dem Befehl [`dotnet run`](../tools/dotnet-run.md) zu starten:

- [RunArguments](#runarguments)
- [RunWorkingDirectory](#runworkingdirectory)

### <a name="runarguments"></a>RunArguments

Die Eigenschaft `RunArguments` definiert die Argumente, die beim Ausführen an die App übergeben werden.

```xml
<PropertyGroup>
  <RunArguments>-mode dryrun</RunArguments>
</PropertyGroup>
```

> [!TIP]
> Sie können zusätzliche Argumente angeben, die an die App übergeben werden sollen, indem Sie die Option [`--` für `dotnet run`](../tools/dotnet-run.md#options)verwenden.

### <a name="runworkingdirectory"></a>RunWorkingDirectory

Die Eigenschaft `RunWorkingDirectory` definiert das Arbeitsverzeichnis für den Anwendungsprozess, in dem diese gestartet werden soll. Dies kann ein absoluter Pfad oder ein Pfad sein, der relativ zum Projektverzeichnis ist. Wenn Sie kein Verzeichnis angeben, wird `OutDir` als Arbeitsverzeichnis verwendet.

```xml
<PropertyGroup>
  <RunWorkingDirectory>c:\temp</RunWorkingDirectory>
</PropertyGroup>
```

## <a name="hosting-properties"></a>Hostingeigenschaften

- [EnableComHosting](#enablecomhosting)
- [EnableDynamicLoading](#enabledynamicloading)

### <a name="enablecomhosting"></a>EnableComHosting

Die `EnableComHosting`-Eigenschaft gibt an, dass eine Assembly einen COM-Server bereitstellt. Wenn die `EnableComHosting`-Eigenschaft auf `true` festgelegt wird, bedeutet dies auch, dass [EnableDynamicLoading](#enabledynamicloading) `true` ist.

```xml
<PropertyGroup>
  <EnableComHosting>True</EnableComHosting>
</PropertyGroup>
```

Weitere Informationen finden Sie unter [Verfügbarmachen von .NET Core-Komponenten in COM](../native-interop/expose-components-to-com.md).

### <a name="enabledynamicloading"></a>EnableDynamicLoading

Die `EnableDynamicLoading`-Eigenschaft gibt an, dass eine Assembly eine dynamisch geladene Komponente ist. Die Komponente kann eine [COM-Bibliothek](/windows/win32/com/the-component-object-model) oder eine Nicht-COM-Bibliothek sein, die [von einem nativen Host verwendet werden kann](../tutorials/netcore-hosting.md). Wenn diese Eigenschaft auf `true` festgelegt wird, hat diese die folgenden Auswirkungen:

- Eine *.runtimeconfig.json*-Datei wird generiert.
- [Rollforward ausführen](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) wird auf `LatestMinor` festgelegt.
- NuGet-Verweise werden lokal kopiert.

```xml
<PropertyGroup>
  <EnableDynamicLoading>true</EnableDynamicLoading>
</PropertyGroup>
```

## <a name="see-also"></a>Siehe auch

- [MSBuild-Schemareferenz](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [Gemeinsame MSBuild-Eigenschaften](/visualstudio/msbuild/common-msbuild-project-properties)
- [MSBuild-Eigenschaften für NuGet-Ziel „pack“](/nuget/reference/msbuild-targets#pack-target)
- [MSBuild-Eigenschaften für NuGet-Ziel „restore“](/nuget/reference/msbuild-targets#restore-properties)
- [Anpassen eines Builds](/visualstudio/msbuild/customize-your-build)
