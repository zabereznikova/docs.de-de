---
title: 'Übersicht: .NET SDKs für Projekte'
titleSuffix: ''
description: Hier erfahren Sie mehr .NET SDKs für Projekte.
ms.date: 09/17/2020
ms.topic: conceptual
ms.openlocfilehash: 2adb0713fabda142d071425a2affe66cc9d4c172
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189667"
---
# <a name="net-project-sdks"></a>.NET SDKs für Projekte

Projekten für .NET Core und .NET 5.0 und höher ist ein SDK (Software Development Kit) zugeordnet. Jedes *Projekt-SDK* besteht aus einer Reihe von MSBuild-[Zielen](/visualstudio/msbuild/msbuild-targets) und zugehörigen [Tasks](/visualstudio/msbuild/msbuild-tasks), mit denen Code kompiliert, paketiert und veröffentlicht wird. Ein Projekt, das auf ein Projekt-SDK verweist, wird zuweilen auch als *Projekt im SDK-Stil* bezeichnet.

## <a name="available-sdks"></a>Verfügbare SDKs

Folgende SDKs sind verfügbar:

| id | Beschreibung | Repository|
| - | - | - |
| `Microsoft.NET.Sdk` | .NET SDK | <https://github.com/dotnet/sdk> |
| `Microsoft.NET.Sdk.Web` | Das .NET [Web SDK](/aspnet/core/razor-pages/web-sdk) | <https://github.com/dotnet/sdk> |
| `Microsoft.NET.Sdk.Razor` | Das .NET [Razor SDK](/aspnet/core/razor-pages/sdk) |
| `Microsoft.NET.Sdk.Worker` | Das .NET Worker Service SDK |
| `Microsoft.NET.Sdk.WindowsDesktop` | Das WinForms und das WPF SDK\* | <https://github.com/dotnet/winforms> und <https://github.com/dotnet/wpf> |

Das .NET SDK ist das Basis-SDK für .NET. Die anderen SDKs verweisen auf das .NET SDK, und Projekten, die den anderen SDKs zugeordnet sind, stehen alle .NET SDK-Eigenschaften zur Verfügung. Das Web SDK ist z. B. sowohl vom .NET SDK als auch vom Razor SDK abhängig.

Sie können auch selbst ein SDK erstellen, das über NuGet verteilt werden kann.

\* Ab .NET 5.0 sollten Windows Forms und Windows Presentation Foundation-Projekte (WPF) das .NET SDK (`Microsoft.NET.Sdk`) anstelle von `Microsoft.NET.Sdk.WindowsDesktop` angeben. Wenn Sie für diese Projekte `TargetFramework` auf `net5.0-windows` und `UseWPF` oder `UseWindowsForms` auf `true` festlegen, wird das Windows Desktop SDK automatisch importiert. Wenn Ihr Projekt auf .NET 5.0 oder höher ausgerichtet ist und das `Microsoft.NET.Sdk.WindowsDesktop` SDK angibt, wird die Buildwarnung NETSDK1137 ausgelöst.

## <a name="project-files"></a>Projektdateien

.NET-Projekte basieren auf dem [MSBuild](/visualstudio/msbuild/msbuild)-Format. Projektdateien mit der Erweiterung *.csproj* für C#-Projekte und *.fsproj* für F#-Projekte, weisen das XML-Format auf. Das Stammelement einer MSBuild-Projektdatei ist das Element [Project](/visualstudio/msbuild/project-element-msbuild). Das `Project`-Element besitzt ein optionales `Sdk`-Attribut, das angibt, welches SDK (und welche Version) verwendet werden soll. Damit Sie die .NET-Tools verwenden und Ihren Code erstellen können, müssen Sie das Attribut `Sdk` auf eine der IDs in der Tabelle [Available SDKs](#available-sdks) (Verfügbare SDKs) festlegen.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
</Project>
```

Um ein aus NuGet stammendes SDK anzugeben, schließen Sie die Version am Ende des Namens ein, oder geben Sie den Namen und die Version in der Datei *global.json* an.

```xml
<Project Sdk="MSBuild.Sdk.Extras/2.0.54">
  ...
