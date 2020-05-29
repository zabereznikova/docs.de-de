---
title: '.NET Core-Projekt-SDKs: Übersicht'
titleSuffix: ''
description: Erfahren Sie mehr über .NET Core-Projekt-SDKs.
ms.date: 02/02/2020
ms.topic: conceptual
ms.openlocfilehash: 88ec1bf2c4917c69b80b997d090219097694d2bc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206061"
---
# <a name="net-core-project-sdks"></a>.NET Core-Projekt-SDKs

.NET Core-Projekten ist ein SDK (Software Development Kit) zugeordnet. Jedes *Projekt-SDK* besteht aus einer Reihe von MSBuild-[Zielen](/visualstudio/msbuild/msbuild-targets) und zugehörigen [Tasks](/visualstudio/msbuild/msbuild-tasks), mit denen Code kompiliert, paketiert und veröffentlicht wird. Ein Projekt, das auf ein Projekt-SDK verweist, wird zuweilen auch als *Projekt im SDK-Stil* bezeichnet.

## <a name="available-sdks"></a>Verfügbare SDKs

Für .NET Core sind die folgenden SDKs verfügbar:

| Id | Beschreibung | Repository|
| - | - | - |
| `Microsoft.NET.Sdk` | Das .NET Core SDK | https://github.com/dotnet/sdk |
| `Microsoft.NET.Sdk.Web` | Das .NET Core [Web SDK](/aspnet/core/razor-pages/web-sdk) | https://github.com/aspnet/websdk |
| `Microsoft.NET.Sdk.Razor` | Das .NET Core [Razor SDK](/aspnet/core/razor-pages/sdk) |
| `Microsoft.NET.Sdk.Worker` | Das .NET Core Worker Service SDK |
| `Microsoft.NET.Sdk.WindowsDesktop` | Das .NET Core WinForms and WPF SDK |

Das .NET Core SDK ist das Basis-SDK für .NET Core. Die anderen SDKs verweisen auf das .NET Core SDK, und Projekten, die den anderen SDKs zugeordnet sind, stehen alle .NET Core SDK-Eigenschaften zur Verfügung. Das Web SDK hängt z. B. sowohl vom .NET Core SDK als auch vom Razor SDK ab.

Sie können auch selbst ein SDK erstellen, das über NuGet verteilt werden kann.

## <a name="project-files"></a>Projektdateien

.NET Core-Projekte basieren auf dem [MSBuild](/visualstudio/msbuild/msbuild)-Format. Projektdateien mit der Erweiterung *.csproj* für C#-Projekte und *.fsproj* für F#-Projekte, weisen das XML-Format auf. Das Stammelement einer MSBuild-Projektdatei ist das Element [Project](/visualstudio/msbuild/project-element-msbuild). Das `Project`-Element besitzt ein optionales `Sdk`-Attribut, das angibt, welches SDK (und welche Version) verwendet werden soll. Um die .NET Core-Tools zu verwenden und Ihren Code zu erstellen, legen Sie das `Sdk`-Attribut auf eine der IDs in der Tabelle [Verfügbare SDKs](#available-sdks) fest.

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

Indem mit einer dieser Möglichkeiten auf ein SDK verwiesen wird, werden Projektdateien für .NET Core erheblich vereinfacht. Während der Auswertung des Projekts fügt MSBuild implizite Importe in der Projektdatei hinzu: im oberen Bereich für `Sdk.props`, im unteren Bereich für `Sdk.targets`.

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

### <a name="default-compilation-includes"></a>Standardmäßige Includedateien für die Kompilierung

Die standardmäßigen Include- und Excludedateien für Compile-Elemente, eingebettete Ressourcen und `None`-Elemente sind im SDK definiert. Im Gegensatz zu SDK-Projekten, die nicht das .NET Framework als Ziel verwenden, müssen Sie diese Elemente nicht in Ihrer Projektdatei angeben, da die Standardwerte die meisten gängigen Anwendungsfälle abdecken. Dadurch wird die Projektdatei kleiner, verständlicher und kann bei Bedarf manuell bearbeitet werden.

