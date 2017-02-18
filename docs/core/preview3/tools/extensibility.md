---
title: .NET Core-CLI-Erweiterbarkeitsmodell | Microsoft-Dokumentation
description: .NET Core-CLI-Erweiterbarkeitsmodell
keywords: CLI, Erweiterbarkeit, benutzerdefinierte Befehle, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 02/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fffc3400-aeb9-4c07-9fea-83bc8dbdcbf3
translationtype: Human Translation
ms.sourcegitcommit: 5a1ba8984d93795e4628a7b911307d513e8de8d1
ms.openlocfilehash: 1b6bc46639fda60e4a23c1ea66d0d0ca8b58acb7

---

# <a name="net-core-cli-extensibility-model-net-core-tools-rc4"></a>.NET Core-CLI-Erweiterbarkeitsmodell (.NET Core Tools RC4)

> [!WARNING]
> Dieses Thema gilt für .NET Core Tools RC4. Informationen zu .NET Core Preview 2-Tools finden Sie im Thema [.NET Core-CLI-Erweiterbarkeitsmodell](../../tools/dotnet-test.md).

## <a name="overview"></a>Übersicht
In diesem Dokument werden die Hauptverfahren beschrieben, mit denen die CLI-Tools erweitert werden, und die Szenarios erläutert, die jedes dieser Tools antreiben. Es wird dargestellt, wie die Tools genutzt werden sollen und wie beide Arten der Tools erstellt werden. 

## <a name="how-to-extend-cli-tools"></a>So können Sie CLI-Tools erweitern
Die RC4 CLI-Tools können auf drei Arten erweitert werden:

1. Projektweise über NuGet-Pakete
2. Über NuGet-Pakete mit benutzerdefinierten Zielen  
3. Über die Systemvariable PATH

Die drei oben beschriebenen Erweiterbarkeitsmechanismen schließen sich nicht gegenseitig aus. Sie können alle oder nur einen verwenden oder sie kombinieren. Welchen Sie auswählen, hängt größtenteils davon ab, welches Ziel Sie mit der Erweiterung erreichen möchten.

## <a name="per-project-based-extensibility"></a>Projektbezogene Erweiterbarkeit
Projektbezogene Tools sind [frameworkabhängige Bereitstellungen](../deploying/index.md), die als NuGet-Pakete verteilt werden. Tools sind nur im Kontext des Projekts, das auf sie verweist, und für das sie wiederhergestellt werden, verfügbar. Ein Aufruf außerhalb des Projektkontexts (beispielsweise außerhalb des Verzeichnisses, das das Projekt enthält) schlägt fehl, da der Befehl nicht gefunden werden kann.

Diese Tools sind ideal für Buildserver, da nichts außer der Projektdatei erforderlich ist. Der Buildprozess führt die Wiederherstellung für das Projekt, das es erstellt, aus, und die Tools stehen zur Verfügung. Sprachprojekte, wie F#, befinden sich auch in dieser Kategorie. Immerhin kann jedes Projekt nur in einer bestimmten Sprache geschrieben werden. 

