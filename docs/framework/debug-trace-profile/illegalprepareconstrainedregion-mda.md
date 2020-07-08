---
title: illegalPrepareConstrainedRegion-MDA
description: Überprüfen Sie den Assistenten für verwaltetes Debuggen von IllegalPrepareConstrainedRegion, der aufgerufen wird, wenn auf einen PrepareConstrainedRegions-Aufruf nicht eine try-Anweisung folgt.
ms.date: 03/30/2017
helpviewer_keywords:
- PrepareConstrainedRegions method
- managed debugging assistants (MDAs), illegal PrepareConstrainedRegions
- try/catch exception handling, managed debugging assistants
- IllegalPrepareConstrainedRegions MDA
- MDAs (managed debugging assistants), illegal PrepareConstrainedRegions
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
ms.openlocfilehash: d6a0d1d95840ebd735806c5547730ae9e0b2aace
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051284"
---
# <a name="illegalprepareconstrainedregion-mda"></a><span data-ttu-id="10315-103">illegalPrepareConstrainedRegion-MDA</span><span class="sxs-lookup"><span data-stu-id="10315-103">illegalPrepareConstrainedRegion MDA</span></span>
<span data-ttu-id="10315-104">Der `illegalPrepareConstrainedRegion`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn ein <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType>-Methodenaufruf der `try`-Anweisung des Ausnahmehandlers nicht direkt vorausgeht.</span><span class="sxs-lookup"><span data-stu-id="10315-104">The `illegalPrepareConstrainedRegion` managed debugging assistant (MDA) is activated when a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> method call does not immediately precede the `try` statement of the exception handler.</span></span> <span data-ttu-id="10315-105">Diese Einschränkung befindet sich auf MSIL-Ebene, daher ist es zulässig, über nicht codeerzeugende Datenquellen zwischen dem Aufruf und `try`, beispielsweise Kommentare, zu verfügen.</span><span class="sxs-lookup"><span data-stu-id="10315-105">This restriction is at the MSIL level, so it is permissible to have non-code-generating source between the call and the `try`, such as comments.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="10315-106">Symptome</span><span class="sxs-lookup"><span data-stu-id="10315-106">Symptoms</span></span>  
 <span data-ttu-id="10315-107">Ein eingeschränkter Ausführungsbereich (CER), der nie als solcher behandelt wird, sondern als ein einfacher Block zur Ausnahmebehandlung (`finally` oder `catch`).</span><span class="sxs-lookup"><span data-stu-id="10315-107">A constrained execution region (CER) that is never treated as such, but as a simple exception handling block (`finally` or `catch`).</span></span> <span data-ttu-id="10315-108">Daher wird der Bereich nicht im Fall einer Out-of-Memory-Bedingung oder eines Threadabbruchs ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="10315-108">As a consequence, the region does not run in the event of an out-of-memory condition or a thread abort.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="10315-109">Ursache</span><span class="sxs-lookup"><span data-stu-id="10315-109">Cause</span></span>  
 <span data-ttu-id="10315-110">Das Muster zur Vorbereitung für einen CER wird nicht richtig befolgt.</span><span class="sxs-lookup"><span data-stu-id="10315-110">The preparation pattern for a CER is not followed correctly.</span></span>  <span data-ttu-id="10315-111">Dies ist ein Fehlerereignis.</span><span class="sxs-lookup"><span data-stu-id="10315-111">This is an error event.</span></span> <span data-ttu-id="10315-112">Der <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> Methoden Befehl, der zum Markieren von Ausnahme Handlern verwendet wird, um einen CER in ihren Blöcken einzuführen, `catch` / `finally` / `fault` / `filter` muss unmittelbar vor der-Anweisung verwendet werden `try` .</span><span class="sxs-lookup"><span data-stu-id="10315-112">The <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method call used to mark exception handlers as introducing a CER in their `catch`/`finally`/`fault`/`filter` blocks must be used immediately before the `try` statement.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="10315-113">Lösung</span><span class="sxs-lookup"><span data-stu-id="10315-113">Resolution</span></span>  
 <span data-ttu-id="10315-114">Stellen Sie sicher, dass der Aufruf von <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> unmittelbar vor der `try`-Anweisung geschieht.</span><span class="sxs-lookup"><span data-stu-id="10315-114">Ensure that the call to <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> happens immediately before the `try` statement.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="10315-115">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="10315-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="10315-116">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="10315-116">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="10315-117">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="10315-117">Output</span></span>  
 <span data-ttu-id="10315-118">Der MDA zeigt den Namen der Methode an, die die <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>-Methode, den MSIL-Offset und eine Meldung aufruft, die angibt, dass der Aufruf dem Beginn des Try-Blocks nicht direkt vorausgeht.</span><span class="sxs-lookup"><span data-stu-id="10315-118">The MDA displays the name of the method calling the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method, the MSIL offset, and a message indicating the call does not immediately precede the beginning of the try block.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="10315-119">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="10315-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="10315-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10315-120">Example</span></span>  
 <span data-ttu-id="10315-121">Das folgende Codebeispiel veranschaulicht das Muster, das bewirkt, dass dieser MDA aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="10315-121">The following code example demonstrates the pattern that causes this MDA to be activated.</span></span>  
  
```csharp
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="10315-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10315-122">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>
- [<span data-ttu-id="10315-123">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="10315-123">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="10315-124">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="10315-124">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
