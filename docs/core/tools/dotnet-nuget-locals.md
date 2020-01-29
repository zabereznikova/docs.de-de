---
title: Befehl „dotnet nuget locals“
description: Der dotnet nuget locals-Befehl löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder Ordner mit globalen Paketen auf dem Computer, bzw. listet diese Ressourcen auf.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: b57c127650555e412af08df6656fb62d75c8ed7c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734080"
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="4e54e-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="4e54e-103">dotnet nuget locals</span></span>

<span data-ttu-id="4e54e-104">**Dieser Artikel gilt für:** ✔️ .NET Core 1.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="4e54e-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="4e54e-105">name</span><span class="sxs-lookup"><span data-stu-id="4e54e-105">Name</span></span>

<span data-ttu-id="4e54e-106">`dotnet nuget locals`: Löscht lokale NuGet-Ressourcen oder listet diese auf.</span><span class="sxs-lookup"><span data-stu-id="4e54e-106">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4e54e-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="4e54e-107">Synopsis</span></span>

```dotnetcli
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a><span data-ttu-id="4e54e-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e54e-108">Description</span></span>

<span data-ttu-id="4e54e-109">Der `dotnet nuget locals`-Befehl löscht lokale NuGet-Ressourcen im http-Anforderungscache, temporären Cache oder Ordner mit globalen Paketen auf dem Computer bzw. listet diese Ressourcen auf.</span><span class="sxs-lookup"><span data-stu-id="4e54e-109">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="4e54e-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="4e54e-110">Arguments</span></span>

* **`CACHE_LOCATION`**

  <span data-ttu-id="4e54e-111">Der aufzulistende oder zu löschende Cachespeicherort.</span><span class="sxs-lookup"><span data-stu-id="4e54e-111">The cache location to list or clear.</span></span> <span data-ttu-id="4e54e-112">Einer der folgenden Werte wird akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="4e54e-112">It accepts one of the following values:</span></span>

  * <span data-ttu-id="4e54e-113">`all`: gibt an, dass der angegebene Vorgang auf alle Cachetypen angewendet wird: Auf den http-Anforderungscache, den Cache für globale Pakete und den temporären Cache.</span><span class="sxs-lookup"><span data-stu-id="4e54e-113">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
  * <span data-ttu-id="4e54e-114">`http-cache`: gibt an, dass der angegebene Vorgang nur auf den http-Anforderungscache angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4e54e-114">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="4e54e-115">Die anderen Cachespeicherorte sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="4e54e-115">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="4e54e-116">`global-packages`: gibt an, dass der angegebene Vorgang nur auf den Cache für globale Pakete angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4e54e-116">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="4e54e-117">Die anderen Cachespeicherorte sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="4e54e-117">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="4e54e-118">`temp`: gibt an, dass der angegebene Vorgang nur auf den temporären Cache angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4e54e-118">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="4e54e-119">Die anderen Cachespeicherorte sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="4e54e-119">The other cache locations aren't affected.</span></span>

## <a name="options"></a><span data-ttu-id="4e54e-120">Optionen</span><span class="sxs-lookup"><span data-stu-id="4e54e-120">Options</span></span>

* **`--force-english-output`**

  <span data-ttu-id="4e54e-121">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="4e54e-121">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="4e54e-122">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="4e54e-122">Prints out a short help for the command.</span></span>

* **`-c|--clear`**

  <span data-ttu-id="4e54e-123">Die Option „clear“ führt einen Löschvorgang für den angegebenen Cachetyp aus.</span><span class="sxs-lookup"><span data-stu-id="4e54e-123">The clear option executes a clear operation on the specified cache type.</span></span> <span data-ttu-id="4e54e-124">Die Inhalte der Cacheverzeichnisse werden rekursiv gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4e54e-124">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="4e54e-125">Der ausführende Benutzer (bzw. die Gruppe) muss über Berechtigungen für die Dateien in den Cacheverzeichnissen verfügen.</span><span class="sxs-lookup"><span data-stu-id="4e54e-125">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="4e54e-126">Andernfalls wird ein Fehler angezeigt, der die Dateien/Ordner angibt, die nicht gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="4e54e-126">If not, an error is displayed indicating the files/folders that weren't cleared.</span></span>

* **`-l|--list`**

  <span data-ttu-id="4e54e-127">Die list-Option wird verwendet, um den Speicherort des angegebenen Cachetyps anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4e54e-127">The list option is used to display the location of the specified cache type.</span></span>

## <a name="examples"></a><span data-ttu-id="4e54e-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="4e54e-128">Examples</span></span>

* <span data-ttu-id="4e54e-129">Zeigt die Pfade aller lokalen Cacheverzeichnisse an (http-Cacheverzeichnis, Cacheverzeichnis für globale Pakete und temporäres Cacheverzeichnis):</span><span class="sxs-lookup"><span data-stu-id="4e54e-129">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```dotnetcli
  dotnet nuget locals all –l
  ```

* <span data-ttu-id="4e54e-130">Zeigt den Pfad für das lokale http-Cacheverzeichnis an:</span><span class="sxs-lookup"><span data-stu-id="4e54e-130">Displays the path for the local http-cache directory:</span></span>

  ```dotnetcli
  dotnet nuget locals http-cache --list
  ```

* <span data-ttu-id="4e54e-131">Löscht alle Dateien aus allen lokalen Cacheverzeichnissen (http-Cacheverzeichnis, Cacheverzeichnis für globale Pakete und temporäres Cacheverzeichnis):</span><span class="sxs-lookup"><span data-stu-id="4e54e-131">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```dotnetcli
  dotnet nuget locals all --clear
  ```

* <span data-ttu-id="4e54e-132">Löscht alle Dateien im lokalen Cacheverzeichnis für globale Pakete:</span><span class="sxs-lookup"><span data-stu-id="4e54e-132">Clears all files in local global-packages cache directory:</span></span>

  ```dotnetcli
  dotnet nuget locals global-packages -c
  ```

* <span data-ttu-id="4e54e-133">Löscht alle Dateien im lokalen temporären Cacheverzeichnis:</span><span class="sxs-lookup"><span data-stu-id="4e54e-133">Clears all files in local temporary cache directory:</span></span>

  ```dotnetcli
  dotnet nuget locals temp -c
  ```

## <a name="troubleshooting"></a><span data-ttu-id="4e54e-134">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="4e54e-134">Troubleshooting</span></span>

<span data-ttu-id="4e54e-135">Weitere Informationen zu häufig auftretenden Problemen und Fehlern bei der Verwendung des `dotnet nuget locals`-Befehls finden Sie unter [Managing the NuGet cache (Verwalten des NuGet-Caches)](/nuget/consume-packages/managing-the-nuget-cache).</span><span class="sxs-lookup"><span data-stu-id="4e54e-135">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>
