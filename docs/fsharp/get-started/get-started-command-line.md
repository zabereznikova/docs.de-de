---
title: Erste Schritte mit F# mit Befehlszeilentools
description: Erfahren Sie, wie Sie eine einfache Lösung mit mehreren Projekten F# unter Verwendung der .net Core-CLI unter einem beliebigen Betriebssystem (Windows, macOS oder Linux) erstellen können.
ms.date: 03/26/2018
ms.openlocfilehash: aa3ed84660a951eeafc11a00ea3831f587b6d876
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559486"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="2774b-103">Erste Schritte in F# mit der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="2774b-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="2774b-104">Dieser Artikel beschreibt, wie Sie mit F# auf jedem Betriebssystem (Windows, MacOS oder Linux) unter Verwendung der .NET Core-CLI beginnen können.</span><span class="sxs-lookup"><span data-stu-id="2774b-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="2774b-105">Dies wird an der Erstellung einer Projektmappe erläutert, die eine Klassenbibliothek enthält auf die von einer Konsolenanwendung zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="2774b-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2774b-106">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="2774b-106">Prerequisites</span></span>

<span data-ttu-id="2774b-107">Sie müssen die neueste Version des [.NET Core SDK](https://dotnet.microsoft.com/download) installieren, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="2774b-107">To begin, you must install the latest [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="2774b-108">In diesem Artikel wird davon ausgegangen, dass Sie wissen, wie Sie eine Befehlszeile verwenden und dass Sie über einen bevorzugten Text-Editor verfügen.</span><span class="sxs-lookup"><span data-stu-id="2774b-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="2774b-109">Sollten Sie noch keinen besitzen, dann ist [Visual Studio Code](get-started-vscode.md) ein geeigneter Text-Editor für F#.</span><span class="sxs-lookup"><span data-stu-id="2774b-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="2774b-110">Erstellen Sie eine einfache Lösung mit mehreren Projekten</span><span class="sxs-lookup"><span data-stu-id="2774b-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="2774b-111">Öffnen Sie eine Eingabeaufforderung/ein Terminal und verwenden Sie den Befehl [dotnet new](../../core/tools/dotnet-new.md) zum Erstellen von neuen Projektmappendatei mit dem Namen `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="2774b-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```dotnetcli
dotnet new sln -o FSNetCore
```

<span data-ttu-id="2774b-112">Nach dem Ausführen des vorherigen Befehls wird die folgende Verzeichnisstruktur erstellt:</span><span class="sxs-lookup"><span data-stu-id="2774b-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="2774b-113">Erstellen der Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="2774b-113">Write a class library</span></span>

<span data-ttu-id="2774b-114">Wechseln Sie zu dem Verzeichnis *FSNetCore*.</span><span class="sxs-lookup"><span data-stu-id="2774b-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="2774b-115">Verwenden Sie den Befehl `dotnet new`, um ein neues Klassenbibliotheksprojekt unter dem Pfad **src/Library** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2774b-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```dotnetcli
dotnet new classlib -lang "F#" -o src/Library
```

<span data-ttu-id="2774b-116">Nach dem Ausführen des vorherigen Befehls wird die folgende Verzeichnisstruktur erstellt:</span><span class="sxs-lookup"><span data-stu-id="2774b-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="2774b-117">Ersetzen Sie den Inhalt der Datei `Library.fs` durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="2774b-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="2774b-118">Fügen Sie das Newtonsoft.Json NuGet-Paket zu dem Bibliotheksprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="2774b-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="2774b-119">Hinzufügen des `Library` Projektes zur `FSNetCore` Projektmappe mithilfe des Befehls [dotnet sln add](../../core/tools/dotnet-sln.md):</span><span class="sxs-lookup"><span data-stu-id="2774b-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="2774b-120">Führen Sie `dotnet build`zum Erstellen des Projekts aus.</span><span class="sxs-lookup"><span data-stu-id="2774b-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="2774b-121">Beim Erstellen werden nicht aufgelöste Abhängigkeiten wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="2774b-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="2774b-122">Schreiben einer Konsolenanwendung, die die Klassenbibliothek verwendet</span><span class="sxs-lookup"><span data-stu-id="2774b-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="2774b-123">Verwenden sie den Befehl `dotnet new`, um eine Konsolenanwendung unter them Pfad **src/App** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2774b-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```dotnetcli
dotnet new console -lang "F#" -o src/App
```

<span data-ttu-id="2774b-124">Nach dem Ausführen des vorherigen Befehls wird die folgende Verzeichnisstruktur erstellt:</span><span class="sxs-lookup"><span data-stu-id="2774b-124">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="2774b-125">Ersetzen Sie den Inhalt von der Datei `Program.fs`durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="2774b-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="2774b-126">Hinzufügen eines Verweises auf das Projekt `Library` mit dem Befehl [dotnet reference add](../../core/tools/dotnet-add-reference.md).</span><span class="sxs-lookup"><span data-stu-id="2774b-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="2774b-127">Hinzufügen des `App` Projektes zur `FSNetCore` Projektmappe mithilfe des `dotnet sln add` Befehls:</span><span class="sxs-lookup"><span data-stu-id="2774b-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```dotnetcli
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="2774b-128">Stellen Sie die nuget-Abhängigkeiten wieder her, `dotnet restore` und führen Sie `dotnet build` zum Erstellen des Projekts aus.</span><span class="sxs-lookup"><span data-stu-id="2774b-128">Restore the NuGet dependencies, `dotnet restore` and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="2774b-129">Wechseln Sie zum Verzeichnis der `src/App` Konsolenanwendung und führen Sie das Projekt mit `Hello World` as Argumente aus:</span><span class="sxs-lookup"><span data-stu-id="2774b-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```console
cd src/App
dotnet run Hello World
```

<span data-ttu-id="2774b-130">Folgendes sollte angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="2774b-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="2774b-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="2774b-131">Next steps</span></span>

<span data-ttu-id="2774b-132">Sehen sie sich [Einführung in F#](../tour.md) an für weitere Informationen zu verschiedenen F#-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="2774b-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
