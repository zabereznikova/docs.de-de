---
title: Erstellen einer Projektvorlage für „dotnet new“
description: Hier erfahren Sie, wie Sie eine Projektvorlage für den Befehl „dotnet new“ erstellen.
author: thraka
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: f53f4037f832265a35f65bf2e5096c7e5a37bcf1
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503536"
---
# <a name="tutorial-create-a-project-template"></a>Tutorial: Erstellen einer Projektvorlage

Mit .NET Core können Sie Vorlagen erstellen und bereitstellen, die Projekte, Dateien und sogar Ressourcen generieren. Dieses Tutorial ist der zweite Teil einer Reihe, die zeigt, wie Sie Vorlagen für die Verwendung mit dem Befehl `dotnet new` erstellen, installieren und deinstallieren.

In diesem Teil der Reihe wird Folgendes vermittelt:

> [!div class="checklist"]
>
> * Erstellen der Ressourcen einer Projektvorlage
> * Erstellen des Konfigurationsordners und der Konfigurationsdatei der Vorlage
> * Installieren einer Vorlage unter Verwendung eines Dateipfads
> * Testen einer Elementvorlage
> * Deinstallieren einer Elementvorlage

## <a name="prerequisites"></a>Voraussetzungen

* Absolvieren Sie [Teil 1](cli-templates-create-item-template.md) dieser Tutorialreihe.
* Öffnen Sie ein Terminal, und navigieren Sie zum Ordner _working\templates_.

## <a name="create-a-project-template"></a>Erstellen einer Projektvorlage

Projektvorlagen ermöglichen die Erstellung sofort einsatzbereiter Projekte, sodass Benutzer ganz einfach mit einer funktionierenden Codegrundlage beginnen können. .NET Core enthält einige Projektvorlagen – beispielsweise eine Konsolenanwendung und eine Klassenbibliothek. In diesem Beispiel wird ein neues Konsolenprojekt erstellt, das C# 8.0 aktiviert und einen Einstiegspunkt vom Typ `async main` erzeugt.

Navigieren Sie in Ihrem Terminal zum Ordner _working\templates_, und erstellen Sie einen neuen Unterordner mit dem Namen _consoleasync_. Öffnen Sie den Unterordner, und führen Sie `dotnet new console` aus, um die Standardkonsolenanwendung zu generieren. Die von dieser Vorlage erstellten Dateien müssen bearbeitet werden, um eine neue Vorlage zu erstellen.

```console
working
└───templates
    └───consoleasync
            consoleasync.csproj
            Program.cs
```

## <a name="modify-programcs"></a>Ändern von „Program.cs“

Öffnen Sie die Datei _program.cs_. Da das Konsolenprojekt keinen asynchronen Einstiegspunkt verwendet, fügen wir einen hinzu. Ändern Sie Ihren Code wie folgt, und speichern Sie die Datei.

```csharp
using System;
using System.Threading.Tasks;

namespace consoleasync
{
    class Program
    {
        static async Task Main(string[] args)
        {
            await Console.Out.WriteAsync("Hello World with C# 8.0!");
        }
    }
}
```

## <a name="modify-consoleasynccsproj"></a>Ändern von „consoleasync.csproj“

Als Nächstes aktualisieren wir die C#-Sprachversion des Projekts auf die Version 8.0. Bearbeiten Sie die Datei _consoleasync.csproj_, und fügen Sie einem Knoten vom Typ `<PropertyGroup>` die Einstellung `<LangVersion>` hinzu.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.2</TargetFramework>

    <LangVersion>8.0</LangVersion>

  </PropertyGroup>
  
</Project>
```

## <a name="build-the-project"></a>Erstellen des Projekts

Bevor Sie eine Projektvorlage fertig stellen, sollten Sie sie testen, um sicherzustellen, dass sie ordnungsgemäß kompiliert und ausgeführt wird.

Führen Sie in Ihrem Terminal den folgenden Befehl aus.

```dotnetcli
dotnet run
```

Sie erhalten die folgende Ausgabe.

```console
Hello World with C# 8.0!
```

Die erstellten Ordner _obj_ und _bin_ können mithilfe von `dotnet run` gelöscht werden. Durch Löschen dieser Dateien wird sichergestellt, dass Ihre Vorlage nur die Dateien enthält, die mit ihrer Vorlage zusammenhängen (und keine Dateien, die durch einen Buildvorgang entstanden sind).

Nachdem Sie den Inhalt der Vorlage erstellt haben, müssen Sie als Nächstes im Stammordner der Vorlage die Vorlagenkonfiguration erstellen.

## <a name="create-the-template-config"></a>Erstellen der Vorlagenkonfiguration

Vorlagen werden in .NET Core anhand eines speziellen Ordners und einer Konfigurationsdatei am Stamm Ihrer Vorlage erkannt. In diesem Tutorial befindet sich Ihr Vorlagenordner unter _working\templates\consoleasync_.

Bei der Vorlagenerstellung werden mit Ausnahme des speziellen Konfigurationsordners alle Dateien und Ordner aus dem Vorlagenordner in die Vorlage eingeschlossen. Dieser Konfigurationsordner heißt _.template.config_.

Erstellen Sie zunächst einen neuen Unterordner namens _.template.config_, und öffnen Sie ihn. Erstellen Sie anschließend eine neue Datei namens _template.json_. Ihre Ordnerstruktur sollte wie folgt aussehen.

```console
working
└───templates
    └───consoleasync
        └───.template.config
                template.json
