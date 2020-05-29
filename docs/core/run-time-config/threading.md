---
title: Konfigurationseinstellungen für das Threading
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Threading für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 1c7c16993a07ef95223481791153b75ab2f61533
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761927"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="3b8b7-103">Laufzeitkonfigurationsoptionen für das Threading</span><span class="sxs-lookup"><span data-stu-id="3b8b7-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="3b8b7-104">CPU-Gruppen</span><span class="sxs-lookup"><span data-stu-id="3b8b7-104">CPU groups</span></span>

- <span data-ttu-id="3b8b7-105">Hiermit wird konfiguriert, ob Threads automatisch über CPU-Gruppen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="3b8b7-106">Wenn Sie diese Einstellung weglassen, werden Threads nicht über CPU-Gruppen verteilt.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-106">If you omit this setting, threads are not distributed across CPU groups.</span></span> <span data-ttu-id="3b8b7-107">Dies entspricht der Einstellung des Werts auf `0`.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-107">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="3b8b7-108">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="3b8b7-108">Setting name</span></span> | <span data-ttu-id="3b8b7-109">Werte</span><span class="sxs-lookup"><span data-stu-id="3b8b7-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="3b8b7-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3b8b7-110">**runtimeconfig.json**</span></span> | <span data-ttu-id="3b8b7-111">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="3b8b7-111">N/A</span></span> | <span data-ttu-id="3b8b7-112">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="3b8b7-112">N/A</span></span> |
| <span data-ttu-id="3b8b7-113">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="3b8b7-113">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="3b8b7-114">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="3b8b7-114">`0` - disabled</span></span><br/><span data-ttu-id="3b8b7-115">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="3b8b7-115">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="3b8b7-116">Mindestanzahl an Threads</span><span class="sxs-lookup"><span data-stu-id="3b8b7-116">Minimum threads</span></span>

- <span data-ttu-id="3b8b7-117">Gibt die Mindestanzahl an Threads für den Arbeitsthreadpool an.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-117">Specifies the minimum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="3b8b7-118">Entspricht der <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>-Methode</span><span class="sxs-lookup"><span data-stu-id="3b8b7-118">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="3b8b7-119">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="3b8b7-119">Setting name</span></span> | <span data-ttu-id="3b8b7-120">Werte</span><span class="sxs-lookup"><span data-stu-id="3b8b7-120">Values</span></span> |
| - | - | - |
| <span data-ttu-id="3b8b7-121">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3b8b7-121">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="3b8b7-122">Eine ganze Zahl, die die Mindestanzahl an Threads angibt</span><span class="sxs-lookup"><span data-stu-id="3b8b7-122">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="3b8b7-123">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="3b8b7-123">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="3b8b7-124">Eine ganze Zahl, die die Mindestanzahl an Threads angibt</span><span class="sxs-lookup"><span data-stu-id="3b8b7-124">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="3b8b7-125">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="3b8b7-125">**Environment variable**</span></span> | <span data-ttu-id="3b8b7-126">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="3b8b7-126">N/A</span></span> | <span data-ttu-id="3b8b7-127">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="3b8b7-127">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="3b8b7-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3b8b7-128">Examples</span></span>

<span data-ttu-id="3b8b7-129">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="3b8b7-129">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="3b8b7-130">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="3b8b7-130">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="3b8b7-131">Maximale Anzahl an Threads</span><span class="sxs-lookup"><span data-stu-id="3b8b7-131">Maximum threads</span></span>

- <span data-ttu-id="3b8b7-132">Gibt die maximale Anzahl an Threads für den Arbeitsthreadpool an.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-132">Specifies the maximum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="3b8b7-133">Entspricht der <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>-Methode</span><span class="sxs-lookup"><span data-stu-id="3b8b7-133">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="3b8b7-134">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="3b8b7-134">Setting name</span></span> | <span data-ttu-id="3b8b7-135">Werte</span><span class="sxs-lookup"><span data-stu-id="3b8b7-135">Values</span></span> |
| - | - | - |
| <span data-ttu-id="3b8b7-136">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="3b8b7-136">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="3b8b7-137">Eine ganze Zahl, die die maximale Anzahl der Threads darstellt</span><span class="sxs-lookup"><span data-stu-id="3b8b7-137">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="3b8b7-138">**MSBuild-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="3b8b7-138">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="3b8b7-139">Eine ganze Zahl, die die maximale Anzahl der Threads darstellt</span><span class="sxs-lookup"><span data-stu-id="3b8b7-139">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="3b8b7-140">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="3b8b7-140">**Environment variable**</span></span> | <span data-ttu-id="3b8b7-141">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="3b8b7-141">N/A</span></span> | <span data-ttu-id="3b8b7-142">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="3b8b7-142">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="3b8b7-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3b8b7-143">Examples</span></span>

<span data-ttu-id="3b8b7-144">*runtimeconfig.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="3b8b7-144">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="3b8b7-145">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="3b8b7-145">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
