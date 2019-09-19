---
title: raceOnRCWCleanup-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 07b6c674e2608ac46bf9870ae26afc2fc1ec99ba
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052346"
---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="6f466-102">raceOnRCWCleanup-MDA</span><span class="sxs-lookup"><span data-stu-id="6f466-102">raceOnRCWCleanup MDA</span></span>
<span data-ttu-id="6f466-103">Der `raceOnRCWCleanup`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn die CLR (Common Language Runtime) ermittelt, dass ein [RWC (Runtime Callable Wrapper)](../../standard/native-interop/runtime-callable-wrapper.md) verwendet wird, wenn ein Freigabeaufruf mithilfe eines Befehls wie etwa der <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>-Methode erfolgt.</span><span class="sxs-lookup"><span data-stu-id="6f466-103">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="6f466-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="6f466-104">Symptoms</span></span>  
 <span data-ttu-id="6f466-105">Zugriffsverletzungen oder Speicherschäden während oder nach dem Freigeben eines RCW mithilfe von <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> oder einer ähnlichen Methode.</span><span class="sxs-lookup"><span data-stu-id="6f466-105">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="6f466-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="6f466-106">Cause</span></span>  
 <span data-ttu-id="6f466-107">Der RCW wird in einem anderen Thread oder für den freigebenden Threadstapel verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f466-107">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="6f466-108">Ein RCW, der verwendet wird, kann nicht freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6f466-108">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="6f466-109">Auflösung</span><span class="sxs-lookup"><span data-stu-id="6f466-109">Resolution</span></span>  
 <span data-ttu-id="6f466-110">Geben Sie einen RCW, der im aktuellen Thread oder in anderen Threads verwendet wird, nicht frei.</span><span class="sxs-lookup"><span data-stu-id="6f466-110">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="6f466-111">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="6f466-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="6f466-112">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="6f466-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="6f466-113">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="6f466-113">Output</span></span>  
 <span data-ttu-id="6f466-114">Eine Meldung mit einer Beschreibung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="6f466-114">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="6f466-115">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6f466-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f466-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f466-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="6f466-117">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="6f466-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="6f466-118">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="6f466-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
