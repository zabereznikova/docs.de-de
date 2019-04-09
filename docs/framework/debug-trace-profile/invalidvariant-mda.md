---
title: invalidVariant-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64f5a4425d70974bae8c4f7bec28041e687fe95f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228483"
---
# <a name="invalidvariant-mda"></a><span data-ttu-id="9a21b-102">invalidVariant-MDA</span><span class="sxs-lookup"><span data-stu-id="9a21b-102">invalidVariant MDA</span></span>
<span data-ttu-id="9a21b-103">Der Assistent für verwaltetes Debugging (MDA) `invalidVariant` wird aktiviert, wenn während eines Aufrufs aus systemeigenem oder unverwaltetem Code an verwalteten Code eine ungültige `VARIANT`-Struktur erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="9a21b-103">The `invalidVariant` managed debugging assistant (MDA) is activated when an invalid `VARIANT` structure is encountered during a call from native or unmanaged code to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="9a21b-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="9a21b-104">Symptoms</span></span>  
 <span data-ttu-id="9a21b-105">Unerwartetes Verhalten während eines Übergangs zwischen nativem und verwaltetem Code, das das Marshalling eines `VARIANT` an ein Objekt einbezieht.</span><span class="sxs-lookup"><span data-stu-id="9a21b-105">Unexpected behavior during a transition between native and managed code involving the marshaling of a `VARIANT` to an object.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="9a21b-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="9a21b-106">Cause</span></span>  
 <span data-ttu-id="9a21b-107">Systemeigener Code übergibt eine fehlerhafte `VARIANT`-Struktur an verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="9a21b-107">Native code is passing a malformed `VARIANT` structure to managed code.</span></span>  <span data-ttu-id="9a21b-108">Zur Laufzeit wird versucht, diesen `VARIANT` an ein Objekt zu marshallen, und der MDA wird aktiviert, wenn der `VARIANT` ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="9a21b-108">The runtime attempts to marshal this `VARIANT` to an object and activates the MDA if the `VARIANT` is not valid.</span></span> <span data-ttu-id="9a21b-109">Beispiele für ungültige `VARIANT`S enthalten unter anderem ein `VARIANT` mit dem `VARTYPE` VT_EMPTY &#124; VT_BYREF oder ein `VARIANT` mit dem `VARTYPE` VT_VARIANT.</span><span class="sxs-lookup"><span data-stu-id="9a21b-109">Examples of invalid `VARIANT`S include a `VARIANT` with `VARTYPE` VT_EMPTY &#124; VT_BYREF or a `VARIANT` with `VARTYPE` VT_VARIANT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="9a21b-110">Auflösung</span><span class="sxs-lookup"><span data-stu-id="9a21b-110">Resolution</span></span>  
 <span data-ttu-id="9a21b-111">Der systemeigene oder unverwaltete Code, der den `VARIANT` übergibt, muss sicherstellen, dass der `VARIANT` korrekt geformt und initialisiert ist.</span><span class="sxs-lookup"><span data-stu-id="9a21b-111">The native or unmanaged code passing the `VARIANT` must ensure that the `VARIANT` is correctly formed and initialized.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="9a21b-112">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="9a21b-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="9a21b-113">Dieser MDA hat keine Auswirkungen auf die Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="9a21b-113">The MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="9a21b-114">Output</span><span class="sxs-lookup"><span data-stu-id="9a21b-114">Output</span></span>  
 <span data-ttu-id="9a21b-115">Eine MDA-Meldung, die angibt, dass zur Laufzeit ein ungültiger `VARIANT` erkannt wurde, der von einem unverwalteten Modul an verwalteten Code übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="9a21b-115">An MDA message indicating that the runtime detected an invalid `VARIANT` passed to managed code by an unmanaged module.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="9a21b-116">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9a21b-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a21b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a21b-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="9a21b-118">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="9a21b-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="9a21b-119">Interop-Marshalling</span><span class="sxs-lookup"><span data-stu-id="9a21b-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
