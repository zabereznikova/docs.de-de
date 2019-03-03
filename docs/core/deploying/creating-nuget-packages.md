---
title: Erstellen eines NuGet-Pakets mit Tools der .NET Core-Befehlszeilenschnittstelle (CLI)
description: Erfahren Sie, wie Sie ein NuGet-Paket mit dem Befehl „dotnet pack“ erstellen.
author: cartermp
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.custom: seodec18
ms.openlocfilehash: 1add3470799b75ebb92c67eed3509523e510ab6c
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57211792"
---
# <a name="how-to-create-a-nuget-package-with-net-core-command-line-interface-cli-tools"></a><span data-ttu-id="6ad9a-103">Erstellen eines NuGet-Pakets mit Tools der .NET Core-Befehlszeilenschnittstelle (CLI)</span><span class="sxs-lookup"><span data-stu-id="6ad9a-103">How to create a NuGet package with .NET Core command-line interface (CLI) tools</span></span>

> [!NOTE]
> <span data-ttu-id="6ad9a-104">Nachfolgend einige Befehlszeilenbeispiele unter Unix.</span><span class="sxs-lookup"><span data-stu-id="6ad9a-104">The following shows command-line samples using Unix.</span></span> <span data-ttu-id="6ad9a-105">Der hier gezeigte Befehl `dotnet pack` funktioniert wie unter Windows.</span><span class="sxs-lookup"><span data-stu-id="6ad9a-105">The `dotnet pack` command as shown here works the same way on Windows.</span></span>

<span data-ttu-id="6ad9a-106">.NET Standard- und .NET Core-Bibliotheken sollten als NuGet-Pakete verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="6ad9a-106">.NET Standard and .NET Core libraries are expected to be distributed as NuGet packages.</span></span> <span data-ttu-id="6ad9a-107">So werden alle .NET Standardbibliotheken verteilt und genutzt.</span><span class="sxs-lookup"><span data-stu-id="6ad9a-107">This is in fact how all of the .NET Standard libraries are distributed and consumed.</span></span> <span data-ttu-id="6ad9a-108">Am einfachsten geht dies mit dem Befehl `dotnet pack`.</span><span class="sxs-lookup"><span data-stu-id="6ad9a-108">This is most easily done with the `dotnet pack` command.</span></span>

<span data-ttu-id="6ad9a-109">Stellen Sie sich vor, dass Sie eine fantastische neue Bibliothek geschrieben haben, die Sie über NuGet verteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="6ad9a-109">Imagine that you just wrote an awesome new library that you would like to distribute over NuGet.</span></span> <span data-ttu-id="6ad9a-110">Sie können hierfür ein NuGet-Paket mit plattformübergreifenden Tools erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ad9a-110">You can create a NuGet package with cross platform tools to do exactly that!</span></span> <span data-ttu-id="6ad9a-111">Als Beispiel dient eine Bibliothek namens **SuperAwesomeLibrary** für `netstandard1.0`.</span><span class="sxs-lookup"><span data-stu-id="6ad9a-111">The following example assumes a library called **SuperAwesomeLibrary** which targets `netstandard1.0`.</span></span>

<span data-ttu-id="6ad9a-112">Wenn Sie transitive Abhängigkeiten haben, also ein Projekt, das von einem anderen Paket abhängig ist, müssen Sie sicherstellen, dass Pakete für die gesamte Projektmappe mit dem Befehl `dotnet restore` wiederhergestellt werden, bevor das NuGet-Paket erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="6ad9a-112">If you have transitive dependencies; that is, a project which depends on another package, you'll need to make sure to restore packages for your entire solution with the `dotnet restore` command before creating a NuGet package.</span></span> <span data-ttu-id="6ad9a-113">Andernfalls wird der Befehl `dotnet pack` nicht ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="6ad9a-113">Failing to do so will result in the `dotnet pack` command to not work properly.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="6ad9a-114">Nachdem Sie sichergestellt haben, dass Pakete wiederhergestellt wurden, können Sie zu dem Verzeichnis navigieren, in dem sich eine Bibliothek befindet:</span><span class="sxs-lookup"><span data-stu-id="6ad9a-114">After ensuring packages are restored, you can navigate to the directory where a library lives:</span></span>

```console
cd src/SuperAwesomeLibrary
```

<span data-ttu-id="6ad9a-115">Anschließend genügt ein einzelner Befehl von der Befehlszeile:</span><span class="sxs-lookup"><span data-stu-id="6ad9a-115">Then it's just a single command from the command line:</span></span>

```console
dotnet pack
```

<span data-ttu-id="6ad9a-116">Ihr Ordner `/bin/Debug` sieht nun wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="6ad9a-116">Your `/bin/Debug` folder will now look like this:</span></span>

```console
$ ls bin/Debug

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="6ad9a-117">Beachten Sie, dass dies ein Paket erzeugt, das debuggt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6ad9a-117">Note that this will produce a package which is capable of being debugged.</span></span> <span data-ttu-id="6ad9a-118">Wenn Sie ein NuGet-Paket mit Release-Binärdateien erstellen möchten, müssen Sie lediglich den Schalter `--configuration` (oder) `-c` und `release` als Argument verwenden.</span><span class="sxs-lookup"><span data-stu-id="6ad9a-118">If you want to build a NuGet package with release binaries, all you need to do is add the `--configuration` (or `-c`) switch and use `release` as the argument.</span></span>

```console
dotnet pack --configuration release
```

<span data-ttu-id="6ad9a-119">Ihr Ordner `/bin` hat nun einen Unterordner `release` mit dem NuGet-Paket und den Release-Binärdateien:</span><span class="sxs-lookup"><span data-stu-id="6ad9a-119">Your `/bin` folder will now have a `release` folder containing your NuGet package with release binaries:</span></span>

```console
$ ls bin/release

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="6ad9a-120">Jetzt haben Sie die erforderlichen Dateien zum Veröffentlichen eines NuGet-Pakets.</span><span class="sxs-lookup"><span data-stu-id="6ad9a-120">And now you have the necessary files to publish a NuGet package!</span></span>

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a><span data-ttu-id="6ad9a-121">Verwechseln Sie nicht `dotnet pack` mit `dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="6ad9a-121">Don't confuse `dotnet pack` with `dotnet publish`</span></span>

<span data-ttu-id="6ad9a-122">Es ist wichtig zu beachten, dass zu keinem Zeitpunkt der Befehl `dotnet publish` beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="6ad9a-122">It is important to note that at no point is the `dotnet publish` command involved.</span></span> <span data-ttu-id="6ad9a-123">Der Befehl `dotnet publish` dient der Bereitstellung von Clientanwendungen mit allen Abhängigkeiten im gleichen Paket – nicht für das Generieren eines NuGet-Pakets, das über NuGet verteilt und genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="6ad9a-123">The `dotnet publish` command is for deploying applications with all of their dependencies in the same bundle -- not for generating a NuGet package to be distributed and consumed via NuGet.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ad9a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ad9a-124">See also</span></span>

- [<span data-ttu-id="6ad9a-125">Schnellstart: Erstellen und Veröffentlichen eines Pakets</span><span class="sxs-lookup"><span data-stu-id="6ad9a-125">Quickstart: Create and publish a package</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)