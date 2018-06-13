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
ms.openlocfilehash: c52f104228db0b9e7f664ee7c1de393aa696c71a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33386729"
---
# <a name="notmarshalable-mda"></a><span data-ttu-id="7c9ba-102">NotMarshalable-MDA</span><span class="sxs-lookup"><span data-stu-id="7c9ba-102">notMarshalable MDA</span></span>
<span data-ttu-id="7c9ba-103">Der `notMarshalable`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die Common Language Runtime (CLR) beim Versuch, eine Schnittstelle über Kontexte hinweg zu marshallen, einen COM-Schnittstellenzeiger ohne gültigen registrierten Proxy/Stub oder eine nicht ordnungsgemäß implementierte `IMarshal`-Schnittstelle erkennt.</span><span class="sxs-lookup"><span data-stu-id="7c9ba-103">The `notMarshalable` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters a COM interface pointer without a valid registered proxy/stub or an incorrect `IMarshal` interface implementation while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="7c9ba-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="7c9ba-104">Symptoms</span></span>  
 <span data-ttu-id="7c9ba-105">Aufrufe werden nicht abgewickelt, oder Aufrufe treten im falschen Kontext für COM-Schnittstellenzeiger auf.</span><span class="sxs-lookup"><span data-stu-id="7c9ba-105">Calls are not serviced, or calls occur in the wrong context for COM interface pointers.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="7c9ba-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="7c9ba-106">Cause</span></span>  
 <span data-ttu-id="7c9ba-107">Beim Versuch, die Schnittstelle über Kontexte hinweg zu marshallen, wurde kein gültiger registrierter Proxy/Stub oder eine fehlerhafte `IMarshal`-Schnittstelle erkannt.</span><span class="sxs-lookup"><span data-stu-id="7c9ba-107">No valid registered proxy/stub or an incorrect `IMarshal` while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="7c9ba-108">Lösung</span><span class="sxs-lookup"><span data-stu-id="7c9ba-108">Resolution</span></span>  
 <span data-ttu-id="7c9ba-109">Stellen Sie sicher, dass ein Proxy/Stub registriert ist und die `IMarshal`-Implementierung gültig ist.</span><span class="sxs-lookup"><span data-stu-id="7c9ba-109">Make sure you have a proxy stub registered and that the `IMarshal` implementation is valid.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="7c9ba-110">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7c9ba-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="7c9ba-111">Dieser MDA hat keine Auswirkungen auf die Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="7c9ba-111">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="7c9ba-112">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="7c9ba-112">Output</span></span>  
 <span data-ttu-id="7c9ba-113">Eine Meldung mit einer Beschreibung des Problems.</span><span class="sxs-lookup"><span data-stu-id="7c9ba-113">A message describing the problem.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="7c9ba-114">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7c9ba-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c9ba-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c9ba-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="7c9ba-116">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="7c9ba-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="7c9ba-117">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="7c9ba-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