```

Öffnen Sie die Datei _template.json_ in Ihrem bevorzugten Text-Editor, fügen Sie den folgenden JSON-Code ein, und speichern Sie die Datei.

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Console", "C#8" ],
  "identity": "ExampleTemplate.AsyncProject",
  "name": "Example templates: async project",
  "shortName": "consoleasync",
  "tags": {
    "language": "C#",
    "type": "project"
  }
}
```

Diese Konfigurationsdatei enthält alle Einstellungen für Ihre Vorlage. Neben Grundeinstellungen wie `name` und `shortName` enthält die Datei auch einen auf `project` festgelegten Wert vom Typ `tags/type`. Dadurch wird Ihre Vorlage als Projektvorlage gekennzeichnet. Sie können eine beliebige Art von Vorlage erstellen. Die Werte `item` und `project` sind allgemeine Namen, die von .NET Core empfohlen werden, damit Benutzer mühelos nach der Art der gesuchten Vorlage filtern können.

Das Element `classifications` stellt die Spalte **Tags** dar, die angezeigt wird, wenn Sie `dotnet new` ausführen und eine Vorlagenliste abrufen. Benutzer können auch anhand von Klassifizierungstags suchen. Die Eigenschaft `tags` in der JSON-Datei darf nicht mit der Tagliste `classifications` verwechselt werden. Hierbei handelt es sich um zwei unterschiedliche Dinge, die leider ähnlich heißen. Das vollständige Schema für die Datei *template.json* finden Sie im [JSON-Schemaspeicher](http://json.schemastore.org/template). Weitere Informationen zur Datei *template.json* finden Sie im [Wiki zur Erstellung von .NET-Vorlagen](https://github.com/dotnet/templating/wiki).

Nachdem Sie nun über eine gültige Datei vom Typ _.template.config/template.json_ verfügen, ist die Vorlage installationsbereit. Löschen Sie vor der Installation der Vorlage alle zusätzlichen Dateiordner und Dateien, die nicht in Ihre Vorlage eingeschlossen werden sollen (wie etwa die Ordner _bin_ und _obj_). Navigieren Sie in Ihrem Terminal zum Ordner _consoleasync_, und führen Sie `dotnet new -i .\` aus, um die Vorlage aus dem aktuellen Ordner zu installieren. Bei Verwenden eines Linux- oder macOS-Betriebssystems muss ein Schrägstrich verwendet werden: `dotnet new -i ./`.

Dieser Befehl gibt eine Liste mit den installierten Vorlagen aus. Darin sollte nun auch Ihre Vorlage enthalten sein.

```dotnetcli
dotnet new -i .\
```

Sie erhalten eine Ausgabe ähnlich der folgenden.

```console
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Console Application                               console               [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync          [C#]              Common/Console/C#8
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

### <a name="test-the-project-template"></a>Testen der Projektvorlage

Testen Sie als Nächstes Ihre installierte Elementvorlage.

1. Navigieren Sie zum Ordner _test_.

1. Erstellen Sie mit dem folgenden Befehl eine neue Konsolenanwendung, die ein funktionierendes Projekt generiert, das Sie mit dem `dotnet run`-Befehl problemlos testen können.

    ```dotnetcli
    dotnet new consoleasync
    ```

    Sie erhalten die folgende Ausgabe.

    ```console
    The template "Example templates: async project" was created successfully.
    ```

1. Führen Sie das Projekt mithilfe des folgenden Befehls aus.

    ```dotnetcli
    dotnet run
    ```

    Sie erhalten die folgende Ausgabe.

    ```console
    Hello World with C# 8.0!
    ```

Herzlichen Glückwunsch! Sie haben eine Projektvorlage mit .NET Core erstellt und bereitgestellt. Zur Vorbereitung auf den nächsten Teil der Tutorialreihe muss die von Ihnen erstellte Vorlage deinstalliert werden. Löschen Sie außerdem auch alle Dateien aus dem Ordner _test_. Dadurch erhalten Sie eine bereinigte Umgebung, die für den nächsten Hauptabschnitt dieses Tutorials bereit ist.

### <a name="uninstall-the-template"></a>Deinstallieren der Vorlage

Da Sie die Vorlage unter Verwendung eines Dateipfads installiert haben, muss sie mit dem **absoluten** Dateipfad deinstalliert werden. Mithilfe des Befehls `dotnet new -u` können Sie eine Liste der installierten Vorlagen anzeigen. Ihre Vorlage sollte am Ende der Liste aufgeführt sein. Führen Sie den Befehl `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>` mit dem angegebenen Pfad aus, um Ihre Vorlage zu deinstallieren.

```dotnetcli
dotnet new -u
```

Sie erhalten eine Ausgabe ähnlich der folgenden.

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
  C:\working\templates\consoleasync
    Templates:
      Example templates: async project (consoleasync) C#
```

Führen Sie den folgenden Befehl aus, um die Vorlage zu deinstallieren.

```dotnetcli
dotnet new -u C:\working\templates\consoleasync
```

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine Projektvorlage erstellt. Im weiteren Verlauf dieser Tutorialreihe erfahren Sie, wie Sie sowohl die Element- als auch die Projektvorlagen in einer praktischen Datei verpacken.

> [!div class="nextstepaction"]
> [Tutorial: Erstellen eines Vorlagenpakets](cli-templates-create-template-pack.md)
