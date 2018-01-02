---
title: Erste Schritte mit f# mit Befehlszeilentools
description: "Informationen Sie zum Verwenden von f# auf allen Betriebssystemen (Windows, Mac OS, Linux) mit der plattformübergreifenden .NET Core-CLI."
keywords: Visual F#, F#, funktionale Programmierung, .NET, .NET Core
author: cartermp
ms.author: phcart
ms.date: 06/14/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 615db1ec-6ef3-4de2-bae6-4586affa9771
ms.openlocfilehash: 4820a8a306bd478429b497a8b7c70ff170c1c655
ms.sourcegitcommit: d095094e942eedf09530ea5636fbaf9029853027
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="ed9f4-104">Erste Schritte mit f# mit der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="ed9f4-104">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="ed9f4-105">Dieser Artikel behandelt, wie Sie ein Betriebssystem (Windows, Mac OS oder Linux) Einstieg können mithilfe von f# mit der .NET Core-CLI.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-105">This article covers how you can get started on any OS (Windows, macOS, or Linux) by using F# with the .NET Core CLI.</span></span> <span data-ttu-id="ed9f4-106">Es geht über das Erstellen einer Lösung mit mehreren Projekten mit einer Klassenbibliothek, die von einer Konsolenanwendung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-106">It will go through building a multi-project solution with a Class Library that is called by a Console Application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ed9f4-107">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="ed9f4-107">Prerequisites</span></span>

