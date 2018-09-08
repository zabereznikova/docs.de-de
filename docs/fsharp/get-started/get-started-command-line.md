---
title: Erste Schritte mit f# mit Befehlszeilentools
description: Erfahren Sie, wie Sie eine einfache Lösung mit mehreren Projekte in f# mit .NET Core-CLI auf einem beliebigen Betriebssystem (Windows, MacOs oder Linux) erstellen.
ms.date: 03/26/2018
ms.openlocfilehash: 8a82970f33c8bbe1b8cdd8fb6499b59b16d3cbf3
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44134804"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Erste Schritte mit f# mit .NET Core-CLI

Dieser Artikel beschreibt, wie Sie mit f# unter jedem Betriebssystem (Windows, MacOS oder Linux) mit .NET Core-CLI beginnen können. Danach wird durch die Erstellung einer Lösung mit mehreren Projekten mit einer Klassenbibliothek, die von einer Konsolenanwendung aufgerufen wird.

## <a name="prerequisites"></a>Erforderliche Komponenten

Um zu beginnen, müssen Sie die neueste Version installieren [.NET Core SDK](https://www.microsoft.com/net/download/).

In diesem Artikel wird davon ausgegangen, dass Sie wissen, wie Sie eine Befehlszeile verwenden und haben einen bevorzugten Text-Editor. Wenn Sie bereits, nicht [Visual Studio Code](get-started-vscode.md) ist eine großartige Möglichkeit, wie ein Text-Editor für f#.

## <a name="build-a-simple-multi-project-solution"></a>Erstellen Sie eine einfache Lösung für die mit mehreren Projekte

Öffnen einer Eingabeaufforderung den Befehl/Terminal, und Verwenden der [Dotnet neue](../../core/tools/dotnet-new.md) Befehl zum Erstellen von neuen Projektmappendatei mit dem Namen `FSNetCore`:

```console
dotnet new sln -o FSNetCore
```

Die folgende Verzeichnisstruktur wird erstellt, nach dem Ausführen des vorherigen Befehls:

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Schreiben Sie eine Klassenbibliothek

Wechseln Sie zum *FSNetCore*.

Verwenden der `dotnet new` Befehl, erstellen Sie ein Klassenbibliotheksprojekt, in der **Src** Ordner "Library".

```console
dotnet new classlib -lang F# -o src/Library
```

Die folgende Verzeichnisstruktur wird erstellt, nach dem Ausführen des vorherigen Befehls:

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Ersetzen Sie den Inhalt der `Library.fs` durch den folgenden Code:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

Fügen Sie das Newtonsoft.Json-NuGet-Paket, auf das Bibliotheksprojekt hinzu.

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Hinzufügen der `Library` Projekt die `FSNetCore` mithilfe der [Dotnet-Sln hinzufügen](../../core/tools/dotnet-sln.md) Befehl:

```console
dotnet sln add src/Library/Library.fsproj
```

Führen Sie `dotnet build` zum Erstellen des Projekts. Beim Erstellen, werden nicht aufgelöste Abhängigkeiten wiederhergestellt werden.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Schreiben einer Konsolenanwendung, die die Class-Bibliothek verwendet

Verwenden der `dotnet new` Befehl erhalten Sie durch erstellen eine Konsolenanwendung in der **Src** Ordner mit dem Namen App.

```console
dotnet new console -lang F# -o src/App
```

Die folgende Verzeichnisstruktur wird erstellt, nach dem Ausführen des vorherigen Befehls:

```console
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

Ersetzen Sie den Inhalt von der `Program.fs` -Datei mit den folgenden Code:

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

Hinzufügen eines Verweises auf die `Library` -Projekt mit [Dotnet Verweis hinzufügen](../../core/tools/dotnet-add-reference.md).

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Hinzufügen der `App` Projekt die `FSNetCore` mithilfe der `dotnet sln add` Befehl:

```console
dotnet sln add src/App/App.fsproj
```

Wiederherstellen der NuGet-Abhängigkeiten, `dotnet restore` ([Siehe Hinweis](#dotnet-restore-note)), und führen Sie `dotnet build` zum Erstellen des Projekts.

Wechseln Sie zum Verzeichnis der `src/App` console-Projekt, und führen Sie das Projekt, das Übergeben von `Hello World` als Argumente:

```console
cd src/App
dotnet run Hello World
```

Sie sollten die folgenden Ergebnisse angezeigt:

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>Nächste Schritte

Als Nächstes sehen Sie sich die [Einführung in f#](../tour.md) Weitere Informationen zu verschiedenen F#-Funktionen.
