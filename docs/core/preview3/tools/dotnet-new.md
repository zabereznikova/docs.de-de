---
title: Befehl dotnet-new | Microsoft-Dokumentation
description: Der dotnet-new-Befehl erstellt neue .NET Core-Projekte im aktuellen Verzeichnis.
keywords: dotnet-new, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 02/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
translationtype: Human Translation
ms.sourcegitcommit: 96fd8ea3e55ea33e0bdd0bf3c50a10d0de6db1a1
ms.openlocfilehash: f0c62647c5817db2057c60a7a95a62f08f7889a5

---
#<a name="dotnet-new-net-core-tools-rc4"></a>dotnet-new (.NET Core Tools RC4)

> [!WARNING]
> Dieses Thema gilt für .NET Core Tools RC4. Informationen zu .NET Core Preview 2-Tools finden Sie im Thema [dotnet-new](../../tools/dotnet-new.md).

## <a name="name"></a>Name
dotnet-new: Erstellt ein neues .NET Core-Projekt im aktuellen Verzeichnis

## <a name="synopsis"></a>Übersicht
```
dotnet new [template] [-lang|--language] [-n|--name] [-o|--output] [-h|--help]
dotnet new [template] [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

## <a name="description"></a>Beschreibung
Der Befehl `dotnet new` bietet eine bequeme Möglichkeit, ein gültiges .NET Core-Projekt und Beispielquellcode zum Ausprobieren des Befehlszeilenschnittstellen-Toolsets (CLI) zu initialisieren. 

Dieser Befehl wird im Kontext eines Verzeichnisses aufgerufen. Sobald der Befehl aufgerufen wurde, richtet er die Ressourcen und Dateien entsprechend der Vorlage und den Optionen ein, die an den Befehl übergeben wurden. 

Danach kann das Projekt kompiliert und/oder weiter bearbeitet werden. 

## <a name="arguments"></a>Argumente
template: Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.

Der Befehl enthält eine Standardliste mit Vorlagen. Verwenden Sie `dotnet new --help`. 

## <a name="options"></a>Optionen

`-l|--list`         

Listet Vorlagen auf, die den angegebenen Namen enthalten.

`-lang|--language`  

Gibt die Sprache der zu erstellenden Vorlage an.

`-n|--name`         

Der Name für die Ausgabe, die erstellt wird. Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.

`-o|--output`       

Speicherort für die generierte Ausgabe.

`-all|--show-all`   

Zeigt alle Vorlagen für einen bestimmten Projekttyp an.

`-h|--help`

Druckt Hilfe für den Befehl.

## <a name="template-options"></a>Vorlagenoptionen
Für jede Projektvorlage kann es zusätzliche Optionen geben. Die Core-Vorlagen haben z. B. die folgenden Optionen:

**console, xunit, mstest**

`-f|--framework`: Gibt an, welches Framework verwendet werden soll. Werte: „netcoreapp1.0“ oder „netcoreapp1.1“ (Standard: „netcoreapp1.0“)

**web, webapi**

`-f|--framework`: Gibt an, welches Framework verwendet werden soll. Werte: „netcoreapp1.0“ oder „netcoreapp1.1“ (Standard: „netcoreapp1.0“)
 
**mvc**

`-f|--framework`: Gibt an, welches Framework verwendet werden soll. Werte: „netcoreapp1.0“ oder „netcoreapp1.1“ (Standard: „netcoreapp1.0“)

`-au|--authentication`: Der zu verwendende Authentifizierungstyp. Werte: „None“ oder „Individual“ (Standard: „None“)

`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll. Werte: „true“ oder „false“ (Standard: „false“)

**classlib**

`-f|--framework`: Gibt an, welches Framework verwendet werden soll. Werte: „netcoreapp1.0“, „netcoreapp1.1“ und „netstandard1.0 - 1.6“ (Standard: „netstandard1.4“).

## <a name="examples"></a>Beispiele

Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:

`dotnet new console -lang f#` 
   
Erstellen Sie ein neues ASP.NET Core C# MVC-Anwendungsprojekt im aktuellen Verzeichnis ohne Authentifizierung, wobei .NET Core 1.0 verwendet werden soll:  

`dotnet new mvc -au None -f netcoreapp1.0`
 
Erstellen Sie eine neue xUnit-Anwendung, die für .NET Core 1.1 vorgesehen ist:

`dotnet new xunit --Framework netcoreapp1.1`

Liste Sie alle für MVC verfügbaren Vorlagen auf:

`dotnet new mvc -l`


<!--HONumber=Feb17_HO3-->


