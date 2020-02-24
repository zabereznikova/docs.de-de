---
title: Erstellen eines Vorlagenpakets für „dotnet new“
description: Hier erfahren Sie, wie Sie eine CSPROJ-Datei zum Erstellen eines Vorlagenpakets für den Befehl „dotnet new“ erstellen.
author: thraka
ms.date: 12/10/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 5bc926861dd6a501d7c2d24bd5f7c4116cc78b2c
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503491"
---
# <a name="tutorial-create-a-template-pack"></a>Tutorial: Erstellen eines Vorlagenpakets

Mit .NET Core können Sie Vorlagen erstellen und bereitstellen, die Projekte, Dateien und sogar Ressourcen generieren. Dieses Tutorial ist der dritte Teil einer Reihe, die zeigt, wie Sie Vorlagen für die Verwendung mit dem Befehl `dotnet new` erstellen, installieren und deinstallieren.

In diesem Teil der Reihe wird Folgendes vermittelt:

> [!div class="checklist"]
>
> * Erstellen eines CSPROJ-Projekts zur Erstellung eines Vorlagenpakets
> * Konfigurieren der Projektdatei zum Ausführen eines Packvorgangs
> * Installieren einer Vorlage aus einer NuGet-Paketdatei
> * Deinstallieren einer Vorlage anhand der Paket-ID

## <a name="prerequisites"></a>Voraussetzungen

* Absolvieren Sie [Teil 1](cli-templates-create-item-template.md) und [Teil 2](cli-templates-create-project-template.md) dieser Tutorialreihe.

  In diesem Tutorial werden die beiden Vorlagen verwendet, die in den ersten beiden Teilen dieses Tutorials erstellt wurden. Sie können auch eine andere Vorlage verwenden, solange diese als Ordner in den Ordner _working\templates\\_ kopiert wird.

* Öffnen Sie ein Terminal, und navigieren Sie zum Ordner _working\\_ .

## <a name="create-a-template-pack-project"></a>Erstellen eines Vorlagenpaketprojekts

Bei einem Vorlagenpaket handelt es sich um eine Datei, in die mindestens eine Vorlage gepackt wurde. Wenn Sie ein Paket installieren oder deinstallieren, werden alle darin enthaltenen Vorlagen hinzugefügt bzw. entfernt. In den vorherigen Teilen dieser Tutorialreihe wurden jeweils nur einzelne Vorlagen verwendet. Wenn Sie eine nicht gepackte Vorlage weitergeben möchten, müssen Sie den Vorlagenordner kopieren und die Installation unter Verwendung dieses Ordners durchführen. Ein Vorlagenpaket ist eine einzelne Datei, die mehrere Vorlagen enthalten kann, was die Weitergabe vereinfacht.

Bei Vorlagenpaketen handelt es sich um NuGet-Paketdateien ( _.nupkg_). Das bedeutet, sie können wie jedes andere NuGet-Paket in einen NuGet-Feed hochgeladen werden. Der Befehl `dotnet new -i` unterstützt die Installation von Vorlagenpaketen aus einem NuGet-Paketfeed. Darüber hinaus kann ein Vorlagenpaket auch direkt über eine _NUPKG-Datei_ installiert werden.

Üblicherweise wird eine C#-Projektdatei verwendet, um Code zu kompilieren und eine Binärdatei zu erstellen. Das Projekt kann jedoch auch verwendet werden, um ein Vorlagenpaket zu generieren. Durch Ändern der Einstellungen der _CSPROJ-Datei_ können Sie sicherstellen, dass kein Code kompiliert wird, und stattdessen alle Ressourcen ihrer Vorlagen als Ressourcen einschließen. Wenn dieses Projekt erstellt wird, wird ein Vorlagenpaket in Form eines NuGet-Pakets erzeugt.

Das erstellte Paket enthält die zuvor erstellte [Elementvorlage](cli-templates-create-item-template.md) und [Paketvorlage](cli-templates-create-project-template.md). Da wir die beiden Vorlagen im Ordner _working\templates\\_ zusammengefasst haben, können wir den Ordner _working_ für die _CSPROJ-Datei_ verwenden.

