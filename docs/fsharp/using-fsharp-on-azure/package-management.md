---
title: 'Verwenden von Paketverwaltung mit F # für Azure'
description: 'Verwenden von Paket oder nuget zum Verwalten von F #-Azure-Abhängigkeiten'
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: 011a363b264079599e8b7d402fe9896045b1fe04
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100112"
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="d39f2-103">Verwalten von Paketen für F#-Azure-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="d39f2-103">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="d39f2-104">Das Abrufen von Paketen für die Azure-Entwicklung ist einfach, wenn Sie einen Paket-Manager verwenden.</span><span class="sxs-lookup"><span data-stu-id="d39f2-104">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="d39f2-105">Die beiden Optionen sind " [Paket](https://fsprojects.github.io/Paket/) " und " [nuget](https://www.nuget.org/)".</span><span class="sxs-lookup"><span data-stu-id="d39f2-105">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="d39f2-106">Verwenden von Paket</span><span class="sxs-lookup"><span data-stu-id="d39f2-106">Using Paket</span></span>

<span data-ttu-id="d39f2-107">Wenn Sie " [Paket](https://fsprojects.github.io/Paket/) " als Abhängigkeits-Manager verwenden, können Sie das Tool verwenden, `paket.exe` um Azure-Abhängigkeiten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d39f2-107">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="d39f2-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d39f2-108">For example:</span></span>

```console
> paket add nuget WindowsAzure.Storage
```

<span data-ttu-id="d39f2-109">Oder wenn Sie [Mono](https://www.mono-project.com/) für die plattformübergreifende .net-Entwicklung verwenden:</span><span class="sxs-lookup"><span data-stu-id="d39f2-109">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

```console
> mono paket.exe add nuget WindowsAzure.Storage
```

<span data-ttu-id="d39f2-110">Dadurch wird `WindowsAzure.Storage` Ihrem Satz von Paketabhängigkeiten für das Projekt im aktuellen Verzeichnis hinzugefügt, die Datei geändert `paket.dependencies` und das Paket heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="d39f2-110">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="d39f2-111">Wenn Sie zuvor Abhängigkeiten eingerichtet haben oder mit einem Projekt arbeiten, in dem Abhängigkeiten von einem anderen Entwickler eingerichtet wurden, können Sie Abhängigkeiten wie folgt lokal auflösen und installieren:</span><span class="sxs-lookup"><span data-stu-id="d39f2-111">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```console
> paket install
```

<span data-ttu-id="d39f2-112">Oder für die Mono-Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="d39f2-112">Or, for Mono development:</span></span>

```console
> mono paket.exe install
```

<span data-ttu-id="d39f2-113">Sie können alle Paketabhängigkeiten wie folgt auf die neueste Version aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="d39f2-113">You can update all your package dependencies to the latest version like this:</span></span>

```console
> paket update
```

<span data-ttu-id="d39f2-114">Oder für die Mono-Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="d39f2-114">Or, for Mono development:</span></span>

```console
> mono paket.exe update
```

## <a name="using-nuget"></a><span data-ttu-id="d39f2-115">Verwenden von nuget</span><span class="sxs-lookup"><span data-stu-id="d39f2-115">Using Nuget</span></span>

<span data-ttu-id="d39f2-116">Wenn Sie [nuget](https://www.nuget.org/) als Abhängigkeits-Manager verwenden, können Sie das Tool verwenden, `nuget.exe` um Azure-Abhängigkeiten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d39f2-116">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="d39f2-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d39f2-117">For example:</span></span>

```console
> nuget install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="d39f2-118">Oder für die Mono-Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="d39f2-118">Or, for Mono development:</span></span>

```console
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="d39f2-119">Dadurch wird `WindowsAzure.Storage` Ihrem Satz von Paketabhängigkeiten für das Projekt im aktuellen Verzeichnis hinzugefügt, und das Paket wird heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="d39f2-119">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="d39f2-120">Wenn Sie zuvor Abhängigkeiten eingerichtet haben oder mit einem Projekt arbeiten, in dem Abhängigkeiten von einem anderen Entwickler eingerichtet wurden, können Sie Abhängigkeiten wie folgt lokal auflösen und installieren:</span><span class="sxs-lookup"><span data-stu-id="d39f2-120">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```console
> nuget restore
```

<span data-ttu-id="d39f2-121">Oder für die Mono-Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="d39f2-121">Or, for Mono development:</span></span>

```console
> mono nuget.exe restore
```

<span data-ttu-id="d39f2-122">Sie können alle Paketabhängigkeiten wie folgt auf die neueste Version aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="d39f2-122">You can update all your package dependencies to the latest version like this:</span></span>

```console
> nuget update
```

<span data-ttu-id="d39f2-123">Oder für die Mono-Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="d39f2-123">Or, for Mono development:</span></span>

```console
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a><span data-ttu-id="d39f2-124">Referenzierende Assemblys</span><span class="sxs-lookup"><span data-stu-id="d39f2-124">Referencing Assemblies</span></span>

<span data-ttu-id="d39f2-125">Um die Pakete im F #-Skript verwenden zu können, müssen Sie mit einer-Direktive auf die Assemblys verweisen, die in den Paketen enthalten sind `#r` .</span><span class="sxs-lookup"><span data-stu-id="d39f2-125">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="d39f2-126">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d39f2-126">For example:</span></span>

```fsharp
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

<span data-ttu-id="d39f2-127">Wie Sie sehen können, müssen Sie den relativen Pfad zur dll und den vollständigen DLL-Namen angeben, der möglicherweise nicht exakt mit dem Paketnamen identisch ist.</span><span class="sxs-lookup"><span data-stu-id="d39f2-127">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="d39f2-128">Der Pfad enthält eine Framework-Version und möglicherweise eine Paket Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="d39f2-128">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="d39f2-129">Wenn Sie alle installierten Assemblys suchen möchten, können Sie diese in einer Windows-Befehlszeile verwenden:</span><span class="sxs-lookup"><span data-stu-id="d39f2-129">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

```console
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

<span data-ttu-id="d39f2-130">Oder in einer Unix-Shell wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d39f2-130">Or in a Unix shell, something like this:</span></span>

```console
> find packages/WindowsAzure.Storage -name "*.dll"
```

<span data-ttu-id="d39f2-131">Dadurch erhalten Sie die Pfade zu den installierten Assemblys.</span><span class="sxs-lookup"><span data-stu-id="d39f2-131">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="d39f2-132">Von dort aus können Sie den richtigen Pfad für Ihre Frameworkversion auswählen.</span><span class="sxs-lookup"><span data-stu-id="d39f2-132">From there, you can select the correct path for your framework version.</span></span>