Die folgende Tabelle zeigt, welche Elemente und welche [Globs](https://en.wikipedia.org/wiki/Glob_(programming)) im .NET Core SDK enthalten und ausgeschlossen sind:

| Element           | Glob einschließen                              | Glob ausschließen                                                  | Glob entfernen              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| Compile           | \*\*/\*.cs (oder andere Spracherweiterungen) | \*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc  | Nicht zutreffend                      |
| EmbeddedResource  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | Nicht zutreffend                      |
| Keine              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | \*\*/\*.cs; \*\*/\*.resx |

> [!NOTE]
> Die Ordner `./bin` und `./obj` aus, die von den MSBuild-Eigenschaften `$(BaseOutputPath)` und `$(BaseIntermediateOutputPath)` dargestellt werden, sind standardmäßig von den Globs ausgeschlossen. Excludedateien werden durch die Eigenschaft `$(DefaultItemExcludes)` dargestellt.

#### <a name="build-errors"></a>Buildfehler

Wenn Sie beliebige dieser Elemente explizit in Ihrer Projektdatei definieren, erhalten Sie wahrscheinlich eine „NETSDK1022“-Buildfehlermeldung ähnlich der folgenden:

  > Doppelte „Compile“-Elemente wurden eingeschlossen. .NET SDK enthält „Compile“-Elemente aus Ihrem Projektverzeichnis in der Standardeinstellung. Sie können diese Elemente aus Ihrer Projektdatei entfernen oder die Eigenschaft „EnableDefaultCompileItems“ auf „FALSE“ festlegen, wenn Sie sie explizit in Ihrer Projektdatei einfügen möchten.

  > Doppelte „EmbeddedResource“-Elemente wurden eingeschlossen. Das .NET SDK enthält „EmbeddedResource“-Elemente aus Ihrem Projektverzeichnis in der Standardeinstellung. Sie können diese Elemente aus Ihrer Projektdatei entfernen oder die Eigenschaft „EnableDefaultEmbeddedResourceItems“ auf FALSE festlegen, wenn Sie sie explizit in Ihrer Projektdatei einschließen möchten.

Zum Beheben der Fehler führen Sie eine der folgenden Aktionen aus:

- Entfernen Sie die expliziten `Compile`-, `EmbeddedResource`- oder `None`-Elemente, die den in der vorherigen Tabelle aufgeführten impliziten Elementen entsprechen.

- Um jedes implizite Einbeziehen von Dateien zu deaktivieren, legen Sie die `EnableDefaultItems`-Eigenschaft auf `false` fest:

  ```xml
  <PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
  </PropertyGroup>
  ```

  Wenn Sie Dateien angeben möchten, die mit Ihrer Anwendung veröffentlicht werden sollen, können Sie weiterhin die bekannten MSBuild-Mechanismen dafür verwenden, wie etwa das `Content`-Element.

- Deaktivieren Sie selektiv nur `Compile`-, `EmbeddedResource`- oder `None`-Globs, indem Sie die `EnableDefaultCompileItems`-, `EnableDefaultEmbeddedResourceItems`- oder `EnableDefaultNoneItems`-Eigenschaft auf `false` festlegen:

  ```xml
  <PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
    <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
  </PropertyGroup>
  ```

  Wenn Sie nur `Compile`-Globs deaktivieren, zeigt der Projektmappen-Explorer in Visual Studio die \*.cs-Elemente weiterhin als Teil des Projekts an, eingeschlossen als `None`-Elemente. Um das implizite `None`-Glob zu deaktivieren, legen Sie auch `EnableDefaultNoneItems` auf `false` fest.

## <a name="customize-the-build"></a>Anpassen des Builds

Es gibt verschiedene Möglichkeiten, [einen Build anzupassen](/visualstudio/msbuild/customize-your-build). Sie können eine Eigenschaft überschreiben, indem Sie sie als Argument an einen [msbuild](/visualstudio/msbuild/msbuild-command-line-reference)- oder [dotnet](../tools/index.md)-Befehl übergeben. Sie können die Eigenschaft auch zur Projektdatei oder zu einer *Directory.Build.props*-Datei hinzufügen. Eine Liste mit nützlichen Eigenschaften für .NET Core-Projekte finden Sie unter [MSBuild-Eigenschaften für .NET Core SDK-Projekte](msbuild-props.md).

### <a name="custom-targets"></a>Benutzerdefinierte Ziele

.NET Core-Projekte können benutzerdefinierte MSBuild-Ziele und -Eigenschaften für Projekte paketieren, die das Paket nutzen. Verwenden Sie diese Art der Erweiterbarkeit, wenn Sie Folgendes vorhaben:

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

- [Installieren von .NET Core](../install/index.md)
- [Vorgehensweise: Verwenden von MSBuild-Projekt-SDKs](/visualstudio/msbuild/how-to-use-project-sdk)
- [Einfügen von MSBuild-Eigenschaften und -Zielen in ein Paket](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package)
