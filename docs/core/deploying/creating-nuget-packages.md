---
title: Erstellen eines NuGet-Pakets mit plattformübergreifenden Tools
description: Erfahren Sie, wie Sie ein NuGet-Paket mit dem Befehl „dotnet pack“ erstellen.
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.openlocfilehash: 6be94c2e2cef443f69b2d6df7c2d490cb1fb629d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-nuget-package-with-cross-platform-tools"></a><span data-ttu-id="72101-103">So erstellen Sie ein NuGet-Paket mit plattformübergreifenden Tools</span><span class="sxs-lookup"><span data-stu-id="72101-103">How to Create a NuGet Package with Cross Platform Tools</span></span>

> [!NOTE]
> <span data-ttu-id="72101-104">Nachfolgend einige Befehlszeilenbeispiele unter Unix.</span><span class="sxs-lookup"><span data-stu-id="72101-104">The following shows command-line samples using Unix.</span></span>  <span data-ttu-id="72101-105">Der hier gezeigte Befehl `dotnet pack` funktioniert wie unter Windows.</span><span class="sxs-lookup"><span data-stu-id="72101-105">The `dotnet pack` command as shown here works the same way on Windows.</span></span>

<span data-ttu-id="72101-106">Bibliotheken sollten für .NET Core 1.0 als NuGet-Pakete verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="72101-106">For .NET Core 1.0, libraries are expected to be distributed as NuGet packages.</span></span>  <span data-ttu-id="72101-107">So werden alle .NET Standardbibliotheken verteilt und genutzt.</span><span class="sxs-lookup"><span data-stu-id="72101-107">This is in fact how all of the .NET Standard libraries are distributed and consumed.</span></span>  <span data-ttu-id="72101-108">Am einfachsten geht dies mit dem Befehl `dotnet pack`.</span><span class="sxs-lookup"><span data-stu-id="72101-108">This is most easily done with the `dotnet pack` command.</span></span>

<span data-ttu-id="72101-109">Stellen Sie sich vor, dass Sie eine fantastische neue Bibliothek geschrieben haben, die Sie über NuGet verteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="72101-109">Imagine that you just wrote an awesome new library that you would like to distribute over NuGet.</span></span>  <span data-ttu-id="72101-110">Sie können hierfür ein NuGet-Paket mit plattformübergreifenden Tools erstellen.</span><span class="sxs-lookup"><span data-stu-id="72101-110">You can create a NuGet package with cross platform tools to do exactly that!</span></span>  <span data-ttu-id="72101-111">Als Beispiel dient eine Bibliothek namens **SuperAwesomeLibrary** für `netstandard1.0`.</span><span class="sxs-lookup"><span data-stu-id="72101-111">The following example assumes a library called **SuperAwesomeLibrary** which targets `netstandard1.0`.</span></span>

<span data-ttu-id="72101-112">Wenn Sie transitive Abhängigkeiten haben, das heißt ein Projekt, das von einem anderen Projekt abhängig ist, müssen Sie sicherstellen, dass Pakete für die gesamte Projektmappe mit dem Befehl `dotnet restore` wiederhergestellt werden, bevor das NuGet-Paket erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="72101-112">If you have transitive dependencies; that is, a project which depends on another project, you'll need to make sure to restore packages for your entire solution with the `dotnet restore` command before creating a NuGet package.</span></span>  <span data-ttu-id="72101-113">Andernfalls wird der Befehl `dotnet pack` nicht ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="72101-113">Failing to do so will result in the `dotnet pack` command to not work properly.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]


<span data-ttu-id="72101-114">Nachdem Sie sichergestellt haben, dass Pakete wiederhergestellt wurden, können Sie zu dem Verzeichnis navigieren, in dem sich eine Bibliothek befindet:</span><span class="sxs-lookup"><span data-stu-id="72101-114">After ensuring packages are restored, you can navigate to the directory where a library lives:</span></span>

`$ cd src/SuperAwesomeLibrary`

<span data-ttu-id="72101-115">Anschließend genügt ein einzelner Befehl von der Befehlszeile:</span><span class="sxs-lookup"><span data-stu-id="72101-115">Then it's just a single command from the command line:</span></span>
    
`$ dotnet pack`

<span data-ttu-id="72101-116">Ihr Ordner `/bin/Debug` sieht nun wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="72101-116">Your `/bin/Debug` folder will now look like this:</span></span>

```
$ ls bin/Debug

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="72101-117">Beachten Sie, dass dies ein Paket erzeugt, das debuggt werden kann.</span><span class="sxs-lookup"><span data-stu-id="72101-117">Note that this will produce a package which is capable of being debugged.</span></span>  <span data-ttu-id="72101-118">Wenn Sie ein NuGet-Paket mit Release-Binärdateien erstellen möchten, müssen Sie lediglich den Schalter `-c`/`--configuration` und das Argument `release` verwenden.</span><span class="sxs-lookup"><span data-stu-id="72101-118">If you want to build a NuGet package with release binaries, all you need to do is add the `-c`/`--configuration` switch and use `release` as the argument.</span></span>

`$ dotnet pack --configuration release`

<span data-ttu-id="72101-119">Ihr Ordner `/bin` hat nun einen Unterordner `release` mit dem NuGet-Paket und den Release-Binärdateien:</span><span class="sxs-lookup"><span data-stu-id="72101-119">Your `/bin` folder will now have a `release` folder containing your NuGet package with release binaries:</span></span>

```
$ ls bin/release

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="72101-120">Jetzt haben Sie die erforderlichen Dateien zum Veröffentlichen eines NuGet-Pakets.</span><span class="sxs-lookup"><span data-stu-id="72101-120">And now you have the necessary files to publish a NuGet package!</span></span>

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a><span data-ttu-id="72101-121">Verwechseln Sie nicht `dotnet pack` mit `dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="72101-121">Don't confuse `dotnet pack` with `dotnet publish`</span></span>

<span data-ttu-id="72101-122">Es ist wichtig zu beachten, dass zu keinem Zeitpunkt der Befehl `dotnet publish` beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="72101-122">It is important to note that at no point is the `dotnet publish` command involved.</span></span>  <span data-ttu-id="72101-123">Der Befehl `dotnet publish` dient der Bereitstellung von Clientanwendungen mit allen Abhängigkeiten im gleichen Paket – nicht für das Generieren eines NuGet-Pakets, das über NuGet verteilt und genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="72101-123">The `dotnet publish` command is for deploying applications with all of their dependencies in the same bundle -  not for generating a NuGet package to be distributed and consumed via NuGet.</span></span>
