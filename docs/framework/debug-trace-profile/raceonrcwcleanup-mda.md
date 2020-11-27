---
title: raceOnRCWCleanup-MDA
description: Überprüfen Sie den raceOnRCWCleanup-MDA (Managed Debug Assistant), der aktiviert wird, wenn der RCW in einem anderen Thread oder auf dem Freigabe Thread Stapel in .NET verwendet wird.
ms.date: 03/30/2017
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
ms.openlocfilehash: 393c5ea44108445a9a1a9d16e7d1d192eced5740
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271446"
---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="706b4-103">raceOnRCWCleanup-MDA</span><span class="sxs-lookup"><span data-stu-id="706b4-103">raceOnRCWCleanup MDA</span></span>

<span data-ttu-id="706b4-104">Der `raceOnRCWCleanup`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn die CLR (Common Language Runtime) ermittelt, dass ein [RWC (Runtime Callable Wrapper)](../../standard/native-interop/runtime-callable-wrapper.md) verwendet wird, wenn ein Freigabeaufruf mithilfe eines Befehls wie etwa der <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>-Methode erfolgt.</span><span class="sxs-lookup"><span data-stu-id="706b4-104">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="706b4-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="706b4-105">Symptoms</span></span>  

 <span data-ttu-id="706b4-106">Zugriffsverletzungen oder Speicherschäden während oder nach dem Freigeben eines RCW mithilfe von <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> oder einer ähnlichen Methode.</span><span class="sxs-lookup"><span data-stu-id="706b4-106">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="706b4-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="706b4-107">Cause</span></span>  

 <span data-ttu-id="706b4-108">Der RCW wird in einem anderen Thread oder für den freigebenden Threadstapel verwendet.</span><span class="sxs-lookup"><span data-stu-id="706b4-108">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="706b4-109">Ein RCW, der verwendet wird, kann nicht freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="706b4-109">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="706b4-110">Lösung</span><span class="sxs-lookup"><span data-stu-id="706b4-110">Resolution</span></span>  

 <span data-ttu-id="706b4-111">Geben Sie einen RCW, der im aktuellen Thread oder in anderen Threads verwendet wird, nicht frei.</span><span class="sxs-lookup"><span data-stu-id="706b4-111">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="706b4-112">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="706b4-112">Effect on the Runtime</span></span>  

 <span data-ttu-id="706b4-113">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="706b4-113">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="706b4-114">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="706b4-114">Output</span></span>  

 <span data-ttu-id="706b4-115">Eine Meldung mit einer Beschreibung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="706b4-115">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="706b4-116">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="706b4-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="706b4-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="706b4-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="706b4-118">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="706b4-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="706b4-119">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="706b4-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