Navigieren Sie in Ihrem Terminal zum Ordner _working_. Erstellen Sie ein neues Projekt, und legen Sie den Namen auf `templatepack` und den Ausgabeordner auf den aktuellen Ordner fest.

```dotnetcli
dotnet new console -n templatepack -o .
```

Der Parameter `-n` legt den Dateinamen für _.csproj_ auf _templatepack.csproj_ fest. Der Parameter `-o` erstellt die Dateien im aktuellen Verzeichnis. Das Ergebnis sollte in etwa wie in der folgenden Ausgabe aussehen:

```dotnetcli
dotnet new console -n templatepack -o .
```

```console
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on .\templatepack.csproj...
  Restore completed in 52.38 ms for C:\working\templatepack.csproj.

Restore succeeded.
```

Öffnen Sie als Nächstes die Datei _templatepack.csproj_ in Ihrem bevorzugten Editor, und ersetzen Sie den Inhalt durch den folgenden XML-Code:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <PackageType>Template</PackageType>
    <PackageVersion>1.0</PackageVersion>
    <PackageId>AdatumCorporation.Utility.Templates</PackageId>
    <Title>AdatumCorporation Templates</Title>
    <Authors>Me</Authors>
    <Description>Templates to use when creating an application for Adatum Corporation.</Description>
    <PackageTags>dotnet-new;templates;contoso</PackageTags>

    <TargetFramework>netstandard2.0</TargetFramework>

    <IncludeContentInPack>true</IncludeContentInPack>
    <IncludeBuildOutput>false</IncludeBuildOutput>
    <ContentTargetFolders>content</ContentTargetFolders>
  </PropertyGroup>

  <ItemGroup>
    <Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />
    <Compile Remove="**\*" />
  </ItemGroup>

</Project>
```

Die Einstellungen vom Typ `<PropertyGroup>` im obigen XML-Code sind in drei Gruppen unterteilt: Die erste Gruppe enthält erforderliche Eigenschaften für ein NuGet-Paket. Die drei Einstellungen vom Typ `<Package` haben mit den NuGet-Paketeigenschaften zu tun, die Ihr Paket in einem NuGet-Feed identifizieren. Der Wert von `<PackageId>` dient insbesondere dazu, das Vorlagenpaket mit einem einzelnen Namen zu deinstallieren (anstatt mit einem Verzeichnispfad). Er kann aber auch verwendet werden, um das Vorlagenpaket aus einem NuGet-Feed zu installieren. Die übrigen Einstellungen (etwa `<Title>` und `<PackageTags>`) hängen mit den im NuGet-Feed angezeigten Metadaten zusammen. Weitere Informationen zu NuGet-Einstellungen finden Sie unter [NuGet pack and restore as MSBuild targets](/nuget/reference/msbuild-targets) (NuGet-Befehle „pack“ und „restore“ als MSBuild-Ziele).

Die Einstellung `<TargetFramework>` muss festgelegt werden, damit MSBuild ordnungsgemäß ausgeführt wird, wenn Sie das Projekt mithilfe des Befehls „pack“ kompilieren und packen.

Die letzten drei Einstellungen dienen zur korrekten Konfiguration des Projekts, damit bei der Erstellung die Vorlagen im entsprechenden Ordner in das NuGet-Paket eingeschlossen werden.

`<ItemGroup>` enthält zwei Einstellungen: Die erste Einstellung (`<Content>`) schließt alles aus dem Ordner _templates_ als Inhalt ein. Außerdem werden alle Ordner vom Typ _bin_ oder _obj_ ausgeschlossen, um zu verhindern, dass kompilierter Code eingeschlossen wird (falls Sie Ihre Vorlagen getestet und kompiliert haben). Die zweite Einstellung (`<Compile>`) schließt alle Codedateien von der Kompilierung aus – unabhängig davon, wo sie sich befinden. Diese Einstellung verhindert, dass das für die Vorlagenpaketerstellung verwendete Projekt versucht, den Code in der Ordnerhierarchie _templates_ zu kompilieren.

## <a name="build-and-install"></a>Erstellen und Installieren

Speichern Sie die Datei, und führen Sie anschließend den Befehl „pack“ aus.

```dotnetcli
dotnet pack
```

Dieser Befehl erstellt sowohl Ihr Projekt als auch ein NuGet-Paket im Ordner _working\bin\Debug_.

```dotnetcli
dotnet pack
```

```console
Microsoft (R) Build Engine version 16.2.0-preview-19278-01+d635043bd for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 123.86 ms for C:\working\templatepack.csproj.

  templatepack -> C:\working\bin\Debug\netstandard2.0\templatepack.dll
  Successfully created package 'C:\working\bin\Debug\AdatumCorporation.Utility.Templates.1.0.0.nupkg'.
