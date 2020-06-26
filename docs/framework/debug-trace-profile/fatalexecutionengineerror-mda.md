---
title: fatalExecutionEngineError-MDA
description: Überprüfen Sie den fatalExecutionEngineError-MDA (Managed Debugging Assistant) in .net, der aufgrund einer unerwarteten Prozess Beendigung aktiviert werden kann.
ms.date: 03/30/2017
helpviewer_keywords:
- corrupted CLR
- fatal execution error
- terminated processes
- unexpected terminations
- fatal errors
- MDAs (managed debugging assistants), fatal errors
- process termination
- FatalExecutionEngineError MDA
- managed debugging assistants (MDAs), fatal errors
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
ms.openlocfilehash: 0806d2eaa1752c88bebd03304fbe5c8094416a48
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415926"
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="c8a35-103">fatalExecutionEngineError-MDA</span><span class="sxs-lookup"><span data-stu-id="c8a35-103">fatalExecutionEngineError MDA</span></span>
<span data-ttu-id="c8a35-104">Der `fatalExecutionEngineError`-Assistent für verwaltetes Debuggen (MDA) wird aktiviert, wenn ein schwerwiegender Fehler in der Common Language Runtime (CLR) erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="c8a35-104">The `fatalExecutionEngineError` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="c8a35-105">Der Prozess wird beendet.</span><span class="sxs-lookup"><span data-stu-id="c8a35-105">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="c8a35-106">Symptome</span><span class="sxs-lookup"><span data-stu-id="c8a35-106">Symptoms</span></span>  
 <span data-ttu-id="c8a35-107">Unerwartete Prozessbeendigung.</span><span class="sxs-lookup"><span data-stu-id="c8a35-107">Unexpected process termination.</span></span> <span data-ttu-id="c8a35-108">Andere Symptome können nicht bestimmt werden, weil es eine Vielzahl von Gründen gibt, warum ein CLR Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="c8a35-108">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="c8a35-109">Ursache</span><span class="sxs-lookup"><span data-stu-id="c8a35-109">Cause</span></span>  
 <span data-ttu-id="c8a35-110">Die CLR wurde schwerwiegend beschädigt.</span><span class="sxs-lookup"><span data-stu-id="c8a35-110">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="c8a35-111">Dies wird meist durch Datenbeschädigung verursacht, die durch eine Reihe von Problemen verursacht werden kann, wie z.B. das Aufrufen falsch formatierter Plattformfunktionen und die Weitergabe ungültiger Daten an die CLR.</span><span class="sxs-lookup"><span data-stu-id="c8a35-111">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="c8a35-112">Lösung</span><span class="sxs-lookup"><span data-stu-id="c8a35-112">Resolution</span></span>  
 <span data-ttu-id="c8a35-113">Das Aktivieren zusätzlicher MDAs kann dabei helfen, das Problem zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c8a35-113">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="c8a35-114">Die folgenden MDAs können besonders hilfreich bei der Problemdiagnose sein:</span><span class="sxs-lookup"><span data-stu-id="c8a35-114">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
- [<span data-ttu-id="c8a35-115">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="c8a35-115">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)  
  
- [<span data-ttu-id="c8a35-116">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="c8a35-116">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)  
  
- [<span data-ttu-id="c8a35-117">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="c8a35-117">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)  
  
- [<span data-ttu-id="c8a35-118">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="c8a35-118">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)  
  
- [<span data-ttu-id="c8a35-119">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="c8a35-119">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)  
  
- [<span data-ttu-id="c8a35-120">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="c8a35-120">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)  
  
- [<span data-ttu-id="c8a35-121">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="c8a35-121">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)  
  
- [<span data-ttu-id="c8a35-122">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="c8a35-122">invalidVariant</span></span>](invalidvariant-mda.md)  
  
- [<span data-ttu-id="c8a35-123">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="c8a35-123">invalidIUnknown</span></span>](invalidiunknown-mda.md)  
  
- [<span data-ttu-id="c8a35-124">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="c8a35-124">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)  
  
- [<span data-ttu-id="c8a35-125">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="c8a35-125">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)  
  
- [<span data-ttu-id="c8a35-126">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="c8a35-126">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="c8a35-127">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="c8a35-127">Effect on the Runtime</span></span>  
 <span data-ttu-id="c8a35-128">Dieser MDA hat keine Auswirkung auf das Verhalten der CLR.</span><span class="sxs-lookup"><span data-stu-id="c8a35-128">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="c8a35-129">Output</span><span class="sxs-lookup"><span data-stu-id="c8a35-129">Output</span></span>  
 <span data-ttu-id="c8a35-130">Die Adresse der CLR-Funktion, die den schwerwiegenden Fehler verursacht hat, die ID des Threads, in dem der Fehler aufgetreten ist, und der Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="c8a35-130">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="c8a35-131">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c8a35-131">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8a35-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8a35-132">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution.Cer>
- [<span data-ttu-id="c8a35-133">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="c8a35-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
