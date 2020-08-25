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
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="cc223-103">Beginnen Sie mit F # mit der .net Core-CLI</span><span class="sxs-lookup"><span data-stu-id="cc223-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="cc223-104">In diesem Artikel erfahren Sie, wie Sie mit der .net Core-CLI mit F # unter jedem Betriebssystem (Windows, macOS oder Linux) beginnen.</span><span class="sxs-lookup"><span data-stu-id="cc223-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="cc223-105">Sie durchläuft das Entwickeln einer Projekt Mappe mit mehreren Projekten mit einer Klassenbibliothek, die von einer Konsolenanwendung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="cc223-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cc223-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="cc223-106">Prerequisites</span></span>

<span data-ttu-id="cc223-107">Zunächst müssen Sie die neuesten [.net Core SDK](https://dotnet.microsoft.com/download)installieren.</span><span class="sxs-lookup"><span data-stu-id="cc223-107">To begin, you must install the latest [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="cc223-108">In diesem Artikel wird davon ausgegangen, dass Sie wissen, wie Sie eine Befehlszeile verwenden und einen bevorzugten Text-Editor verwenden können.</span><span class="sxs-lookup"><span data-stu-id="cc223-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="cc223-109">Wenn Sie Sie nicht bereits verwenden, ist [Visual Studio Code](get-started-vscode.md) eine gute Option als Text-Editor für F #.</span><span class="sxs-lookup"><span data-stu-id="cc223-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="cc223-110">Erstellen Sie eine einfache Lösung mit mehreren Projekten</span><span class="sxs-lookup"><span data-stu-id="cc223-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="cc223-111">Öffnen Sie eine Eingabeaufforderung/ein Terminal, und erstellen Sie mit dem Befehl [dotnet New](../../core/tools/dotnet-new.md) eine neue Projektmappendatei mit dem Namen `FSNetCore` :</span><span class="sxs-lookup"><span data-stu-id="cc223-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```dotnetcli
dotnet new sln -o FSNetCore
```

<span data-ttu-id="cc223-112">Nach dem Ausführen des vorherigen Befehls wird die folgende Verzeichnisstruktur erstellt:</span><span class="sxs-lookup"><span data-stu-id="cc223-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="cc223-113">Schreiben einer Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="cc223-113">Write a class library</span></span>

<span data-ttu-id="cc223-114">Wechseln Sie in das Verzeichnis *fsnetcore*.</span><span class="sxs-lookup"><span data-stu-id="cc223-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="cc223-115">Verwenden Sie den `dotnet new` Befehl, und erstellen Sie ein Klassen Bibliotheksprojekt im Ordner **src** mit dem Namen Library.</span><span class="sxs-lookup"><span data-stu-id="cc223-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```dotnetcli
dotnet new classlib -lang "F#" -o src/Library
```

<span data-ttu-id="cc223-116">Nach dem Ausführen des vorherigen Befehls wird die folgende Verzeichnisstruktur erstellt:</span><span class="sxs-lookup"><span data-stu-id="cc223-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="cc223-117">Ersetzen Sie den Inhalt von `Library.fs` durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="cc223-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    let json = JsonConvert.SerializeObject(value)
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value json
```

<span data-ttu-id="cc223-118">Fügen Sie dem Bibliotheksprojekt die Newtonsoft.Jsfür das nuget-Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="cc223-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="cc223-119">Fügen Sie das `Library` Projekt der Projekt Mappe `FSNetCore` mit dem Befehl [dotnet sln Add](../../core/tools/dotnet-sln.md) hinzu:</span><span class="sxs-lookup"><span data-stu-id="cc223-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="cc223-120">Führen `dotnet build` Sie aus, um das Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cc223-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="cc223-121">Nicht aufgelöste Abhängigkeiten werden bei der Erstellung wieder hergestellt.</span><span class="sxs-lookup"><span data-stu-id="cc223-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="cc223-122">Schreiben einer Konsolenanwendung, die die Klassenbibliothek verwendet</span><span class="sxs-lookup"><span data-stu-id="cc223-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="cc223-123">Verwenden Sie den `dotnet new` Befehl, und erstellen Sie eine Konsolenanwendung im Ordner **src** mit dem Namen app.</span><span class="sxs-lookup"><span data-stu-id="cc223-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```dotnetcli
dotnet new console -lang "F#" -o src/App
```

<span data-ttu-id="cc223-124">Nach dem Ausführen des vorherigen Befehls wird die folgende Verzeichnisstruktur erstellt:</span><span class="sxs-lookup"><span data-stu-id="cc223-124">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="cc223-125">Ersetzen Sie den Inhalt der Datei `Program.fs` durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="cc223-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="cc223-126">Fügen Sie mithilfe von " `Library` [dotnet Add Reference](../../core/tools/dotnet-add-reference.md)" einen Verweis auf das Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="cc223-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="cc223-127">Fügen Sie das `App` Projekt der Projekt Mappe `FSNetCore` mit dem folgenden Befehl hinzu `dotnet sln add` :</span><span class="sxs-lookup"><span data-stu-id="cc223-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```dotnetcli
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="cc223-128">Stellen Sie die nuget-Abhängigkeiten wieder her, `dotnet restore` und führen `dotnet build` Sie zum Erstellen des Projekts aus.</span><span class="sxs-lookup"><span data-stu-id="cc223-128">Restore the NuGet dependencies, `dotnet restore` and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="cc223-129">Wechseln Sie zum `src/App` Konsolen Projekt, und führen Sie das Projekt aus, das `Hello World` als Argument übergeben wird:</span><span class="sxs-lookup"><span data-stu-id="cc223-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```dotnetcli
cd src/App
dotnet run Hello World
```

<span data-ttu-id="cc223-130">Die Ergebnisse sollten wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="cc223-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="cc223-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="cc223-131">Next steps</span></span>

<span data-ttu-id="cc223-132">Sehen Sie sich als nächstes die Einführung in [f #](../tour.md) an, um mehr über verschiedene f #-Features zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="cc223-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
