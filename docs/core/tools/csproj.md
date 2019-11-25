---
title: Erweiterungen des CSPROJ-Formats für .NET Core
description: Erfahren Sie mehr über die Unterschiede zwischen vorhandenen CSPROJ-Dateien und CSPROJ-Dateien von .NET Core
ms.date: 04/08/2019
ms.openlocfilehash: 4ce9227839a610308071c36185b63db8b1ee86ed
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739296"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a>Erweiterungen des CSPROJ-Formats für .NET Core

In diesem Dokument werden die Änderungen erläutert, die an die Projektdateien beim Wechsel von *project.json* auf *csproj* und [MSBuild](https://github.com/Microsoft/MSBuild) hinzugefügt wurden. Weitere Informationen über die allgemeine Projektdateisyntax und eine Referenz finden Sie in der Dokumentation zur [MSBuild-Projektdatei](/visualstudio/msbuild/msbuild-project-file-schema-reference).

## <a name="implicit-package-references"></a>Implizite Paketverweise

Es wird implizit auf Metapakete verwiesen, basierend auf der Grundlage des/der Zielfameworks, das/die in der `<TargetFramework>`- oder `<TargetFrameworks>`-Eigenschaft Ihrer Projektdatei angegeben wurde/n. `<TargetFrameworks>` wird ignoriert, wenn `<TargetFramework>` angegeben wird, egal wie die Reihenfolge ist. Weitere Informationen finden Sie unter [Pakete, Metapakete und Frameworks](../packages.md). 

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp2.1</TargetFramework>
 </PropertyGroup>
 ```

 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp2.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a>Empfehlungen

Da implizit auf die `Microsoft.NETCore.App`- oder `NETStandard.Library`-Metapakete verwiesen wird, sehen Sie im Folgenden unsere empfohlenen bewährten Methoden:

- Wenn .NET Core oder .NET Standard angezielt wird, darf nie ein expliziter Verweis auf die `Microsoft.NETCore.App`- oder `NETStandard.Library`-Metapakete über das `<PackageReference>`-Element in Ihrer Projektdatei vorhanden sein.
- Wenn Sie .NET Core anzielen und eine bestimmte Version der Runtime benötigen, sollten Sie die `<RuntimeFrameworkVersion>`-Eigenschaft in Ihrem Projekt (z.B. `1.0.4`) verwenden, anstatt auf Metapakete zu verweisen.
  - Dies kann vorkommen, wenn Sie [eigenständige Bereitstellungen](../deploying/index.md#self-contained-deployments-scd) verwenden und Sie z.B. eine bestimmte Patchversion der 1.0.0 LTS-Laufzeit benötigen.
- Wenn Sie .NET Standard anzielen und eine bestimmte Version der `NETStandard.Library`-Metapakete benötigen, können Sie die `<NetStandardImplicitPackageVersion>`-Eigenschaft verwenden und die Version festlegen, die Sie benötigen.
- Fügen Sie dem `Microsoft.NETCore.App`- oder `NETStandard.Library`-Metapaket in .NET Framework-Projekten nicht explizit Verweise hinzu, und aktualisieren Sie diese auch nicht. Wenn bei der Verwendung eines auf .NET Standard basierenden NuGet-Pakets eine bestimmte Version von `NETStandard.Library` benötigt wird, installiert NuGet diese automatisch.

## <a name="implicit-version-for-some-package-references"></a>Implizite Version für einige Paketverweise

Die meisten Anwendungen von [`<PackageReference>`](#packagereference) erfordern das Festlegen des Attributs `Version`, um die zu verwendende NuGet-Paketversion anzugeben. Bei Verwendung von .NET Core 2.1 oder 2.2 und Verweis auf [Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) oder [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage) ist das Attribut jedoch nicht erforderlich. Das .NET Core SDK kann automatisch die Version dieser Pakete auswählen, die verwendet werden soll.

### <a name="recommendation"></a>Empfehlung

Wenn Sie auf die Pakete `Microsoft.AspNetCore.App` oder `Microsoft.AspNetCore.All` verweisen, geben Sie deren Version nicht an. Wenn eine Version angegeben wird, kann das SDK eine Warnung NETSDK1071 ausgeben. Um diese Warnung zu beheben, entfernen Sie die Paketversion wie im folgenden Beispiel:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore.App" />
</ItemGroup>
```

> Bekanntes Problem: Das.NET Core 2.1 SDK unterstützte diese Syntax nur, wenn das Projekt auch „Microsoft.NET.Sdk.Web“ verwendet. Dies wird im .NET Core SDK 2.2 gelöst.

Diese Verweise auf ASP.NET Core-Metapakete haben ein etwas anderes Verhalten als die meisten normalen NuGet-Pakete. [Frameworkabhängige Bereitstellungen](../deploying/index.md#framework-dependent-deployments-fdd) von Anwendungen, die das Metapaket verwenden, profitieren automatisch vom freigegebenen ASP.NET Core-Framework. Bei Verwendung des Metapakets werden **keine** Objekte aus den referenzierten NuGet-Paketen für ASP.NET Core mit der Anwendung bereitgestellt. Das freigegebene ASP.NET Core-Framework enthält diese Objekte. Die Objekte im freigegebenen Framework sind zur Verbesserung der Startzeit für die Zielplattform optimiert. Weitere Informationen zu freigegebenen Frameworks finden Sie unter [Packen von .NET Core-Verteilungen](../build/distribution-packaging.md).

Wenn eine Version angegeben *ist*, wird sie als *Mindestversion* des ASP.NET Core Shared Framework-abhängigen Frameworks und als *exakte* Version für eigenständige Bereitstellungen behandelt. Dies kann folgenden Konsequenzen haben:

- Wenn die auf dem Server installierte Version von ASP.NET Core kleiner ist als die in der „PackageReference“ angegebene Version, kann der .NET Core-Prozess nicht gestartet werden. Aktualisierungen des Metapakets sind oft auf NuGet.org verfügbar, bevor Updates in Hostingumgebungen wie Azure bereitgestellt werden. Das Aktualisieren der Version auf PackageReference auf ASP.NET Core kann dazu führen, dass eine bereitgestellte Anwendung fehlschlägt.
- Wenn die Anwendung als [eigenständige Bereitstellung](../deploying/index.md#self-contained-deployments-scd) bereitgestellt wird, enthält die Anwendung möglicherweise nicht die neuesten Sicherheitsupdates für .NET Core. Wenn keine Version angegeben ist, kann das SDK automatisch die neueste Version von ASP.NET Core in die eigenständige Bereitstellung aufnehmen.

## <a name="default-compilation-includes-in-net-core-projects"></a>Standardkompilierung in .NET Core-Projekten

Beim Wechsel zum *csproj*-Format in den neuesten SDK-Versionen, haben wir die Standardaufnahmen- und ausschlüsse für Compile-Elemente und eingebettete Ressourcen zu den SDK-Eigenschaftendateien verschoben. Dies bedeutet, dass Sie diese Elemente nicht länger in Ihrer Projektdatei angeben müssen.

Der Hauptgrund dafür ist die Übersichtlichkeit in Ihrer Projektdatei. Die Standardeinstellungen im SDK sollten die gängigen Anwendungsbeispiele abdecken. Es besteht keine Notwendigkeit, sie in jedem Projekt zu wiederholen, das Sie erstellen. Dies führt zu kleineren Projektdateien, die viel einfacher zu verstehen und bei Bedarf auch manuell zu bearbeiten sind.

Die folgende Tabelle zeigt, welche Elemente und welche [Globs](https://en.wikipedia.org/wiki/Glob_(programming)) im SDK enthalten und ausgeschlossen sind:

| Element           | Glob einschließen                              | Glob ausschließen                                                  | Glob entfernen              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| Compile           | \*\*/\*.cs (oder andere Spracherweiterungen) | \*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc  | Nicht zutreffend                      |
| EmbeddedResource  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | Nicht zutreffend                      |
| Keine              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | \*\*/\*.cs; \*\*/\*.resx   |

> [!NOTE]
> **Glob ausschließen** schließt immer die Ordner `./bin` und `./obj` aus, die von den MSBuild-Eigenschaften `$(BaseOutputPath)` und `$(BaseIntermediateOutputPath)` dargestellt werden. Als Ganzes werden alle Ausschlüsse von `$(DefaultItemExcludes)` dargestellt.

Wenn Sie über Globs in Ihrem Projekt verfügen, und Sie versuchen, es mit dem neuesten SDK zu erstellen, erhalten Sie den folgenden Fehler:

> Doppelte Compile-Elemente waren enthalten. .NET SDK enthält Compile-Elemente aus Ihrem Projektverzeichnis in der Standardeinstellung. Sie können diese Elemente aus Ihrer Projektdatei entfernen oder die Eigenschaft „EnableDefaultCompileItems“ auf „FALSE“ festlegen, wenn Sie sie explizit in Ihrer Projektdatei einfügen möchten.

Um diesen Fehler zu umgehen, können Sie entweder die expliziten `Compile`-Elemente entfernen, die mit denen übereinstimmen, die in der vorherigen Tabelle aufgeführt sind, oder Sie können die `<EnableDefaultCompileItems>`-Eigenschaft auf `false` wie folgt festlegen:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

Wenn diese Eigenschaft auf `false` festgelegt wird, wird der implizite Einschluss deaktiviert, und das Verhalten wird wieder auf das der vorherigen SDKs festgelegt. Bei diesem Verhalten müssen Sie die Standardglobs in Ihrem Projekt festlegen.

Diese Änderung ändert die Hauptfunktionsweise anderer Aufnahmen nicht. Wenn Sie z.B. einige Dateien angeben möchten, die mit Ihrer Anwendung veröffentlicht werden, können Sie weiterhin die bekannten Mechanismen in *csproj* dafür nutzen (z.B. das `<Content>`-Element).

`<EnableDefaultCompileItems>` deaktiviert nur `Compile`-Globmuster, wirkt sich jedoch nicht auf andere Globmuster wie das implizite `None`-Globmuster aus, das ebenfalls für \*.cs-Elemente gilt. Deshalb zeigt **Projektmappen-Explorer** die \*.cs-Elemente weiterhin als Teil des Projekts an, die als `None`-Elemente eingebunden wurden. Sie können ebenso `<EnableDefaultNoneItems>` auf FALSE festlegen, um das implizite `None`-Globmuster zu deaktivieren, so wie hier dargestellt:

```xml
<PropertyGroup>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

Sie können die `<EnableDefaultItems>`-Eigenschaft wie im folgenden Beispiel auf `false` festlegen, um **alle impliziten Globmuster** zu deaktivieren:

```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a>Anzeige des gesamten Projekts wie in MSBuild

Obwohl diese csproj-Änderungen für eine erhebliche Vereinfachung der Projektdateien sorgen, möchten Sie vielleicht das vollständig erweiterte Projekt anzeigen, so wie es von MSBuild erkannt wird, nachdem das SDK und die zugehörigen Ziele eingeschlossen wurden. Führen Sie eine Vorverarbeitung des Projekts mit der [`/pp`-Option](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) des Befehls [`dotnet msbuild`](dotnet-msbuild.md) durch. Dieser zeigt die importierten Dateien, ihre Quellen und ihren Beitrag zum Build, ohne das Projekt tatsächlich zu erstellen:

`dotnet msbuild -pp:fullproject.xml`

Wenn das Projekt mehrere Zielframeworks umfasst, sollten nur Ergebnisse für ein Framework ausgegeben werden, indem dieses als MSBuild-Eigenschaft angegeben wird:

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a>Erweiterungen

### <a name="sdk-attribute"></a>SDK-Attribut

Das `<Project>`-Stammelement der *CSPROJ*-Datei hat ein neues Attribut namens `Sdk`. `Sdk` gibt an, welches SDK vom Projekt verwendet wird. Das SDK ist, wie das [Schichtendokument](cli-msbuild-architecture.md) beschreibt, ein Satz von MSBuild-[Aufgaben](/visualstudio/msbuild/msbuild-tasks) und -[Zielen](/visualstudio/msbuild/msbuild-targets), die .NET Core-Code erstellen können. Für .NET Core sind die folgenden SDKs verfügbar:

1. Das .NET Core SDK mit der `Microsoft.NET.Sdk`-ID
2. Das .NET Core Web-SDK mit der `Microsoft.NET.Sdk.Web`-ID
3. Das .NET Core Razor-Klassenbibliothek SDK mit der ID von `Microsoft.NET.Sdk.Razor`
4. Der .NET Core-Workerdienst mit der ID `Microsoft.NET.Sdk.Worker` (seit .NET Core 3.0)
5. .NET Core WinForms und WPF mit der ID `Microsoft.NET.Sdk.WindowsDesktop` (seit .NET Core 3.0)

Das `Sdk`-Attribut muss auf eine dieser IDs auf dem `<Project>`-Element festgelegt werden, um die .NET Core-Tools nutzen und Codes erstellen zu können.

### <a name="packagereference"></a>PackageReference

Ein `<PackageReference>`-Element gibt eine [NuGet-Abhängigkeit im Projekt an](/nuget/consume-packages/package-references-in-project-files). Das `Include`-Attribut gibt die Paket-ID an.

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a>Version

Das erforderliche Attribut `Version` gibt die Version des wiederherzustellenden Pakets an. Das Attribut berücksichtigt die Regeln für das [NuGet-Versionsschema](/nuget/reference/package-versioning#version-ranges-and-wildcards). Das Standardverhalten ist eine genau Übereinstimmung mit der Version. Beispiel: Die Angabe von `Version="1.2.3"` ist gleichbedeutend mit der NuGet-Notation `[1.2.3]` für die genaue 1.2.3 Version des Pakets.

#### <a name="includeassets-excludeassets-and-privateassets"></a>IncludeAssets, ExcludeAssets und PrivateAssets

Das `IncludeAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt werden sollen. Standardmäßig sind alle Paketobjekte enthalten.

Das `ExcludeAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, nicht genutzt werden sollen.

Das `PrivateAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt, aber nicht an das nächste Projekt übertragen werden sollen. Die Objekte `Analyzers`, `Build` und `ContentFiles` sind standardmäßig privat, wenn dieses Attribut nicht vorhanden ist.

> [!NOTE]
> `PrivateAssets` entspricht dem Element *project.json*/*xproj* `SuppressParent`.

Diese Attribute können eines oder mehrere der folgenden Elemente enthalten, getrennt durch das Semikolon `;`-Zeichen, wenn mehr als eines aufgeführt ist:

- `Compile` gibt an, dass die Inhalte des Ordners *lib* zum Kompilieren verfügbar sind.
- `Runtime` gibt an, dass die Inhalte des Ordners *runtime* verteilt werden.
- `ContentFiles`: Gibt an, dass die Inhalte des *contentfiles*-Ordner verwendet werden.
- `Build` gibt an, dass die Eigenschaften/Ziele im Ordner *build* verwendet werden.
- `Native` gibt an, dass die Inhalte nativer Objekte für die Runtime in den *Ausgabeordner* kopiert werden.
- `Analyzers`: Gibt an, dass Analysen verwendet werden

Alternativ kann das Attribut Folgendes enthalten:

- `None`: Keines der Objekte wird verwendet.
- `All`: Alle Objekte werden verwendet.

### <a name="dotnetclitoolreference"></a>DotNetCliToolReference

Ein `<DotNetCliToolReference>`-Element gibt das CLI-Tool an, das der Benutzer im Kontext des Projekts wiederherstellen möchte. Es ist ein Ersatz für den `tools`-Knoten in *project.json*.

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a>Version

`Version` gibt die Version des wiederherzustellenden Pakets an. Das Attribut berücksichtigt die Regeln für das [NuGet-Versionsschema](/nuget/create-packages/dependency-versions#version-ranges). Das Standardverhalten ist eine genau Übereinstimmung mit der Version. Beispiel: Die Angabe von `Version="1.2.3"` ist gleichbedeutend mit der NuGet-Notation `[1.2.3]` für die genaue 1.2.3 Version des Pakets.

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers

Das Eigenschaftenelement `<RuntimeIdentifiers>` ermöglicht die Angabe einer durch Semikolons getrennten Liste von [Runtime-IDs (RIDs)](../rid-catalog.md) für das Projekt.
RIDs ermöglichen das Veröffentlichen eigenständiger Bereitstellungen.

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a>RuntimeIdentifier

Das Eigenschaftenelement `<RuntimeIdentifier>` ermöglicht die Angabe von nur einer einzigen [Runtime-ID (RID)](../rid-catalog.md) für das Projekt. RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung.

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

Verwenden Sie stattdessen `<RuntimeIdentifiers>` (Plural), wenn Sie für mehrere Runtimes eine Veröffentlichung durchführen müssen. Durch `<RuntimeIdentifier>` können Sie Builds schneller abschließen, wenn nur eine einzige Runtime erforderlich ist.

### <a name="packagetargetfallback"></a>PackageTargetFallback

Das Eigenschaftenelement `<PackageTargetFallback>` ermöglicht die Angabe mehrerer kompatibler Ziele, die verwendet werden, wenn Pakete wiederhergestellt werden. Dies soll ermöglichen, dass Pakete, in denen das .NET [TxM (Target x Moniker)](/nuget/schema/target-frameworks) verwendet wird, mit Paketen funktionieren, in denen kein .NET TxM deklariert ist. Wird in einem Projekt das .NET TxM verwendet, müssen alle Pakete, zu denen es eine Abhängigkeit gibt, ebenfalls ein .NET TxM haben. Dies trifft nur dann nicht zu, wenn Sie das `<PackageTargetFallback>`-Element zu Ihrem Projekt hinzufügen, sodass Nicht-.NET-Plattformen mit .NET kompatibel sind.

Im folgenden Beispiel werden die Fallbacks für alle Ziele in Ihrem Projekt bereitgestellt:

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

Im folgenden Beispiel werden nur die Fallbacks für das `netcoreapp2.1`-Ziel angegeben:

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="build-events"></a>Buildereignisse

Die Art und Weise, wie Präbuild- und Postbuildereignisse in der Projektdatei angegeben werden, hat sich geändert. Die Eigenschaften „PreBuildEvent“ und „PostBuildEvent“ werden im SDK-Projektformat nicht empfohlen, da Makros wie $(ProjectDir) nicht aufgelöst werden. Der folgende Code wird z. B. nicht mehr unterstützt:

```xml
<PropertyGroup>
    <PreBuildEvent>"$(ProjectDir)PreBuildEvent.bat" "$(ProjectDir)..\" "$(ProjectDir)" "$(TargetDir)" />
</PropertyGroup>
```

Verwenden Sie in Projekten im SDK-Format ein MSBuild-Ziel namens `PreBuild` oder `PostBuild`, und legen Sie die Eigenschaft `BeforeTargets` für `PreBuild` oder die Eigenschaft `AfterTargets` für `PostBuild` fest. Verwenden Sie für das vorherige Beispiel den folgenden Code:

```xml
<Target Name="PreBuild" BeforeTargets="PreBuildEvent">
    <Exec Command="&quot;$(ProjectDir)PreBuildEvent.bat&quot; &quot;$(ProjectDir)..\&quot; &quot;$(ProjectDir)&quot; &quot;$(TargetDir)&quot;" />
</Target>

<Target Name="PostBuild" AfterTargets="PostBuildEvent">
   <Exec Command="echo Output written to $(TargetDir)" />
</Target>
```

> [!NOTE]
>Sie können einen beliebigen Namen für die MSBuild-Ziele verwenden, aber die Visual Studio-IDE erkennt `PreBuild`- und `PostBuild`-Ziele. Daher empfiehlt es sich, diese Namen zu verwenden, damit Sie die Befehle in der Visual Studio-IDE bearbeiten können. 

## <a name="nuget-metadata-properties"></a>NuGet-Metadateneigenschaften

Mit dem Wechsel zu MSBuild haben wir die Eingabemetadaten, die beim Packen eines NuGet-Pakets verwendet werden, aus *project.json* in *.csproj*-Dateien verschoben. Die Eingaben sind MSBuild-Eigenschaften, sodass sie in eine `<PropertyGroup>`-Gruppe wechseln müssen. In der folgenden Liste sind die Eigenschaften aufgeführt, die als Eingaben für den Packvorgang verwendet werden, wenn der Befehl `dotnet pack` oder das MSBuild-Ziel `Pack` verwendet wird, das Bestandteil des SDK ist:

### <a name="ispackable"></a>IsPackable

Ein Boolescher Wert, der angibt, ob das Projekt verpackt werden kann. Der Standardwert ist `true`sein.

### <a name="packageversion"></a>PackageVersion

Gibt die Version an, die das resultierende Paket haben wird. Akzeptiert alle Arten von NuGet-Versionszeichenfolgen. Standardmäßig beträgt der Wert `$(Version)` der Eigenschaft `Version` im Projekt.

### <a name="packageid"></a>PackageId

Gibt den Namen für das resultierende Paket an. Wenn nicht angegeben, verwendet der `pack`-Vorgang standardmäßig `AssemblyName` oder den Verzeichnisnamen als Paketnamen.

### <a name="title"></a>Titel

Ein benutzerfreundlicher Titel des Pakets, der in der Regel in der Benutzeroberfläche wie auf nuget.org angezeigt wird und der Paket-Manager in Visual Studio. Wenn nicht angegeben, wird stattdessen die Paket-ID verwendet.

### <a name="authors"></a>Authors

Eine durch Semikolons getrennte Liste der Paketautoren, die mit Profilnamen unter nuget.org übereinstimmen. Diese werden im NuGet-Katalog unter nuget.org angezeigt und werden verwendet, um Querverweise auf Pakete von den gleichen Autoren zu geben.

### <a name="packagedescription"></a>PackageDescription

Eine ausführliche Beschreibung des Pakets für die Anzeige der Benutzeroberfläche.

### <a name="description"></a>BESCHREIBUNG

Eine lange Beschreibung für die Assembly. Wenn `PackageDescription` nicht angegeben ist, wird diese Eigenschaft auch als Beschreibung des Pakets verwendet.

### <a name="copyright"></a>Copyright

Copyright-Informationen für das Paket.

### <a name="packagerequirelicenseacceptance"></a>PackageRequireLicenseAcceptance

Ein Boolescher Wert, der angibt, ob der Client den Verbraucher dazu auffordern muss, die Paketlizenz vor der Installation des Pakets zu akzeptieren. Die Standardeinstellung ist `false`.

### <a name="packagelicenseexpression"></a>PackageLicenseExpression

Ein [SPDX Lizenzbezeichner](https://spdx.org/licenses/) oder ein Ausdruck. Beispielsweise `Apache-2.0`.

Hier ist die vollständige Liste der [SPDX Lizenzbezeichner](https://spdx.org/licenses/). NuGet.org akzeptiert nur von OSI oder FSF genehmigte Lizenzen, wenn der Ausdruck „license type“ verwendet wird.

Die genaue Syntax für die Lizenzausdrücke wird unten in [ABNF](https://tools.ietf.org/html/rfc5234) beschrieben.

```abnf
license-id            = <short form license identifier from https://spdx.org/spdx-specification-21-web-version#h.luq9dgcle9mo>

license-exception-id  = <short form license exception identifier from https://spdx.org/spdx-specification-21-web-version#h.ruv3yl8g6czd>

simple-expression = license-id / license-id”+”

compound-expression =  1*1(simple-expression /
                simple-expression "WITH" license-exception-id /
                compound-expression "AND" compound-expression /
                compound-expression "OR" compound-expression ) /
                "(" compound-expression ")" )

license-expression =  1*1(simple-expression / compound-expression / UNLICENSED)
```

> [!NOTE]
> `PackageLicenseExpression`, `PackageLicenseFile` oder `PackageLicenseUrl` können jeweils nur einzeln angegeben werden.

### <a name="packagelicensefile"></a>PackageLicenseFile

Pfad zu einer Lizenzdatei innerhalb des Pakets, wenn Sie eine Lizenz verwenden, der kein SPDX-Bezeichner zugewiesen wurde, oder es sich um eine benutzerdefinierte Lizenz handelt (sonst wird `PackageLicenseExpression` bevorzugt).

Ersetzt `PackageLicenseUrl`, kann nicht mit `PackageLicenseExpression` kombiniert werden und erfordert Visual Studio 15.9.4, .NET SDK 2.1.502 oder 2.2.101 oder höher.

Sie müssen sicherstellen, dass die Lizenzdatei gepackt ist, indem Sie sie explizit zum Projekt hinzufügen. Beispielnutzung:

```xml
<PropertyGroup>
  <PackageLicenseFile>LICENSE.txt</PackageLicenseFile>
</PropertyGroup>
<ItemGroup>
  <None Include="licenses\LICENSE.txt" Pack="true" PackagePath="$(PackageLicenseFile)"/>
</ItemGroup>
```

### <a name="packagelicenseurl"></a>PackageLicenseUrl

Eine URL für die Lizenz, die auf das Paket angewendet werden kann. (_seit Visual Studio 15.9.4, .NET SDK 2.1.502 und 2.2.101 veraltet_)

### <a name="packageiconurl"></a>PackageIconUrl

Eine URL für ein 64x64-Bild mit transparentem Hintergrund, das als Symbol für das Paket in der UI-Anzeige verwendet wird.

### <a name="packagereleasenotes"></a>PackageReleaseNotes

Anmerkungen zu diesem Paket.

### <a name="packagetags"></a>PackageTags

Eine durch Semikolons getrennte Liste von Tags, die das Paket festlegt.

### <a name="packageoutputpath"></a>PackageOutputPath

Bestimmt den Ausgabepfad, in dem das gepackte Paket abgelegt wird. Der Standardwert ist `$(OutputPath)`.

### <a name="includesymbols"></a>IncludeSymbols
Dieser Boolesche Wert gibt an, ob das Paket ein zusätzliches Symbolpaket erstellen soll, wenn das Projekt verpackt wird. Das Format des Symbolpakets wird durch die Eigenschaft `SymbolPackageFormat` gesteuert.

### <a name="symbolpackageformat"></a>SymbolPackageFormat
Gibt das Format des Symbolpakets an. Im Fall von „symbols.nupkg“ wird ein älteres Symbolpaket mit der Erweiterung *.symbols.nupkg* erstellt, das PDB-, DLL- und andere Ausgabedateien enthält. Im Fall von „snupkg“ wird ein Symbolpaket dieses Typs erstellt, das die portablen PDB-Dateien enthält. Der Standardwert ist „symbols.nupkg“.

### <a name="includesource"></a>IncludeSource

Dieser Boolesche Wert gibt an, ob der Packprozess ein Quellpaket erstellen sollte. Das Quellpaket enthält den Quellcode der Bibliothek sowie die PDB-Dateien. Quelldateien werden im `src/ProjectName`-Verzeichnis in der resultierenden Paketdatei gespeichert.

### <a name="istool"></a>IsTool

Gibt an, ob alle Ausgabedateien in den *Tools*-Ordner anstelle des *Lib*-Ordners kopiert werden. Beachten Sie, dass dies anders als ein `DotNetCliTool` ist, der angegeben wird, indem die `PackageType` in der *.csproj*-Datei eingestellt wird.

### <a name="repositoryurl"></a>RepositoryUrl

Gibt die URL für das Repository an, in der sich der Quellcode für das Paket befindet und/oder aus der es erstellt wird.

### <a name="repositorytype"></a>RepositoryType

Gibt den Verzeichnistyp an. Der Standardwert ist „Git“.

### <a name="repositorybranch"></a>RepositoryBranch
Gibt den Namen des Quellbranch im Repository an. Wenn das Projekt in einem NuGet-Paket gepackt ist, wird es den Paketmetadaten hinzugefügt.

### <a name="repositorycommit"></a>RepositoryCommit
Optionaler Repositorycommit oder ein Changeset, um anzugeben, für welches Quellpaket die Erstellung erfolgt ist. `RepositoryUrl` muss ebenfalls angegeben werden, damit diese Eigenschaft einbezogen wird. Wenn das Projekt in einem NuGet-Paket gepackt ist, wird dieser Commit oder das Changeset den Paketmetadaten hinzugefügt.

### <a name="nopackageanalysis"></a>NoPackageAnalysis

Gibt an, dass der Packvorgang keine Paketanalyse nach dem Erstellen des Pakets ausführen sollte.

### <a name="minclientversion"></a>MinClientVersion

Gibt die minimale Version des NuGet-Clients an, der dieses Paket installieren kann. Dies wird von nuget.exe und dem Paket-Manager von Visual Studio erzwungen.

### <a name="includebuildoutput"></a>IncludeBuildOutput

Dieser Boolesche Werte gibt an, ob die Buildausgabeassemblys in die *.nupkg*-Datei gepackt werden sollen oder nicht.

### <a name="includecontentinpack"></a>IncludeContentInPack

Dieser Boolesche Wert gibt an, ob alle Elemente, die über einen `Content`-Typ verfügen, automatisch im resultierenden Paket enthalten sind. Die Standardeinstellung ist `true`.

### <a name="buildoutputtargetfolder"></a>BuildOutputTargetFolder

Gibt den Ordner an, in dem die Ausgabeassemblys abgelegt werden. Die Ausgabeassemblys (und andere Ausgabedateien) werden in ihre jeweiligen Frameworkordner kopiert.

### <a name="contenttargetfolders"></a>ContentTargetFolders

Diese Eigenschaft gibt den Standardspeicherort an, an dem alle Inhaltsdateien gespeichert werden sollten, wenn `PackagePath` für sie nicht angegeben ist. Der Standardwert ist „content;contentFiles“.

### <a name="nuspecfile"></a>NuspecFile

Relativer oder absoluter Pfad zur *.nuspec*-Datei, die für die Komprimierung verwendet wird.

> [!NOTE]
> Wenn die *.nuspec*-Datei angegeben ist, wird sie **ausschließlich** zur Verpackung von Informationen verwendet, und die Information in den Projekten wird nicht verwendet.

### <a name="nuspecbasepath"></a>NuspecBasePath

Der Basispfad für die *.nuspec*-Datei.

### <a name="nuspecproperties"></a>NuspecProperties

Durch Semikolons getrennte Liste der Schlüssel = Wertpaare.

## <a name="assemblyinfo-properties"></a>AssemblyInfo-Eigenschaften

[Assembly-Attribute](../../standard/assembly/set-attributes.md), die normalerweise in einer *AssemblyInfo*-Datei vorlagen, werden jetzt automatisch aus Eigenschaften generiert.

### <a name="properties-per-attribute"></a>Eigenschaften pro Attribut

Jedes Attribut weist eine Eigenschaft auf, die seinen Inhalt steuert, und eine weitere zum Deaktivieren seiner Erstellung, wie in der folgenden Tabelle ersichtlich:

| Attribut                                                      | Eigenschaft               | Eigenschaft zum Deaktivieren                             |
|----------------------------------------------------------------|------------------------|-------------------------------------------------|
| <xref:System.Reflection.AssemblyCompanyAttribute>              | `Company`              | `GenerateAssemblyCompanyAttribute`              |
| <xref:System.Reflection.AssemblyConfigurationAttribute>        | `Configuration`        | `GenerateAssemblyConfigurationAttribute`        |
| <xref:System.Reflection.AssemblyCopyrightAttribute>            | `Copyright`            | `GenerateAssemblyCopyrightAttribute`            |
| <xref:System.Reflection.AssemblyDescriptionAttribute>          | `Description`          | `GenerateAssemblyDescriptionAttribute`          |
| <xref:System.Reflection.AssemblyFileVersionAttribute>          | `FileVersion`          | `GenerateAssemblyFileVersionAttribute`          |
| <xref:System.Reflection.AssemblyInformationalVersionAttribute> | `InformationalVersion` | `GenerateAssemblyInformationalVersionAttribute` |
| <xref:System.Reflection.AssemblyProductAttribute>              | `Product`              | `GenerateAssemblyProductAttribute`              |
| <xref:System.Reflection.AssemblyTitleAttribute>                | `AssemblyTitle`        | `GenerateAssemblyTitleAttribute`                |
| <xref:System.Reflection.AssemblyVersionAttribute>              | `AssemblyVersion`      | `GenerateAssemblyVersionAttribute`              |
| <xref:System.Resources.NeutralResourcesLanguageAttribute>      | `NeutralLanguage`      | `GenerateNeutralResourcesLanguageAttribute`     |

Notizen:

- Das Standardverhalten von `AssemblyVersion` und `FileVersion` besteht in der Übernahme des Werts von `$(Version)` ohne Suffix. Wenn `$(Version)` beispielsweise `1.2.3-beta.4` ist, wäre der Wert `1.2.3`.
- `InformationalVersion` hat standardmäßig den Wert von `$(Version)`.
- An `InformationalVersion` ist `$(SourceRevisionId)` angefügt, wenn die Eigenschaft vorhanden ist. Sie kann mithilfe von `IncludeSourceRevisionInInformationalVersion` deaktiviert werden.
- Die Eigenschaften `Copyright` und `Description` werden auch für NuGet-Metadaten verwendet.
- `Configuration` wird vom gesamten Buildprozess gemeinsam verwendet und über den `--configuration`-Parameter von `dotnet`-Befehlen festgelegt.

### <a name="generateassemblyinfo"></a>GenerateAssemblyInfo

Ein boolescher Wert zum Aktivieren oder Deaktivieren der AssemblyInfo-Erstellung insgesamt. Der Standardwert ist `true`sein.

### <a name="generatedassemblyinfofile"></a>GeneratedAssemblyInfoFile

Der Pfad der generierten Assembly-Infodatei. Standardmäßig eine Datei im `$(IntermediateOutputPath)` (obj)-Verzeichnis.
