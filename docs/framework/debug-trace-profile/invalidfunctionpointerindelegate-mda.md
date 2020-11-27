---
title: InvalidFunctionPointerInDelegate-MDA
description: Überprüfen Sie den invalidfunctionpointerindelegaten Managed Debug Assistant (MDA), der aufgerufen wird, wenn ein ungültiger Funktionszeiger an einen Delegaten übermittelt wird.
ms.date: 03/30/2017
helpviewer_keywords:
- invalidFunctionPointerInDelegate MDA
- managed debugging assistants (MDAs), invalid function pointer to delegates
- MDAs (managed debugging assistants), invalid function pointer to delegates
- function pointers, invalid
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- invalid function pointers
ms.assetid: 99ae44f1-783e-49a9-9009-24f54bbd0f09
ms.openlocfilehash: 8072d35a45cb1e0590aa5533210d0e0f86913164
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272617"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="8a10c-103">InvalidFunctionPointerInDelegate-MDA</span><span class="sxs-lookup"><span data-stu-id="8a10c-103">invalidFunctionPointerInDelegate MDA</span></span>

<span data-ttu-id="8a10c-104">Der `invalidFunctionPointerInDelegate` Assistent für verwaltetes Debuggen (MDA) wird aktiviert, wenn ein ungültiger Funktionszeiger übergeben wird, um einen Delegaten über einen systemeigenen Funktionszeiger zu konstruieren.</span><span class="sxs-lookup"><span data-stu-id="8a10c-104">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8a10c-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="8a10c-105">Symptoms</span></span>  

 <span data-ttu-id="8a10c-106">Zugriffsverletzungen oder unerwartete Speicherschäden beim Verwenden eines Delegaten über einen Funktionszeiger.</span><span class="sxs-lookup"><span data-stu-id="8a10c-106">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8a10c-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="8a10c-107">Cause</span></span>  

 <span data-ttu-id="8a10c-108">Es wurde ein ungültiger Funktionszeiger angegeben.</span><span class="sxs-lookup"><span data-stu-id="8a10c-108">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8a10c-109">Lösung</span><span class="sxs-lookup"><span data-stu-id="8a10c-109">Resolution</span></span>  

 <span data-ttu-id="8a10c-110">Geben Sie einen gültigen Funktionszeiger an.</span><span class="sxs-lookup"><span data-stu-id="8a10c-110">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8a10c-111">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="8a10c-111">Effect on the Runtime</span></span>  

 <span data-ttu-id="8a10c-112">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="8a10c-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8a10c-113">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="8a10c-113">Output</span></span>  

 <span data-ttu-id="8a10c-114">Der ungültige Funktionszeiger.</span><span class="sxs-lookup"><span data-stu-id="8a10c-114">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="8a10c-115">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8a10c-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a10c-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a10c-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="8a10c-117">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="8a10c-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="8a10c-118">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="8a10c-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