</Project>
```

Das [Sdk](/visualstudio/msbuild/sdk-element-msbuild)-Element auf der obersten Ebene ist eine weitere Möglichkeit, das SDK anzugeben:

```xml
<Project>
  <Sdk Name="Microsoft.NET.Sdk" />
  ...
</Project>
```

Wenn Sie mit einer dieser Möglichkeiten auf ein SDK verweisen, werden Projektdateien für .NET erheblich vereinfacht. Während der Auswertung des Projekts fügt MSBuild implizite Importe in der Projektdatei hinzu: im oberen Bereich für `Sdk.props`, im unteren Bereich für `Sdk.targets`.

```xml
<Project>
  <!-- Implicit top import -->
  <Import Project="Sdk.props" Sdk="Microsoft.NET.Sdk" />
  ...
  <!-- Implicit bottom import -->
  <Import Project="Sdk.targets" Sdk="Microsoft.NET.Sdk" />
</Project>
```

> [!TIP]
> Auf einem Windows-Computer befinden sich die Dateien *Sdk.props* und *Sdk.targets* im Ordner *%ProgramFiles%\dotnet\sdk\\[version]\Sdks\Microsoft.NET.Sdk\Sdk*.

### <a name="preprocess-the-project-file"></a>Vorverarbeiten der Projektdatei

Mithilfe des Befehls `dotnet msbuild -preprocess` können Sie ein vollständig erweitertes Projekt so anzeigen, wie es für MSBuild dargestellt wird, nachdem das SDK und die zugehörigen Ziele angegeben wurden. Die Option [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) des Befehls [`dotnet msbuild`](../tools/dotnet-msbuild.md) zeigt die importierten Dateien, ihre Quellen und ihren Beitrag zum Build, ohne das Projekt tatsächlich zu erstellen.

Wenn das Projekt mehrere Zielframeworks umfasst, geben Sie die Ergebnisse des Befehls nur für ein Framework aus, indem Sie dieses als MSBuild-Eigenschaft angeben. Zum Beispiel:

`dotnet msbuild -property:TargetFramework=netcoreapp2.0 -preprocess:output.xml`

## <a name="default-includes-and-excludes"></a>Standardmäßige Aufnahmen und Ausschlüsse

Die standardmäßigen Aufnahmen und Ausschlüsse für [`Compile`-Elemente](/visualstudio/msbuild/common-msbuild-project-items#compile), [eingebettete Ressourcen](/visualstudio/msbuild/common-msbuild-project-items#embeddedresource) und [`None`-Elemente](/visualstudio/msbuild/common-msbuild-project-items#none) sind im SDK definiert. Im Gegensatz zu SDK-Projekten, die nicht das .NET Framework als Ziel verwenden, müssen Sie diese Elemente nicht in Ihrer Projektdatei angeben, da die Standardwerte die meisten gängigen Anwendungsfälle abdecken. Durch dieses Verhalten wird die Projektdatei kleiner, verständlicher und kann bei Bedarf manuell bearbeitet werden.

Die folgende Tabelle zeigt, welche Elemente und welche [Globs](https://en.wikipedia.org/wiki/Glob_(programming)) im .NET SDK enthalten bzw. nicht enthalten sind:

| Element           | Glob einschließen                              | Glob ausschließen                                                  | Glob entfernen              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| Compile           | \*\*/\*.cs (oder andere Spracherweiterungen) | \*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc  | Nicht zutreffend                      |
| EmbeddedResource  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | Nicht zutreffend                      |
| Keine              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | \*\*/\*.cs; \*\*/\*.resx |

> [!NOTE]
> Die Ordner `./bin` und `./obj` aus, die von den MSBuild-Eigenschaften `$(BaseOutputPath)` und `$(BaseIntermediateOutputPath)` dargestellt werden, sind standardmäßig von den Globs ausgeschlossen. Ausschlüsse werden durch die [DefaultItemExcludes-Eigenschaft](msbuild-props.md#defaultitemexcludes) dargestellt.

### <a name="build-errors"></a>Buildfehler

Wenn Sie beliebige dieser Elemente explizit in Ihrer Projektdatei definieren, erhalten Sie wahrscheinlich eine „NETSDK1022“-Buildfehlermeldung ähnlich der folgenden:

  > Doppelte „Compile“-Elemente wurden eingeschlossen. .NET SDK enthält „Compile“-Elemente aus Ihrem Projektverzeichnis in der Standardeinstellung. Sie können diese Elemente aus Ihrer Projektdatei entfernen oder die Eigenschaft „EnableDefaultCompileItems“ auf „FALSE“ festlegen, wenn Sie sie explizit in Ihrer Projektdatei einfügen möchten.

  > Doppelte „EmbeddedResource“-Elemente wurden eingeschlossen. Das .NET SDK enthält „EmbeddedResource“-Elemente aus Ihrem Projektverzeichnis in der Standardeinstellung. Sie können diese Elemente aus Ihrer Projektdatei entfernen oder die Eigenschaft „EnableDefaultEmbeddedResourceItems“ auf FALSE festlegen, wenn Sie sie explizit in Ihrer Projektdatei einschließen möchten.

Zum Beheben der Fehler führen Sie eine der folgenden Aktionen aus:

- Entfernen Sie die expliziten `Compile`-, `EmbeddedResource`- oder `None`-Elemente, die den in der vorherigen Tabelle aufgeführten impliziten Elementen entsprechen.

- Um jedes implizite Einbeziehen von Dateien zu deaktivieren, legen Sie die [EnableDefaultItems-Eigenschaft](msbuild-props.md#enabledefaultitems) auf `false` fest:

  ```xml
  <PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
  </PropertyGroup>
  ```

  Wenn Sie Dateien angeben möchten, die mit Ihrer Anwendung veröffentlicht werden sollen, können Sie weiterhin die bekannten MSBuild-Mechanismen dafür verwenden, wie etwa das `Content`-Element.

- Deaktivieren Sie selektiv nur die Globs `Compile`, `EmbeddedResource` oder `None`, indem Sie die Eigenschaft [EnableDefaultCompileItems](msbuild-props.md#enabledefaultcompileitems), [EnableDefaultEmbeddedResourceItems](msbuild-props.md#enabledefaultembeddedresourceitems), oder [EnableDefaultNoneItems](msbuild-props.md#enabledefaultnoneitems) auf `false` festlegen:

  ```xml
  <PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
    <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
  </PropertyGroup>
  ```

  Wenn Sie nur `Compile`-Globs deaktivieren, zeigt der Projektmappen-Explorer in Visual Studio die \*.cs-Elemente weiterhin als Teil des Projekts an, eingeschlossen als `None`-Elemente. Um das implizite `None`-Glob zu deaktivieren, legen Sie auch `EnableDefaultNoneItems` auf `false` fest.

## <a name="build-events"></a>Buildereignisse

Verwenden Sie in Projekten im SDK-Format ein MSBuild-Ziel namens `PreBuild` oder `PostBuild`, und legen Sie die Eigenschaft `BeforeTargets` für `PreBuild` oder die Eigenschaft `AfterTargets` für `PostBuild` fest.

```xml
<Target Name="PreBuild" BeforeTargets="PreBuildEvent">
    <Exec Command="&quot;$(ProjectDir)PreBuildEvent.bat&quot; &quot;$(ProjectDir)..\&quot; &quot;$(ProjectDir)&quot; &quot;$(TargetDir)&quot;" />
