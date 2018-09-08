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
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="28ec7-103">Erste Schritte mit f# mit .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="28ec7-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="28ec7-104">Dieser Artikel beschreibt, wie Sie mit f# unter jedem Betriebssystem (Windows, MacOS oder Linux) mit .NET Core-CLI beginnen können.</span><span class="sxs-lookup"><span data-stu-id="28ec7-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="28ec7-105">Danach wird durch die Erstellung einer Lösung mit mehreren Projekten mit einer Klassenbibliothek, die von einer Konsolenanwendung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="28ec7-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="28ec7-106">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="28ec7-106">Prerequisites</span></span>

<span data-ttu-id="28ec7-107">Um zu beginnen, müssen Sie die neueste Version installieren [.NET Core SDK](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="28ec7-107">To begin, you must install the latest [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

<span data-ttu-id="28ec7-108">In diesem Artikel wird davon ausgegangen, dass Sie wissen, wie Sie eine Befehlszeile verwenden und haben einen bevorzugten Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="28ec7-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="28ec7-109">Wenn Sie bereits, nicht [Visual Studio Code](get-started-vscode.md) ist eine großartige Möglichkeit, wie ein Text-Editor für f#.</span><span class="sxs-lookup"><span data-stu-id="28ec7-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="28ec7-110">Erstellen Sie eine einfache Lösung für die mit mehreren Projekte</span><span class="sxs-lookup"><span data-stu-id="28ec7-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="28ec7-111">Öffnen einer Eingabeaufforderung den Befehl/Terminal, und Verwenden der [Dotnet neue](../../core/tools/dotnet-new.md) Befehl zum Erstellen von neuen Projektmappendatei mit dem Namen `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="28ec7-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```console
dotnet new sln -o FSNetCore
```

<span data-ttu-id="28ec7-112">Die folgende Verzeichnisstruktur wird erstellt, nach dem Ausführen des vorherigen Befehls:</span><span class="sxs-lookup"><span data-stu-id="28ec7-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="28ec7-113">Schreiben Sie eine Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="28ec7-113">Write a class library</span></span>

<span data-ttu-id="28ec7-114">Wechseln Sie zum *FSNetCore*.</span><span class="sxs-lookup"><span data-stu-id="28ec7-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="28ec7-115">Verwenden der `dotnet new` Befehl, erstellen Sie ein Klassenbibliotheksprojekt, in der **Src** Ordner "Library".</span><span class="sxs-lookup"><span data-stu-id="28ec7-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```console
dotnet new classlib -lang F# -o src/Library
```

<span data-ttu-id="28ec7-116">Die folgende Verzeichnisstruktur wird erstellt, nach dem Ausführen des vorherigen Befehls:</span><span class="sxs-lookup"><span data-stu-id="28ec7-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="28ec7-117">Ersetzen Sie den Inhalt der `Library.fs` durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="28ec7-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="28ec7-118">Fügen Sie das Newtonsoft.Json-NuGet-Paket, auf das Bibliotheksprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="28ec7-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="28ec7-119">Hinzufügen der `Library` Projekt die `FSNetCore` mithilfe der [Dotnet-Sln hinzufügen](../../core/tools/dotnet-sln.md) Befehl:</span><span class="sxs-lookup"><span data-stu-id="28ec7-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```console
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="28ec7-120">Führen Sie `dotnet build` zum Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="28ec7-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="28ec7-121">Beim Erstellen, werden nicht aufgelöste Abhängigkeiten wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="28ec7-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="28ec7-122">Schreiben einer Konsolenanwendung, die die Class-Bibliothek verwendet</span><span class="sxs-lookup"><span data-stu-id="28ec7-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="28ec7-123">Verwenden der `dotnet new` Befehl erhalten Sie durch erstellen eine Konsolenanwendung in der **Src** Ordner mit dem Namen App.</span><span class="sxs-lookup"><span data-stu-id="28ec7-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```console
dotnet new console -lang F# -o src/App
```

<span data-ttu-id="28ec7-124">Die folgende Verzeichnisstruktur wird erstellt, nach dem Ausführen des vorherigen Befehls:</span><span class="sxs-lookup"><span data-stu-id="28ec7-124">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="28ec7-125">Ersetzen Sie den Inhalt von der `Program.fs` -Datei mit den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="28ec7-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="28ec7-126">Hinzufügen eines Verweises auf die `Library` -Projekt mit [Dotnet Verweis hinzufügen](../../core/tools/dotnet-add-reference.md).</span><span class="sxs-lookup"><span data-stu-id="28ec7-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="28ec7-127">Hinzufügen der `App` Projekt die `FSNetCore` mithilfe der `dotnet sln add` Befehl:</span><span class="sxs-lookup"><span data-stu-id="28ec7-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```console
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="28ec7-128">Wiederherstellen der NuGet-Abhängigkeiten, `dotnet restore` ([Siehe Hinweis](#dotnet-restore-note)), und führen Sie `dotnet build` zum Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="28ec7-128">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="28ec7-129">Wechseln Sie zum Verzeichnis der `src/App` console-Projekt, und führen Sie das Projekt, das Übergeben von `Hello World` als Argumente:</span><span class="sxs-lookup"><span data-stu-id="28ec7-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```console
cd src/App
dotnet run Hello World
```

<span data-ttu-id="28ec7-130">Sie sollten die folgenden Ergebnisse angezeigt:</span><span class="sxs-lookup"><span data-stu-id="28ec7-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="28ec7-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="28ec7-131">Next steps</span></span>

<span data-ttu-id="28ec7-132">Als Nächstes sehen Sie sich die [Einführung in f#](../tour.md) Weitere Informationen zu verschiedenen F#-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="28ec7-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
