---
title: Verwenden des Paketverwaltung mit f# für Azure
description: Verwenden von Paket "oder" NuGet-zum Verwalten der F#-Azure-Abhängigkeiten
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: fd9c4a15ab0741d44d6d5cf909b7219d310affb0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566969"
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="0d884-103">Verwalten von Paketen für F#-Azure-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="0d884-103">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="0d884-104">Abrufen von Paketen für die Azure-Entwicklung ist einfach, wenn Sie einen Paket-Manager verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d884-104">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="0d884-105">Die beiden Optionen sind [Paket](https://fsprojects.github.io/Paket/) und [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="0d884-105">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="0d884-106">Paket verwenden</span><span class="sxs-lookup"><span data-stu-id="0d884-106">Using Paket</span></span>

<span data-ttu-id="0d884-107">Bei Verwendung von [Paket](https://fsprojects.github.io/Paket/) als der Abhängigkeit-Managers können Sie die `paket.exe` Tool zum Hinzufügen von Azure-Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="0d884-107">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="0d884-108">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0d884-108">For example:</span></span>

    > paket add nuget WindowsAzure.Storage

<span data-ttu-id="0d884-109">Oder, bei Verwendung von [Mono](https://www.mono-project.com/) für die plattformübergreifende .NET-Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="0d884-109">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

    > mono paket.exe add nuget WindowsAzure.Storage

<span data-ttu-id="0d884-110">Dadurch wird hinzugefügt `WindowsAzure.Storage` für Ihren Abhängigkeiten des Pakets für das Projekt im aktuellen Verzeichnis ändern die `paket.dependencies` Datei, und Laden Sie das Paket.</span><span class="sxs-lookup"><span data-stu-id="0d884-110">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="0d884-111">Wenn Sie Abhängigkeiten zuvor eingerichtet haben, oder Arbeiten mit einem Projekt, in denen Abhängigkeiten von anderen Entwicklern wurden eingerichtet sind, können Sie beheben und Installieren von Abhängigkeiten lokal wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0d884-111">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > paket install

<span data-ttu-id="0d884-112">Oder für den Mono-Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="0d884-112">Or, for Mono development:</span></span>

    > mono paket.exe install

<span data-ttu-id="0d884-113">Sie können alle Ihre Abhängigkeiten des Pakets auf die neueste Version wie folgt aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="0d884-113">You can update all your package dependencies to the latest version like this:</span></span>

    > paket update

<span data-ttu-id="0d884-114">Oder für den Mono-Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="0d884-114">Or, for Mono development:</span></span>

    > mono paket.exe update

## <a name="using-nuget"></a><span data-ttu-id="0d884-115">Mithilfe von Nuget</span><span class="sxs-lookup"><span data-stu-id="0d884-115">Using Nuget</span></span>

<span data-ttu-id="0d884-116">Bei Verwendung von [NuGet](https://www.nuget.org/) als der Abhängigkeit-Managers können Sie die `nuget.exe` Tool zum Hinzufügen von Azure-Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="0d884-116">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="0d884-117">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0d884-117">For example:</span></span>

    > nuget install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="0d884-118">Oder für den Mono-Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="0d884-118">Or, for Mono development:</span></span>

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="0d884-119">Dadurch wird hinzugefügt `WindowsAzure.Storage` für Ihren Abhängigkeiten des Pakets für das Projekt im aktuellen Verzeichnis und der Download des Pakets.</span><span class="sxs-lookup"><span data-stu-id="0d884-119">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="0d884-120">Wenn Sie Abhängigkeiten zuvor eingerichtet haben, oder Arbeiten mit einem Projekt, in denen Abhängigkeiten von anderen Entwicklern wurden eingerichtet sind, können Sie beheben und Installieren von Abhängigkeiten lokal wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0d884-120">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > nuget restore 

<span data-ttu-id="0d884-121">Oder für den Mono-Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="0d884-121">Or, for Mono development:</span></span>

    > mono nuget.exe restore

<span data-ttu-id="0d884-122">Sie können alle Ihre Abhängigkeiten des Pakets auf die neueste Version wie folgt aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="0d884-122">You can update all your package dependencies to the latest version like this:</span></span>

    > nuget update

<span data-ttu-id="0d884-123">Oder für den Mono-Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="0d884-123">Or, for Mono development:</span></span>

    > mono nuget.exe update

## <a name="referencing-assemblies"></a><span data-ttu-id="0d884-124">Referenzierende Assemblys</span><span class="sxs-lookup"><span data-stu-id="0d884-124">Referencing Assemblies</span></span>

<span data-ttu-id="0d884-125">Um die Pakete in Ihrem f#-Skript verwenden, müssen Sie die in den Paketen, die mit enthaltenen Assemblys verweisen eine `#r` Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="0d884-125">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="0d884-126">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0d884-126">For example:</span></span>

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

<span data-ttu-id="0d884-127">Wie Sie sehen können, müssen Sie den relativen Pfad zur DLL und den vollständigen DLL-Namen, der nicht genau identisch mit den Paketnamen möglicherweise angeben.</span><span class="sxs-lookup"><span data-stu-id="0d884-127">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="0d884-128">Der Pfad wird ein Framework, Version und möglicherweise eine Paket-Versionsnummer enthalten.</span><span class="sxs-lookup"><span data-stu-id="0d884-128">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="0d884-129">Um die installierten Assemblys zu suchen, können Sie etwa wie folgt in einer Windows-Befehlszeile verwenden:</span><span class="sxs-lookup"><span data-stu-id="0d884-129">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

<span data-ttu-id="0d884-130">Oder in einer Unix-Shell, etwa wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0d884-130">Or in a Unix shell, something like this:</span></span>

    > find packages/WindowsAzure.Storage -name "*.dll"

<span data-ttu-id="0d884-131">Sie erhalten die Pfade zu den installierten Assemblys.</span><span class="sxs-lookup"><span data-stu-id="0d884-131">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="0d884-132">Von dort aus können Sie den richtigen Pfad für die Framework-Version auswählen.</span><span class="sxs-lookup"><span data-stu-id="0d884-132">From there, you can select the correct path for your framework version.</span></span>
