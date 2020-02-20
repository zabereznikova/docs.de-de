---
title: Erste Schritte mit F# mit Befehlszeilentools
description: Erfahren Sie, wie Sie eine einfache Lösung mit mehreren Projekten F# unter Verwendung der .net Core-CLI unter einem beliebigen Betriebssystem (Windows, macOS oder Linux) erstellen können.
ms.date: 03/26/2018
ms.openlocfilehash: 6f67314f49150e20b18734f21f24daa3ce856922
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504144"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Erste Schritte in F# mit der .NET Core-CLI

Dieser Artikel beschreibt, wie Sie mit F# auf jedem Betriebssystem (Windows, MacOS oder Linux) unter Verwendung der .NET Core-CLI beginnen können. Dies wird an der Erstellung einer Projektmappe erläutert, die eine Klassenbibliothek enthält auf die von einer Konsolenanwendung zugegriffen wird.

## <a name="prerequisites"></a>Voraussetzungen

Zunächst müssen Sie die neuesten [.net Core SDK](https://dotnet.microsoft.com/download)installieren.

In diesem Artikel wird davon ausgegangen, dass Sie wissen, wie Sie eine Befehlszeile verwenden und dass Sie über einen bevorzugten Text-Editor verfügen. Wenn Sie Sie nicht bereits verwenden, ist [Visual Studio Code](get-started-vscode.md) eine gute Option als Text-Editor für F#.

## <a name="build-a-simple-multi-project-solution"></a>Erstellen Sie eine einfache Lösung mit mehreren Projekten

Öffnen Sie eine Eingabeaufforderung/ein Terminal, und erstellen Sie mit dem Befehl [dotnet New](../../core/tools/dotnet-new.md) eine neue Projektmappendatei mit dem Namen `FSNetCore`:

```dotnetcli
dotnet new sln -o FSNetCore
```

Nach dem Ausführen des vorherigen Befehls wird die folgende Verzeichnisstruktur erstellt:

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Erstellen der Klassenbibliothek

Wechseln Sie in das Verzeichnis *fsnetcore*.

Verwenden Sie den Befehl `dotnet new`, und erstellen Sie ein Klassen Bibliotheksprojekt im Ordner **src** mit dem Namen Library.

```dotnetcli
dotnet new classlib -lang "F#" -o src/Library
```

Nach dem Ausführen des vorherigen Befehls wird die folgende Verzeichnisstruktur erstellt:

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

Ersetzen Sie den Inhalt `Library.fs` durch den folgenden Code:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

Fügen Sie das Newtonsoft.Json NuGet-Paket zu dem Bibliotheksprojekt hinzu.

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Fügen Sie der Projekt Mappe `FSNetCore` mithilfe des Befehls [dotnet sln Add](../../core/tools/dotnet-sln.md) das `Library`-Projekt hinzu:

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

Führen Sie `dotnet build` aus, um das Projekt zu erstellen. Beim Erstellen werden nicht aufgelöste Abhängigkeiten wiederhergestellt.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Schreiben einer Konsolenanwendung, die die Klassenbibliothek verwendet

Verwenden Sie den Befehl `dotnet new`, und erstellen Sie im Ordner **src** eine Konsolenanwendung mit dem Namen app.

```dotnetcli
dotnet new console -lang "F#" -o src/App
```

Nach dem Ausführen des vorherigen Befehls wird die folgende Verzeichnisstruktur erstellt:

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

Ersetzen Sie den Inhalt der Datei `Program.fs` durch den folgenden Code:

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

Fügen Sie mithilfe von " [dotnet Add Reference](../../core/tools/dotnet-add-reference.md)" einen Verweis auf das `Library` Projekt hinzu.

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Fügen Sie der `FSNetCore` Projekt Mappe mit dem `dotnet sln add`-Befehl das `App`-Projekt hinzu:

```dotnetcli
dotnet sln add src/App/App.fsproj
```

Stellen Sie die nuget-Abhängigkeiten wieder her, `dotnet restore` und führen Sie `dotnet build` zum Erstellen des Projekts aus.

Wechseln Sie in das `src/App` Konsolen Projekt, und führen Sie das Projekt aus, das `Hello World` als Argumente übergibt:

```dotnetcli
cd src/App
dotnet run Hello World
```

Die Ergebnisse sollten wie folgt aussehen:

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>Nächste Schritte

Sehen Sie sich als nächstes die [Tour F# ](../tour.md) durch an, um mehr F# über verschiedene Features zu erfahren.
