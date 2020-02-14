---
title: marshalCleanupError-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- cleanup operations
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- marshaling cleanup error
- MarshalCleanupError MDA
- memory, cleanup errors
ms.assetid: 2f5d9e7c-ae51-4155-a435-54347aa1f091
ms.openlocfilehash: 1a14c548ce960d53f47934595171189db28edfbb
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216155"
---
# <a name="marshalcleanuperror-mda"></a><span data-ttu-id="c72b5-102">marshalCleanupError-MDA</span><span class="sxs-lookup"><span data-stu-id="c72b5-102">marshalCleanupError MDA</span></span>
<span data-ttu-id="c72b5-103">Der `marshalCleanupError`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die Common Language Runtime (CLR) beim Bereinigen von temporären Strukturen und Arbeitsspeicher, die zum Marshalling von Datentypen über die Grenze zwischen nativem und verwaltetem Code verwendet wurden, auf einen Fehler stößt.</span><span class="sxs-lookup"><span data-stu-id="c72b5-103">The `marshalCleanupError` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters an error while attempting to clean up temporary structures and memory used for marshaling data types between native and managed code boundaries.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="c72b5-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="c72b5-104">Symptoms</span></span>  
 <span data-ttu-id="c72b5-105">Beim Übergang von systemeigenem zu verwaltetem Code tritt Speicherverlust auf, der Laufzeitzustand (wie z. B. die Threadkultur) wird nicht wiederhergestellt oder es treten Fehler beim Bereinigen von <xref:System.Runtime.InteropServices.SafeHandle> auf.</span><span class="sxs-lookup"><span data-stu-id="c72b5-105">A memory leak occurs when making native and managed code transitions, runtime state such as thread culture is not restored, or errors occur in <xref:System.Runtime.InteropServices.SafeHandle> cleanup.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="c72b5-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="c72b5-106">Cause</span></span>  
 <span data-ttu-id="c72b5-107">Beim Bereinigen temporärer Strukturen ist ein unerwarteter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c72b5-107">An unexpected error occurred while cleaning up temporary structures.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="c72b5-108">Lösung</span><span class="sxs-lookup"><span data-stu-id="c72b5-108">Resolution</span></span>  
 <span data-ttu-id="c72b5-109">Überprüfen Sie alle Destruktoren-, Finalizer- und benutzerdefinierten Marshallerimplementierungen für <xref:System.Runtime.InteropServices.SafeHandle> auf Fehler.</span><span class="sxs-lookup"><span data-stu-id="c72b5-109">Review all <xref:System.Runtime.InteropServices.SafeHandle> destructor, finalizer, and custom marshaler implementations for errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="c72b5-110">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="c72b5-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="c72b5-111">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="c72b5-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="c72b5-112">Output</span><span class="sxs-lookup"><span data-stu-id="c72b5-112">Output</span></span>  
 <span data-ttu-id="c72b5-113">Eine Meldung über den während der Bereinigung fehlgeschlagenen Vorgang.</span><span class="sxs-lookup"><span data-stu-id="c72b5-113">A message reporting the operation that failed during cleanup.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="c72b5-114">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c72b5-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c72b5-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c72b5-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="c72b5-116">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="c72b5-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="c72b5-117">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="c72b5-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
