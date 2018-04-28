---
title: dotnet nuget locals-Befehl – .NET Core-CLI
description: Der dotnet nuget locals-Befehl löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder Ordner mit globalen Paketen auf dem Computer, bzw. listet diese Ressourcen auf.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 1dfa50ff0971a82b3f6aafd86492fd57d8cf6a82
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="28ba6-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="28ba6-103">dotnet nuget locals</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="28ba6-104">name</span><span class="sxs-lookup"><span data-stu-id="28ba6-104">Name</span></span>

<span data-ttu-id="28ba6-105">`dotnet nuget locals`: Löscht lokale NuGet-Ressourcen oder listet diese auf.</span><span class="sxs-lookup"><span data-stu-id="28ba6-105">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="28ba6-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="28ba6-106">Synopsis</span></span>

`dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="28ba6-107">description</span><span class="sxs-lookup"><span data-stu-id="28ba6-107">Description</span></span>

<span data-ttu-id="28ba6-108">Der `dotnet nuget locals`-Befehl löscht lokale NuGet-Ressourcen im http-Anforderungscache, temporären Cache oder Ordner mit globalen Paketen auf dem Computer bzw. listet diese Ressourcen auf.</span><span class="sxs-lookup"><span data-stu-id="28ba6-108">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="28ba6-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="28ba6-109">Arguments</span></span>

`CACHE_LOCATION`

<span data-ttu-id="28ba6-110">Einer der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="28ba6-110">One of the following values:</span></span>

* <span data-ttu-id="28ba6-111">`all`: gibt an, dass der angegebene Vorgang auf alle Cachetypen angewendet wird: Auf den http-Anforderungscache, den Cache für globale Pakete und den temporären Cache.</span><span class="sxs-lookup"><span data-stu-id="28ba6-111">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
* <span data-ttu-id="28ba6-112">`http-cache`: gibt an, dass der angegebene Vorgang nur auf den http-Anforderungscache angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="28ba6-112">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="28ba6-113">Die anderen Cachespeicherorte sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="28ba6-113">The other cache locations are not affected.</span></span>
* <span data-ttu-id="28ba6-114">`global-packages`: gibt an, dass der angegebene Vorgang nur auf den Cache für globale Pakete angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="28ba6-114">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="28ba6-115">Die anderen Cachespeicherorte sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="28ba6-115">The other cache locations are not affected.</span></span>
* <span data-ttu-id="28ba6-116">`temp`: gibt an, dass der angegebene Vorgang nur auf den temporären Cache angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="28ba6-116">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="28ba6-117">Die anderen Cachespeicherorte sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="28ba6-117">The other cache locations are not affected.</span></span>

## <a name="options"></a><span data-ttu-id="28ba6-118">Optionen</span><span class="sxs-lookup"><span data-stu-id="28ba6-118">Options</span></span>

`-h|--help`

<span data-ttu-id="28ba6-119">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="28ba6-119">Prints out a short help for the command.</span></span>

`-c|--clear`

<span data-ttu-id="28ba6-120">Die clear-Option führt einen Löschvorgang für den angegebenen Cachetyp aus.</span><span class="sxs-lookup"><span data-stu-id="28ba6-120">The clear option performs a clear operation on the specified cache type.</span></span> <span data-ttu-id="28ba6-121">Die Inhalte der Cacheverzeichnisse werden rekursiv gelöscht.</span><span class="sxs-lookup"><span data-stu-id="28ba6-121">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="28ba6-122">Der ausführende Benutzer (bzw. die Gruppe) muss über Berechtigungen für die Dateien in den Cacheverzeichnissen verfügen.</span><span class="sxs-lookup"><span data-stu-id="28ba6-122">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="28ba6-123">Andernfalls wird ein Fehler angezeigt, der die Dateien/Ordner angibt, die nicht gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="28ba6-123">If not, an error is displayed indicating the files/folders which were not cleared.</span></span>

`-l|--list`

<span data-ttu-id="28ba6-124">Die list-Option wird verwendet, um den Speicherort des angegebenen Cachetyps anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="28ba6-124">The list option is used to display the location of the specified cache type.</span></span> 

`--force-english-output`

<span data-ttu-id="28ba6-125">Erzwingt, dass die Befehlszeilenausgabe auf Englisch ist.</span><span class="sxs-lookup"><span data-stu-id="28ba6-125">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="28ba6-126">Beispiele</span><span class="sxs-lookup"><span data-stu-id="28ba6-126">Examples</span></span>

<span data-ttu-id="28ba6-127">Zeigt die Pfade aller lokalen Cacheverzeichnisse an (http-Cacheverzeichnis, Cacheverzeichnis für globale Pakete und temporäres Cacheverzeichnis):</span><span class="sxs-lookup"><span data-stu-id="28ba6-127">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals –l all`

<span data-ttu-id="28ba6-128">Zeigt den Pfad für das lokale http-Cacheverzeichnis an:</span><span class="sxs-lookup"><span data-stu-id="28ba6-128">Displays the path for the local http-cache directory:</span></span>

`dotnet nuget locals --list http-cache`

<span data-ttu-id="28ba6-129">Löscht alle Dateien aus allen lokalen Cacheverzeichnissen (http-Cacheverzeichnis, Cacheverzeichnis für globale Pakete und temporäres Cacheverzeichnis):</span><span class="sxs-lookup"><span data-stu-id="28ba6-129">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals --clear all`

<span data-ttu-id="28ba6-130">Löscht alle Dateien im lokalen Cacheverzeichnis für globale Pakete:</span><span class="sxs-lookup"><span data-stu-id="28ba6-130">Clears all files in local global-packages cache directory:</span></span>

`dotnet nuget locals -c global-packages`

<span data-ttu-id="28ba6-131">Löscht alle Dateien im lokalen temporären Cacheverzeichnis:</span><span class="sxs-lookup"><span data-stu-id="28ba6-131">Clears all files in local temporary cache directory:</span></span>

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a><span data-ttu-id="28ba6-132">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="28ba6-132">Troubleshooting</span></span>

<span data-ttu-id="28ba6-133">Weitere Informationen zu häufig auftretenden Problemen und Fehlern bei der Verwendung des `dotnet nuget locals`-Befehls finden Sie unter [Managing the NuGet cache (Verwalten des NuGet-Caches)](/nuget/consume-packages/managing-the-nuget-cache).</span><span class="sxs-lookup"><span data-stu-id="28ba6-133">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>