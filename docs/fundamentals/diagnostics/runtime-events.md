---
title: Lauf Zeit Ereignisse
description: Überprüfen Sie die von der .NET-Runtime (CoreCLR) ausgegebenen Diagnose Ereignisse, die mit etw, lttng oder eventpipe verwendet werden können.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- runtime events (CoreCLR)
- ETW, EventPipe runtime events (CoreCLR)
ms.openlocfilehash: 33fa7275ce40934ce043b4d0dba5749c37515755
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "96592083"
---
# <a name="net-runtime-events"></a><span data-ttu-id="44192-103">.Net-Lauf Zeit Ereignisse</span><span class="sxs-lookup"><span data-stu-id="44192-103">.NET runtime events</span></span>

<span data-ttu-id="44192-104">Die .NET-Runtime (CoreCLR) gibt verschiedene Ereignisse aus, die verwendet werden können, um Probleme mit der .NET-Anwendung zu diagnostizieren, die über verschiedene Mechanismen, wie z `ETW` . b., und, genutzt werden können `LTTng` `EventPipe` .</span><span class="sxs-lookup"><span data-stu-id="44192-104">The .NET runtime (CoreCLR) emits various events that can be used to diagnose issues with your .NET application that can be consumed via various mechanisms such as `ETW`, `LTTng`, and `EventPipe`.</span></span>

<span data-ttu-id="44192-105">Dieses Dokument dient als Referenz zu den Ereignissen, die von der .net Core-Laufzeit ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="44192-105">This document serves as a reference on the events that are fired by .NET Core runtime.</span></span>

<span data-ttu-id="44192-106">Informationen zu Lauf Zeit Ereignissen in .NET Framework finden Sie unter [CLR-ETW-Ereignisse](../../framework/performance/clr-etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="44192-106">For runtime events in .NET Framework, see [CLR ETW Events](../../framework/performance/clr-etw-events.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="44192-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="44192-107">In this section</span></span>

<span data-ttu-id="44192-108">[Konfliktereignisse](runtime-contention-events.md)</span><span class="sxs-lookup"><span data-stu-id="44192-108">[Contention Events](runtime-contention-events.md)</span></span>\
<span data-ttu-id="44192-109">Diese Ereignisse sammeln Informationen zu Monitor Sperr Konflikten.</span><span class="sxs-lookup"><span data-stu-id="44192-109">These events collect information about monitor lock contentions.</span></span>

<span data-ttu-id="44192-110">[Garbage Collection-Ereignisse](runtime-garbage-collection-events.md)</span><span class="sxs-lookup"><span data-stu-id="44192-110">[Garbage Collection Events](runtime-garbage-collection-events.md)</span></span>\
<span data-ttu-id="44192-111">Diese Ereignisse sammeln Informationen, die die Garbage Collection betreffen.</span><span class="sxs-lookup"><span data-stu-id="44192-111">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="44192-112">Sie helfen bei der Diagnose und beim Debuggen, einschließlich der Ermittlung, wie oft Garbage Collection ausgeführt wurde, wie viel Arbeitsspeicher während Garbage Collection freigegeben wurde usw.</span><span class="sxs-lookup"><span data-stu-id="44192-112">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, etc.</span></span>

<span data-ttu-id="44192-113">[Ausnahme Ereignisse](runtime-exception-events.md)</span><span class="sxs-lookup"><span data-stu-id="44192-113">[Exception Events](runtime-exception-events.md)</span></span>\
<span data-ttu-id="44192-114">Diese Lauf Zeit Ereignisse erfassen Informationen zu Ausnahmen, die ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="44192-114">These runtime events capture information about exceptions that are thrown.</span></span>

<span data-ttu-id="44192-115">[Interop-Ereignisse](runtime-interop-events.md)</span><span class="sxs-lookup"><span data-stu-id="44192-115">[Interop Events](runtime-interop-events.md)</span></span>\
<span data-ttu-id="44192-116">Diese Lauf Zeit Ereignisse erfassen Informationen über Common Intermediate Language (CIL)-Stub-Generierung.</span><span class="sxs-lookup"><span data-stu-id="44192-116">These runtime events capture information about Common Intermediate Language (CIL) stub generation.</span></span>

<span data-ttu-id="44192-117">[Lade-und Binder Ereignisse](runtime-loader-binder-events.md)</span><span class="sxs-lookup"><span data-stu-id="44192-117">[Loader and Binder Events](runtime-loader-binder-events.md)</span></span>\
<span data-ttu-id="44192-118">Diese Ereignisse sammeln Informationen in Bezug auf das Laden und Entladen von Assemblys und Modulen.</span><span class="sxs-lookup"><span data-stu-id="44192-118">These events collect information relating to loading and unloading assemblies and modules.</span></span>

<span data-ttu-id="44192-119">[Methoden Ereignisse](runtime-method-events.md)</span><span class="sxs-lookup"><span data-stu-id="44192-119">[Method Events](runtime-method-events.md)</span></span>\
<span data-ttu-id="44192-120">Diese Ereignisse sammeln Informationen, die für Methoden spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="44192-120">These events collect information that is specific to methods.</span></span> <span data-ttu-id="44192-121">Die Nutzlast dieser Ereignisse ist für die Symbolauflösung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="44192-121">The payload of these events is required for symbol resolution.</span></span> <span data-ttu-id="44192-122">Darüber hinaus bieten diese Ereignisse hilfreiche Informationen, beispielsweise, wie oft eine Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="44192-122">In addition, these events provide helpful information such as the number of times a method was called.</span></span>

<span data-ttu-id="44192-123">[Thread Ereignisse](runtime-thread-events.md)</span><span class="sxs-lookup"><span data-stu-id="44192-123">[Thread Events](runtime-thread-events.md)</span></span>\
<span data-ttu-id="44192-124">Diese Ereignisse sammeln Informationen zu Arbeits- und E/A-Threads.</span><span class="sxs-lookup"><span data-stu-id="44192-124">These events collect information about worker and I/O threads.</span></span>

<span data-ttu-id="44192-125">[Typereignisse](runtime-type-events.md)</span><span class="sxs-lookup"><span data-stu-id="44192-125">[Type Events](runtime-type-events.md)</span></span>\
<span data-ttu-id="44192-126">Diese Ereignisse sammeln Informationen über das Typsystem.</span><span class="sxs-lookup"><span data-stu-id="44192-126">These events collect information about the type system.</span></span>
