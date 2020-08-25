---
title: 'Einstieg in F # mit Befehlszeilen Tools'
description: 'Erfahren Sie, wie Sie eine einfache Lösung mit mehreren Projekten in F # erstellen, indem Sie die .net Core-CLI unter jedem Betriebssystem (Windows, macOS oder Linux) verwenden.'
ms.date: 08/15/2020
ms.openlocfilehash: e652b66337a3122de8e6bd4d62d86fb6082b759d
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811989"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>Beginnen Sie mit F # mit der .net Core-CLI

In diesem Artikel erfahren Sie, wie Sie mit der .net Core-CLI mit F # unter jedem Betriebssystem (Windows, macOS oder Linux) beginnen. Sie durchläuft das Entwickeln einer Projekt Mappe mit mehreren Projekten mit einer Klassenbibliothek, die von einer Konsolenanwendung aufgerufen wird.

## <a name="prerequisites"></a>Voraussetzungen

Zunächst müssen Sie die neuesten [.net Core SDK](https://dotnet.microsoft.com/download)installieren.

In diesem Artikel wird davon ausgegangen, dass Sie wissen, wie Sie eine Befehlszeile verwenden und einen bevorzugten Text-Editor verwenden können. Wenn Sie Sie nicht bereits verwenden, ist [Visual Studio Code](get-started-vscode.md) eine gute Option als Text-Editor für F #.

## <a name="build-a-simple-multi-project-solution"></a>Erstellen Sie eine einfache Lösung mit mehreren Projekten

Öffnen Sie eine Eingabeaufforderung/ein Terminal, und erstellen Sie mit dem Befehl [dotnet New](../../core/tools/dotnet-new.md) eine neue Projektmappendatei mit dem Namen `FSNetCore` :

```dotnetcli
dotnet new sln -o FSNetCore
```

Nach dem Ausführen des vorherigen Befehls wird die folgende Verzeichnisstruktur erstellt:

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>Schreiben einer Klassenbibliothek

Wechseln Sie in das Verzeichnis *fsnetcore*.

Verwenden Sie den `dotnet new` Befehl, und erstellen Sie ein Klassen Bibliotheksprojekt im Ordner **src** mit dem Namen Library.

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

Ersetzen Sie den Inhalt von `Library.fs` durch den folgenden Code:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    let json = JsonConvert.SerializeObject(value)
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value json
```

Fügen Sie dem Bibliotheksprojekt die Newtonsoft.Jsfür das nuget-Paket hinzu.

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

Fügen Sie das `Library` Projekt der Projekt Mappe `FSNetCore` mit dem Befehl [dotnet sln Add](../../core/tools/dotnet-sln.md) hinzu:

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

Führen `dotnet build` Sie aus, um das Projekt zu erstellen. Nicht aufgelöste Abhängigkeiten werden bei der Erstellung wieder hergestellt.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>Schreiben einer Konsolenanwendung, die die Klassenbibliothek verwendet

Verwenden Sie den `dotnet new` Befehl, und erstellen Sie eine Konsolenanwendung im Ordner **src** mit dem Namen app.

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

    for arg in argv do
        let value = getJsonNetJson arg
        printfn "%s" value

    0 // return an integer exit code
```

Fügen Sie mithilfe von " `Library` [dotnet Add Reference](../../core/tools/dotnet-add-reference.md)" einen Verweis auf das Projekt hinzu.

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

Fügen Sie das `App` Projekt der Projekt Mappe `FSNetCore` mit dem folgenden Befehl hinzu `dotnet sln add` :

```dotnetcli
dotnet sln add src/App/App.fsproj
```

Stellen Sie die nuget-Abhängigkeiten wieder her, `dotnet restore` und führen `dotnet build` Sie zum Erstellen des Projekts aus.

Wechseln Sie zum `src/App` Konsolen Projekt, und führen Sie das Projekt aus, das `Hello World` als Argument übergeben wird:

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

Sehen Sie sich als nächstes die Einführung in [f #](../tour.md) an, um mehr über verschiedene f #-Features zu erfahren.
