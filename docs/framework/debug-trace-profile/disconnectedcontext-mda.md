---
title: disconnectedContext-MDA
description: Überprüfen Sie den disconnectedContext-Assistenten für verwaltetes Debuggen in .net, der aufgerufen wird, wenn die CLR versucht, zu einem getrennten Apartment oder Kontext zu wechseln.
ms.date: 03/30/2017
helpviewer_keywords:
- DisconnectedContext MDA
- MDAs (managed debugging assistants), disconnected context
- dead context
- transitioning disconnected apartment or context
- context disconnections
- managed debugging assistants (MDAs), disconnected context
ms.assetid: 1887d31d-7006-4491-93b3-68fd5b05f71d
ms.openlocfilehash: 0b24aadefab7a7cb2a5294f25e674d188beec814
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416082"
---
# <a name="disconnectedcontext-mda"></a><span data-ttu-id="143a9-103">disconnectedContext-MDA</span><span class="sxs-lookup"><span data-stu-id="143a9-103">disconnectedContext MDA</span></span>
<span data-ttu-id="143a9-104">Der `disconnectedContext`-Assistent für verwaltetes Debuggen (MDA) wird aktiviert, wenn die CLR versucht, einen Übergang zu einem getrennten Apartment oder Kontext durchzuführen, während gerade eine Anforderung für ein COM-Objekt verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="143a9-104">The `disconnectedContext` managed debugging assistant (MDA) is activated when the CLR attempts to transition into a disconnected apartment or context while servicing a request concerning a COM object.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="143a9-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="143a9-105">Symptoms</span></span>  
 <span data-ttu-id="143a9-106">Aufrufe, die auf einem [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) ausgeführt werden, werden an die zugrunde liegende COM-Komponente im aktuellen Apartment oder Kontext zugestellt, statt an den, in dem sie vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="143a9-106">Calls made on a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) are delivered to the underlying COM component in the current apartment or context instead of the one in which they exist.</span></span> <span data-ttu-id="143a9-107">Dies kann zur Beschädigung oder zu Datenverlusten führen, wenn die COM-Komponente keine Multithread-Komponente ist, wie im Fall von Singlethread-Apartment-Komponenten (Single Thread Apartment, STA).</span><span class="sxs-lookup"><span data-stu-id="143a9-107">This can cause corruption and or data loss if the COM component is not multithreaded, as in the case of single-threaded apartment (STA) components.</span></span> <span data-ttu-id="143a9-108">Alternativ kann der Aufruf, wenn der RCW selbst ein Proxy ist, dazu führen, dass eine <xref:System.Runtime.InteropServices.COMException> mit einem HRESULT von RPC_E_WRONG_THREAD ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="143a9-108">Alternatively, if the RCW is itself a proxy, the call might result in the throwing of a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="143a9-109">Ursache</span><span class="sxs-lookup"><span data-stu-id="143a9-109">Cause</span></span>  
 <span data-ttu-id="143a9-110">Das OLE-Apartment oder der OLE-Kontext wurde heruntergefahren, als die CLR versucht hat, darin überzugehen.</span><span class="sxs-lookup"><span data-stu-id="143a9-110">The OLE apartment or context has been shut down when the CLR attempts to transition into it.</span></span> <span data-ttu-id="143a9-111">Dies wird meist durch STA-Apartments verursacht, die heruntergefahren werden, bevor alle COM-Komponenten, die im Besitz des Apartments sind, vollständig freigegeben wurden. Dies kann als Ergebnis eines expliziten Aufrufs aus Benutzercode von einem RCW auftreten, oder während die CLR selbst die COM-Komponente manipuliert, z. B. wenn die CLR die COM-Komponente freigibt, nachdem für den zugeordneten RCW eine Garbage Collection durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="143a9-111">This is most commonly caused by STA apartments being shut down before all the COM components owned by the apartment were completely released This can occur as a result of an explicit call from user code on an RCW or while the CLR itself is manipulating the COM component, for example when the CLR is releasing the COM component when the associated RCW has been garbage collected.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="143a9-112">Lösung</span><span class="sxs-lookup"><span data-stu-id="143a9-112">Resolution</span></span>  
 <span data-ttu-id="143a9-113">Um dieses Problem zu vermeiden, stellen Sie sicher, dass der Thread, der das STA besitzt, nicht beendet wird, bevor die Anwendung mit allen Objekten fertig ist, die in diesem Apartment vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="143a9-113">To avoid this problem, ensure the thread that owns the STA does not terminate before the application has finished with all the objects that live in the apartment.</span></span> <span data-ttu-id="143a9-114">Dasselbe gilt für Kontexte. Stellen Sie sicher, dass Kontexte nicht heruntergefahren werden, bevor die Anwendung mit allen COM-Komponenten vollständig fertig ist, die in diesem Kontext vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="143a9-114">The same applies to contexts; ensure contexts are not shut down before the application is completely finished with any COM components that live inside the context.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="143a9-115">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="143a9-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="143a9-116">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="143a9-116">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="143a9-117">Es werden nur Daten zu dem getrennten Kontext gemeldet.</span><span class="sxs-lookup"><span data-stu-id="143a9-117">It only reports data about the disconnected context.</span></span>  
  
## <a name="output"></a><span data-ttu-id="143a9-118">Output</span><span class="sxs-lookup"><span data-stu-id="143a9-118">Output</span></span>  
 <span data-ttu-id="143a9-119">Meldet das Kontextcookie des getrennten Apartments oder Kontexts.</span><span class="sxs-lookup"><span data-stu-id="143a9-119">Reports the context cookie of the disconnected apartment or context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="143a9-120">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="143a9-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <disconnectedContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="143a9-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="143a9-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="143a9-122">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="143a9-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="143a9-123">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="143a9-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
