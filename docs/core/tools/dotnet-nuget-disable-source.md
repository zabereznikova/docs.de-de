---
title: Befehl „dotnet nuget disable source“
description: Mit dem Befehl „dotnet nuget enable source“ wird eine vorhandene Quelle in Ihren NuGet-Konfigurationsdateien deaktiviert.
ms.date: 03/20/2020
ms.openlocfilehash: 54acb40b1944eaff347107e8f3439578ec8e0f3c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463567"
---
# <a name="dotnet-nuget-disable-source"></a><span data-ttu-id="66224-103">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="66224-103">dotnet nuget disable source</span></span>

<span data-ttu-id="66224-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.1.200 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="66224-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="66224-105">name</span><span class="sxs-lookup"><span data-stu-id="66224-105">Name</span></span>

<span data-ttu-id="66224-106">`dotnet nuget disable source`: Deaktivieren einer NuGet-Quelle.</span><span class="sxs-lookup"><span data-stu-id="66224-106">`dotnet nuget disable source` - Disable a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="66224-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="66224-107">Synopsis</span></span>

```dotnetcli
dotnet nuget disable source <NAME> [--configfile <FILE>]

dotnet nuget disable source -h|--help
```

## <a name="description"></a><span data-ttu-id="66224-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66224-108">Description</span></span>

<span data-ttu-id="66224-109">Mit dem Befehl `dotnet nuget disable source` wird eine vorhandene Quelle in Ihren NuGet-Konfigurationsdateien deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="66224-109">The `dotnet nuget disable source` command disables an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="66224-110">Argumente</span><span class="sxs-lookup"><span data-stu-id="66224-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="66224-111">Name der Quelle.</span><span class="sxs-lookup"><span data-stu-id="66224-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="66224-112">Optionen</span><span class="sxs-lookup"><span data-stu-id="66224-112">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="66224-113">Die NuGet-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="66224-113">The NuGet configuration file.</span></span> <span data-ttu-id="66224-114">Sofern angegeben, werden nur die Einstellungen aus dieser Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="66224-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="66224-115">Falls nicht angegeben, wird die Hierarchie der Konfigurationsdateien aus dem aktuellen Verzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="66224-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="66224-116">Weitere Informationen finden Sie unter [Gängige NuGet-Konfigurationen](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="66224-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="66224-117">Beispiele</span><span class="sxs-lookup"><span data-stu-id="66224-117">Examples</span></span>

- <span data-ttu-id="66224-118">Deaktivieren einer Quelle mit dem Namen `mySource`:</span><span class="sxs-lookup"><span data-stu-id="66224-118">Disable a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget disable source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="66224-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66224-119">See also</span></span>

- [<span data-ttu-id="66224-120">Paketquellenabschnitte in NuGet.config-Dateien</span><span class="sxs-lookup"><span data-stu-id="66224-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="66224-121">Befehl „sources“ (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="66224-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
