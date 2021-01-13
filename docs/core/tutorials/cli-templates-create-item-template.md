---
title: Erstellen einer Elementvorlage für „dotnet new“ – .NET-CLI
titleSuffix: ''
description: Hier erfahren Sie, wie Sie eine Elementvorlage für den Befehl „dotnet new“ erstellen. Elementvorlagen können beliebig viele Dateien enthalten.
author: adegeo
ms.date: 12/11/2020
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: d213646a933c77bd0d9a3f1aa9b6b4948b66439b
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633662"
---
# <a name="tutorial-create-an-item-template"></a>Tutorial: Erstellen einer Elementvorlage

Mit .NET können Sie Vorlagen erstellen und bereitstellen, die Projekte, Dateien und sogar Ressourcen generieren. Dieses Tutorial ist der erste Teil einer Reihe, in der Sie erfahren, wie Sie Vorlagen für die Verwendung mit dem Befehl `dotnet new` erstellen, installieren und deinstallieren.

In diesem Teil der Reihe wird Folgendes vermittelt:

> [!div class="checklist"]
>
> * Erstellen einer Klasse für eine Elementvorlage
> * Erstellen des Konfigurationsordners und der Konfigurationsdatei der Vorlage
> * Installieren einer Vorlage unter Verwendung eines Dateipfads
> * Testen einer Elementvorlage
> * Deinstallieren einer Elementvorlage

## <a name="prerequisites"></a>Voraussetzungen

