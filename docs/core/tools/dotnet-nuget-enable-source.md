---
title: Befehl „dotnet nuget enable source“
description: Mit dem Befehl „dotnet nuget enable source“ wird eine vorhandene Quelle in Ihren NuGet-Konfigurationsdateien aktiviert.
ms.date: 03/20/2020
ms.openlocfilehash: 38fb5917361bd7952fef9c31ed897fb81f005155
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463561"
---
# <a name="dotnet-nuget-enable-source"></a><span data-ttu-id="c331f-103">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="c331f-103">dotnet nuget enable source</span></span>

<span data-ttu-id="c331f-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.1.200 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="c331f-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c331f-105">name</span><span class="sxs-lookup"><span data-stu-id="c331f-105">Name</span></span>

<span data-ttu-id="c331f-106">`dotnet nuget enable source`: Aktivieren einer NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="c331f-106">`dotnet nuget enable source` - Enable a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c331f-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c331f-107">Synopsis</span></span>

```dotnetcli
dotnet nuget enable source <NAME> [--configfile <FILE>]

dotnet nuget enable source -h|--help
```

## <a name="description"></a><span data-ttu-id="c331f-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c331f-108">Description</span></span>

<span data-ttu-id="c331f-109">Mit dem Befehl `dotnet nuget enable source` wird eine vorhandene Quelle in Ihren NuGet-Konfigurationsdateien aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c331f-109">The `dotnet nuget enable source` command enables an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="c331f-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="c331f-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="c331f-111">Name der Quelle.</span><span class="sxs-lookup"><span data-stu-id="c331f-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="c331f-112">Optionen</span><span class="sxs-lookup"><span data-stu-id="c331f-112">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="c331f-113">Die NuGet-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c331f-113">The NuGet configuration file.</span></span> <span data-ttu-id="c331f-114">Sofern angegeben, werden nur die Einstellungen aus dieser Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="c331f-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="c331f-115">Falls nicht angegeben, wird die Hierarchie der Konfigurationsdateien aus dem aktuellen Verzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="c331f-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="c331f-116">Weitere Informationen finden Sie unter [Gängige NuGet-Konfigurationen](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="c331f-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="c331f-117">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c331f-117">Examples</span></span>

- <span data-ttu-id="c331f-118">Aktivieren einer Quelle mit dem Namen `mySource`:</span><span class="sxs-lookup"><span data-stu-id="c331f-118">Enable a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget enable source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="c331f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c331f-119">See also</span></span>

- [<span data-ttu-id="c331f-120">Paketquellenabschnitte in NuGet.config-Dateien</span><span class="sxs-lookup"><span data-stu-id="c331f-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="c331f-121">Befehl „sources“ (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="c331f-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
