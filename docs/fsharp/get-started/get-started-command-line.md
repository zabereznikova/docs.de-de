---
title: Erste Schritte mit F# mit Befehlszeilentools
description: Erfahren Sie, wie Sie eine einfache Lösung mit mehreren Projekte in F# mit .NET Core-CLI auf einem beliebigen Betriebssystem (Windows, MacOS oder Linux) erstellen.
ms.date: 03/26/2018
ms.openlocfilehash: bc9b223fcf133ffe8b19d5284dcbd3c14a426235
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938696"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Erste Schritte in F# mit der .NET Core-CLI

Dieser Artikel beschreibt, wie Sie mit F# auf jedem Betriebssystem (Windows, MacOS oder Linux) unter Verwendung der .NET Core-CLI beginnen können. Dies wird an der Erstellung einer Projektmappe erläutert, die eine Klassenbibliothek enthält auf die von einer Konsolenanwendung zugegriffen wird.

## <a name="prerequisites"></a>Vorraussetzungen

Sie müssen die neueste Version des [.NET Core SDK](https://www.microsoft.com/net/download/) installieren, um zu beginnen.

In diesem Artikel wird davon ausgegangen, dass Sie wissen, wie Sie eine Befehlszeile verwenden und dass Sie über einen bevorzugten Text-Editor verfügen. Sollten Sie noch keinen besitzen, dann ist [Visual Studio Code](get-started-vscode.md) ein geeigneter Text-Editor für F#.

## <a name="build-a-simple-multi-project-solution"></a>Erstellen Sie eine einfache Lösung für die mit mehreren Projekte

Öffnen Sie eine Eingabeaufforderung/ein Terminal und verwenden Sie den Befehl [dotnet new](../../core/tools/dotnet-new.md) zum Erstellen von neuen Projektmappendatei mit dem Namen `FSNetCore`:

```console
dotnet new sln -o FSNetCore
```

Die folgende Verzeichnisstruktur wird erstellt, nach dem Ausführen des vorherigen Befehls:

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Erstellen der Klassenbibliothek

Wechseln Sie zu dem Verzeichnis *FSNetCore*.

Verwenden Sie den Befehl `dotnet new`, um ein neues Klassenbibliotheksprojekt unter dem Pfad **src/Library** zu erstellen.

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

Ersetzen Sie den Inhalt der Datei `Library.fs` durch den folgenden Code:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

Fügen Sie das Newtonsoft.Json NuGet-Paket zu dem Bibliotheksprojekt hinzu.

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Hinzufügen des `Library` Projektes zur `FSNetCore` Projektmappe mithilfe des Befehls [dotnet sln add](../../core/tools/dotnet-sln.md):

```console
dotnet sln add src/Library/Library.fsproj
```

Führen Sie `dotnet build`zum Erstellen des Projekts aus. Beim Erstellen werden nicht aufgelöste Abhängigkeiten wiederhergestellt.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Schreiben einer Konsolenanwendung, die die Klassenbibliothek verwendet

Verwenden sie den Befehl `dotnet new`, um eine Konsolenanwendung unter them Pfad **src/App** zu erstellen.

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

Ersetzen Sie den Inhalt von der Datei `Program.fs`durch den folgenden Code:

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

Hinzufügen eines Verweises auf das Projekt `Library` mit dem Befehl [dotnet reference add](../../core/tools/dotnet-add-reference.md).

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Hinzufügen des `App` Projektes zur `FSNetCore` Projektmappe mithilfe des `dotnet sln add` Befehls:

```console
dotnet sln add src/App/App.fsproj
```

Wiederherstellen der NuGet-Abhängigkeiten, `dotnet restore` , und führen Sie `dotnet build` zum Erstellen des Projekts.

Wechseln Sie zum Verzeichnis der `src/App` Konsolenanwendung und führen Sie das Projekt mit `Hello World` as Argumente aus:

```console
cd src/App
dotnet run Hello World
```

Folgendes sollte angezeigt werden:

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>Nächste Schritte

Sehen sie sich [Einführung in F#](../tour.md) an für weitere Informationen zu verschiedenen F#-Funktionen.
