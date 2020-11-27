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
ms.openlocfilehash: 7cbf04e8605ccf18e89882dd09b96cc7c59330c9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272786"
---
# <a name="illegalprepareconstrainedregion-mda"></a><span data-ttu-id="f9496-103">illegalPrepareConstrainedRegion-MDA</span><span class="sxs-lookup"><span data-stu-id="f9496-103">illegalPrepareConstrainedRegion MDA</span></span>

<span data-ttu-id="f9496-104">Der `illegalPrepareConstrainedRegion`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn ein <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType>-Methodenaufruf der `try`-Anweisung des Ausnahmehandlers nicht direkt vorausgeht.</span><span class="sxs-lookup"><span data-stu-id="f9496-104">The `illegalPrepareConstrainedRegion` managed debugging assistant (MDA) is activated when a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> method call does not immediately precede the `try` statement of the exception handler.</span></span> <span data-ttu-id="f9496-105">Diese Einschränkung befindet sich auf MSIL-Ebene, daher ist es zulässig, über nicht codeerzeugende Datenquellen zwischen dem Aufruf und `try`, beispielsweise Kommentare, zu verfügen.</span><span class="sxs-lookup"><span data-stu-id="f9496-105">This restriction is at the MSIL level, so it is permissible to have non-code-generating source between the call and the `try`, such as comments.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f9496-106">Symptome</span><span class="sxs-lookup"><span data-stu-id="f9496-106">Symptoms</span></span>  

 <span data-ttu-id="f9496-107">Ein eingeschränkter Ausführungsbereich (CER), der nie als solcher behandelt wird, sondern als ein einfacher Block zur Ausnahmebehandlung (`finally` oder `catch`).</span><span class="sxs-lookup"><span data-stu-id="f9496-107">A constrained execution region (CER) that is never treated as such, but as a simple exception handling block (`finally` or `catch`).</span></span> <span data-ttu-id="f9496-108">Daher wird der Bereich nicht im Fall einer Out-of-Memory-Bedingung oder eines Threadabbruchs ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f9496-108">As a consequence, the region does not run in the event of an out-of-memory condition or a thread abort.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f9496-109">Ursache</span><span class="sxs-lookup"><span data-stu-id="f9496-109">Cause</span></span>  

 <span data-ttu-id="f9496-110">Das Muster zur Vorbereitung für einen CER wird nicht richtig befolgt.</span><span class="sxs-lookup"><span data-stu-id="f9496-110">The preparation pattern for a CER is not followed correctly.</span></span>  <span data-ttu-id="f9496-111">Dies ist ein Fehlerereignis.</span><span class="sxs-lookup"><span data-stu-id="f9496-111">This is an error event.</span></span> <span data-ttu-id="f9496-112">Der <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> Methoden Befehl, der zum Markieren von Ausnahme Handlern verwendet wird, um einen CER in ihren Blöcken einzuführen, `catch` / `finally` / `fault` / `filter` muss unmittelbar vor der-Anweisung verwendet werden `try` .</span><span class="sxs-lookup"><span data-stu-id="f9496-112">The <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method call used to mark exception handlers as introducing a CER in their `catch`/`finally`/`fault`/`filter` blocks must be used immediately before the `try` statement.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f9496-113">Lösung</span><span class="sxs-lookup"><span data-stu-id="f9496-113">Resolution</span></span>  

 <span data-ttu-id="f9496-114">Stellen Sie sicher, dass der Aufruf von <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> unmittelbar vor der `try`-Anweisung geschieht.</span><span class="sxs-lookup"><span data-stu-id="f9496-114">Ensure that the call to <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> happens immediately before the `try` statement.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f9496-115">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f9496-115">Effect on the Runtime</span></span>  

 <span data-ttu-id="f9496-116">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="f9496-116">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f9496-117">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="f9496-117">Output</span></span>  

 <span data-ttu-id="f9496-118">Der MDA zeigt den Namen der Methode an, die die <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>-Methode, den MSIL-Offset und eine Meldung aufruft, die angibt, dass der Aufruf dem Beginn des Try-Blocks nicht direkt vorausgeht.</span><span class="sxs-lookup"><span data-stu-id="f9496-118">The MDA displays the name of the method calling the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method, the MSIL offset, and a message indicating the call does not immediately precede the beginning of the try block.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f9496-119">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="f9496-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="f9496-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9496-120">Example</span></span>  

 <span data-ttu-id="f9496-121">Das folgende Codebeispiel veranschaulicht das Muster, das bewirkt, dass dieser MDA aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="f9496-121">The following code example demonstrates the pattern that causes this MDA to be activated.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f9496-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f9496-122">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>
- [<span data-ttu-id="f9496-123">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="f9496-123">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f9496-124">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="f9496-124">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
