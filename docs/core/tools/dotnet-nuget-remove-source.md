---
title: Befehl „dotnet nuget remove source“
description: Mit dem Befehl „dotnet nuget remove source“ wird eine vorhandene Quelle aus Ihren NuGet-Konfigurationsdateien entfernt.
ms.date: 03/20/2020
ms.openlocfilehash: b259873e1885644b272136fa31414410bdfd9f27
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463493"
---
# <a name="dotnet-nuget-remove-source"></a><span data-ttu-id="1c957-103">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="1c957-103">dotnet nuget remove source</span></span>

<span data-ttu-id="1c957-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.1.200 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="1c957-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="1c957-105">Name</span><span class="sxs-lookup"><span data-stu-id="1c957-105">Name</span></span>

<span data-ttu-id="1c957-106">`dotnet nuget remove source`: Entfernen einer NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="1c957-106">`dotnet nuget remove source` - Remove a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1c957-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="1c957-107">Synopsis</span></span>

```dotnetcli
dotnet nuget remove source <NAME> [--configfile <FILE>]

dotnet nuget remove source -h|--help
```

## <a name="description"></a><span data-ttu-id="1c957-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c957-108">Description</span></span>

<span data-ttu-id="1c957-109">Mit dem Befehl `dotnet nuget remove source` wird eine vorhandene Quelle aus Ihren NuGet-Konfigurationsdateien entfernt.</span><span class="sxs-lookup"><span data-stu-id="1c957-109">The `dotnet nuget remove source` command removes an existing source from your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="1c957-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="1c957-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="1c957-111">Name der Quelle.</span><span class="sxs-lookup"><span data-stu-id="1c957-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="1c957-112">Optionen</span><span class="sxs-lookup"><span data-stu-id="1c957-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="1c957-113">Die NuGet-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="1c957-113">The NuGet configuration file.</span></span> <span data-ttu-id="1c957-114">Sofern angegeben, werden nur die Einstellungen aus dieser Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c957-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="1c957-115">Falls nicht angegeben, wird die Hierarchie der Konfigurationsdateien aus dem aktuellen Verzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c957-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="1c957-116">Weitere Informationen finden Sie unter [Gängige NuGet-Konfigurationen](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="1c957-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="1c957-117">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1c957-117">Examples</span></span>

- <span data-ttu-id="1c957-118">Entfernen einer Quelle mit dem Namen `mySource`:</span><span class="sxs-lookup"><span data-stu-id="1c957-118">Remove a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget remove source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="1c957-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c957-119">See also</span></span>

- [<span data-ttu-id="1c957-120">Paketquellenabschnitte in NuGet.config-Dateien</span><span class="sxs-lookup"><span data-stu-id="1c957-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="1c957-121">Befehl „sources“ (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="1c957-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
