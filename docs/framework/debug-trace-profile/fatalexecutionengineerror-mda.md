---
title: fatalExecutionEngineError-MDA
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
ms.openlocfilehash: e25c9ef6ec43089f1d85479d1afe301232ed1d4f
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217493"
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="23ea6-102">fatalExecutionEngineError-MDA</span><span class="sxs-lookup"><span data-stu-id="23ea6-102">fatalExecutionEngineError MDA</span></span>
<span data-ttu-id="23ea6-103">Der `fatalExecutionEngineError`-Assistent für verwaltetes Debuggen (MDA) wird aktiviert, wenn ein schwerwiegender Fehler in der Common Language Runtime (CLR) erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="23ea6-103">The `fatalExecutionEngineError` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="23ea6-104">Der Prozess wird beendet.</span><span class="sxs-lookup"><span data-stu-id="23ea6-104">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="23ea6-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="23ea6-105">Symptoms</span></span>  
 <span data-ttu-id="23ea6-106">Unerwartete Prozessbeendigung.</span><span class="sxs-lookup"><span data-stu-id="23ea6-106">Unexpected process termination.</span></span> <span data-ttu-id="23ea6-107">Andere Symptome können nicht bestimmt werden, weil es eine Vielzahl von Gründen gibt, warum ein CLR Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="23ea6-107">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="23ea6-108">Ursache</span><span class="sxs-lookup"><span data-stu-id="23ea6-108">Cause</span></span>  
 <span data-ttu-id="23ea6-109">Die CLR wurde schwerwiegend beschädigt.</span><span class="sxs-lookup"><span data-stu-id="23ea6-109">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="23ea6-110">Dies wird meist durch Datenbeschädigung verursacht, die durch eine Reihe von Problemen verursacht werden kann, wie z.B. das Aufrufen falsch formatierter Plattformfunktionen und die Weitergabe ungültiger Daten an die CLR.</span><span class="sxs-lookup"><span data-stu-id="23ea6-110">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="23ea6-111">Lösung</span><span class="sxs-lookup"><span data-stu-id="23ea6-111">Resolution</span></span>  
 <span data-ttu-id="23ea6-112">Das Aktivieren zusätzlicher MDAs kann dabei helfen, das Problem zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="23ea6-112">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="23ea6-113">Die folgenden MDAs können besonders hilfreich bei der Problemdiagnose sein:</span><span class="sxs-lookup"><span data-stu-id="23ea6-113">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
- [<span data-ttu-id="23ea6-114">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="23ea6-114">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)  
  
- [<span data-ttu-id="23ea6-115">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="23ea6-115">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)  
  
- [<span data-ttu-id="23ea6-116">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="23ea6-116">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)  
  
- [<span data-ttu-id="23ea6-117">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="23ea6-117">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)  
  
- [<span data-ttu-id="23ea6-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="23ea6-118">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)  
  
- [<span data-ttu-id="23ea6-119">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="23ea6-119">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)  
  
- [<span data-ttu-id="23ea6-120">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="23ea6-120">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)  
  
- [<span data-ttu-id="23ea6-121">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="23ea6-121">invalidVariant</span></span>](invalidvariant-mda.md)  
  
- [<span data-ttu-id="23ea6-122">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="23ea6-122">invalidIUnknown</span></span>](invalidiunknown-mda.md)  
  
- [<span data-ttu-id="23ea6-123">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="23ea6-123">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)  
  
- [<span data-ttu-id="23ea6-124">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="23ea6-124">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)  
  
- [<span data-ttu-id="23ea6-125">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="23ea6-125">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="23ea6-126">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="23ea6-126">Effect on the Runtime</span></span>  
 <span data-ttu-id="23ea6-127">Dieser MDA hat keine Auswirkung auf das Verhalten der CLR.</span><span class="sxs-lookup"><span data-stu-id="23ea6-127">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="23ea6-128">Output</span><span class="sxs-lookup"><span data-stu-id="23ea6-128">Output</span></span>  
 <span data-ttu-id="23ea6-129">Die Adresse der CLR-Funktion, die den schwerwiegenden Fehler verursacht hat, die ID des Threads, in dem der Fehler aufgetreten ist, und der Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="23ea6-129">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="23ea6-130">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="23ea6-130">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="23ea6-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23ea6-131">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution.Cer>
- [<span data-ttu-id="23ea6-132">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="23ea6-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
