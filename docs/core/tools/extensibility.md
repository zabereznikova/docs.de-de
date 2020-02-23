---
title: .NET Core-CLI-Erweiterbarkeitsmodell
description: Erfahren Sie, wie Sie die .NET Core-CLI erweitern können.
ms.date: 04/12/2017
ms.openlocfilehash: 56a9cedc090ddca446c0ee1a60f2ca49590e7635
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451154"
---
# <a name="net-core-cli-extensibility-model"></a>.NET Core-CLI-Erweiterbarkeitsmodell

In diesem Artikel werden die unterschiedlichen Möglichkeiten vorgestellt, mit denen Sie die .NET Core-CLI erweitern können, und es werden die Szenarien erläutert, in denen diese jeweils genutzt werden.
Sie sehen, wie Sie die Tools verarbeiten und wie unterschiedliche Typen von Tools erstellt werden können.

## <a name="how-to-extend-the-cli"></a>Erweitern der CLI
Die CLI kann auf drei Arten erweitert werden:

1. [Projektweise über NuGet-Pakete](#per-project-based-extensibility)

   Die projektbezogenen Tools sind im Kontext des Projekts enthalten, aber sie ermöglichen eine einfache Installation über die Wiederherstellung.

2. [Über NuGet-Pakete mit benutzerdefinierten Zielen](#custom-targets)

   Mithilfe benutzerdefinierter Ziele können Sie den Buildprozess einfach mit benutzerdefinierten Aufgaben erweitern.

3. [Über die Systemvariable PATH](#path-based-extensibility)

   Auf PATH basierende Tools eignen sich für allgemeine projektübergreifende Tools, die auf einem einzelnen Computer verwendet werden.

Die drei oben beschriebenen Erweiterbarkeitsmechanismen schließen sich nicht gegenseitig aus. Sie können beide oder nur einen verwenden. Welchen Sie auswählen, hängt größtenteils davon ab, welches Ziel Sie mit der Erweiterung erreichen möchten.

## <a name="per-project-based-extensibility"></a>Projektbezogene Erweiterbarkeit
Projektbezogene Tools sind [frameworkabhängige Bereitstellungen](../deploying/index.md#publish-runtime-dependent), die als NuGet-Pakete verteilt werden. Tools sind nur im Kontext des Projekts verfügbar, das auf sie verweist und für das sie gespeichert sind. Ein Aufruf außerhalb des Projektkontexts (z.B. außerhalb des Verzeichnisses, das das Projekt enthält) schlägt fehl, da der Befehl nicht gefunden werden kann.

Diese Tools sind ideal für Buildserver, da nichts außer der Projektdatei erforderlich ist. Der Buildprozess führt die Wiederherstellung für das Projekt, das es erstellt, aus, und die Tools stehen zur Verfügung. Sprachprojekte, wie F#, befinden sich auch in dieser Kategorie, da jedes Projekt nur in einer bestimmten Sprache geschrieben werden kann.

Schließlich bietet dieses Erweiterbarkeitsmodell Unterstützung für die Erstellung von Tools, die Zugriff auf die Buildausgabe des Projekts benötigen. Verschiedene Razor-Ansicht-Tools in [ASP.NET](https://www.asp.net/)-MVC-Anwendungen fallen z.B. in diese Kategorie.

### <a name="consuming-per-project-tools"></a>Tools pro Projekt verwenden
Zum Nutzen dieser Tools müssen Sie das Element `<DotNetCliToolReference>` für jedes Tool hinzufügen, das Sie der Projektdatei verwenden möchten. Im Element `<DotNetCliToolReference>` verweisen Sie auf das Paket, in dem sich das Tool befindet, und geben die Version an, die Sie benötigen. Nach der Ausführung von [`dotnet restore`](dotnet-restore.md) werden das Tool und die zugehörigen Abhängigkeiten wiederhergestellt.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Für Tools, die die Buildausgabe des Projekts zur Ausführung laden müssen, gibt es normalerweise eine andere Abhängigkeit, die unter den regulären Abhängigkeiten in der Projektdatei angezeigt wird. Da die CLI als Build-Engine MSBuild verwendet, wird empfohlen, diese Teile des Tools als benutzerdefinierte MSBuild-[Ziele](/visualstudio/msbuild/msbuild-targets) und -[Aufgaben](/visualstudio/msbuild/msbuild-tasks) zu schreiben, da sie auf diese Weise am gesamten Buildprozess teilnehmen können. Außerdem können sie mühelos sämtliche Daten abrufen, die über den Build erstellt werden, z.B. den Speicherort der Ausgabedateien, die aktuell erstellte Konfiguration usw. Alle diese Informationen bilden eine Gruppe von MSBuild-Eigenschaften, die von jedem beliebigen Ziel gelesen werden können. Weiter unten in diesem Dokument erfahren Sie, wie über NuGet ein benutzerdefiniertes Ziel hinzugefügt wird.

Betrachten wir ein Beispiel, bei dem ein Tools-Only-Tool zu einem einfachen Projekt hinzugefügt wird. Für einen Beispielbefehl namens `dotnet-api-search`, mit dem Sie die NuGet-Pakete nach der angegebenen API durchsuchen können, sehen Sie hier die Projektdatei einer Konsolenanwendung, die dieses Tool verwendet:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <!-- The tools reference -->
  <ItemGroup>
    <DotNetCliToolReference Include="dotnet-api-search" Version="1.0.0" />
  </ItemGroup>
</Project>
```

Das Element `<DotNetCliToolReference>` weist eine ähnliche Struktur auf wie das Element `<PackageReference>`. Er benötigt die Paket-ID des Pakets mit dem Tool und dessen Version, damit ein Wiederherstellungsvorgang ausgeführt werden kann.

### <a name="building-tools"></a>Erstellen von Tools
Wie bereits erwähnt, sind Tools nur portable Konsolenanwendungen. Sie würden ein Tool erstellen, so wie Sie alle Konsolenanwendungen erstellen würden.
Nachdem Sie es erstellt haben, führen Sie den [`dotnet pack`](dotnet-pack.md)-Befehl aus, um ein NuGet-Paket (NUPKG-Datei) zu erstellen, das Ihren Code, die Informationen zu seinen Abhängigkeiten usw. enthält. Die können den Paketnamen benennen, aber die Anwendung darin, das tatsächliche Binär-Tool, muss der `dotnet-<command>`-Konvention entsprechen, damit `dotnet` es aufrufen kann.

> [!NOTE]
> In Versionen der .NET Core-Befehlszeilentools vor RC3 hatte der Befehl `dotnet pack` einen Fehler, der dazu führte, dass die Datei *.runtimeconfig.json* nicht mit dem Tool gepackt wurde. Fehlt diese Datei, treten zur Laufzeit Fehler auf. Wenn dieses Verhalten auftritt, sollten Sie auf die neuesten Tools aktualisieren und erneut versuchen, den Befehl `dotnet pack` auszuführen.

Da Tools portable Anwendungen sind, muss der Benutzer des Tools über die Version der .NET Core-Bibliotheken verfügen, für die das Tool entwickelt wurde, um das Tool auszuführen. Jede andere Abhängigkeit, die das Tool verwendet und nicht in den .NET Core-Bibliotheken enthalten ist, wird wiederhergestellt und im NuGet-Cache gespeichert. Das gesamte Tool wird daher mithilfe der Assemblys aus den .NET Core-Bibliotheken sowie Assemblys aus dem NuGet-Cache ausgeführt.

Diese Art von Tools haben ein Abhängigkeitsdiagramm, das komplett unabhängig ist vom Abhängigkeitsdiagramm des Projekts, welches sie verwendet. Der Wiederherstellungsvorgang wird zuerst die Projektabhängigkeiten wiederherstellen und dann jedes der Tools und deren Abhängigkeiten.

Umfangreichere Beispiele und verschiedene Kombinationen dessen finden Sie im [.NET Core-CLI-Repository](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestProjects).
Sie finden auch die [Implementierung von verwendeten Tools](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestPackages) im gleichen Repository.

## <a name="custom-targets"></a>Benutzerdefinierte Ziele

NuGet kann [benutzerdefinierte MSBuild-Ziele und PROPS-Dateien packen](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package). Seit .NET Core MSBuild verwendet, gilt derselbe Erweiterbarkeitsmechanismus auch für .NET Core-Projekte. Sie nutzen diese Art von Erweiterbarkeit, wenn Sie den Buildprozess erweitern möchten, im Buildprozess auf Artefakte wie generierte Dateien zugreifen oder die Konfiguration überprüfen möchten, in der der Build aufgerufen wird usw.

Im folgenden Beispiel können Sie die Projektdatei des Ziels mithilfe der `csproj`-Syntax anzeigen. Dies zeigt dem [`dotnet pack`](dotnet-pack.md)-Befehl, was genau gepackt werden soll, wobei die Zieldateien sowie die Assemblys in den Ordner *Erstellen* im Paket platziert werden. Beachten Sie das `<ItemGroup>`-Element, das über die Eigenschaft `Label` verfügt, die auf `dotnet pack instructions` festgelegt ist, sowie das Ziel, das darunter definiert ist.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <Description>Sample Packer</Description>
    <VersionPrefix>0.1.0-preview</VersionPrefix>
    <TargetFramework>netstandard1.3</TargetFramework>
    <DebugType>portable</DebugType>
    <AssemblyName>SampleTargets.PackerTarget</AssemblyName>
  </PropertyGroup>
  <ItemGroup>
    <EmbeddedResource Include="Resources\Pkg\dist-template.xml;compiler\resources\**\*" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
    <None Include="build\SampleTargets.PackerTarget.targets" />
  </ItemGroup>
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
  <ItemGroup>
    <PackageReference Include="Microsoft.Extensions.DependencyModel" Version="1.0.1-beta-000933"/>
    <PackageReference Include="Microsoft.Build.Framework" Version="0.1.0-preview-00028-160627" />
    <PackageReference Include="Microsoft.Build.Utilities.Core" Version="0.1.0-preview-00028-160627" />
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
  <ItemGroup />
  <PropertyGroup Label="Globals">
    <ProjectGuid>463c66f0-921d-4d34-8bde-7c9d0bffaf7b</ProjectGuid>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(TargetFramework)' == 'netstandard1.3' ">
    <DefineConstants>$(DefineConstants);NETSTANDARD1_3</DefineConstants>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">
    <DefineConstants>$(DefineConstants);RELEASE</DefineConstants>
  </PropertyGroup>
</Project>
```

Die Nutzung benutzerdefinierter Ziele erfolgt durch Bereitstellung einer `<PackageReference>`, die auf ein Paket und dessen Version innerhalb des Projekts verweist, das erweitert wird. Im Gegensatz zu den Tools wird das benutzerdefinierte Zielpaket in die Hülle der Abhängigkeiten des nutzenden Projekts eingeschlossen.

Die Verwendung des benutzerdefinierten Ziels hängt ausschließlich von seiner Konfiguration ab. Da dies ein MSBuild-Ziel ist, kann es von einem angegebenen Ziel abhängen, nach einem anderen Ziel ausgeführt werden und mit dem Befehl `dotnet msbuild -t:<target-name>` auch manuell aufgerufen werden.

Wenn Sie jedoch Ihren Benutzern eine bessere Erfahrung bieten möchten, können Sie projektbezogene Tools und benutzerdefinierte Ziele kombinieren. In diesem Szenario akzeptiert das projektbezogene Tool lediglich die benötigten Parameter, die in den erforderlichen Aufruf von [`dotnet msbuild`](dotnet-msbuild.md) übersetzt werden, über den das Ziel ausgeführt wird. Sie sehen ein Beispiel dieser Art von Synergie im Repository mit den [MVP Summit 2016 Hackathon-Beispielen](https://github.com/dotnet/MVPSummitHackathon2016) im Projekt [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer).

## <a name="path-based-extensibility"></a>PFAD-basierte Erweiterbarkeit
Die PFAD-basierte Erweiterbarkeit wird in der Regel für Entwicklungscomputer verwendet, bei denen Sie ein Tool brauchen, das konzeptionell mehr als ein einzelnes Projekt abdeckt. Der größte Nachteil dieses Extensionsmechanismus ist, dass es mit dem Computer verknüpft ist, auf dem das Tool existiert. Wenn Sie ihn auf einem anderen Computer benötigen, müssten Sie ihn bereitstellen.

Dieses Muster der Erweiterbarkeit des CLI-Toolsets ist sehr einfach. Wie in der [Übersicht über die .NET Core-CLI](index.md) beschrieben, kann der `dotnet`-Treiber jeden Befehl ausführen, der nach der `dotnet-<command>`-Konvention benannt ist. Die Standardauflösungslogik wird zuerst mehrere Speicherorte überprüfen und schließlich an den SYSTEMPFAD fallen. Wenn der angeforderte Befehl im SYSTEMPFAD vorhanden und eine Binärdatei ist, die aufgerufen werden kann, wird sie der `dotnet`-Treiber aufrufen.

Bei der Datei muss es sich um eine ausführbare Datei handeln. Auf Unix-Systemen bedeutet dies alles, das das ausführbare Bit über `chmod +x` festgelegt hat. Unter Windows können Sie *CMD*-Dateien verwenden.

Sehen wir uns nun die einfache Implementierung eines „Hello World“-Tools an. Wir verwenden jeweils `bash` und `cmd` unter Windows.
Der folgende Befehl liefert einfach „Hello World“ an die Konsole.

```bash
#!/bin/bash

echo "Hello World!"
```

```cmd
echo "Hello World"
```

Auf Mac OS können wir dieses Skript als `dotnet-hello` speichern und sein ausführbares Bit mit `chmod +x dotnet-hello` festlegen. Wir erstellen dann eine symbolische Verknüpfung in `/usr/local/bin` mit dem Befehl `ln -s <full_path>/dotnet-hello /usr/local/bin/`. So kann der Befehl mit der `dotnet hello`-Syntax aufgerufen werden.

Wir können unter Windows das Skript als `dotnet-hello.cmd` speichern und es an einem Speicherort speichern, der sich in einem Systempfad befindet (oder Sie können es einem Ordner hinzufügen, der sich bereits im Pfad befindet). Verwenden Sie danach einfach `dotnet hello`, um dieses Beispiel auszuführen.
