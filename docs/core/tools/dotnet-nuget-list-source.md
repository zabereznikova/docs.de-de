---
title: Befehl „dotnet nuget list source“
description: Mit dem Befehl „dotnet nuget list source“ werden alle vorhandenen Quellen aus Ihren NuGet-Konfigurationsdateien aufgelistet.
ms.date: 03/20/2020
ms.openlocfilehash: 8b14413949bd60ddeed977d19eec9bb99982da70
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463544"
---
# <a name="dotnet-nuget-list-source"></a><span data-ttu-id="d9a77-103">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="d9a77-103">dotnet nuget list source</span></span>

<span data-ttu-id="d9a77-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.1.200 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="d9a77-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d9a77-105">Name</span><span class="sxs-lookup"><span data-stu-id="d9a77-105">Name</span></span>

<span data-ttu-id="d9a77-106">`dotnet nuget list source`: Auflisten aller konfigurierten NuGet-Quellen.</span><span class="sxs-lookup"><span data-stu-id="d9a77-106">`dotnet nuget list source` - Lists all configured NuGet sources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d9a77-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d9a77-107">Synopsis</span></span>

```dotnetcli
dotnet nuget list source [--format [Detailed|Short]] [--configfile <FILE>]

dotnet nuget list source -h|--help
```

## <a name="description"></a><span data-ttu-id="d9a77-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9a77-108">Description</span></span>

<span data-ttu-id="d9a77-109">Mit dem Befehl `dotnet nuget list source` werden alle vorhandenen Quellen aus Ihren NuGet-Konfigurationsdateien aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="d9a77-109">The `dotnet nuget list source` command lists all existing sources from your NuGet configuration files.</span></span>

## <a name="options"></a><span data-ttu-id="d9a77-110">Optionen</span><span class="sxs-lookup"><span data-stu-id="d9a77-110">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="d9a77-111">Die NuGet-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="d9a77-111">The NuGet configuration file.</span></span> <span data-ttu-id="d9a77-112">Sofern angegeben, werden nur die Einstellungen aus dieser Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9a77-112">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="d9a77-113">Falls nicht angegeben, wird die Hierarchie der Konfigurationsdateien aus dem aktuellen Verzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9a77-113">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="d9a77-114">Weitere Informationen finden Sie unter [Gängige NuGet-Konfigurationen](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="d9a77-114">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`--format [Detailed|Short]`**

  <span data-ttu-id="d9a77-115">Das Format der Ausgabe des Auflistungsbefehls: `Detailed` (Standardwert) und `Short`.</span><span class="sxs-lookup"><span data-stu-id="d9a77-115">The format of the list command output: `Detailed` (the default) and `Short`.</span></span>

## <a name="examples"></a><span data-ttu-id="d9a77-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d9a77-116">Examples</span></span>

- <span data-ttu-id="d9a77-117">Auflisten konfigurierter Quellen aus dem aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="d9a77-117">List configured sources from the current directory:</span></span>

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a><span data-ttu-id="d9a77-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9a77-118">See also</span></span>

- [<span data-ttu-id="d9a77-119">Paketquellenabschnitte in NuGet.config-Dateien</span><span class="sxs-lookup"><span data-stu-id="d9a77-119">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="d9a77-120">Befehl „sources“ (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="d9a77-120">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
