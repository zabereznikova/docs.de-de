---
title: failedQI-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a3338595e8b541fcda93b091eeddf17919a483c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614392"
---
# <a name="failedqi-mda"></a><span data-ttu-id="b5b57-102">failedQI-MDA</span><span class="sxs-lookup"><span data-stu-id="b5b57-102">failedQI MDA</span></span>
<span data-ttu-id="b5b57-103">Der `failedQI`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die CLR stellvertretend für einen RCW (Runtime Callable Wrapper) `QueryInterface` für einen COM-Schnittstellenzeiger aufruft und der Aufruf von `QueryInterface` fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="b5b57-103">The `failedQI` managed debugging assistant (MDA) is activated when the runtime calls `QueryInterface` on a COM interface pointer on behalf of a runtime callable wrapper (RCW), and the `QueryInterface` call fails.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="b5b57-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="b5b57-104">Symptoms</span></span>  
 <span data-ttu-id="b5b57-105">Eine Umwandlung für einen RCW schlägt fehl, oder ein Aufruf von COM von einem RCW aus schlägt unerwartet fehl.</span><span class="sxs-lookup"><span data-stu-id="b5b57-105">A cast on an RCW fails, or a call to COM from an RCW fails unexpectedly.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="b5b57-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="b5b57-106">Cause</span></span>  
  
-   <span data-ttu-id="b5b57-107">Der Aufruf erfolgt im falschen Kontext.</span><span class="sxs-lookup"><span data-stu-id="b5b57-107">The call is made from the wrong context.</span></span>  
  
-   <span data-ttu-id="b5b57-108">Der registrierte Proxy kann den Aufruf von `QueryInterface` nicht ausführen, weil der Aufruf im falschen Kontext erfolgte.</span><span class="sxs-lookup"><span data-stu-id="b5b57-108">The registered proxy is failing the `QueryInterface` call because the call was attempted in the wrong context.</span></span>  
  
-   <span data-ttu-id="b5b57-109">Ein OLE zugehöriger Proxy hat einen falschen Wert für HRESULT zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b5b57-109">An OLE-owned proxy returned a failure HRESULT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="b5b57-110">Auflösung</span><span class="sxs-lookup"><span data-stu-id="b5b57-110">Resolution</span></span>  
 <span data-ttu-id="b5b57-111">Informationen hierzu finden Sie in der MSDN-Dokumentation zu COM-Regeln.</span><span class="sxs-lookup"><span data-stu-id="b5b57-111">See the MSDN documentation on COM rules.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="b5b57-112">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b5b57-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="b5b57-113">Wenn ein Aufruf von `QueryInterface` fehlschlägt, erfolgt ein Kontextwechsel, und der Aufruf von `QueryInterface` wird erneut ausgeführt, um zu ermitteln, ob ein falscher Kontext für das Fehlschlagen verantwortlich war.</span><span class="sxs-lookup"><span data-stu-id="b5b57-113">If a `QueryInterface` call fails, the context is switched and the `QueryInterface` call is attempted again to see if an incorrect context was at fault.</span></span>  
  
## <a name="output"></a><span data-ttu-id="b5b57-114">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="b5b57-114">Output</span></span>  
 <span data-ttu-id="b5b57-115">Der verwaltete Name der Schnittstelle, die GUID der Schnittstelle und das HRESULT des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="b5b57-115">The managed name of the interface, the GUID of the interface, and the HRESULT of the failure.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="b5b57-116">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b5b57-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5b57-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5b57-117">See also</span></span>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="b5b57-118">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="b5b57-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="b5b57-119">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="b5b57-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