* [.NET 5.0 SDK](https://dotnet.microsoft.com/download) oder höher
* Lesen Sie den Referenzartikel [Benutzerdefinierte Vorlagen für dotnet new](../tools/custom-templates.md).

  Der Referenzartikel enthält grundlegende Informationen zu Vorlagen und zu deren Erstellung. Einige dieser Informationen werden hier wiederholt.

* Öffnen Sie ein Terminal, und navigieren Sie zum Ordner _working\templates_.

## <a name="create-the-required-folders"></a>Erstellen der erforderlichen Ordner

In dieser Reihe werden ein Arbeitsordner als Vorlagenquelle und ein Testordner zum Testen Ihrer Vorlagen verwendet. Der Arbeitsordner und der Testordner müssen sich im gleichen übergeordneten Ordner befinden.

Erstellen Sie zunächst den übergeordneten Ordner. Dieser kann einen beliebigen Namen haben. Erstellen Sie anschließend einen Unterordner mit dem Namen _working_. Erstellen Sie im Ordner _working_ einen Unterordner mit dem Namen _templates_.

Erstellen Sie als Nächstes unter dem übergeordneten Ordner einen Ordner mit dem Namen _test_. Die Ordnerstruktur sollte wie folgt aussehen.

```console
parent_folder
├───test
└───working
    └───templates
```

## <a name="create-an-item-template"></a>Erstellen einer Elementvorlage

Eine Elementvorlage ist eine spezielle Art von Vorlage, die eine oder mehrere Dateien enthält. Diese Art von Vorlage ist hilfreich, wenn Sie beispielsweise eine Konfigurations-, Code- oder Projektmappendatei generieren möchten. In diesem Beispiel wird eine Klasse erstellt, die dem Zeichenfolgentyp eine Erweiterungsmethode hinzufügt.

Navigieren Sie in Ihrem Terminal zum Ordner _working\templates_, und erstellen Sie einen neuen Unterordner mit dem Namen _extensions_. Öffnen Sie den Ordner.

```console
working
└───templates
    └───extensions
```

Erstellen Sie eine neue Datei namens _CommonExtensions.cs_, und öffnen Sie sie mit Ihrem bevorzugten Text-Editor. Diese Klasse stellt eine Erweiterungsmethode namens `Reverse` bereit, die den Inhalt einer Zeichenfolge umkehrt. Fügen Sie den folgenden Code ein, und speichern Sie die Datei:

```csharp
using System;

namespace System
{
    public static class StringExtensions
    {
        public static string Reverse(this string value)
        {
            var tempArray = value.ToCharArray();
            Array.Reverse(tempArray);
            return new string(tempArray);
        }
    }
}
```

Nachdem Sie den Inhalt der Vorlage erstellt haben, müssen Sie als Nächstes im Stammordner der Vorlage die Vorlagenkonfiguration erstellen.

## <a name="create-the-template-config"></a>Erstellen der Vorlagenkonfiguration

Vorlagen werden anhand eines speziellen Ordners und einer Konfigurationsdatei am Stamm Ihrer Vorlage erkannt. In diesem Tutorial befindet sich Ihr Vorlagenordner unter _working\templates\extensions_.

Bei der Vorlagenerstellung werden mit Ausnahme des speziellen Konfigurationsordners alle Dateien und Ordner aus dem Vorlagenordner in die Vorlage eingeschlossen. Dieser Konfigurationsordner heißt _.template.config_.

Erstellen Sie zunächst einen neuen Unterordner namens _.template.config_, und öffnen Sie ihn. Erstellen Sie anschließend eine neue Datei namens _template.json_. Ihre Ordnerstruktur sollte wie folgt aussehen:

```console
working
└───templates
    └───extensions
        └───.template.config
                template.json
```

Öffnen Sie die Datei _template.json_ mit Ihrem bevorzugten Text-Editor, fügen Sie den folgenden JSON-Code ein, und speichern Sie die Datei.

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Code" ],
  "identity": "ExampleTemplate.StringExtensions",
  "name": "Example templates: string extensions",
  "shortName": "stringext",
  "tags": {
    "language": "C#",
    "type": "item"
  }
}
```

Diese Konfigurationsdatei enthält alle Einstellungen für Ihre Vorlage. Neben Grundeinstellungen wie `name` und `shortName` enthält die Datei auch einen auf `item` festgelegten Wert vom Typ `tags/type`. Dadurch wird die Vorlage als Elementvorlage kategorisiert. Sie können eine beliebige Art von Vorlage erstellen. Die Werte `item` und `project` sind allgemeine Namen, die von .NET empfohlen werden, damit Benutzer leicht nach der gesuchten Vorlagenart filtern können.

Das Element `classifications` stellt die Spalte **Tags** dar, die angezeigt wird, wenn Sie `dotnet new` ausführen und eine Vorlagenliste abrufen. Benutzer können auch anhand von Klassifizierungstags suchen. Die Eigenschaft `tags` in der JSON-Datei darf nicht mit der Tagliste `classifications` verwechselt werden. Hierbei handelt es sich um zwei unterschiedliche Dinge, die leider ähnlich heißen. Das vollständige Schema für die Datei *template.json* finden Sie im [JSON-Schemaspeicher](http://json.schemastore.org/template). Weitere Informationen zur Datei *template.json* finden Sie im [Wiki zur Erstellung von .NET-Vorlagen](https://github.com/dotnet/templating/wiki).

Nachdem Sie nun über eine gültige Datei vom Typ _.template.config/template.json_ verfügen, ist die Vorlage installationsbereit. Navigieren Sie in Ihrem Terminal zum Ordner _extensions_, und führen Sie den folgenden Befehl aus, um die Vorlage aus dem aktuellen Ordner zu installieren:

* **Unter Windows:** `dotnet new -i .\`
* **Unter Linux oder macOS:** `dotnet new -i ./`

Dieser Befehl gibt eine Liste mit den installierten Vorlagen aus. Darin sollte nun auch Ihre Vorlage enthalten sein.

```console
C:\working\templates\extensions> dotnet new -i .\
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name               Language          Tags
--------------------------------------------      -------------------      ------------      ----------------------
Example templates: string extensions              stringext                [C#]              Common/Code
Console Application                               console                  [C#], F#, VB      Common/Console
Class library                                     classlib                 [C#], F#, VB      Common/Library
WPF Application                                   wpf                      [C#], VB          Common/WPF
```

## <a name="test-the-item-template"></a>Testen der Elementvorlage

Testen Sie als Nächstes Ihre installierte Elementvorlage. Navigieren Sie zum Ordner _test/_ , und erstellen Sie mithilfe des Befehls `dotnet new console` eine neue Konsolenanwendung. Dadurch wird ein funktionierendes Projekt generiert, das Sie mühelos mit dem Befehl `dotnet run` testen können.

```dotnetcli
dotnet new console
```

Sie erhalten eine Ausgabe ähnlich der folgenden.

```console
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on C:\test\test.csproj...
  Restore completed in 54.82 ms for C:\test\test.csproj.

Restore succeeded.
```

Führen Sie das Projekt mit Folgendem aus.

```dotnetcli
dotnet run
```

Sie erhalten die folgende Ausgabe.

```console
Hello World!
```

Führen Sie `dotnet new stringext` aus, um _CommonExtensions.cs_ auf der Grundlage der Vorlage zu generieren.

```dotnetcli
dotnet new stringext
```

Sie erhalten die folgende Ausgabe.

```console
The template "Example templates: string extensions" was created successfully.
```

Ändern Sie den Code in _Program.cs_, um die Zeichenfolge `"Hello World"` mit der von der Vorlage bereitgestellten Erweiterungsmethode umzukehren.

```csharp
Console.WriteLine("Hello World!".Reverse());
```

Führen Sie das Programm erneut aus. Das Ergebnis ist nun umgekehrt:

```dotnetcli
dotnet run
```

Sie erhalten die folgende Ausgabe.

```console
!dlroW olleH
```

Herzlichen Glückwunsch! Sie haben eine Elementvorlage mit .NET erstellt und bereitgestellt. Zur Vorbereitung auf den nächsten Teil der Tutorialreihe muss die von Ihnen erstellte Vorlage deinstalliert werden. Löschen Sie außerdem auch alle Dateien aus dem Ordner _test_. Dadurch erhalten Sie eine bereinigte Umgebung, die für den nächsten Hauptabschnitt dieses Tutorials bereit ist.

## <a name="uninstall-the-template"></a>Deinstallieren der Vorlage

Da Sie die Vorlage unter Verwendung eines Dateipfads installiert haben, muss sie mit dem **absoluten** Dateipfad deinstalliert werden. Mithilfe des Befehls `dotnet new -u` können Sie eine Liste der installierten Vorlagen anzeigen. Ihre Vorlage sollte am Ende der Liste aufgeführt sein. Deinstallieren Sie Ihre Vorlage mit dem aufgeführten Deinstallationsbefehl (`Uninstall Command`).

```dotnetcli
dotnet new -u
```

Sie erhalten eine Ausgabe ähnlich der folgenden.

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ProjectTemplates.2.2
    Details:
      NuGetPackageId: Microsoft.DotNet.Common.ProjectTemplates.2.2
      Version: 1.0.2-beta4
      Author: Microsoft
    Templates:
      Class library (classlib) C#
      Class library (classlib) F#
      Class library (classlib) VB
      Console Application (console) C#
      Console Application (console) F#
      Console Application (console) VB
    Uninstall Command:
      dotnet new -u Microsoft.DotNet.Common.ProjectTemplates.2.2

... cut to save space ...

C:\Test\templatetutorial\working\templates\extensions
    Templates:
      Example templates: string extensions (stringext) C#
    Uninstall Command:
      dotnet new -u C:\working\templates\extensions
```

Führen Sie den in der Ausgabe gezeigten Deinstallationsbefehl (`Uninstall Command`) aus, um die von Ihnen erstellte Vorlage zu deinstallieren.

```dotnetcli
dotnet new -u C:\working\templates\extensions
```

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine Elementvorlage erstellt. Im nächsten Teil dieser Tutorialreihe erfahren Sie, wie Sie eine Projektvorlage erstellen.

> [!div class="nextstepaction"]
> [Tutorial: Erstellen einer Projektvorlage](cli-templates-create-project-template.md)