```

Installieren Sie als Nächstes mithilfe des Befehls `dotnet new -i PATH_TO_NUPKG_FILE` die Vorlagenpaketdatei.

```console
C:\working> dotnet new -i C:\working\bin\Debug\AdatumCorporation.Utility.Templates.1.0.0.nupkg
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Example templates: string extensions              stringext             [C#]              Common/Code
Console Application                               console               [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync          [C#]              Common/Console/C#8
Class library                                     classlib              [C#], F#, VB      Common/Library
```

Wenn Sie das NuGet-Paket in einen NuGet-Feed hochgeladen haben, können Sie den Befehl `dotnet new -i PACKAGEID` verwenden. `PACKAGEID` entspricht dabei der Einstellung `<PackageId>` aus der _CSPROJ-Datei_. Diese Paket-ID ist mit der NuGet-Paket-ID identisch.

## <a name="uninstall-the-template-pack"></a>Deinstallieren des Vorlagenpakets

Beim Entfernen eines Vorlagenpakets spielt es keine Rolle, ob Sie das Vorlagenpaket direkt über die _NUPKG-Datei_ oder per NuGet-Feed installiert haben. Verwenden Sie die Paket-ID (`<PackageId>`) der Vorlage, die Sie deinstallieren möchten. Mithilfe des Befehls `dotnet new -u` können Sie eine Liste der installierten Vorlagen abrufen.

```dotnetcli
dotnet new -u
```

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      dotnet gitignore file (gitignore)
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)

... cut to save space ...

  NUnit3.DotNetNew.Template
    Templates:
      NUnit 3 Test Project (nunit) C#
      NUnit 3 Test Item (nunit-test) C#
      NUnit 3 Test Project (nunit) F#
      NUnit 3 Test Item (nunit-test) F#
      NUnit 3 Test Project (nunit) VB
      NUnit 3 Test Item (nunit-test) VB
  AdatumCorporation.Utility.Templates
    Templates:
      Example templates: async project (consoleasync) C#
      Example templates: string extensions (stringext) C#
```

Führen Sie `dotnet new -u AdatumCorporation.Utility.Templates` aus, um die Vorlage zu deinstallieren. Der Befehl `dotnet new` gibt Hilfeinformationen aus, in denen Ihre zuvor installierten Vorlagen nicht mehr enthalten sein sollten.

Herzlichen Glückwunsch! Sie haben ein Vorlagenpaket installiert und deinstalliert.

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zu Vorlagen (die Ihnen größtenteils bereits bekannt sein dürften) finden Sie im Artikel [Benutzerdefinierte Vorlagen für dotnet new](../tools/custom-templates.md).

* [dotnet/templating GitHub repo Wiki (GitHub-Repositorywiki dotnet/templating)](https://github.com/dotnet/templating/wiki)
* [dotnet/dotnet-template-samples-GitHub-Repository](https://github.com/dotnet/dotnet-template-samples)
* [*template.json*-Schema im JSON-Schemaspeicher](http://json.schemastore.org/template)
