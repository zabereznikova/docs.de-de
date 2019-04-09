---
title: NotMarshalable-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), interface pointer not marshalable
- interface pointer not marshalable MDA
- MDAs (managed debugging assistants), interface pointer not marshalable
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- marshalable interface pointers
- MDAs (managed debugging assistants), marshaling
- notMarshalable MDA
ms.assetid: 96e7b2c1-843f-4d64-b519-740c3a18b50a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 30db07ddf935b5ce13b1fe4212f7f6a40270ae93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226104"
---
# <a name="notmarshalable-mda"></a><span data-ttu-id="f766d-102">NotMarshalable-MDA</span><span class="sxs-lookup"><span data-stu-id="f766d-102">notMarshalable MDA</span></span>
<span data-ttu-id="f766d-103">Der `notMarshalable`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die Common Language Runtime (CLR) beim Versuch, eine Schnittstelle über Kontexte hinweg zu marshallen, einen COM-Schnittstellenzeiger ohne gültigen registrierten Proxy/Stub oder eine nicht ordnungsgemäß implementierte `IMarshal`-Schnittstelle erkennt.</span><span class="sxs-lookup"><span data-stu-id="f766d-103">The `notMarshalable` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters a COM interface pointer without a valid registered proxy/stub or an incorrect `IMarshal` interface implementation while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f766d-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="f766d-104">Symptoms</span></span>  
 <span data-ttu-id="f766d-105">Aufrufe werden nicht abgewickelt, oder Aufrufe treten im falschen Kontext für COM-Schnittstellenzeiger auf.</span><span class="sxs-lookup"><span data-stu-id="f766d-105">Calls are not serviced, or calls occur in the wrong context for COM interface pointers.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f766d-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="f766d-106">Cause</span></span>  
 <span data-ttu-id="f766d-107">Beim Versuch, die Schnittstelle über Kontexte hinweg zu marshallen, wurde kein gültiger registrierter Proxy/Stub oder eine fehlerhafte `IMarshal`-Schnittstelle erkannt.</span><span class="sxs-lookup"><span data-stu-id="f766d-107">No valid registered proxy/stub or an incorrect `IMarshal` while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f766d-108">Auflösung</span><span class="sxs-lookup"><span data-stu-id="f766d-108">Resolution</span></span>  
 <span data-ttu-id="f766d-109">Stellen Sie sicher, dass ein Proxy/Stub registriert ist und die `IMarshal`-Implementierung gültig ist.</span><span class="sxs-lookup"><span data-stu-id="f766d-109">Make sure you have a proxy stub registered and that the `IMarshal` implementation is valid.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f766d-110">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f766d-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="f766d-111">Dieser MDA hat keine Auswirkungen auf die Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="f766d-111">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f766d-112">Output</span><span class="sxs-lookup"><span data-stu-id="f766d-112">Output</span></span>  
 <span data-ttu-id="f766d-113">Eine Meldung mit einer Beschreibung des Problems.</span><span class="sxs-lookup"><span data-stu-id="f766d-113">A message describing the problem.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f766d-114">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="f766d-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f766d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f766d-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f766d-116">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="f766d-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f766d-117">Interop-Marshalling</span><span class="sxs-lookup"><span data-stu-id="f766d-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
