---
title: invalidVariant-MDA
description: Überprüfen Sie den invalidVariant-Assistenten für verwaltetes Debuggen, der aufgerufen wird, wenn eine ungültige Variante bei einem Aufruf von System eigenem/nicht verwaltetem zu verwaltetem Code auftritt
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
ms.openlocfilehash: ab1233d9faa86ef1508fa8fe2b5af46cb37bd523
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051635"
---
# <a name="invalidvariant-mda"></a><span data-ttu-id="92d8b-103">invalidVariant-MDA</span><span class="sxs-lookup"><span data-stu-id="92d8b-103">invalidVariant MDA</span></span>
<span data-ttu-id="92d8b-104">Der Assistent für verwaltetes Debugging (MDA) `invalidVariant` wird aktiviert, wenn während eines Aufrufs aus systemeigenem oder unverwaltetem Code an verwalteten Code eine ungültige `VARIANT`-Struktur erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="92d8b-104">The `invalidVariant` managed debugging assistant (MDA) is activated when an invalid `VARIANT` structure is encountered during a call from native or unmanaged code to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="92d8b-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="92d8b-105">Symptoms</span></span>  
 <span data-ttu-id="92d8b-106">Unerwartetes Verhalten während eines Übergangs zwischen nativem und verwaltetem Code, das das Marshalling eines `VARIANT` an ein Objekt einbezieht.</span><span class="sxs-lookup"><span data-stu-id="92d8b-106">Unexpected behavior during a transition between native and managed code involving the marshaling of a `VARIANT` to an object.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="92d8b-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="92d8b-107">Cause</span></span>  
 <span data-ttu-id="92d8b-108">Systemeigener Code übergibt eine fehlerhafte `VARIANT`-Struktur an verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="92d8b-108">Native code is passing a malformed `VARIANT` structure to managed code.</span></span>  <span data-ttu-id="92d8b-109">Zur Laufzeit wird versucht, diesen `VARIANT` an ein Objekt zu marshallen, und der MDA wird aktiviert, wenn der `VARIANT` ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="92d8b-109">The runtime attempts to marshal this `VARIANT` to an object and activates the MDA if the `VARIANT` is not valid.</span></span> <span data-ttu-id="92d8b-110">Beispiele für ungültige `VARIANT`S enthalten unter anderem ein `VARIANT` mit dem `VARTYPE` VT_EMPTY &#124; VT_BYREF oder ein `VARIANT` mit dem `VARTYPE` VT_VARIANT.</span><span class="sxs-lookup"><span data-stu-id="92d8b-110">Examples of invalid `VARIANT`S include a `VARIANT` with `VARTYPE` VT_EMPTY &#124; VT_BYREF or a `VARIANT` with `VARTYPE` VT_VARIANT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="92d8b-111">Lösung</span><span class="sxs-lookup"><span data-stu-id="92d8b-111">Resolution</span></span>  
 <span data-ttu-id="92d8b-112">Der systemeigene oder unverwaltete Code, der den `VARIANT` übergibt, muss sicherstellen, dass der `VARIANT` korrekt geformt und initialisiert ist.</span><span class="sxs-lookup"><span data-stu-id="92d8b-112">The native or unmanaged code passing the `VARIANT` must ensure that the `VARIANT` is correctly formed and initialized.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="92d8b-113">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="92d8b-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="92d8b-114">Dieser MDA hat keine Auswirkungen auf die Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="92d8b-114">The MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="92d8b-115">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="92d8b-115">Output</span></span>  
 <span data-ttu-id="92d8b-116">Eine MDA-Meldung, die angibt, dass zur Laufzeit ein ungültiger `VARIANT` erkannt wurde, der von einem unverwalteten Modul an verwalteten Code übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="92d8b-116">An MDA message indicating that the runtime detected an invalid `VARIANT` passed to managed code by an unmanaged module.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="92d8b-117">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="92d8b-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="92d8b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92d8b-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="92d8b-119">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="92d8b-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="92d8b-120">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="92d8b-120">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