</Target>

<Target Name="PostBuild" AfterTargets="PostBuildEvent">
   <Exec Command="echo Output written to $(TargetDir)" />
</Target>
```

> [!NOTE]
>
> - Sie können die MSBuild-Ziele beliebig benennen. Die Visual Studio-IDE erkennt jedoch `PreBuild`- und `PostBuild`-Ziele. Wenn Sie diese Namen verwenden, können Sie also Befehle in der IDE bearbeiten.
> - Die Eigenschaften `PreBuildEvent` und `PostBuildEvent` sollten in SDK-Projekten nicht verwendet werden, da Makros wie `$(ProjectDir)` nicht aufgelöst werden. Beispielsweise wird der folgende Code nicht unterstützt:
>
> ```xml
> <PropertyGroup>
>   <PreBuildEvent>"$(ProjectDir)PreBuildEvent.bat" "$(ProjectDir)..\" "$(ProjectDir)" "$(TargetDir)"</PreBuildEvent>
> </PropertyGroup>
> ```

## <a name="customize-the-build"></a>Anpassen des Builds

Es gibt verschiedene Möglichkeiten, [einen Build anzupassen](/visualstudio/msbuild/customize-your-build). Sie können eine Eigenschaft überschreiben, indem Sie sie als Argument an einen [msbuild](/visualstudio/msbuild/msbuild-command-line-reference)- oder [dotnet](../tools/index.md)-Befehl übergeben. Sie können die Eigenschaft auch zur Projektdatei oder zu einer *Directory.Build.props*-Datei hinzufügen. Eine Liste mit nützlichen Eigenschaften für .NET-Projekte finden Sie in der [MSBuild-Referenz für .NET Core SDK-Projekte](msbuild-props.md).

### <a name="custom-targets"></a>Benutzerdefinierte Ziele

.NET-Projekte können benutzerdefinierte MSBuild-Ziele und -Eigenschaften für Projekte in Pakete packen, die das Paket nutzen. Verwenden Sie diese Art der Erweiterbarkeit, wenn Sie Folgendes vorhaben:

- Erweitern des Buildprozesses
- Zugreifen auf Artefakte des Buildprozesses, z. B. generierte Dateien
- Untersuchen einer Konfiguration, in der der Build aufgerufen wird

Sie fügen benutzerdefinierte Buildziele oder -eigenschaften hinzu, indem Sie Dateien im Format `<package_id>.targets` oder `<package_id>.props` (z. B.`Contoso.Utility.UsefulStuff.targets`) im *build*-Ordner des Projekts platzieren.

Der XML-Code ist ein Codeausschnitt aus einer *.csproj*-Datei, die den Befehl [`dotnet pack`](../tools/dotnet-pack.md) anweist, was paketiert werden soll. Das Element `<ItemGroup Label="dotnet pack instructions">` platziert die Zieledateien innerhalb des Pakets in den Ordner *build*. Das Element `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` platziert die Assemblys und *.json*-Dateien in den Ordner *build*.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  ...
  <ItemGroup Label="dotnet pack instructions">
    <Content Include="build\*.targets">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">
    <!-- Collect these items inside a target that runs after build but before packaging. -->
    <ItemGroup>
      <Content Include="$(OutputPath)\*.dll;$(OutputPath)\*.json">
        <Pack>true</Pack>
        <PackagePath>build\</PackagePath>
      </Content>
    </ItemGroup>
  </Target>
  ...

</Project>
```

