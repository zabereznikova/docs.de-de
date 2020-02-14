---
title: illegalPrepareConstrainedRegion-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- PrepareConstrainedRegions method
- managed debugging assistants (MDAs), illegal PrepareConstrainedRegions
- try/catch exception handling, managed debugging assistants
- IllegalPrepareConstrainedRegions MDA
- MDAs (managed debugging assistants), illegal PrepareConstrainedRegions
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
ms.openlocfilehash: b80d6160876834b22e8d9d1eb7112b8b67c15fcc
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216464"
---
# <a name="illegalprepareconstrainedregion-mda"></a><span data-ttu-id="c1419-102">illegalPrepareConstrainedRegion-MDA</span><span class="sxs-lookup"><span data-stu-id="c1419-102">illegalPrepareConstrainedRegion MDA</span></span>
<span data-ttu-id="c1419-103">Der `illegalPrepareConstrainedRegion`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn ein <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType>-Methodenaufruf der `try`-Anweisung des Ausnahmehandlers nicht direkt vorausgeht.</span><span class="sxs-lookup"><span data-stu-id="c1419-103">The `illegalPrepareConstrainedRegion` managed debugging assistant (MDA) is activated when a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> method call does not immediately precede the `try` statement of the exception handler.</span></span> <span data-ttu-id="c1419-104">Diese Einschränkung befindet sich auf MSIL-Ebene, daher ist es zulässig, über nicht codeerzeugende Datenquellen zwischen dem Aufruf und `try`, beispielsweise Kommentare, zu verfügen.</span><span class="sxs-lookup"><span data-stu-id="c1419-104">This restriction is at the MSIL level, so it is permissible to have non-code-generating source between the call and the `try`, such as comments.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="c1419-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="c1419-105">Symptoms</span></span>  
 <span data-ttu-id="c1419-106">Ein eingeschränkter Ausführungsbereich (CER), der nie als solcher behandelt wird, sondern als ein einfacher Block zur Ausnahmebehandlung (`finally` oder `catch`).</span><span class="sxs-lookup"><span data-stu-id="c1419-106">A constrained execution region (CER) that is never treated as such, but as a simple exception handling block (`finally` or `catch`).</span></span> <span data-ttu-id="c1419-107">Daher wird der Bereich nicht im Fall einer Out-of-Memory-Bedingung oder eines Threadabbruchs ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c1419-107">As a consequence, the region does not run in the event of an out-of-memory condition or a thread abort.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="c1419-108">Ursache</span><span class="sxs-lookup"><span data-stu-id="c1419-108">Cause</span></span>  
 <span data-ttu-id="c1419-109">Das Muster zur Vorbereitung für einen CER wird nicht richtig befolgt.</span><span class="sxs-lookup"><span data-stu-id="c1419-109">The preparation pattern for a CER is not followed correctly.</span></span>  <span data-ttu-id="c1419-110">Dies ist ein Fehlerereignis.</span><span class="sxs-lookup"><span data-stu-id="c1419-110">This is an error event.</span></span> <span data-ttu-id="c1419-111">Der <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> Methoden Aufruf, der zum Markieren von Ausnahme Handlern als Einführung eines CERs in der `catch`/`finally`/`fault`/`filter`-Blöcke verwendet wird, muss unmittelbar vor der `try`-Anweisung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c1419-111">The <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method call used to mark exception handlers as introducing a CER in their `catch`/`finally`/`fault`/`filter` blocks must be used immediately before the `try` statement.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="c1419-112">Lösung</span><span class="sxs-lookup"><span data-stu-id="c1419-112">Resolution</span></span>  
 <span data-ttu-id="c1419-113">Stellen Sie sicher, dass der Aufruf von <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> unmittelbar vor der `try`-Anweisung geschieht.</span><span class="sxs-lookup"><span data-stu-id="c1419-113">Ensure that the call to <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> happens immediately before the `try` statement.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="c1419-114">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="c1419-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="c1419-115">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="c1419-115">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="c1419-116">Output</span><span class="sxs-lookup"><span data-stu-id="c1419-116">Output</span></span>  
 <span data-ttu-id="c1419-117">Der MDA zeigt den Namen der Methode an, die die <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>-Methode, den MSIL-Offset und eine Meldung aufruft, die angibt, dass der Aufruf dem Beginn des Try-Blocks nicht direkt vorausgeht.</span><span class="sxs-lookup"><span data-stu-id="c1419-117">The MDA displays the name of the method calling the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method, the MSIL offset, and a message indicating the call does not immediately precede the beginning of the try block.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="c1419-118">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c1419-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="c1419-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1419-119">Example</span></span>  
 <span data-ttu-id="c1419-120">Das folgende Codebeispiel veranschaulicht das Muster, das bewirkt, dass dieser MDA aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="c1419-120">The following code example demonstrates the pattern that causes this MDA to be activated.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c1419-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1419-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>
- [<span data-ttu-id="c1419-122">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="c1419-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="c1419-123">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="c1419-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
