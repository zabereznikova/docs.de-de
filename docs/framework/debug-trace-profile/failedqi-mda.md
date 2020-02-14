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
ms.openlocfilehash: 4c36ec514645a38ef1228e76bdf6dbd06e886bae
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217504"
---
# <a name="failedqi-mda"></a><span data-ttu-id="bb5f8-102">failedQI-MDA</span><span class="sxs-lookup"><span data-stu-id="bb5f8-102">failedQI MDA</span></span>
<span data-ttu-id="bb5f8-103">Der `failedQI`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die CLR stellvertretend für einen RCW (Runtime Callable Wrapper) `QueryInterface` für einen COM-Schnittstellenzeiger aufruft und der Aufruf von `QueryInterface` fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="bb5f8-103">The `failedQI` managed debugging assistant (MDA) is activated when the runtime calls `QueryInterface` on a COM interface pointer on behalf of a runtime callable wrapper (RCW), and the `QueryInterface` call fails.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="bb5f8-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="bb5f8-104">Symptoms</span></span>  
 <span data-ttu-id="bb5f8-105">Eine Umwandlung für einen RCW schlägt fehl, oder ein Aufruf von COM von einem RCW aus schlägt unerwartet fehl.</span><span class="sxs-lookup"><span data-stu-id="bb5f8-105">A cast on an RCW fails, or a call to COM from an RCW fails unexpectedly.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="bb5f8-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="bb5f8-106">Cause</span></span>  
  
- <span data-ttu-id="bb5f8-107">Der Aufruf erfolgt im falschen Kontext.</span><span class="sxs-lookup"><span data-stu-id="bb5f8-107">The call is made from the wrong context.</span></span>  
  
- <span data-ttu-id="bb5f8-108">Der registrierte Proxy kann den Aufruf von `QueryInterface` nicht ausführen, weil der Aufruf im falschen Kontext erfolgte.</span><span class="sxs-lookup"><span data-stu-id="bb5f8-108">The registered proxy is failing the `QueryInterface` call because the call was attempted in the wrong context.</span></span>  
  
- <span data-ttu-id="bb5f8-109">Ein OLE zugehöriger Proxy hat einen falschen Wert für HRESULT zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bb5f8-109">An OLE-owned proxy returned a failure HRESULT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="bb5f8-110">Lösung</span><span class="sxs-lookup"><span data-stu-id="bb5f8-110">Resolution</span></span>  
 <span data-ttu-id="bb5f8-111">Informationen hierzu finden Sie in der MSDN-Dokumentation zu COM-Regeln.</span><span class="sxs-lookup"><span data-stu-id="bb5f8-111">See the MSDN documentation on COM rules.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="bb5f8-112">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="bb5f8-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="bb5f8-113">Wenn ein Aufruf von `QueryInterface` fehlschlägt, erfolgt ein Kontextwechsel, und der Aufruf von `QueryInterface` wird erneut ausgeführt, um zu ermitteln, ob ein falscher Kontext für das Fehlschlagen verantwortlich war.</span><span class="sxs-lookup"><span data-stu-id="bb5f8-113">If a `QueryInterface` call fails, the context is switched and the `QueryInterface` call is attempted again to see if an incorrect context was at fault.</span></span>  
  
## <a name="output"></a><span data-ttu-id="bb5f8-114">Output</span><span class="sxs-lookup"><span data-stu-id="bb5f8-114">Output</span></span>  
 <span data-ttu-id="bb5f8-115">Der verwaltete Name der Schnittstelle, die GUID der Schnittstelle und das HRESULT des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="bb5f8-115">The managed name of the interface, the GUID of the interface, and the HRESULT of the failure.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="bb5f8-116">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="bb5f8-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb5f8-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb5f8-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="bb5f8-118">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="bb5f8-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="bb5f8-119">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="bb5f8-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
