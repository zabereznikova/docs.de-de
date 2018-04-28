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
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="3d48e-103">Erste Schritte mit f# mit der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="3d48e-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="3d48e-104">Dieser Artikel behandelt, wie Sie mit f# unter jedem Betriebssystem (Windows, Mac OS oder Linux) mit der .NET Core-CLI beginnen können.</span><span class="sxs-lookup"><span data-stu-id="3d48e-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="3d48e-105">Erstellen einer Lösung mit mehreren Projekten mit einer Klassenbibliothek, die von einer Konsolenanwendung aufgerufen wird, durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="3d48e-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3d48e-106">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="3d48e-106">Prerequisites</span></span>

<span data-ttu-id="3d48e-107">Um zu beginnen, müssen Sie installieren die [.NET Core SDK 1.0 oder höher](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="3d48e-107">To begin, you must install the [.NET Core SDK 1.0 or later](https://www.microsoft.com/net/download/).</span></span> <span data-ttu-id="3d48e-108">Besteht keine Notwendigkeit zum Deinstallieren einer früheren Version von .NET Core SDK, wie sie die Seite-an-Seite-Installationen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3d48e-108">There is no need to uninstall a previous version of the .NET Core SDK, as it supports side-by-side installations.</span></span>

<span data-ttu-id="3d48e-109">In diesem Artikel wird davon ausgegangen, dass Sie wissen, wie Sie eine Befehlszeile verwenden und haben einen bevorzugten Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="3d48e-109">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="3d48e-110">Wenn Sie nicht bereits, verwenden [Visual Studio Code](https://code.visualstudio.com) ist eine sinnvolle Option als einem Text-Editor für f#.</span><span class="sxs-lookup"><span data-stu-id="3d48e-110">If you don't already use it, [Visual Studio Code](https://code.visualstudio.com) is a great option as a text editor for F#.</span></span> <span data-ttu-id="3d48e-111">Um awesome Funktionen wie IntelliSense, bessere syntaxhervorhebung und mehr zu erhalten, können Sie Herunterladen der [Ionide Erweiterung](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="3d48e-111">To get awesome features like IntelliSense, better syntax highlighting, and more, you can download the [Ionide Extension](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="3d48e-112">Erstellen Sie eine einfache Lösung für mehrere Projekte</span><span class="sxs-lookup"><span data-stu-id="3d48e-112">Build a simple multi-project solution</span></span>

<span data-ttu-id="3d48e-113">Öffnen Sie einen Eingabeaufforderungsfenster/Terminal und Verwenden der [Dotnet neue](../../core/tools/dotnet-new.md) Befehl zum Erstellen der neuen Projektmappendatei mit dem Namen `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="3d48e-113">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```
dotnet new sln -o FSNetCore
```

<span data-ttu-id="3d48e-114">Die folgende Verzeichnisstruktur wird nach der Ausführung mit dem vorherigen Befehls erzeugt:</span><span class="sxs-lookup"><span data-stu-id="3d48e-114">The following directory structure is produced after running the previous command:</span></span>

```
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="3d48e-115">Schreiben Sie eine Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="3d48e-115">Write a class library</span></span>

<span data-ttu-id="3d48e-116">Wechseln Sie *FSNetCore*.</span><span class="sxs-lookup"><span data-stu-id="3d48e-116">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="3d48e-117">Verwenden der `dotnet new` Befehl, erstellen Sie ein Klassenbibliotheksprojekt, in dem **Src** Ordner mit dem Namen Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="3d48e-117">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```
dotnet new lib -lang F# -o src/Library
```

<span data-ttu-id="3d48e-118">Die folgende Verzeichnisstruktur wird nach der Ausführung mit dem vorherigen Befehls erzeugt:</span><span class="sxs-lookup"><span data-stu-id="3d48e-118">The following directory structure is produced after running the previous command:</span></span>

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="3d48e-119">Ersetzen Sie den Inhalt des `Library.fs` durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="3d48e-119">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="3d48e-120">Das Steuerelementbibliothek-Projekt das Newtonsoft.Json NuGet-Paket hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3d48e-120">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="3d48e-121">Hinzufügen der `Library` -Projekt auf die `FSNetCore` Lösung mithilfe der [Dotnet Sln hinzufügen](../../core/tools/dotnet-sln.md) Befehl:</span><span class="sxs-lookup"><span data-stu-id="3d48e-121">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="3d48e-122">Wiederherstellen von NuGet-Abhängigkeiten mithilfe der `dotnet restore` Befehl ([Siehe Hinweis](#dotnet-restore-note)) und führen Sie `dotnet build` zum Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="3d48e-122">Restore the NuGet dependencies using the `dotnet restore` command ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="3d48e-123">Schreiben Sie eine Konsolenanwendung, die in der Klassenbibliothek benötigt.</span><span class="sxs-lookup"><span data-stu-id="3d48e-123">Write a console application that consumes the class library</span></span>

<span data-ttu-id="3d48e-124">Verwenden der `dotnet new` Befehl, erstellen Sie eine Konsolenanwendung in der **Src** Ordner mit dem Namen App.</span><span class="sxs-lookup"><span data-stu-id="3d48e-124">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```
dotnet new console -lang F# -o src/App
```

<span data-ttu-id="3d48e-125">Die folgende Verzeichnisstruktur wird nach der Ausführung mit dem vorherigen Befehls erzeugt:</span><span class="sxs-lookup"><span data-stu-id="3d48e-125">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="3d48e-126">Ersetzen Sie den Inhalt von der `Program.fs` Datei durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="3d48e-126">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="3d48e-127">Hinzufügen eines Verweises auf die `Library` Projekt mit [Dotnet Verweis hinzufügen](../../core/tools/dotnet-add-reference.md).</span><span class="sxs-lookup"><span data-stu-id="3d48e-127">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="3d48e-128">Hinzufügen der `App` -Projekt auf die `FSNetCore` Lösung mithilfe der `dotnet sln add` Befehl:</span><span class="sxs-lookup"><span data-stu-id="3d48e-128">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="3d48e-129">Wiederherstellen von NuGet Abhängigkeiten `dotnet restore` ([Siehe Hinweis](#dotnet-restore-note)) und führen Sie `dotnet build` zum Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="3d48e-129">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="3d48e-130">Ändern Sie das Verzeichnis, das `src/App` Konsole Projekt, und führen Sie das Projekt, das Übergeben von `Hello World` als Argumente:</span><span class="sxs-lookup"><span data-stu-id="3d48e-130">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```
cd src/App
dotnet run Hello World
```

<span data-ttu-id="3d48e-131">Daraufhin sollte die folgenden Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="3d48e-131">You should see the following results:</span></span>

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]