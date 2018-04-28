---
title: Erste Schritte mit f# mit Befehlszeilentools
description: Erfahren Sie, wie eine einfache Lösung für mehrere Projekte in f#-verwenden die .NET Core-CLI unter jedem Betriebssystem (Windows, Mac OS oder Linux) zu erstellen.
author: cartermp
ms.author: phcart
ms.date: 03/26/2018
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 767385be605d863644db563a2e86a41ca80527c4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Erste Schritte mit f# mit der .NET Core-CLI

Dieser Artikel behandelt, wie Sie mit f# unter jedem Betriebssystem (Windows, Mac OS oder Linux) mit der .NET Core-CLI beginnen können. Erstellen einer Lösung mit mehreren Projekten mit einer Klassenbibliothek, die von einer Konsolenanwendung aufgerufen wird, durchlaufen.

## <a name="prerequisites"></a>Erforderliche Komponenten

Um zu beginnen, müssen Sie installieren die [.NET Core SDK 1.0 oder höher](https://www.microsoft.com/net/download/). Besteht keine Notwendigkeit zum Deinstallieren einer früheren Version von .NET Core SDK, wie sie die Seite-an-Seite-Installationen unterstützt.

In diesem Artikel wird davon ausgegangen, dass Sie wissen, wie Sie eine Befehlszeile verwenden und haben einen bevorzugten Text-Editor. Wenn Sie nicht bereits, verwenden [Visual Studio Code](https://code.visualstudio.com) ist eine sinnvolle Option als einem Text-Editor für f#. Um awesome Funktionen wie IntelliSense, bessere syntaxhervorhebung und mehr zu erhalten, können Sie Herunterladen der [Ionide Erweiterung](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).

## <a name="build-a-simple-multi-project-solution"></a>Erstellen Sie eine einfache Lösung für mehrere Projekte

Öffnen Sie einen Eingabeaufforderungsfenster/Terminal und Verwenden der [Dotnet neue](../../core/tools/dotnet-new.md) Befehl zum Erstellen der neuen Projektmappendatei mit dem Namen `FSNetCore`:

```
dotnet new sln -o FSNetCore
```

Die folgende Verzeichnisstruktur wird nach der Ausführung mit dem vorherigen Befehls erzeugt:

```
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Schreiben Sie eine Klassenbibliothek

Wechseln Sie *FSNetCore*.

Verwenden der `dotnet new` Befehl, erstellen Sie ein Klassenbibliotheksprojekt, in dem **Src** Ordner mit dem Namen Bibliothek.

```
dotnet new lib -lang F# -o src/Library
```

Die folgende Verzeichnisstruktur wird nach der Ausführung mit dem vorherigen Befehls erzeugt:

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Ersetzen Sie den Inhalt des `Library.fs` durch den folgenden Code:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

Das Steuerelementbibliothek-Projekt das Newtonsoft.Json NuGet-Paket hinzugefügt.

```
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Hinzufügen der `Library` -Projekt auf die `FSNetCore` Lösung mithilfe der [Dotnet Sln hinzufügen](../../core/tools/dotnet-sln.md) Befehl:

```
dotnet sln add src/Library/Library.fsproj
```

Wiederherstellen von NuGet-Abhängigkeiten mithilfe der `dotnet restore` Befehl ([Siehe Hinweis](#dotnet-restore-note)) und führen Sie `dotnet build` zum Erstellen des Projekts.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Schreiben Sie eine Konsolenanwendung, die in der Klassenbibliothek benötigt.

Verwenden der `dotnet new` Befehl, erstellen Sie eine Konsolenanwendung in der **Src** Ordner mit dem Namen App.

```
dotnet new console -lang F# -o src/App
```

Die folgende Verzeichnisstruktur wird nach der Ausführung mit dem vorherigen Befehls erzeugt:

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

Ersetzen Sie den Inhalt von der `Program.fs` Datei durch den folgenden Code:

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

Hinzufügen eines Verweises auf die `Library` Projekt mit [Dotnet Verweis hinzufügen](../../core/tools/dotnet-add-reference.md).

```
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Hinzufügen der `App` -Projekt auf die `FSNetCore` Lösung mithilfe der `dotnet sln add` Befehl:

```
dotnet sln add src/App/App.fsproj
```

Wiederherstellen von NuGet Abhängigkeiten `dotnet restore` ([Siehe Hinweis](#dotnet-restore-note)) und führen Sie `dotnet build` zum Erstellen des Projekts.

Ändern Sie das Verzeichnis, das `src/App` Konsole Projekt, und führen Sie das Projekt, das Übergeben von `Hello World` als Argumente:

```
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