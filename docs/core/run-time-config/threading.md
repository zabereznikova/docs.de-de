---
title: Konfigurationseinstellungen für das Threading
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Threading für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6a920dbc301830e3f4c95bf637ff3de6d4f464ff
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998828"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="c1d51-103">Laufzeitkonfigurationsoptionen für das Threading</span><span class="sxs-lookup"><span data-stu-id="c1d51-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="c1d51-104">CPU-Gruppen</span><span class="sxs-lookup"><span data-stu-id="c1d51-104">CPU groups</span></span>

- <span data-ttu-id="c1d51-105">Hiermit wird konfiguriert, ob Threads automatisch über CPU-Gruppen verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="c1d51-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="c1d51-106">Standard: Deaktiviert (`0`)</span><span class="sxs-lookup"><span data-stu-id="c1d51-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="c1d51-107">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c1d51-107">Setting name</span></span> | <span data-ttu-id="c1d51-108">Werte</span><span class="sxs-lookup"><span data-stu-id="c1d51-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="c1d51-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c1d51-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="c1d51-110">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c1d51-110">N/A</span></span> | <span data-ttu-id="c1d51-111">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c1d51-111">N/A</span></span> |
| <span data-ttu-id="c1d51-112">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c1d51-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="c1d51-113">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="c1d51-113">`0` - disabled</span></span><br/><span data-ttu-id="c1d51-114">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="c1d51-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="c1d51-115">Mindestanzahl an Threads</span><span class="sxs-lookup"><span data-stu-id="c1d51-115">Minimum threads</span></span>

- <span data-ttu-id="c1d51-116">Gibt die Mindestanzahl an Threads für den Arbeitsthreadpool an</span><span class="sxs-lookup"><span data-stu-id="c1d51-116">Specifies the minimum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="c1d51-117">Entspricht der <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>-Methode</span><span class="sxs-lookup"><span data-stu-id="c1d51-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="c1d51-118">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c1d51-118">Setting name</span></span> | <span data-ttu-id="c1d51-119">Werte</span><span class="sxs-lookup"><span data-stu-id="c1d51-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="c1d51-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c1d51-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="c1d51-121">Eine ganze Zahl, die die Mindestanzahl an Threads angibt</span><span class="sxs-lookup"><span data-stu-id="c1d51-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="c1d51-122">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c1d51-122">**Environment variable**</span></span> | <span data-ttu-id="c1d51-123">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c1d51-123">N/A</span></span> | <span data-ttu-id="c1d51-124">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c1d51-124">N/A</span></span> |

## <a name="maximum-threads"></a><span data-ttu-id="c1d51-125">Maximale Anzahl an Threads</span><span class="sxs-lookup"><span data-stu-id="c1d51-125">Maximum threads</span></span>

- <span data-ttu-id="c1d51-126">Gibt die maximale Anzahl an Threads für den Arbeitsthreadpool an</span><span class="sxs-lookup"><span data-stu-id="c1d51-126">Specifies the maximum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="c1d51-127">Entspricht der <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>-Methode</span><span class="sxs-lookup"><span data-stu-id="c1d51-127">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="c1d51-128">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="c1d51-128">Setting name</span></span> | <span data-ttu-id="c1d51-129">Werte</span><span class="sxs-lookup"><span data-stu-id="c1d51-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="c1d51-130">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c1d51-130">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="c1d51-131">Eine ganze Zahl, die die maximale Anzahl der Threads darstellt</span><span class="sxs-lookup"><span data-stu-id="c1d51-131">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="c1d51-132">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="c1d51-132">**Environment variable**</span></span> | <span data-ttu-id="c1d51-133">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c1d51-133">N/A</span></span> | <span data-ttu-id="c1d51-134">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="c1d51-134">N/A</span></span> |
