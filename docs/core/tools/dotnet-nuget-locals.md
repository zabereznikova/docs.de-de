---
title: Befehl „dotnet nuget locals“
description: Der dotnet nuget locals-Befehl löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder Ordner mit globalen Paketen auf dem Computer, bzw. listet diese Ressourcen auf.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: 5b421b5058528a93c7be58eef2932937cc9cc12d
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463531"
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="83ac9-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="83ac9-103">dotnet nuget locals</span></span>

<span data-ttu-id="83ac9-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="83ac9-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="83ac9-105">Name</span><span class="sxs-lookup"><span data-stu-id="83ac9-105">Name</span></span>

<span data-ttu-id="83ac9-106">`dotnet nuget locals`: Löscht lokale NuGet-Ressourcen oder listet diese auf.</span><span class="sxs-lookup"><span data-stu-id="83ac9-106">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="83ac9-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="83ac9-107">Synopsis</span></span>

```dotnetcli
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]

dotnet nuget locals -h|--help
```

## <a name="description"></a><span data-ttu-id="83ac9-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="83ac9-108">Description</span></span>

<span data-ttu-id="83ac9-109">Der `dotnet nuget locals`-Befehl löscht lokale NuGet-Ressourcen im http-Anforderungscache, temporären Cache oder Ordner mit globalen Paketen auf dem Computer bzw. listet diese Ressourcen auf.</span><span class="sxs-lookup"><span data-stu-id="83ac9-109">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="83ac9-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="83ac9-110">Arguments</span></span>

- **`CACHE_LOCATION`**

  <span data-ttu-id="83ac9-111">Der aufzulistende oder zu löschende Cachespeicherort.</span><span class="sxs-lookup"><span data-stu-id="83ac9-111">The cache location to list or clear.</span></span> <span data-ttu-id="83ac9-112">Einer der folgenden Werte wird akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="83ac9-112">It accepts one of the following values:</span></span>

  * <span data-ttu-id="83ac9-113">`all`: gibt an, dass der angegebene Vorgang auf alle Cachetypen angewendet wird: Auf den http-Anforderungscache, den Cache für globale Pakete und den temporären Cache.</span><span class="sxs-lookup"><span data-stu-id="83ac9-113">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
  * <span data-ttu-id="83ac9-114">`http-cache`: gibt an, dass der angegebene Vorgang nur auf den http-Anforderungscache angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="83ac9-114">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="83ac9-115">Die anderen Cachespeicherorte sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="83ac9-115">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="83ac9-116">`global-packages`: gibt an, dass der angegebene Vorgang nur auf den Cache für globale Pakete angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="83ac9-116">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="83ac9-117">Die anderen Cachespeicherorte sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="83ac9-117">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="83ac9-118">`temp`: gibt an, dass der angegebene Vorgang nur auf den temporären Cache angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="83ac9-118">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="83ac9-119">Die anderen Cachespeicherorte sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="83ac9-119">The other cache locations aren't affected.</span></span>

## <a name="options"></a><span data-ttu-id="83ac9-120">Optionen</span><span class="sxs-lookup"><span data-stu-id="83ac9-120">Options</span></span>

- **`--force-english-output`**

  <span data-ttu-id="83ac9-121">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="83ac9-121">Forces the application to run using an invariant, English-based culture.</span></span>

- **`-h|--help`**

  <span data-ttu-id="83ac9-122">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="83ac9-122">Prints out a short help for the command.</span></span>

- **`-c|--clear`**

  <span data-ttu-id="83ac9-123">Die Option „clear“ führt einen Löschvorgang für den angegebenen Cachetyp aus.</span><span class="sxs-lookup"><span data-stu-id="83ac9-123">The clear option executes a clear operation on the specified cache type.</span></span> <span data-ttu-id="83ac9-124">Die Inhalte der Cacheverzeichnisse werden rekursiv gelöscht.</span><span class="sxs-lookup"><span data-stu-id="83ac9-124">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="83ac9-125">Der ausführende Benutzer (bzw. die Gruppe) muss über Berechtigungen für die Dateien in den Cacheverzeichnissen verfügen.</span><span class="sxs-lookup"><span data-stu-id="83ac9-125">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="83ac9-126">Andernfalls wird ein Fehler angezeigt, der die Dateien/Ordner angibt, die nicht gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="83ac9-126">If not, an error is displayed indicating the files/folders that weren't cleared.</span></span>

- **`-l|--list`**

  <span data-ttu-id="83ac9-127">Die list-Option wird verwendet, um den Speicherort des angegebenen Cachetyps anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="83ac9-127">The list option is used to display the location of the specified cache type.</span></span>

## <a name="examples"></a><span data-ttu-id="83ac9-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="83ac9-128">Examples</span></span>

- <span data-ttu-id="83ac9-129">Zeigt die Pfade aller lokalen Cacheverzeichnisse an (http-Cacheverzeichnis, Cacheverzeichnis für globale Pakete und temporäres Cacheverzeichnis):</span><span class="sxs-lookup"><span data-stu-id="83ac9-129">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```dotnetcli
  dotnet nuget locals all –l
  ```

- <span data-ttu-id="83ac9-130">Zeigt den Pfad für das lokale http-Cacheverzeichnis an:</span><span class="sxs-lookup"><span data-stu-id="83ac9-130">Displays the path for the local http-cache directory:</span></span>

  ```dotnetcli
  dotnet nuget locals http-cache --list
  ```

- <span data-ttu-id="83ac9-131">Löscht alle Dateien aus allen lokalen Cacheverzeichnissen (http-Cacheverzeichnis, Cacheverzeichnis für globale Pakete und temporäres Cacheverzeichnis):</span><span class="sxs-lookup"><span data-stu-id="83ac9-131">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```dotnetcli
  dotnet nuget locals all --clear
  ```

- <span data-ttu-id="83ac9-132">Löscht alle Dateien im lokalen Cacheverzeichnis für globale Pakete:</span><span class="sxs-lookup"><span data-stu-id="83ac9-132">Clears all files in local global-packages cache directory:</span></span>

  ```dotnetcli
  dotnet nuget locals global-packages -c
  ```

- <span data-ttu-id="83ac9-133">Löscht alle Dateien im lokalen temporären Cacheverzeichnis:</span><span class="sxs-lookup"><span data-stu-id="83ac9-133">Clears all files in local temporary cache directory:</span></span>

  ```dotnetcli
  dotnet nuget locals temp -c
  ```

## <a name="troubleshooting"></a><span data-ttu-id="83ac9-134">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="83ac9-134">Troubleshooting</span></span>

<span data-ttu-id="83ac9-135">Weitere Informationen zu häufig auftretenden Problemen und Fehlern bei der Verwendung des `dotnet nuget locals`-Befehls finden Sie unter [Managing the NuGet cache (Verwalten des NuGet-Caches)](/nuget/consume-packages/managing-the-nuget-cache).</span><span class="sxs-lookup"><span data-stu-id="83ac9-135">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>
