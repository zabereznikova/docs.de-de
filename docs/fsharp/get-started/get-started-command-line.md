---
title: Erste Schritte mit F# mit Befehlszeilentools
description: Erfahren Sie, wie Sie eine einfache Lösung mit mehreren Projekte in F# mit .NET Core-CLI auf einem beliebigen Betriebssystem (Windows, MacOS oder Linux) erstellen.
ms.date: 03/26/2018
ms.openlocfilehash: 8a82970f33c8bbe1b8cdd8fb6499b59b16d3cbf3
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "45673908"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="3165c-103">Erste Schritte in F# mit der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="3165c-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="3165c-104">Dieser Artikel beschreibt, wie Sie mit F# auf jedem Betriebssystem (Windows, MacOS oder Linux) unter Verwendung der .NET Core-CLI beginnen können.</span><span class="sxs-lookup"><span data-stu-id="3165c-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="3165c-105">Dies wird an der Erstellung einer Projektmappe erläutert, die eine Klassenbibliothek enthält auf die von einer Konsolenanwendung zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="3165c-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3165c-106">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3165c-106">Prerequisites</span></span>

<span data-ttu-id="3165c-107">Sie müssen die neueste Version des [.NET Core SDK](https://www.microsoft.com/net/download/) installieren, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="3165c-107">To begin, you must install the latest [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

<span data-ttu-id="3165c-108">In diesem Artikel wird davon ausgegangen, dass Sie wissen, wie Sie eine Befehlszeile verwenden und dass Sie über einen bevorzugten Text-Editor verfügen.</span><span class="sxs-lookup"><span data-stu-id="3165c-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="3165c-109">Sollten Sie noch keinen besitzen, dann ist [Visual Studio Code](get-started-vscode.md) ein geeigneter Text-Editor für F#.</span><span class="sxs-lookup"><span data-stu-id="3165c-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="3165c-110">Erstellen Sie eine einfache Lösung für die mit mehreren Projekte</span><span class="sxs-lookup"><span data-stu-id="3165c-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="3165c-111">Öffnen Sie eine Eingabeaufforderung/ein Terminal und verwenden Sie den Befehl [dotnet new](../../core/tools/dotnet-new.md) zum Erstellen von neuen Projektmappendatei mit dem Namen `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="3165c-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```console
dotnet new sln -o FSNetCore
```

<span data-ttu-id="3165c-112">Die folgende Verzeichnisstruktur wird erstellt, nach dem Ausführen des vorherigen Befehls:</span><span class="sxs-lookup"><span data-stu-id="3165c-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="3165c-113">Erstellen der Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="3165c-113">Write a class library</span></span>

<span data-ttu-id="3165c-114">Wechseln Sie zu dem Verzeichnis *FSNetCore*.</span><span class="sxs-lookup"><span data-stu-id="3165c-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="3165c-115">Verwenden Sie den Befehl `dotnet new`, um ein neues Klassenbibliotheksprojekt unter dem Pfad **src/Library** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3165c-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```console
dotnet new classlib -lang F# -o src/Library
```

<span data-ttu-id="3165c-116">Die folgende Verzeichnisstruktur wird erstellt, nach dem Ausführen des vorherigen Befehls:</span><span class="sxs-lookup"><span data-stu-id="3165c-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="3165c-117">Ersetzen Sie den Inhalt der Datei `Library.fs` durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="3165c-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="3165c-118">Fügen Sie das Newtonsoft.Json NuGet-Paket zu dem Bibliotheksprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="3165c-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="3165c-119">Hinzufügen des `Library` Projektes zur `FSNetCore` Projektmappe mithilfe des Befehls [dotnet sln add](../../core/tools/dotnet-sln.md):</span><span class="sxs-lookup"><span data-stu-id="3165c-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```console
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="3165c-120">Führen Sie `dotnet build`zum Erstellen des Projekts aus.</span><span class="sxs-lookup"><span data-stu-id="3165c-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="3165c-121">Beim Erstellen werden nicht aufgelöste Abhängigkeiten wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="3165c-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="3165c-122">Schreiben einer Konsolenanwendung, die die Klassenbibliothek verwendet</span><span class="sxs-lookup"><span data-stu-id="3165c-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="3165c-123">Verwenden sie den Befehl `dotnet new`, um eine Konsolenanwendung unter them Pfad **src/App** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3165c-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```console
dotnet new console -lang F# -o src/App
```

<span data-ttu-id="3165c-124">Die folgende Verzeichnisstruktur wird erstellt, nach dem Ausführen des vorherigen Befehls:</span><span class="sxs-lookup"><span data-stu-id="3165c-124">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="3165c-125">Ersetzen Sie den Inhalt von der Datei `Program.fs`durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="3165c-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="3165c-126">Hinzufügen eines Verweises auf das Projekt `Library` mit dem Befehl [dotnet reference add](../../core/tools/dotnet-add-reference.md).</span><span class="sxs-lookup"><span data-stu-id="3165c-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="3165c-127">Hinzufügen des `App` Projektes zur `FSNetCore` Projektmappe mithilfe des `dotnet sln add` Befehls:</span><span class="sxs-lookup"><span data-stu-id="3165c-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```console
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="3165c-128">Wiederherstellen der NuGet-Abhängigkeiten mit dem Befehl `dotnet restore` ([Siehe Hinweis](#dotnet-restore-note)) und Erstellung des Projektes mit `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="3165c-128">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="3165c-129">Wechseln Sie zum Verzeichnis der `src/App` Konsolenanwendung und führen Sie das Projekt mit `Hello World` as Argumente aus:</span><span class="sxs-lookup"><span data-stu-id="3165c-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```console
cd src/App
dotnet run Hello World
```

<span data-ttu-id="3165c-130">Folgendes sollte angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="3165c-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="3165c-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3165c-131">Next steps</span></span>

<span data-ttu-id="3165c-132">Sehen sie sich [Einführung in f#](../tour.md) an für weitere Informationen zu verschiedenen F#-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="3165c-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
