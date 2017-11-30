---
title: Erste Schritte mit f# mit Befehlszeilentools
description: "Informationen Sie zum f# mit plattformübergreifenden .NET Core CLI verwenden."
keywords: Visual F#, F#, funktionale Programmierung, .NET, .NET Core
author: cartermp
ms.author: phcart
ms.date: 06/14/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 615db1ec-6ef3-4de2-bae6-4586affa9771
ms.openlocfilehash: a23d4861ce599f20f37ecd0564a0187e7b9b739f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Erste Schritte mit f# mit der .NET Core-CLI

Dieser Artikel behandelt, wie Ihnen den Einstieg mit f# auf .NET Core. Es geht über das Erstellen einer Lösung mit mehreren Projekten mit einer Klassenbibliothek, die von einer Konsolenanwendung aufgerufen wird.

## <a name="prerequisites"></a>Erforderliche Komponenten

Um zu beginnen, müssen Sie installieren die [.NET Core SDK 1.0 oder höher](https://dot.net/core). Besteht keine Notwendigkeit zum Deinstallieren einer früheren Version von .NET Core SDK, wie sie die Seite-an-Seite-Installationen unterstützt.

In diesem Artikel wird davon ausgegangen, dass Sie wissen, wie Sie eine Befehlszeile verwenden und haben einen bevorzugten Text-Editor. Wenn Sie nicht bereits, verwenden [Visual Studio Code](https://code.visualstudio.com) ist eine sinnvolle Option als einem Text-Editor für f#. Um awesome Funktionen wie IntelliSense, bessere syntaxhervorhebung und mehr zu erhalten, können Sie Herunterladen der [Ionide Erweiterung](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).

## <a name="building-a-simple-multi-project-solution"></a>Erstellen einer Lösung für einfache mit mehreren Projekten

Öffnen Sie einen Eingabeaufforderungsfenster/Terminal und Verwenden der `dotnet new` Befehl zum Erstellen der neuen Projektmappendatei mit dem Namen `FSNetCore`:

```
dotnet new sln -o FSNetCore
```

Die folgende Verzeichnisstruktur wird als Ergebnis der Datenbankbefehl wird abgeschlossen erzeugt:

```
FSNetCore
    ├── FSNetCore.sln
```

Wechseln Sie *FSNetCore* , und starten Sie den Projektmappenordner Projekte hinzufügen.
 
### <a name="writing-a-class-library"></a>Schreiben eine Klassenbibliothek

Verwenden der `dotnet new` Befehl, erstellen Sie ein Klassenbibliotheksprojekt, in dem **Src** Ordner mit dem Namen Bibliothek. 

```bash
dotnet new lib -lang F# -o src/Library 
```

Die folgende Verzeichnisstruktur wird als Ergebnis der Datenbankbefehl wird abgeschlossen erzeugt:

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Ersetzen Sie den Inhalt des `Library.fs` durch Folgendes:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value = 
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value  (JsonConvert.SerializeObject(value))
```

Das Steuerelementbibliothek-Projekt das Newtonsoft.Json NuGet-Paket hinzugefügt.

```bash
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Hinzufügen der `Library` -Projekt auf die `FSNetCore` Lösung mithilfe der `dotnet sln add` Befehl:

```bash
dotnet sln add src/Library/Library.fsproj
```

Wiederherstellen von NuGet Abhängigkeiten `dotnet restore` ([Siehe Hinweis](#dotnet-restore-note)) und führen Sie `dotnet build` zum Erstellen des Projekts.

### <a name="writing-a-console-application-which-consumes-the-class-library"></a>Schreiben einer Konsolenanwendung von der die Klassenbibliothek in Anspruch nimmt

Verwenden der `dotnet new` Befehl, erstellen Sie eine Konsolen-app in der **Src** Ordner mit dem Namen App. 

```bash
dotnet new console -lang F# -o src/App 
```

Die folgende Verzeichnisstruktur wird als Ergebnis der Datenbankbefehl wird abgeschlossen erzeugt:

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        ├── App
        │   ├── App.fsproj
        │   ├── Program.fs
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Änderung `Program.fs` an:

```fsharp
open System
open Library

[<EntryPoint>]
let main argv = 
    printfn "Nice command-line arguments! Here's what JSON.NET has to say about them:"

    argv
    |> Array.map getJsonNetJson
    |> Array.iter (printfn "%s")

    0 // return an integer exit code
```

Hinzufügen eines Verweises auf die `Library` Projekt mit `dotnet add reference`.

```bash
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Hinzufügen der `App` -Projekt auf die `FSNetCore` Lösung mithilfe der `dotnet sln add` Befehl:

```bash
dotnet sln add src/App/App.fsproj
```

Wiederherstellen von NuGet Abhängigkeiten `dotnet restore` ([Siehe Hinweis](#dotnet-restore-note)) und führen Sie `dotnet build` zum Erstellen des Projekts.

Ändern Sie das Verzeichnis, das `src/App` Konsole Projekt, und führen Sie das Projekt, das Übergeben von `Hello World` als Argumente.

```bash
cd src/App
dotnet run Hello World
``` 

Daraufhin sollte die folgenden Ergebnisse:

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```
<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]