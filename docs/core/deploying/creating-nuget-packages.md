---
title: Erstellen eines NuGet-Pakets mit der .NET Core-CLI
description: Erfahren Sie, wie Sie ein NuGet-Paket mit dem Befehl „dotnet pack“ erstellen.
author: cartermp
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.openlocfilehash: ddc19faa7547637036686146f8600f40713541a8
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740865"
---
# <a name="how-to-create-a-nuget-package-with-net-core-command-line-interface-cli-tools"></a><span data-ttu-id="382d2-103">Erstellen eines NuGet-Pakets mit Tools der .NET Core-Befehlszeilenschnittstelle (CLI)</span><span class="sxs-lookup"><span data-stu-id="382d2-103">How to create a NuGet package with .NET Core command-line interface (CLI) tools</span></span>

> [!NOTE]
> <span data-ttu-id="382d2-104">Nachfolgend einige Befehlszeilenbeispiele unter Unix.</span><span class="sxs-lookup"><span data-stu-id="382d2-104">The following shows command-line samples using Unix.</span></span> <span data-ttu-id="382d2-105">Der hier gezeigte Befehl `dotnet pack` funktioniert wie unter Windows.</span><span class="sxs-lookup"><span data-stu-id="382d2-105">The `dotnet pack` command as shown here works the same way on Windows.</span></span>

<span data-ttu-id="382d2-106">.NET Standard- und .NET Core-Bibliotheken sollten als NuGet-Pakete verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="382d2-106">.NET Standard and .NET Core libraries are expected to be distributed as NuGet packages.</span></span> <span data-ttu-id="382d2-107">So werden alle .NET Standardbibliotheken verteilt und genutzt.</span><span class="sxs-lookup"><span data-stu-id="382d2-107">This is in fact how all of the .NET Standard libraries are distributed and consumed.</span></span> <span data-ttu-id="382d2-108">Am einfachsten geht dies mit dem Befehl `dotnet pack`.</span><span class="sxs-lookup"><span data-stu-id="382d2-108">This is most easily done with the `dotnet pack` command.</span></span>

<span data-ttu-id="382d2-109">Stellen Sie sich vor, dass Sie eine fantastische neue Bibliothek geschrieben haben, die Sie über NuGet verteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="382d2-109">Imagine that you just wrote an awesome new library that you would like to distribute over NuGet.</span></span> <span data-ttu-id="382d2-110">Sie können zu genau diesem Zweck ein NuGet-Paket mit plattformübergreifenden Tools erstellen!</span><span class="sxs-lookup"><span data-stu-id="382d2-110">You can create a NuGet package with cross-platform tools to do exactly that!</span></span> <span data-ttu-id="382d2-111">Als Beispiel dient eine Bibliothek namens **SuperAwesomeLibrary** für das Ziel `netstandard1.0`.</span><span class="sxs-lookup"><span data-stu-id="382d2-111">The following example assumes a library called **SuperAwesomeLibrary** that targets `netstandard1.0`.</span></span>

<span data-ttu-id="382d2-112">Wenn Sie transitive Abhängigkeiten haben, also ein Projekt, das von einem anderen Paket abhängig ist, stellen Sie sicher, dass Sie Pakete für die gesamte Projektmappe mit dem Befehl `dotnet restore` wiederherstellen, bevor Sie das NuGet-Paket erstellen.</span><span class="sxs-lookup"><span data-stu-id="382d2-112">If you have transitive dependencies, that is, a project that depends on another package, make sure to restore packages for the entire solution with the `dotnet restore` command before you create a NuGet package.</span></span> <span data-ttu-id="382d2-113">Andernfalls funktioniert der Befehl `dotnet pack` nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="382d2-113">Failing to do so will result in the `dotnet pack` command not working properly.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="382d2-114">Nachdem Sie sichergestellt haben, dass Pakete wiederhergestellt wurden, können Sie zu dem Verzeichnis navigieren, in dem sich eine Bibliothek befindet:</span><span class="sxs-lookup"><span data-stu-id="382d2-114">After ensuring packages are restored, you can navigate to the directory where a library lives:</span></span>

```console
cd src/SuperAwesomeLibrary
```

<span data-ttu-id="382d2-115">Anschließend genügt ein einzelner Befehl von der Befehlszeile:</span><span class="sxs-lookup"><span data-stu-id="382d2-115">Then it's just a single command from the command line:</span></span>

```dotnetcli
dotnet pack
```

<span data-ttu-id="382d2-116">Der Ordner */bin/debug* sieht nun wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="382d2-116">Your */bin/Debug* folder will now look like this:</span></span>

```console
$ ls bin/Debug
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="382d2-117">Es wird ein Paket generiert, das debuggt werden kann.</span><span class="sxs-lookup"><span data-stu-id="382d2-117">This produces a package that is capable of being debugged.</span></span> <span data-ttu-id="382d2-118">Wenn Sie ein NuGet-Paket mit Release-Binärdateien erstellen möchten, müssen Sie lediglich den Schalter `--configuration` (oder) `-c` und `release` als Argument verwenden.</span><span class="sxs-lookup"><span data-stu-id="382d2-118">If you want to build a NuGet package with release binaries, all you need to do is add the `--configuration` (or `-c`) switch and use `release` as the argument.</span></span>

```dotnetcli
dotnet pack --configuration release
```

<span data-ttu-id="382d2-119">Ihr Ordner */bin* weist nun einen Unterordner *release* mit dem NuGet-Paket und den Releasebinärdateien auf:</span><span class="sxs-lookup"><span data-stu-id="382d2-119">Your */bin* folder will now have a *release* folder containing your NuGet package with release binaries:</span></span>

```console
$ ls bin/release
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="382d2-120">Jetzt haben Sie die erforderlichen Dateien zum Veröffentlichen eines NuGet-Pakets.</span><span class="sxs-lookup"><span data-stu-id="382d2-120">And now you have the necessary files to publish a NuGet package!</span></span>

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a><span data-ttu-id="382d2-121">Verwechseln Sie nicht `dotnet pack` mit `dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="382d2-121">Don't confuse `dotnet pack` with `dotnet publish`</span></span>

<span data-ttu-id="382d2-122">Es ist wichtig zu beachten, dass zu keinem Zeitpunkt der Befehl `dotnet publish` beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="382d2-122">It is important to note that at no point is the `dotnet publish` command involved.</span></span> <span data-ttu-id="382d2-123">Der Befehl `dotnet publish` dient der Bereitstellung von Clientanwendungen mit allen Abhängigkeiten im gleichen Paket – nicht für das Generieren eines NuGet-Pakets, das über NuGet verteilt und genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="382d2-123">The `dotnet publish` command is for deploying applications with all of their dependencies in the same bundle -- not for generating a NuGet package to be distributed and consumed via NuGet.</span></span>

## <a name="see-also"></a><span data-ttu-id="382d2-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="382d2-124">See also</span></span>

- [<span data-ttu-id="382d2-125">Schnellstart: Erstellen und Veröffentlichen eines Pakets</span><span class="sxs-lookup"><span data-stu-id="382d2-125">Quickstart: Create and publish a package</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)
