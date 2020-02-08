---
title: Konfigurationseinstellungen für das Threading
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Threading für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 68b8e93ca6ec3f708a7a627307655ada1955500a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789855"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="37d42-103">Laufzeitkonfigurationsoptionen für das Threading</span><span class="sxs-lookup"><span data-stu-id="37d42-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="37d42-104">CPU-Gruppen</span><span class="sxs-lookup"><span data-stu-id="37d42-104">CPU groups</span></span>

- <span data-ttu-id="37d42-105">Hiermit wird konfiguriert, ob Threads automatisch über CPU-Gruppen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="37d42-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="37d42-106">Standard: Deaktiviert (`0`)</span><span class="sxs-lookup"><span data-stu-id="37d42-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="37d42-107">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="37d42-107">Setting name</span></span> | <span data-ttu-id="37d42-108">Werte</span><span class="sxs-lookup"><span data-stu-id="37d42-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="37d42-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="37d42-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="37d42-110">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="37d42-110">N/A</span></span> | <span data-ttu-id="37d42-111">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="37d42-111">N/A</span></span> |
| <span data-ttu-id="37d42-112">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="37d42-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="37d42-113">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="37d42-113">`0` - disabled</span></span><br/><span data-ttu-id="37d42-114">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="37d42-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="37d42-115">Mindestanzahl an Threads</span><span class="sxs-lookup"><span data-stu-id="37d42-115">Minimum threads</span></span>

- <span data-ttu-id="37d42-116">Gibt die Mindestanzahl an Threads für den Arbeitsthreadpool an.</span><span class="sxs-lookup"><span data-stu-id="37d42-116">Specifies the minimum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="37d42-117">Entspricht der <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>-Methode</span><span class="sxs-lookup"><span data-stu-id="37d42-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="37d42-118">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="37d42-118">Setting name</span></span> | <span data-ttu-id="37d42-119">Werte</span><span class="sxs-lookup"><span data-stu-id="37d42-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="37d42-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="37d42-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="37d42-121">Eine ganze Zahl, die die Mindestanzahl an Threads angibt</span><span class="sxs-lookup"><span data-stu-id="37d42-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="37d42-122">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="37d42-122">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="37d42-123">Eine ganze Zahl, die die Mindestanzahl an Threads angibt</span><span class="sxs-lookup"><span data-stu-id="37d42-123">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="37d42-124">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="37d42-124">**Environment variable**</span></span> | <span data-ttu-id="37d42-125">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="37d42-125">N/A</span></span> | <span data-ttu-id="37d42-126">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="37d42-126">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="37d42-127">Beispiele</span><span class="sxs-lookup"><span data-stu-id="37d42-127">Examples</span></span>

<span data-ttu-id="37d42-128">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="37d42-128">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="37d42-129">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="37d42-129">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="37d42-130">Maximale Anzahl an Threads</span><span class="sxs-lookup"><span data-stu-id="37d42-130">Maximum threads</span></span>

- <span data-ttu-id="37d42-131">Gibt die maximale Anzahl an Threads für den Arbeitsthreadpool an.</span><span class="sxs-lookup"><span data-stu-id="37d42-131">Specifies the maximum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="37d42-132">Entspricht der <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>-Methode</span><span class="sxs-lookup"><span data-stu-id="37d42-132">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="37d42-133">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="37d42-133">Setting name</span></span> | <span data-ttu-id="37d42-134">Werte</span><span class="sxs-lookup"><span data-stu-id="37d42-134">Values</span></span> |
| - | - | - |
| <span data-ttu-id="37d42-135">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="37d42-135">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="37d42-136">Eine ganze Zahl, die die maximale Anzahl der Threads darstellt</span><span class="sxs-lookup"><span data-stu-id="37d42-136">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="37d42-137">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="37d42-137">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="37d42-138">Eine ganze Zahl, die die maximale Anzahl der Threads darstellt</span><span class="sxs-lookup"><span data-stu-id="37d42-138">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="37d42-139">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="37d42-139">**Environment variable**</span></span> | <span data-ttu-id="37d42-140">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="37d42-140">N/A</span></span> | <span data-ttu-id="37d42-141">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="37d42-141">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="37d42-142">Beispiele</span><span class="sxs-lookup"><span data-stu-id="37d42-142">Examples</span></span>

<span data-ttu-id="37d42-143">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="37d42-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="37d42-144">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="37d42-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
