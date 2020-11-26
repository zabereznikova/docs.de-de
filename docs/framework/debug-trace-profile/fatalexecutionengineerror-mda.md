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
ms.openlocfilehash: a9347338d53755b74b3ff291f75cb6b221134130
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244274"
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="e4735-103">fatalExecutionEngineError-MDA</span><span class="sxs-lookup"><span data-stu-id="e4735-103">fatalExecutionEngineError MDA</span></span>

<span data-ttu-id="e4735-104">Der `fatalExecutionEngineError`-Assistent für verwaltetes Debuggen (MDA) wird aktiviert, wenn ein schwerwiegender Fehler in der Common Language Runtime (CLR) erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="e4735-104">The `fatalExecutionEngineError` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="e4735-105">Der Prozess wird beendet.</span><span class="sxs-lookup"><span data-stu-id="e4735-105">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="e4735-106">Symptome</span><span class="sxs-lookup"><span data-stu-id="e4735-106">Symptoms</span></span>  

 <span data-ttu-id="e4735-107">Unerwartete Prozessbeendigung.</span><span class="sxs-lookup"><span data-stu-id="e4735-107">Unexpected process termination.</span></span> <span data-ttu-id="e4735-108">Andere Symptome können nicht bestimmt werden, weil es eine Vielzahl von Gründen gibt, warum ein CLR Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="e4735-108">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="e4735-109">Ursache</span><span class="sxs-lookup"><span data-stu-id="e4735-109">Cause</span></span>  

 <span data-ttu-id="e4735-110">Die CLR wurde schwerwiegend beschädigt.</span><span class="sxs-lookup"><span data-stu-id="e4735-110">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="e4735-111">Dies wird meist durch Datenbeschädigung verursacht, die durch eine Reihe von Problemen verursacht werden kann, wie z.B. das Aufrufen falsch formatierter Plattformfunktionen und die Weitergabe ungültiger Daten an die CLR.</span><span class="sxs-lookup"><span data-stu-id="e4735-111">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="e4735-112">Lösung</span><span class="sxs-lookup"><span data-stu-id="e4735-112">Resolution</span></span>  

 <span data-ttu-id="e4735-113">Das Aktivieren zusätzlicher MDAs kann dabei helfen, das Problem zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e4735-113">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="e4735-114">Die folgenden MDAs können besonders hilfreich bei der Problemdiagnose sein:</span><span class="sxs-lookup"><span data-stu-id="e4735-114">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
- [<span data-ttu-id="e4735-115">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="e4735-115">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)  
  
- [<span data-ttu-id="e4735-116">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="e4735-116">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)  
  
- [<span data-ttu-id="e4735-117">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="e4735-117">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)  
  
- [<span data-ttu-id="e4735-118">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="e4735-118">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)  
  
- [<span data-ttu-id="e4735-119">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="e4735-119">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)  
  
- [<span data-ttu-id="e4735-120">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="e4735-120">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)  
  
- [<span data-ttu-id="e4735-121">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="e4735-121">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)  
  
- [<span data-ttu-id="e4735-122">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="e4735-122">invalidVariant</span></span>](invalidvariant-mda.md)  
  
- [<span data-ttu-id="e4735-123">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="e4735-123">invalidIUnknown</span></span>](invalidiunknown-mda.md)  
  
- [<span data-ttu-id="e4735-124">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="e4735-124">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)  
  
- [<span data-ttu-id="e4735-125">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="e4735-125">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)  
  
- [<span data-ttu-id="e4735-126">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="e4735-126">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e4735-127">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="e4735-127">Effect on the Runtime</span></span>  

 <span data-ttu-id="e4735-128">Dieser MDA hat keine Auswirkung auf das Verhalten der CLR.</span><span class="sxs-lookup"><span data-stu-id="e4735-128">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e4735-129">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="e4735-129">Output</span></span>  

 <span data-ttu-id="e4735-130">Die Adresse der CLR-Funktion, die den schwerwiegenden Fehler verursacht hat, die ID des Threads, in dem der Fehler aufgetreten ist, und der Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e4735-130">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="e4735-131">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e4735-131">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4735-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e4735-132">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution.Cer>
- [<span data-ttu-id="e4735-133">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="e4735-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
