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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226104"
---
# <a name="notmarshalable-mda"></a><span data-ttu-id="f540c-102">NotMarshalable-MDA</span><span class="sxs-lookup"><span data-stu-id="f540c-102">notMarshalable MDA</span></span>
<span data-ttu-id="f540c-103">Der `notMarshalable`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die Common Language Runtime (CLR) beim Versuch, eine Schnittstelle über Kontexte hinweg zu marshallen, einen COM-Schnittstellenzeiger ohne gültigen registrierten Proxy/Stub oder eine nicht ordnungsgemäß implementierte `IMarshal`-Schnittstelle erkennt.</span><span class="sxs-lookup"><span data-stu-id="f540c-103">The `notMarshalable` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters a COM interface pointer without a valid registered proxy/stub or an incorrect `IMarshal` interface implementation while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f540c-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="f540c-104">Symptoms</span></span>  
 <span data-ttu-id="f540c-105">Aufrufe werden nicht abgewickelt, oder Aufrufe treten im falschen Kontext für COM-Schnittstellenzeiger auf.</span><span class="sxs-lookup"><span data-stu-id="f540c-105">Calls are not serviced, or calls occur in the wrong context for COM interface pointers.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f540c-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="f540c-106">Cause</span></span>  
 <span data-ttu-id="f540c-107">Beim Versuch, die Schnittstelle über Kontexte hinweg zu marshallen, wurde kein gültiger registrierter Proxy/Stub oder eine fehlerhafte `IMarshal`-Schnittstelle erkannt.</span><span class="sxs-lookup"><span data-stu-id="f540c-107">No valid registered proxy/stub or an incorrect `IMarshal` while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f540c-108">Auflösung</span><span class="sxs-lookup"><span data-stu-id="f540c-108">Resolution</span></span>  
 <span data-ttu-id="f540c-109">Stellen Sie sicher, dass ein Proxy/Stub registriert ist und die `IMarshal`-Implementierung gültig ist.</span><span class="sxs-lookup"><span data-stu-id="f540c-109">Make sure you have a proxy stub registered and that the `IMarshal` implementation is valid.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f540c-110">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f540c-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="f540c-111">Dieser MDA hat keine Auswirkungen auf die Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="f540c-111">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f540c-112">Output</span><span class="sxs-lookup"><span data-stu-id="f540c-112">Output</span></span>  
 <span data-ttu-id="f540c-113">Eine Meldung mit einer Beschreibung des Problems.</span><span class="sxs-lookup"><span data-stu-id="f540c-113">A message describing the problem.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f540c-114">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="f540c-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f540c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f540c-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f540c-116">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="f540c-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f540c-117">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="f540c-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
