---
title: disconnectedContext-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- DisconnectedContext MDA
- MDAs (managed debugging assistants), disconnected context
- dead context
- transitioning disconnected apartment or context
- context disconnections
- managed debugging assistants (MDAs), disconnected context
ms.assetid: 1887d31d-7006-4491-93b3-68fd5b05f71d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb42c04df6e02ff43421b7af6bf2d51b53aa3e69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755128"
---
# <a name="disconnectedcontext-mda"></a><span data-ttu-id="96b25-102">disconnectedContext-MDA</span><span class="sxs-lookup"><span data-stu-id="96b25-102">disconnectedContext MDA</span></span>
<span data-ttu-id="96b25-103">Der `disconnectedContext`-Assistent für verwaltetes Debuggen (MDA) wird aktiviert, wenn die CLR versucht, einen Übergang zu einem getrennten Apartment oder Kontext durchzuführen, während gerade eine Anforderung für ein COM-Objekt verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="96b25-103">The `disconnectedContext` managed debugging assistant (MDA) is activated when the CLR attempts to transition into a disconnected apartment or context while servicing a request concerning a COM object.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="96b25-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="96b25-104">Symptoms</span></span>  
 <span data-ttu-id="96b25-105">Aufrufe, die auf einem [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) ausgeführt werden, werden an die zugrunde liegende COM-Komponente im aktuellen Apartment oder Kontext zugestellt, statt an den, in dem sie vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="96b25-105">Calls made on a [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) are delivered to the underlying COM component in the current apartment or context instead of the one in which they exist.</span></span> <span data-ttu-id="96b25-106">Dies kann zur Beschädigung oder zu Datenverlusten führen, wenn die COM-Komponente keine Multithread-Komponente ist, wie im Fall von Singlethread-Apartment-Komponenten (Single Thread Apartment, STA).</span><span class="sxs-lookup"><span data-stu-id="96b25-106">This can cause corruption and or data loss if the COM component is not multithreaded, as in the case of single-threaded apartment (STA) components.</span></span> <span data-ttu-id="96b25-107">Alternativ kann der Aufruf, wenn der RCW selbst ein Proxy ist, dazu führen, dass eine <xref:System.Runtime.InteropServices.COMException> mit einem HRESULT von RPC_E_WRONG_THREAD ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="96b25-107">Alternatively, if the RCW is itself a proxy, the call might result in the throwing of a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="96b25-108">Ursache</span><span class="sxs-lookup"><span data-stu-id="96b25-108">Cause</span></span>  
 <span data-ttu-id="96b25-109">Das OLE-Apartment oder der OLE-Kontext wurde heruntergefahren, als die CLR versucht hat, darin überzugehen.</span><span class="sxs-lookup"><span data-stu-id="96b25-109">The OLE apartment or context has been shut down when the CLR attempts to transition into it.</span></span> <span data-ttu-id="96b25-110">Dies wird meist durch STA-Apartments verursacht, die heruntergefahren werden, bevor alle COM-Komponenten, die im Besitz des Apartments sind, vollständig freigegeben wurden. Dies kann als Ergebnis eines expliziten Aufrufs aus Benutzercode von einem RCW auftreten, oder während die CLR selbst die COM-Komponente manipuliert, z. B. wenn die CLR die COM-Komponente freigibt, nachdem für den zugeordneten RCW eine Garbage Collection durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="96b25-110">This is most commonly caused by STA apartments being shut down before all the COM components owned by the apartment were completely released This can occur as a result of an explicit call from user code on an RCW or while the CLR itself is manipulating the COM component, for example when the CLR is releasing the COM component when the associated RCW has been garbage collected.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="96b25-111">Auflösung</span><span class="sxs-lookup"><span data-stu-id="96b25-111">Resolution</span></span>  
 <span data-ttu-id="96b25-112">Um dieses Problem zu vermeiden, stellen Sie sicher, dass der Thread, der das STA besitzt, nicht beendet wird, bevor die Anwendung mit allen Objekten fertig ist, die in diesem Apartment vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="96b25-112">To avoid this problem, ensure the thread that owns the STA does not terminate before the application has finished with all the objects that live in the apartment.</span></span> <span data-ttu-id="96b25-113">Dasselbe gilt für Kontexte. Stellen Sie sicher, dass Kontexte nicht heruntergefahren werden, bevor die Anwendung mit allen COM-Komponenten vollständig fertig ist, die in diesem Kontext vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="96b25-113">The same applies to contexts; ensure contexts are not shut down before the application is completely finished with any COM components that live inside the context.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="96b25-114">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="96b25-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="96b25-115">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="96b25-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="96b25-116">Es werden nur Daten zu dem getrennten Kontext gemeldet.</span><span class="sxs-lookup"><span data-stu-id="96b25-116">It only reports data about the disconnected context.</span></span>  
  
## <a name="output"></a><span data-ttu-id="96b25-117">Output</span><span class="sxs-lookup"><span data-stu-id="96b25-117">Output</span></span>  
 <span data-ttu-id="96b25-118">Meldet das Kontextcookie des getrennten Apartments oder Kontexts.</span><span class="sxs-lookup"><span data-stu-id="96b25-118">Reports the context cookie of the disconnected apartment or context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="96b25-119">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="96b25-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <disconnectedContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="96b25-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96b25-120">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="96b25-121">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="96b25-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="96b25-122">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="96b25-122">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
