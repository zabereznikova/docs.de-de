---
title: Mit der Paketverwaltung mit F# für Azure
description: Verwenden Sie zum Verwalten von Paket-Abhängigkeits oder Nuget F# Azure-Abhängigkeiten
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: fd9c4a15ab0741d44d6d5cf909b7219d310affb0
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "33566969"
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="8679b-103">Verwalten von Paketen für F#-Azure-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="8679b-103">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="8679b-104">Abrufen von Paketen für Azure-Entwicklung ist einfach, wenn Sie einen Paket-Manager verwenden.</span><span class="sxs-lookup"><span data-stu-id="8679b-104">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="8679b-105">Die beiden Optionen sind [Paket-Abhängigkeits](https://fsprojects.github.io/Paket/) und [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="8679b-105">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="8679b-106">Mithilfe der Paket-Abhängigkeits</span><span class="sxs-lookup"><span data-stu-id="8679b-106">Using Paket</span></span>

<span data-ttu-id="8679b-107">Bei Verwendung von [Paket-Abhängigkeits](https://fsprojects.github.io/Paket/) als Ihre Abhängigkeits-Manager können Sie mit der `paket.exe` Tool, um die Azure-Abhängigkeiten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8679b-107">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="8679b-108">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8679b-108">For example:</span></span>

    > paket add nuget WindowsAzure.Storage

<span data-ttu-id="8679b-109">Oder, bei Verwendung von [Mono](https://www.mono-project.com/) für die .NET-Entwicklung Cross-Platform:</span><span class="sxs-lookup"><span data-stu-id="8679b-109">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

    > mono paket.exe add nuget WindowsAzure.Storage

<span data-ttu-id="8679b-110">Hiermit wird `WindowsAzure.Storage` zu Ihren paketabhängigkeiten für das Projekt im aktuellen Verzeichnis, Ändern der `paket.dependencies` Datei, und Laden Sie das Paket.</span><span class="sxs-lookup"><span data-stu-id="8679b-110">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="8679b-111">Wenn Sie Abhängigkeiten bereits eingerichtet haben, oder Arbeiten mit einem Projekt, in denen Abhängigkeiten von anderen Entwicklern wurden eingerichtet sind, können zu beheben und installieren Sie die Abhängigkeiten lokal wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8679b-111">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > paket install

<span data-ttu-id="8679b-112">Oder, für die Mono-Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="8679b-112">Or, for Mono development:</span></span>

    > mono paket.exe install

<span data-ttu-id="8679b-113">Sie können alle Ihre paketabhängigkeiten auf die neueste Version wie folgt aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="8679b-113">You can update all your package dependencies to the latest version like this:</span></span>

    > paket update

<span data-ttu-id="8679b-114">Oder, für die Mono-Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="8679b-114">Or, for Mono development:</span></span>

    > mono paket.exe update

## <a name="using-nuget"></a><span data-ttu-id="8679b-115">Mithilfe von Nuget</span><span class="sxs-lookup"><span data-stu-id="8679b-115">Using Nuget</span></span>

<span data-ttu-id="8679b-116">Bei Verwendung von [NuGet](https://www.nuget.org/) als Ihre Abhängigkeits-Manager können Sie mit der `nuget.exe` Tool, um die Azure-Abhängigkeiten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8679b-116">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="8679b-117">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8679b-117">For example:</span></span>

    > nuget install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="8679b-118">Oder, für die Mono-Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="8679b-118">Or, for Mono development:</span></span>

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="8679b-119">Hiermit wird `WindowsAzure.Storage` der Gruppe der paketabhängigkeiten für das Projekt in das aktuelle Verzeichnis und das Herunterladen des Pakets.</span><span class="sxs-lookup"><span data-stu-id="8679b-119">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="8679b-120">Wenn Sie Abhängigkeiten bereits eingerichtet haben, oder Arbeiten mit einem Projekt, in denen Abhängigkeiten von anderen Entwicklern wurden eingerichtet sind, können zu beheben und installieren Sie die Abhängigkeiten lokal wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8679b-120">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > nuget restore 

<span data-ttu-id="8679b-121">Oder, für die Mono-Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="8679b-121">Or, for Mono development:</span></span>

    > mono nuget.exe restore

<span data-ttu-id="8679b-122">Sie können alle Ihre paketabhängigkeiten auf die neueste Version wie folgt aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="8679b-122">You can update all your package dependencies to the latest version like this:</span></span>

    > nuget update

<span data-ttu-id="8679b-123">Oder, für die Mono-Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="8679b-123">Or, for Mono development:</span></span>

    > mono nuget.exe update

## <a name="referencing-assemblies"></a><span data-ttu-id="8679b-124">Referenzierende Assemblys</span><span class="sxs-lookup"><span data-stu-id="8679b-124">Referencing Assemblies</span></span>

<span data-ttu-id="8679b-125">Um verwenden Ihre Pakete in Ihre F# Skript müssen Sie auf die Assemblys enthalten, die in den Paketen, die mit einem `#r` Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="8679b-125">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="8679b-126">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8679b-126">For example:</span></span>

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

<span data-ttu-id="8679b-127">Wie Sie sehen können, müssen Sie geben den relativen Pfad der DLL und der vollständige Name der DLL, der genau identisch mit den Paketnamen möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="8679b-127">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="8679b-128">Der Pfad wird eine Framework-Version und ggf. eine Versionsnummer des Pakets enthalten.</span><span class="sxs-lookup"><span data-stu-id="8679b-128">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="8679b-129">Um alle installierten Assemblys zu suchen, können Sie etwa wie folgt in einer Windows-Befehlszeile verwenden:</span><span class="sxs-lookup"><span data-stu-id="8679b-129">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

<span data-ttu-id="8679b-130">Oder in einer Unix-Shell, dann etwa wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8679b-130">Or in a Unix shell, something like this:</span></span>

    > find packages/WindowsAzure.Storage -name "*.dll"

<span data-ttu-id="8679b-131">Dadurch erhalten die Pfade zu den installierten Assemblys Sie.</span><span class="sxs-lookup"><span data-stu-id="8679b-131">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="8679b-132">Von dort aus können Sie den richtigen Pfad für Ihre Frameworkversion auswählen.</span><span class="sxs-lookup"><span data-stu-id="8679b-132">From there, you can select the correct path for your framework version.</span></span>
