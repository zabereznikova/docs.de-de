---
title: marshalCleanupError-MDA
description: Überprüfen Sie den "marshalCleanupError Managed Debug Assistant" (MDA), der aufgerufen wird, weil ein unerwarteter Fehler beim Bereinigen von temporären Strukturen aufgetreten ist.
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
ms.openlocfilehash: 3c7498d6f51484de3a2e84d611a2634f53724ab6
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051609"
---
# <a name="marshalcleanuperror-mda"></a><span data-ttu-id="b2fdc-103">marshalCleanupError-MDA</span><span class="sxs-lookup"><span data-stu-id="b2fdc-103">marshalCleanupError MDA</span></span>
<span data-ttu-id="b2fdc-104">Der `marshalCleanupError`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die Common Language Runtime (CLR) beim Bereinigen von temporären Strukturen und Arbeitsspeicher, die zum Marshalling von Datentypen über die Grenze zwischen nativem und verwaltetem Code verwendet wurden, auf einen Fehler stößt.</span><span class="sxs-lookup"><span data-stu-id="b2fdc-104">The `marshalCleanupError` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters an error while attempting to clean up temporary structures and memory used for marshaling data types between native and managed code boundaries.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="b2fdc-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="b2fdc-105">Symptoms</span></span>  
 <span data-ttu-id="b2fdc-106">Beim Übergang von systemeigenem zu verwaltetem Code tritt Speicherverlust auf, der Laufzeitzustand (wie z. B. die Threadkultur) wird nicht wiederhergestellt oder es treten Fehler beim Bereinigen von <xref:System.Runtime.InteropServices.SafeHandle> auf.</span><span class="sxs-lookup"><span data-stu-id="b2fdc-106">A memory leak occurs when making native and managed code transitions, runtime state such as thread culture is not restored, or errors occur in <xref:System.Runtime.InteropServices.SafeHandle> cleanup.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="b2fdc-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="b2fdc-107">Cause</span></span>  
 <span data-ttu-id="b2fdc-108">Beim Bereinigen temporärer Strukturen ist ein unerwarteter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b2fdc-108">An unexpected error occurred while cleaning up temporary structures.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="b2fdc-109">Lösung</span><span class="sxs-lookup"><span data-stu-id="b2fdc-109">Resolution</span></span>  
 <span data-ttu-id="b2fdc-110">Überprüfen Sie alle Destruktoren-, Finalizer- und benutzerdefinierten Marshallerimplementierungen für <xref:System.Runtime.InteropServices.SafeHandle> auf Fehler.</span><span class="sxs-lookup"><span data-stu-id="b2fdc-110">Review all <xref:System.Runtime.InteropServices.SafeHandle> destructor, finalizer, and custom marshaler implementations for errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="b2fdc-111">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b2fdc-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="b2fdc-112">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="b2fdc-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="b2fdc-113">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="b2fdc-113">Output</span></span>  
 <span data-ttu-id="b2fdc-114">Eine Meldung über den während der Bereinigung fehlgeschlagenen Vorgang.</span><span class="sxs-lookup"><span data-stu-id="b2fdc-114">A message reporting the operation that failed during cleanup.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="b2fdc-115">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b2fdc-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2fdc-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2fdc-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="b2fdc-117">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="b2fdc-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="b2fdc-118">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="b2fdc-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
