---
title: failedQI-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 87fe67e1e64d69912095e1d9587d277805a3eb80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="failedqi-mda"></a><span data-ttu-id="0ec9e-102">failedQI-MDA</span><span class="sxs-lookup"><span data-stu-id="0ec9e-102">failedQI MDA</span></span>
<span data-ttu-id="0ec9e-103">Der `failedQI`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die CLR stellvertretend für einen RCW (Runtime Callable Wrapper) `QueryInterface` für einen COM-Schnittstellenzeiger aufruft und der Aufruf von `QueryInterface` fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="0ec9e-103">The `failedQI` managed debugging assistant (MDA) is activated when the runtime calls `QueryInterface` on a COM interface pointer on behalf of a runtime callable wrapper (RCW), and the `QueryInterface` call fails.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="0ec9e-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="0ec9e-104">Symptoms</span></span>  
 <span data-ttu-id="0ec9e-105">Eine Umwandlung für einen RCW schlägt fehl, oder ein Aufruf von COM von einem RCW aus schlägt unerwartet fehl.</span><span class="sxs-lookup"><span data-stu-id="0ec9e-105">A cast on an RCW fails, or a call to COM from an RCW fails unexpectedly.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="0ec9e-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="0ec9e-106">Cause</span></span>  
  
-   <span data-ttu-id="0ec9e-107">Der Aufruf erfolgt im falschen Kontext.</span><span class="sxs-lookup"><span data-stu-id="0ec9e-107">The call is made from the wrong context.</span></span>  
  
-   <span data-ttu-id="0ec9e-108">Der registrierte Proxy kann den Aufruf von `QueryInterface` nicht ausführen, weil der Aufruf im falschen Kontext erfolgte.</span><span class="sxs-lookup"><span data-stu-id="0ec9e-108">The registered proxy is failing the `QueryInterface` call because the call was attempted in the wrong context.</span></span>  
  
-   <span data-ttu-id="0ec9e-109">Ein OLE zugehöriger Proxy hat einen falschen Wert für HRESULT zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0ec9e-109">An OLE-owned proxy returned a failure HRESULT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="0ec9e-110">Auflösung</span><span class="sxs-lookup"><span data-stu-id="0ec9e-110">Resolution</span></span>  
 <span data-ttu-id="0ec9e-111">Informationen hierzu finden Sie in der MSDN-Dokumentation zu COM-Regeln.</span><span class="sxs-lookup"><span data-stu-id="0ec9e-111">See the MSDN documentation on COM rules.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="0ec9e-112">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="0ec9e-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="0ec9e-113">Wenn ein Aufruf von `QueryInterface` fehlschlägt, erfolgt ein Kontextwechsel, und der Aufruf von `QueryInterface` wird erneut ausgeführt, um zu ermitteln, ob ein falscher Kontext für das Fehlschlagen verantwortlich war.</span><span class="sxs-lookup"><span data-stu-id="0ec9e-113">If a `QueryInterface` call fails, the context is switched and the `QueryInterface` call is attempted again to see if an incorrect context was at fault.</span></span>  
  
## <a name="output"></a><span data-ttu-id="0ec9e-114">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="0ec9e-114">Output</span></span>  
 <span data-ttu-id="0ec9e-115">Der verwaltete Name der Schnittstelle, die GUID der Schnittstelle und das HRESULT des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="0ec9e-115">The managed name of the interface, the GUID of the interface, and the HRESULT of the failure.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="0ec9e-116">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0ec9e-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ec9e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ec9e-117">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="0ec9e-118">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="0ec9e-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="0ec9e-119">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="0ec9e-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