Damit ein benutzerdefiniertes Ziel in Ihrem Projekt genutzt werden kann, fügen Sie ein `PackageReference`-Element hinzu, das auf das Paket und dessen Version zeigt. Im Gegensatz zu den Tools wird das benutzerdefinierte Zielpaket in die Abhängigkeiten des nutzenden Projekts eingeschlossen.

Sie können konfigurieren, wie das benutzerdefinierte Ziel genutzt werden soll. Da es sich um ein MSBuild-Ziel handelt, kann es von einem angegebenen Ziel abhängig sein, nach einem anderen Ziel ausgeführt werden oder mit dem Befehl `dotnet msbuild -t:<target-name>` manuell aufgerufen werden. Wenn Sie jedoch ein besseres Benutzererlebnis bieten möchten, können Sie projektbezogene Tools und benutzerdefinierte Ziele kombinieren. In diesem Szenario akzeptiert das projektbezogene Tool alle erforderlichen Parameter und übersetzt diese in den erforderlichen [`dotnet msbuild`](../tools/dotnet-msbuild.md)-Aufruf, der das Ziel ausführt. Sie sehen ein Beispiel dieser Art von Synergie im Repository mit den [MVP Summit 2016 Hackathon-Beispielen](https://github.com/dotnet/MVPSummitHackathon2016) im Projekt [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer).

## <a name="see-also"></a>Siehe auch

- [Installieren von .NET Core](../install/index.yml)
- [Vorgehensweise: Verwenden von MSBuild-Projekt-SDKs](/visualstudio/msbuild/how-to-use-project-sdk)
- [Einfügen von MSBuild-Eigenschaften und -Zielen in ein Paket](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package)
