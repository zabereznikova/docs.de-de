---
title: NotMarshalable-MDA
description: Überprüfen Sie den notmarshalling-Assistenten für verwaltetes Debuggen, der aktiviert werden kann, wenn Aufrufe nicht gewartet werden oder im falschen Kontext für COM-Schnittstellen Zeiger auftreten.
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
ms.openlocfilehash: 344c275d8645b16de3ecb06517297df06323ced4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254557"
---
# <a name="notmarshalable-mda"></a><span data-ttu-id="e78ad-103">NotMarshalable-MDA</span><span class="sxs-lookup"><span data-stu-id="e78ad-103">notMarshalable MDA</span></span>

<span data-ttu-id="e78ad-104">Der `notMarshalable`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die Common Language Runtime (CLR) beim Versuch, eine Schnittstelle über Kontexte hinweg zu marshallen, einen COM-Schnittstellenzeiger ohne gültigen registrierten Proxy/Stub oder eine nicht ordnungsgemäß implementierte `IMarshal`-Schnittstelle erkennt.</span><span class="sxs-lookup"><span data-stu-id="e78ad-104">The `notMarshalable` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters a COM interface pointer without a valid registered proxy/stub or an incorrect `IMarshal` interface implementation while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="e78ad-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="e78ad-105">Symptoms</span></span>  

 <span data-ttu-id="e78ad-106">Aufrufe werden nicht abgewickelt, oder Aufrufe treten im falschen Kontext für COM-Schnittstellenzeiger auf.</span><span class="sxs-lookup"><span data-stu-id="e78ad-106">Calls are not serviced, or calls occur in the wrong context for COM interface pointers.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="e78ad-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="e78ad-107">Cause</span></span>  

 <span data-ttu-id="e78ad-108">Beim Versuch, die Schnittstelle über Kontexte hinweg zu marshallen, wurde kein gültiger registrierter Proxy/Stub oder eine fehlerhafte `IMarshal`-Schnittstelle erkannt.</span><span class="sxs-lookup"><span data-stu-id="e78ad-108">No valid registered proxy/stub or an incorrect `IMarshal` while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="e78ad-109">Lösung</span><span class="sxs-lookup"><span data-stu-id="e78ad-109">Resolution</span></span>  

 <span data-ttu-id="e78ad-110">Stellen Sie sicher, dass ein Proxy/Stub registriert ist und die `IMarshal`-Implementierung gültig ist.</span><span class="sxs-lookup"><span data-stu-id="e78ad-110">Make sure you have a proxy stub registered and that the `IMarshal` implementation is valid.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e78ad-111">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="e78ad-111">Effect on the Runtime</span></span>  

 <span data-ttu-id="e78ad-112">Dieser MDA hat keine Auswirkungen auf die Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="e78ad-112">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e78ad-113">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="e78ad-113">Output</span></span>  

 <span data-ttu-id="e78ad-114">Eine Meldung mit einer Beschreibung des Problems.</span><span class="sxs-lookup"><span data-stu-id="e78ad-114">A message describing the problem.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="e78ad-115">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e78ad-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e78ad-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e78ad-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="e78ad-117">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="e78ad-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="e78ad-118">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="e78ad-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
