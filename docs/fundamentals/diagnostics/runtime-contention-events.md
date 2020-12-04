---
title: Lauf Zeit Ereignisse für Sperr Konflikte überwachen
description: Weitere Informationen zu den Monitor Sperr Konflikten finden Sie unter ETW-Ereignisse.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- monitor lock contention events (CoreCLR)
- ETW, EventPipe, LTTng contention events (CoreCLR)
ms.openlocfilehash: 38e5f493d4b223b4839dbd6f814cf656722189b2
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "96592084"
---
# <a name="net-runtime-contention-events"></a><span data-ttu-id="4c8cd-103">.Net-Lauf Zeit konfliktereignisse</span><span class="sxs-lookup"><span data-stu-id="4c8cd-103">.NET runtime contention events</span></span>

<span data-ttu-id="4c8cd-104">Diese Lauf Zeit Ereignisse erfassen Informationen zu Monitor Sperr Konflikten wie z `Monitor.Enter` . b. mit oder dem c#-Schlüsselwort Lock.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-104">These runtime events capture information about monitor lock contentions such as with `Monitor.Enter` or the C# lock keyword.</span></span> <span data-ttu-id="4c8cd-105">Weitere Informationen zur Verwendung dieser Ereignisse zu Diagnose Zwecken finden Sie unter [Protokollierung und Ablauf Verfolgung von .NET-Anwendungen](../../core/diagnostics/logging-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="4c8cd-105">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="contentionstart_v1-event"></a><span data-ttu-id="4c8cd-106">ContentionStart_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="4c8cd-106">ContentionStart_V1 event</span></span>

<span data-ttu-id="4c8cd-107">Dieses Ereignis wird zu Beginn eines Monitor Sperr Konflikts ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-107">This event is emitted at the start of a monitor lock contention.</span></span>

|<span data-ttu-id="4c8cd-108">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="4c8cd-108">Keyword for raising the event</span></span>|<span data-ttu-id="4c8cd-109">Ebene</span><span class="sxs-lookup"><span data-stu-id="4c8cd-109">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c8cd-110">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="4c8cd-110">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="4c8cd-111">Information (4)</span><span class="sxs-lookup"><span data-stu-id="4c8cd-111">Informational (4)</span></span>|

 <span data-ttu-id="4c8cd-112">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-112">The following table shows event information.</span></span>

|<span data-ttu-id="4c8cd-113">Ereignis</span><span class="sxs-lookup"><span data-stu-id="4c8cd-113">Event</span></span>|<span data-ttu-id="4c8cd-114">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="4c8cd-114">Event ID</span></span>|<span data-ttu-id="4c8cd-115">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="4c8cd-115">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|<span data-ttu-id="4c8cd-116">81</span><span class="sxs-lookup"><span data-stu-id="4c8cd-116">81</span></span>|<span data-ttu-id="4c8cd-117">Ein Monitor Sperr Konflikt wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-117">A monitor lock contention starts.</span></span>|

|<span data-ttu-id="4c8cd-118">Feldname</span><span class="sxs-lookup"><span data-stu-id="4c8cd-118">Field name</span></span>|<span data-ttu-id="4c8cd-119">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4c8cd-119">Data type</span></span>|<span data-ttu-id="4c8cd-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4c8cd-120">Description</span></span>|
|----------------|---------------|-----------------|
|`Flags`|`win:UInt8`|<span data-ttu-id="4c8cd-121">`0` für verwaltete; `1` für nativ.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-121">`0` for managed; `1` for native.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4c8cd-122">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-122">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="contentionstop_v1-event"></a><span data-ttu-id="4c8cd-123">ContentionStop_V1 Ereignis</span><span class="sxs-lookup"><span data-stu-id="4c8cd-123">ContentionStop_V1 event</span></span>

<span data-ttu-id="4c8cd-124">Dieses Ereignis wird am Ende eines Monitor Sperr Konflikts ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-124">This event is emitted at the end of a monitor lock contention.</span></span>

|<span data-ttu-id="4c8cd-125">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="4c8cd-125">Keyword for raising the event</span></span>|<span data-ttu-id="4c8cd-126">Ebene</span><span class="sxs-lookup"><span data-stu-id="4c8cd-126">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c8cd-127">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="4c8cd-127">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="4c8cd-128">Information (4)</span><span class="sxs-lookup"><span data-stu-id="4c8cd-128">Informational (4)</span></span>|

 <span data-ttu-id="4c8cd-129">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-129">The following table shows event information.</span></span>

|<span data-ttu-id="4c8cd-130">Ereignis</span><span class="sxs-lookup"><span data-stu-id="4c8cd-130">Event</span></span>|<span data-ttu-id="4c8cd-131">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="4c8cd-131">Event ID</span></span>|<span data-ttu-id="4c8cd-132">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="4c8cd-132">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ContentionStop_V1`|<span data-ttu-id="4c8cd-133">91</span><span class="sxs-lookup"><span data-stu-id="4c8cd-133">91</span></span>|<span data-ttu-id="4c8cd-134">Ein Monitor Sperr Konflikt wird beendet.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-134">A monitor lock contention ends.</span></span>|

|<span data-ttu-id="4c8cd-135">Feldname</span><span class="sxs-lookup"><span data-stu-id="4c8cd-135">Field name</span></span>|<span data-ttu-id="4c8cd-136">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4c8cd-136">Data type</span></span>|<span data-ttu-id="4c8cd-137">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4c8cd-137">Description</span></span>|
|----------------|---------------|-----------------|
|`Flags`|`win:UInt8`|<span data-ttu-id="4c8cd-138">`0` für verwaltete; `1` für nativ.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-138">`0` for managed; `1` for native.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="4c8cd-139">Eindeutige ID für die CoreCLR-Instanz.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-139">Unique ID for the instance of CoreCLR.</span></span>|
|`DurationNs`|`win:Double`|<span data-ttu-id="4c8cd-140">Die Dauer des Konflikts in Nanosekunden.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-140">Duration of the contention in nanoseconds.</span></span>|
