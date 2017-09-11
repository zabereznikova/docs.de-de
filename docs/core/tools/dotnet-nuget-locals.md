---
title: "dotnet-nuget-locals-Befehl – .NET Core-CLI"
description: "Der dotnet-nuget-locals-Befehl löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder Ordner mit globalen Paketen auf dem Computer, bzw. listet diese Ressourcen auf."
keywords: dotnet-nuget-locals, CLI, CLI-Befehl, .NET Core
author: karann-msft
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8440229e-317e-4dc1-9463-cba5fdb12c3b
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2c9ea7b3b7c61b347cb7c56254773290f04a0cd6
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-nuget-locals"></a><span data-ttu-id="ffe30-104">dotnet-nuget locals</span><span class="sxs-lookup"><span data-stu-id="ffe30-104">dotnet-nuget locals</span></span>

## <a name="name"></a><span data-ttu-id="ffe30-105">Name</span><span class="sxs-lookup"><span data-stu-id="ffe30-105">Name</span></span>

<span data-ttu-id="ffe30-106">`dotnet-nuget locals`: Löscht lokale NuGet-Ressourcen oder listet diese auf.</span><span class="sxs-lookup"><span data-stu-id="ffe30-106">`dotnet-nuget locals` - Clears or lists local NuGet resources.</span></span> 

## <a name="synopsis"></a><span data-ttu-id="ffe30-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ffe30-107">Synopsis</span></span>

`dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="ffe30-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ffe30-108">Description</span></span>

<span data-ttu-id="ffe30-109">Der `dotnet nuget locals`-Befehl löscht lokale NuGet-Ressourcen im http-Anforderungscache, temporären Cache oder Ordner mit globalen Paketen auf dem Computer bzw. listet diese Ressourcen auf.</span><span class="sxs-lookup"><span data-stu-id="ffe30-109">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="ffe30-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="ffe30-110">Arguments</span></span>

`CACHE_LOCATION`

<span data-ttu-id="ffe30-111">Einer der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="ffe30-111">One of the following values:</span></span>

`all`

<span data-ttu-id="ffe30-112">Gibt an, dass der angegebene Vorgang auf alle Cachetypen angewendet wird: Auf den http-Anforderungscache, den Cache für globale Pakete und den temporären Cache.</span><span class="sxs-lookup"><span data-stu-id="ffe30-112">Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>

`http-cache`

<span data-ttu-id="ffe30-113">Gibt an, dass der angegebene Vorgang nur auf den http-Anforderungscache angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ffe30-113">Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="ffe30-114">Die anderen Cachespeicherorte sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="ffe30-114">The other cache locations are not affected.</span></span>

`global-packages`

<span data-ttu-id="ffe30-115">Gibt an, dass der angegebene Vorgang nur auf den Cache für globale Pakete angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ffe30-115">Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="ffe30-116">Die anderen Cachespeicherorte sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="ffe30-116">The other cache locations are not affected.</span></span>

`temp`

<span data-ttu-id="ffe30-117">Gibt an, dass der angegebene Vorgang nur auf den temporären Cache angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ffe30-117">Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="ffe30-118">Die anderen Cachespeicherorte sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="ffe30-118">The other cache locations are not affected.</span></span>

## <a name="options"></a><span data-ttu-id="ffe30-119">Optionen</span><span class="sxs-lookup"><span data-stu-id="ffe30-119">Options</span></span>

`-h|--help`

<span data-ttu-id="ffe30-120">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="ffe30-120">Prints out a short help for the command.</span></span>  

`-c|--clear`

<span data-ttu-id="ffe30-121">Die clear-Option führt einen Löschvorgang für den angegebenen Cachetyp aus.</span><span class="sxs-lookup"><span data-stu-id="ffe30-121">The clear option performs a clear operation on the specified cache type.</span></span> <span data-ttu-id="ffe30-122">Die Inhalte der Cacheverzeichnisse werden rekursiv gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ffe30-122">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="ffe30-123">Der ausführende Benutzer (bzw. die Gruppe) muss über Berechtigungen für die Dateien in den Cacheverzeichnissen verfügen.</span><span class="sxs-lookup"><span data-stu-id="ffe30-123">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="ffe30-124">Andernfalls wird ein Fehler angezeigt, der die Dateien/Ordner angibt, die nicht gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="ffe30-124">If not, an error is displayed indicating the files/folders which were not cleared.</span></span>

`-l|--list`

<span data-ttu-id="ffe30-125">Die list-Option wird verwendet, um den Speicherort des angegebenen Cachetyps anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ffe30-125">The list option is used to display the location of the specified cache type.</span></span> 

`--force-english-output`

<span data-ttu-id="ffe30-126">Erzwingt, dass die Befehlszeilenausgabe auf Englisch ist.</span><span class="sxs-lookup"><span data-stu-id="ffe30-126">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="ffe30-127">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ffe30-127">Examples</span></span>

<span data-ttu-id="ffe30-128">Zeigt die Pfade aller lokalen Cacheverzeichnisse an (http-Cacheverzeichnis, Cacheverzeichnis für globale Pakete und temporäres Cacheverzeichnis):</span><span class="sxs-lookup"><span data-stu-id="ffe30-128">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals –l all`

<span data-ttu-id="ffe30-129">Zeigt den Pfad für das lokale http-Cacheverzeichnis an:</span><span class="sxs-lookup"><span data-stu-id="ffe30-129">Displays the path for the local http-cache directory:</span></span>

`dotnet nuget locals --list http-cache`

<span data-ttu-id="ffe30-130">Löscht alle Dateien aus allen lokalen Cacheverzeichnissen (http-Cacheverzeichnis, Cacheverzeichnis für globale Pakete und temporäres Cacheverzeichnis):</span><span class="sxs-lookup"><span data-stu-id="ffe30-130">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals --clear all`

<span data-ttu-id="ffe30-131">Löscht alle Dateien im lokalen Cacheverzeichnis für globale Pakete:</span><span class="sxs-lookup"><span data-stu-id="ffe30-131">Clears all files in local global-packages cache directory:</span></span>

`dotnet nuget locals -c global-packages`

<span data-ttu-id="ffe30-132">Löscht alle Dateien im lokalen temporären Cacheverzeichnis:</span><span class="sxs-lookup"><span data-stu-id="ffe30-132">Clears all files in local temporary cache directory:</span></span>

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a><span data-ttu-id="ffe30-133">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="ffe30-133">Troubleshooting</span></span>

<span data-ttu-id="ffe30-134">Weitere Informationen zu häufig auftretenden Problemen und Fehlern bei der Verwendung des `dotnet nuget locals`-Befehls finden Sie unter [Managing the NuGet cache (Verwalten des NuGet-Caches)](/nuget/consume-packages/managing-the-nuget-cache).</span><span class="sxs-lookup"><span data-stu-id="ffe30-134">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>