Schließlich bietet dieses Erweiterbarkeitsmodell Unterstützung für die Erstellung von Tools, die Zugriff auf die Buildausgabe des Projekts benötigen. Verschiedene Razor-Ansicht-Tools in [ASP.NET](https://www.asp.net/)-MVC-Anwendungen fallen z.B. in diese Kategorie. 

### <a name="consuming-per-project-tools"></a>Tools pro Projekt verwenden
Zum Nutzen dieser Tools müssen Sie das Element `<DotNetCliToolReference>` für jedes Tool hinzufügen, das Sie der Projektdatei verwenden möchten. Im Element `<DotNetCliToolReference>` verweisen Sie auf das Paket, in dem sich das Tool befindet, und geben die Version an, die Sie benötigen. Nach der Ausführung von `dotnet restore` werden das Tool und die zugehörigen Abhängigkeiten wiederhergestellt. 

Für Tools, die die Buildausgabe des Projekts zur Ausführung laden müssen, gibt es normalerweise eine andere Abhängigkeit, die unter den regulären Abhängigkeiten in der Projektdatei angezeigt wird. Da die RC4-Version der CLI als Buildmodul MSBuild verwendet, wird empfohlen, diese Teile des Tools als benutzerdefinierte MSBuild-Ziele- und -Aufgaben zu schreiben, da sie auf diese Weise am gesamten Buildprozess teilnehmen können. Außerdem können sie mühelos sämtliche Daten abrufen, die über den Build erstellt werden, z.B. den Speicherort der Ausgabedateien, die aktuell erstellte Konfiguration usw. Alle diese Informationen in RC4 bilden eine Gruppe von MSBuild-Eigenschaften, die von jedem beliebigen Ziel gelesen werden können. Weiter unten in diesem Dokument erfahren Sie, wie über NuGet ein benutzerdefiniertes Ziel hinzugefügt wird. 

Betrachten wir ein Beispiel, bei dem ein Tools-Only-Tool zu einem einfachen Projekt hinzugefügt wird. Für einen Beispielbefehl namens `dotnet-api-search`, mit dem Sie die NuGet-Pakete nach der angegebenen API durchsuchen können, sehen Sie hier die Projektdatei einer Konsolenanwendung, die dieses Tool verwendet:


```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1/TargetFramework>
  </PropertyGroup>

  <!-- The tools reference -->
  <ItemGroup>
    <DotNetCliToolReference Include="dotnet-api-search" Version="1.0.0" />
  </ItemGroup>
</Project>
```

Das Element `<DotNetCliToolReference>` weist eine ähnliche Struktur auf wie das Element `<PackageReference>`. Er benötigt mindestens die Paket-ID des Pakets mit dem Tool und dessen Version. 

### <a name="building-tools"></a>Erstellen von Tools
Wie bereits erwähnt, sind Tools nur portable Konsolenanwendungen. Sie würden eins erstellen, so wie Sie alle Konsolenanwendungen erstellen würden. Nachdem Sie es erstellt haben, würden Sie den [`dotnet pack`](dotnet-pack.md)-Befehl ausführen, um ein NuGet-Paket (Nupkg) zu erstellen, das Ihren Code, die Informationen zu seinen Abhängigkeiten usw. enthält. Der Verfasser kann den Paketnamen bestimmen, aber die Anwendung darin, das tatsächliche Binär-Tool, muss der `dotnet-<command>`-Konvention entsprechen, damit `dotnet` es aufrufen kann. 

> [!NOTE]
> In Vor-RC3-Versionen der .NET Core-Befehlszeilentools hat der Befehl `dotnet pack` einen Fehler, der dazu führt, dass die Datei `runtime.config.json` nicht mit dem Tool gepackt wird. Fehlt diese Datei, treten zur Laufzeit Fehler auf. Wenn dieses Verhalten auftritt, sollten Sie auf die neuesten Tools aktualisieren und erneut versuchen, den Befehl `dotnet pack` auszuführen. 

Da Tools portable Anwendungen sind, benötigt der Benutzer des Tools die Version der .NET Core-Bibliotheken, für die das Tool entwickelt wurde, um das Tool auszuführen. Jede andere Abhängigkeit, die das Tool verwendet und nicht in den .NET Core-Bibliotheken enthalten ist, wird wiederhergestellt und im NuGet-Cache gespeichert. Das gesamte Tool wird daher mithilfe der Assemblys aus den .NET Core-Bibliotheken sowie Assemblys aus dem NuGet-Cache ausgeführt. 

Diese Art von Tools haben ein Abhängigkeitsdiagramm, das komplett unabhängig ist vom Abhängigkeitsdiagramm des Projekts, welches sie verwendet. Der Wiederherstellungsvorgang wird zuerst die Projektabhängigkeiten wiederherstellen und dann jedes der Tools und deren Abhängigkeiten. 

Umfangreichere Beispiele und verschiedene Kombinationen dessen finden Sie im [.NET Core-CLI-Repository](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/TestAssets/TestProjects). Sie finden auch die [Implementierung von verwendeten Tools](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/TestAssets/TestPackages) im gleichen Repository. 

### <a name="custom-targets"></a>Benutzerdefinierte Ziele
NuGet bietet seit geraumer Zeit die Möglichkeit, benutzerdefinierte MSBuild-Ziel- und Eigenschaftendateien zu packen. Sie finden die offizielle Dokumentation dazu auf der [Website der NuGet-Dokumentation](https://docs.microsoft.com/nuget/create-packages/creating-a-package#including-msbuild-props-and-targets-in-a-package). Mit dem Schritt in der CLI zum Verwenden von MSBuild gilt derselbe Mechanismus für Erweiterbarkeit für .NET Core-Projekte. Sie nutzen diese Art von Erweiterbarkeit, wenn Sie den Buildprozess erweitern möchten, im Buildprozess auf Artefakte wie generierte Dateien zugreifen oder die Konfiguration überprüfen möchten, in der der Build aufgerufen wird usw. 

Zur Referenz ist die Projektdatei des Beispielziels unten aufgeführt. Sie sehen, wie die neue `csproj`-Syntax genutzt wird, um den Befehl `dotnet pack` anzuweisen, was gepackt werden soll, damit die Zieldateien und Assemblys im Ordner `build` im Paket platziert werden. Beachten Sie das Element `<ItemGroup>` darunter, dessen `Label`-Eigenschaft auf „dotnet pack instructions“ festgelegt ist. 

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
    <Content Include="build\*.targets;$(OutputPath)\*.dll;$(OutputPath)\*.json">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
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

Die Verwendung des benutzerdefinierten Ziels hängt ausschließlich von seiner Konfiguration ab. Da es das übliche MSBuild-Ziel ist, kann es von einem angegebenen Ziel abhängen, nach einem anderen Ziel ausgeführt werden und mit dem Befehl `dotnet msbuild /t:<target-name>` auch manuell aufgerufen werden. 

Wenn Sie jedoch Ihren Benutzern eine bessere Erfahrung bieten möchten, können Sie projektbezogene Tools und benutzerdefinierte Ziele kombinieren. In diesem Szenario akzeptiert das projektbezogene Tool lediglich die benötigten Parameter, die in den erforderlichen Aufruf von `dotnet msbuild` übersetzt werden, über den das Ziel ausgeführt wird. Sie sehen ein Beispiel dieser Art von Synergie im Repository mit den [MVP Summit 2016 Hackathon-Beispielen](https://github.com/dotnet/MVPSummitHackathon2016) im Projekt [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer). 

### <a name="path-based-extensibility"></a>PFAD-basierte Erweiterbarkeit
Die PFAD-basierte Erweiterbarkeit wird in der Regel für Entwicklungscomputer verwendet, bei denen Sie ein Tool brauchen, das konzeptionell mehr als ein einzelnes Projekt abdeckt. Der größte Nachteil dieses Extensionsmechanismus ist, dass es mit dem Computer verknüpft ist, auf dem das Tool existiert. Wenn Sie ihn auf einem anderen Computer benötigen, müssten Sie ihn bereitstellen.

Dieses Muster der Erweiterbarkeit des CLI-Toolsets ist sehr einfach. Wie in der [Übersicht über die .NET Core-CLI](index.md) beschrieben, kann der `dotnet`-Treiber jeden Befehl ausführen, der nach der `dotnet-<command>`-Konvention benannt ist. Die Standardaufkösungslogik wird zuerst mehrere Speicherorte überprüfen und schließlich an den SYSTEMPFAD fallen. Wenn der angeforderte Befehl im SYSTEMPFAD vorhanden und eine Binärdatei ist, die aufgerufen werden kann, wird sie der `dotnet`-Treiber aufrufen. 

Die Binärdatei kann nahezu alles sein, das vom Betriebssystem ausgeführt werden kann. Auf Unix-Systemen bedeutet dies alles, das das ausführbare Bit über `chmod +x` festgelegt hat. Auf Windows bedeutet dies alles, das Windows ausführen kann. 

Als Beispiel sehen wir uns eine sehr einfache Implementierung eines `dotnet clean`-Befehls an. Wir verwenden `bash`, um den Befehl zu implementieren. Der Befehl löscht einfach die `bin/`- und `obj/`-Verzeichnisse im aktuellen Verzeichnis. Wenn das `--lock`-Argument übergeben wird, wird es auch die `project.lock.json`-Datei löschen. Der gesamte Befehl wird unten angezeigt. 

```bash
#!/bin/bash

# Delete the bin and obj dirs
rm -rf bin/ obj/

LOCK_FILE=$1
if [[ "$LOCK_FILE" = "--lock" ]]; then
    rm project.lock.json
fi


echo "Cleaning complete..."
```

Auf Mac OS können wir dieses Skript als `dotnet-clean` speichern und sein ausführbares Bit mit `chmod +x dotnet-clean` festlegen. Wir erstellen dann eine symbolische Verknüpfung in `/usr/local/bin` mit dem Befehl `ln -s dotnet-clean /usr/local/bin/`. So kann der Befehl „Bereinigen“ mit der `dotnet clean`-Syntax aufgerufen werden. Sie können dies testen, indem Sie eine App erstellen, `dotnet build` und anschließend `dotnet clean` darauf ausführen. 

## <a name="conclusion"></a>Schlussfolgerung
Die .NET Core CLI-Tools lassen drei wichtige Erweiterungsmöglichkeiten zu. Die pprojektbezogenen Tools sind im Kontext des Projekts enthalten, aber sie ermöglichen eine einfache Installation über die Wiederherstellung. Mithilfe benutzerdefinierter Ziele können Sie den Buildprozess einfach mit benutzerdefinierten Aufgaben erweitern. Auf PATH basierende Tools eignen sich für allgemeine projektübergreifende Tools, die auf einem einzelnen Computer verwendet werden. 




<!--HONumber=Feb17_HO2-->


