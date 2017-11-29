---
title: invalidVariant-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ee537dcb03dc76968b829f827c73542c07922a3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="invalidvariant-mda"></a><span data-ttu-id="521a8-102">invalidVariant-MDA</span><span class="sxs-lookup"><span data-stu-id="521a8-102">invalidVariant MDA</span></span>
<span data-ttu-id="521a8-103">Der Assistent für verwaltetes Debugging (MDA) `invalidVariant` wird aktiviert, wenn während eines Aufrufs aus systemeigenem oder unverwaltetem Code an verwalteten Code eine ungültige `VARIANT`-Struktur erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="521a8-103">The `invalidVariant` managed debugging assistant (MDA) is activated when an invalid `VARIANT` structure is encountered during a call from native or unmanaged code to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="521a8-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="521a8-104">Symptoms</span></span>  
 <span data-ttu-id="521a8-105">Unerwartetes Verhalten während eines Übergangs zwischen systemeigenem und verwaltetem Code, das das Marshalling eines `VARIANT` an ein Objekt einbezieht.</span><span class="sxs-lookup"><span data-stu-id="521a8-105">Unexpected behavior during a transition between native and managed code involving the marshaling of a `VARIANT` to an object.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="521a8-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="521a8-106">Cause</span></span>  
 <span data-ttu-id="521a8-107">Systemeigener Code übergibt eine fehlerhafte `VARIANT`-Struktur an verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="521a8-107">Native code is passing a malformed `VARIANT` structure to managed code.</span></span>  <span data-ttu-id="521a8-108">Zur Laufzeit wird versucht, diesen `VARIANT` an ein Objekt zu marshallen, und der MDA wird aktiviert, wenn der `VARIANT` ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="521a8-108">The runtime attempts to marshal this `VARIANT` to an object and activates the MDA if the `VARIANT` is not valid.</span></span> <span data-ttu-id="521a8-109">Beispiele für ungültige `VARIANT`S enthalten unter anderem ein `VARIANT` mit dem `VARTYPE` VT_EMPTY &#124; VT_BYREF oder ein `VARIANT` mit dem `VARTYPE` VT_VARIANT.</span><span class="sxs-lookup"><span data-stu-id="521a8-109">Examples of invalid `VARIANT`S include a `VARIANT` with `VARTYPE` VT_EMPTY &#124; VT_BYREF or a `VARIANT` with `VARTYPE` VT_VARIANT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="521a8-110">Auflösung</span><span class="sxs-lookup"><span data-stu-id="521a8-110">Resolution</span></span>  
 <span data-ttu-id="521a8-111">Der systemeigene oder unverwaltete Code, der den `VARIANT` übergibt, muss sicherstellen, dass der `VARIANT` korrekt geformt und initialisiert ist.</span><span class="sxs-lookup"><span data-stu-id="521a8-111">The native or unmanaged code passing the `VARIANT` must ensure that the `VARIANT` is correctly formed and initialized.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="521a8-112">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="521a8-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="521a8-113">Dieser MDA hat keine Auswirkungen auf die Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="521a8-113">The MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="521a8-114">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="521a8-114">Output</span></span>  
 <span data-ttu-id="521a8-115">Eine MDA-Meldung, die angibt, dass zur Laufzeit ein ungültiger `VARIANT` erkannt wurde, der von einem unverwalteten Modul an verwalteten Code übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="521a8-115">An MDA message indicating that the runtime detected an invalid `VARIANT` passed to managed code by an unmanaged module.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="521a8-116">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="521a8-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="521a8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="521a8-117">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="521a8-118">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="521a8-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="521a8-119">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="521a8-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