<span data-ttu-id="ed9f4-108">Um zu beginnen, müssen Sie installieren die [.NET Core SDK 1.0 oder höher](https://dot.net/core).</span><span class="sxs-lookup"><span data-stu-id="ed9f4-108">To begin, you must install the [.NET Core SDK 1.0 or later](https://dot.net/core).</span></span> <span data-ttu-id="ed9f4-109">Besteht keine Notwendigkeit zum Deinstallieren einer früheren Version von .NET Core SDK, wie sie die Seite-an-Seite-Installationen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-109">There is no need to uninstall a previous version of the .NET Core SDK, as it supports side-by-side installations.</span></span>

<span data-ttu-id="ed9f4-110">In diesem Artikel wird davon ausgegangen, dass Sie wissen, wie Sie eine Befehlszeile verwenden und haben einen bevorzugten Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-110">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="ed9f4-111">Wenn Sie nicht bereits, verwenden [Visual Studio Code](https://code.visualstudio.com) ist eine sinnvolle Option als einem Text-Editor für f#.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-111">If you don't already use it, [Visual Studio Code](https://code.visualstudio.com) is a great option as a text editor for F#.</span></span> <span data-ttu-id="ed9f4-112">Um awesome Funktionen wie IntelliSense, bessere syntaxhervorhebung und mehr zu erhalten, können Sie Herunterladen der [Ionide Erweiterung](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="ed9f4-112">To get awesome features like IntelliSense, better syntax highlighting, and more, you can download the [Ionide Extension](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span>

## <a name="building-a-simple-multi-project-solution"></a><span data-ttu-id="ed9f4-113">Erstellen einer Lösung für einfache mit mehreren Projekten</span><span class="sxs-lookup"><span data-stu-id="ed9f4-113">Building a Simple Multi-project Solution</span></span>

<span data-ttu-id="ed9f4-114">Öffnen Sie einen Eingabeaufforderungsfenster/Terminal und Verwenden der `dotnet new` Befehl zum Erstellen der neuen Projektmappendatei mit dem Namen `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="ed9f4-114">Open a command prompt/terminal and use the `dotnet new` command to create new solution file called `FSNetCore`:</span></span>

```
dotnet new sln -o FSNetCore
```

<span data-ttu-id="ed9f4-115">Die folgende Verzeichnisstruktur wird als Ergebnis der Datenbankbefehl wird abgeschlossen erzeugt:</span><span class="sxs-lookup"><span data-stu-id="ed9f4-115">The folowing directory structure is produced as a result of the command completing:</span></span>

```
FSNetCore
    ├── FSNetCore.sln
```

<span data-ttu-id="ed9f4-116">Wechseln Sie *FSNetCore* , und starten Sie den Projektmappenordner Projekte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-116">Change directories to *FSNetCore* and start adding projects to the solution folder.</span></span>
 
### <a name="writing-a-class-library"></a><span data-ttu-id="ed9f4-117">Schreiben eine Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="ed9f4-117">Writing a Class library</span></span>

<span data-ttu-id="ed9f4-118">Verwenden der `dotnet new` Befehl, erstellen Sie ein Klassenbibliotheksprojekt, in dem **Src** Ordner mit dem Namen Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-118">Use the `dotnet new` command, create a Class Library project in the **src** folder named Library.</span></span> 

```bash
dotnet new lib -lang F# -o src/Library 
```

<span data-ttu-id="ed9f4-119">Die folgende Verzeichnisstruktur wird als Ergebnis der Datenbankbefehl wird abgeschlossen erzeugt:</span><span class="sxs-lookup"><span data-stu-id="ed9f4-119">The following directory structure is produced as a result of the command completing:</span></span>

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="ed9f4-120">Ersetzen Sie den Inhalt des `Library.fs` durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ed9f4-120">Replace the contents of `Library.fs` with the following:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value = 
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value  (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="ed9f4-121">Das Steuerelementbibliothek-Projekt das Newtonsoft.Json NuGet-Paket hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-121">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```bash
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="ed9f4-122">Hinzufügen der `Library` -Projekt auf die `FSNetCore` Lösung mithilfe der `dotnet sln add` Befehl:</span><span class="sxs-lookup"><span data-stu-id="ed9f4-122">Add the `Library` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```bash
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="ed9f4-123">Wiederherstellen von NuGet Abhängigkeiten `dotnet restore` ([Siehe Hinweis](#dotnet-restore-note)) und führen Sie `dotnet build` zum Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-123">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

### <a name="writing-a-console-application-which-consumes-the-class-library"></a><span data-ttu-id="ed9f4-124">Schreiben einer Konsolenanwendung von der die Klassenbibliothek in Anspruch nimmt</span><span class="sxs-lookup"><span data-stu-id="ed9f4-124">Writing a Console Application which Consumes the Class Library</span></span>

<span data-ttu-id="ed9f4-125">Verwenden der `dotnet new` Befehl, erstellen Sie eine Konsolen-app in der **Src** Ordner mit dem Namen App.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-125">Use the `dotnet new` command, create a Console app in the **src** folder named App.</span></span> 

```bash
dotnet new console -lang F# -o src/App 
```

<span data-ttu-id="ed9f4-126">Die folgende Verzeichnisstruktur wird als Ergebnis der Datenbankbefehl wird abgeschlossen erzeugt:</span><span class="sxs-lookup"><span data-stu-id="ed9f4-126">The following directory structure is produced as a result of the command completing:</span></span>

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

<span data-ttu-id="ed9f4-127">Änderung `Program.fs` an:</span><span class="sxs-lookup"><span data-stu-id="ed9f4-127">Change `Program.fs` to:</span></span>

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

<span data-ttu-id="ed9f4-128">Hinzufügen eines Verweises auf die `Library` Projekt mit `dotnet add reference`.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-128">Add a reference to the `Library` project using `dotnet add reference`.</span></span>

```bash
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="ed9f4-129">Hinzufügen der `App` -Projekt auf die `FSNetCore` Lösung mithilfe der `dotnet sln add` Befehl:</span><span class="sxs-lookup"><span data-stu-id="ed9f4-129">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```bash
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="ed9f4-130">Wiederherstellen von NuGet Abhängigkeiten `dotnet restore` ([Siehe Hinweis](#dotnet-restore-note)) und führen Sie `dotnet build` zum Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-130">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="ed9f4-131">Ändern Sie das Verzeichnis, das `src/App` Konsole Projekt, und führen Sie das Projekt, das Übergeben von `Hello World` als Argumente.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-131">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments.</span></span>

```bash
cd src/App
dotnet run Hello World
``` 

<span data-ttu-id="ed9f4-132">Daraufhin sollte die folgenden Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="ed9f4-132">You should see the following results:</span></span>

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```
<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
