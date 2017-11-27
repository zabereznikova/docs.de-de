---
title: InvalidFunctionPointerInDelegate-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5e9fd1faacc7be5b95e2bab0d8fdbee105e35498
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="a649f-102">InvalidFunctionPointerInDelegate-MDA</span><span class="sxs-lookup"><span data-stu-id="a649f-102">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="a649f-103">Der `invalidFunctionPointerInDelegate` Assistent für verwaltetes Debuggen (MDA) wird aktiviert, wenn ein ungültiger Funktionszeiger übergeben wird, um einen Delegaten über einen systemeigenen Funktionszeiger zu konstruieren.</span><span class="sxs-lookup"><span data-stu-id="a649f-103">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a649f-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="a649f-104">Symptoms</span></span>  
 <span data-ttu-id="a649f-105">Zugriffsverletzungen oder unerwartete Speicherschäden beim Verwenden eines Delegaten über einen Funktionszeiger.</span><span class="sxs-lookup"><span data-stu-id="a649f-105">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a649f-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="a649f-106">Cause</span></span>  
 <span data-ttu-id="a649f-107">Es wurde ein ungültiger Funktionszeiger angegeben.</span><span class="sxs-lookup"><span data-stu-id="a649f-107">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a649f-108">Lösung</span><span class="sxs-lookup"><span data-stu-id="a649f-108">Resolution</span></span>  
 <span data-ttu-id="a649f-109">Geben Sie einen gültigen Funktionszeiger an.</span><span class="sxs-lookup"><span data-stu-id="a649f-109">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a649f-110">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a649f-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="a649f-111">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="a649f-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a649f-112">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="a649f-112">Output</span></span>  
 <span data-ttu-id="a649f-113">Der ungültige Funktionszeiger.</span><span class="sxs-lookup"><span data-stu-id="a649f-113">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a649f-114">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a649f-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a649f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a649f-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="a649f-116">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="a649f-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="a649f-117">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="a649f-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
