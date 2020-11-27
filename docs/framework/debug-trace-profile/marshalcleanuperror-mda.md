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
ms.openlocfilehash: e65136f022caa7b1e18a27f7b97a4ef4c27f42d3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271188"
---
# <a name="marshalcleanuperror-mda"></a><span data-ttu-id="d05d3-103">marshalCleanupError-MDA</span><span class="sxs-lookup"><span data-stu-id="d05d3-103">marshalCleanupError MDA</span></span>

<span data-ttu-id="d05d3-104">Der `marshalCleanupError`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die Common Language Runtime (CLR) beim Bereinigen von temporären Strukturen und Arbeitsspeicher, die zum Marshalling von Datentypen über die Grenze zwischen nativem und verwaltetem Code verwendet wurden, auf einen Fehler stößt.</span><span class="sxs-lookup"><span data-stu-id="d05d3-104">The `marshalCleanupError` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters an error while attempting to clean up temporary structures and memory used for marshaling data types between native and managed code boundaries.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="d05d3-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="d05d3-105">Symptoms</span></span>  

 <span data-ttu-id="d05d3-106">Beim Übergang von systemeigenem zu verwaltetem Code tritt Speicherverlust auf, der Laufzeitzustand (wie z. B. die Threadkultur) wird nicht wiederhergestellt oder es treten Fehler beim Bereinigen von <xref:System.Runtime.InteropServices.SafeHandle> auf.</span><span class="sxs-lookup"><span data-stu-id="d05d3-106">A memory leak occurs when making native and managed code transitions, runtime state such as thread culture is not restored, or errors occur in <xref:System.Runtime.InteropServices.SafeHandle> cleanup.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="d05d3-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="d05d3-107">Cause</span></span>  

 <span data-ttu-id="d05d3-108">Beim Bereinigen temporärer Strukturen ist ein unerwarteter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d05d3-108">An unexpected error occurred while cleaning up temporary structures.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="d05d3-109">Lösung</span><span class="sxs-lookup"><span data-stu-id="d05d3-109">Resolution</span></span>  

 <span data-ttu-id="d05d3-110">Überprüfen Sie alle Destruktoren-, Finalizer- und benutzerdefinierten Marshallerimplementierungen für <xref:System.Runtime.InteropServices.SafeHandle> auf Fehler.</span><span class="sxs-lookup"><span data-stu-id="d05d3-110">Review all <xref:System.Runtime.InteropServices.SafeHandle> destructor, finalizer, and custom marshaler implementations for errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="d05d3-111">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="d05d3-111">Effect on the Runtime</span></span>  

 <span data-ttu-id="d05d3-112">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="d05d3-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d05d3-113">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="d05d3-113">Output</span></span>  

 <span data-ttu-id="d05d3-114">Eine Meldung über den während der Bereinigung fehlgeschlagenen Vorgang.</span><span class="sxs-lookup"><span data-stu-id="d05d3-114">A message reporting the operation that failed during cleanup.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="d05d3-115">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d05d3-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d05d3-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d05d3-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="d05d3-117">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="d05d3-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="d05d3-118">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="d05d3-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
