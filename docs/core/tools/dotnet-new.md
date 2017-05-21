---
title: "Befehl „dotnet-new“ – .NET Core-CLI | Microsoft-Dokumentation"
description: Der dotnet-new-Befehl erstellt neue .NET Core-Projekte im aktuellen Verzeichnis.
keywords: dotnet-new, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
ms.translationtype: Human Translation
ms.sourcegitcommit: 68fbe2e9895825bbbb41cfe025bfdf1d4f9d3d04
ms.openlocfilehash: 14279ea6fdf4af52c0492f2dad1171d8150ac95b
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---

# <a name="dotnet-new"></a>dotnet-new

## <a name="name"></a>Name

`dotnet-new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.

## <a name="synopsis"></a>Übersicht

```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet new` bietet eine praktische Möglichkeit, ein gültiges .NET Core-Projekt zu initialisieren. 

Der Befehl ruft das [Vorlagenmodul](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.

## <a name="arguments"></a>Argumente

`TEMPLATE`

Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird. Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können. Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).

Der Befehl enthält eine Standardliste mit Vorlagen. Verwenden Sie `dotnet new -all`, um eine Liste der verfügbaren Vorlagen abzurufen. Die folgende Tabelle zeigt die Vorlagen, die bereits mit dem SDK vorinstalliert sind. Die Standardsprache für die Vorlage wird in den Klammern angezeigt.

|Vorlagenbeschreibung  | Vorlagenname  | Sprachen |
|----------------------|----------------|-----------|
| Konsolenanwendung  | Konsole        | [C#], F#  |
| Klassenbibliothek        | classlib       | [C#], F#  |
| Unittestprojekt    | mstest         | [C#], F#  |
| xUnit-Testprojekt   | xunit          | [C#], F#  |
| ASP.NET Core leer   | Web            | [C#]      |
| ASP.NET Core-Webapp | MVC            | [C#], F#  |
| ASP.NET Core-Web-API | Web-API         | [C#]      |
| NuGet-Konfiguration         | nugetconfig    |           |
| Web-Konfiguration           | webconfig      |           |
| Projektmappendatei        | sln            |           |

## <a name="options"></a>Optionen

`-h|--help`

Druckt Hilfe für den Befehl. Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.

`-l|--list`

Listet Vorlagen auf, die den angegebenen Namen enthalten. Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind. Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.

`-lang|--language {C#|F#}`

Gibt die Sprache der zu erstellenden Vorlage an. Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)). Für einige Vorlagen nicht gültig.

`-n|--name <OUTPUT_NAME>`

Der Name für die erstellte Ausgabe. Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.

`-o|--output <OUTPUT_DIRECTORY>`

Speicherort für die generierte Ausgabe. Der Standardwert ist das aktuelle Verzeichnis.

`-all|--show-all`

Zeigt alle Vorlagen für eine bestimmte Art von Projekt bei Ausführung im Kontext des `dotnet new`-Befehls allein an. Bei der Ausführung im Kontext einer bestimmten Vorlage wie z.B. `dotnet new web -all` wird `-all` als Flag zur Erzwingung der Erstellung interpretiert. Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.

## <a name="template-options"></a>Vorlagenoptionen

Für jede Projektvorlage kann es zusätzliche Optionen geben. Die Core-Vorlagen haben die folgenden Optionen:

**console, xunit, mstest, web, webapi**

`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll. Werte: `netcoreapp1.0` oder `netcoreapp1.1` (Standard: `netcoreapp1.0`)

**mvc**

`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll. Werte: `netcoreapp1.0` oder `netcoreapp1.1` (`Default: netcoreapp1.0`)

`-au|--auth`: Der zu verwendende Authentifizierungstyp. Werte: `None` oder `Individual` (Standard: `None`)

`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll. Werte: `true` oder `false` (Standard: `false`)

**classlib**

`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll. Werte: `netcoreapp1.0`, `netcoreapp1.1` oder `netstandard1.0` bis `netstandard1.6` (Standard: `netstandard1.4`)

## <a name="examples"></a>Beispiele

Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:

`dotnet new console -lang f#` 
   
Erstellen Sie ein neues ASP.NET Core C# MVC-Anwendungsprojekt im aktuellen Verzeichnis ohne Authentifizierung, wobei .NET Core 1.0 verwendet werden soll:  

`dotnet new mvc -au None -f netcoreapp1.0`
 
Erstellen Sie eine neue xUnit-Anwendung, die für .NET Core 1.1 vorgesehen ist:

`dotnet new xunit --Framework netcoreapp1.1`

Liste Sie alle für MVC verfügbaren Vorlagen auf:

`dotnet new mvc -l`

