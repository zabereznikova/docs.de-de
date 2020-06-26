---
title: asynchronousThreadAbort-MDA
description: Überprüfen Sie, wie der AsynchronousThreadAbort-Assistent für verwaltetes Debuggen (MDA) aktiviert wird, wenn ein Thread versucht, einen asynchronen Abbruch in einen anderen Thread einzufügen.
ms.date: 03/30/2017
helpviewer_keywords:
- asynchronous thread aborts
- AsynchronousThreadAbort MDA
- managed debugging assistants (MDAs), asynchronous thread aborts
- threading [.NET Framework], managed debugging assistants
- MDAs (managed debugging assistants), asynchronous thread aborts
ms.assetid: 9ebe40b2-d703-421e-8660-984acc42bfe0
ms.openlocfilehash: 469372d57d9c21198353d171fec16458691eb25d
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415666"
---
# <a name="asynchronousthreadabort-mda"></a><span data-ttu-id="a690e-103">asynchronousThreadAbort-MDA</span><span class="sxs-lookup"><span data-stu-id="a690e-103">asynchronousThreadAbort MDA</span></span>
<span data-ttu-id="a690e-104">Der `asynchronousThreadAbort`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn ein Thread versucht, einen asynchronen Abbruch in einem anderen Thread hervorzurufen.</span><span class="sxs-lookup"><span data-stu-id="a690e-104">The `asynchronousThreadAbort` managed debugging assistant (MDA) is activated when a thread attempts to introduce an asynchronous abort into another thread.</span></span> <span data-ttu-id="a690e-105">Der `asynchronousThreadAbort`-MDA wird nicht durch synchrone Threadabbrüche aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a690e-105">Synchronous thread aborts do not activate the `asynchronousThreadAbort` MDA.</span></span>

## <a name="symptoms"></a><span data-ttu-id="a690e-106">Symptome</span><span class="sxs-lookup"><span data-stu-id="a690e-106">Symptoms</span></span>
 <span data-ttu-id="a690e-107">Eine Anwendung stürzt mit einer nicht behandelten <xref:System.Threading.ThreadAbortException> ab, wenn der Thread der Hauptanwendung abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="a690e-107">An application crashes with an unhandled <xref:System.Threading.ThreadAbortException> when the main application thread is aborted.</span></span> <span data-ttu-id="a690e-108">Die Folgen der fortgesetzten Ausführung dieser Anwendung sind möglicherweise schwerwiegender als ein Absturz und können zur weiteren Beschädigung von Daten führen.</span><span class="sxs-lookup"><span data-stu-id="a690e-108">If the application were to continue to execute, the consequences might be worse than the application crashing, possibly resulting in further data corruption.</span></span>

 <span data-ttu-id="a690e-109">Als unteilbar konzipierte Vorgänge wurden wahrscheinlich nach der partiellen Fertigstellung unterbrochen. Dadurch befinden sich die Anwendungsdaten nun in einem nicht vorhersagbaren Zustand.</span><span class="sxs-lookup"><span data-stu-id="a690e-109">Operations meant to be atomic have likely been interrupted after partial completion, leaving application data in an unpredictable state.</span></span> <span data-ttu-id="a690e-110">Eine <xref:System.Threading.ThreadAbortException> kann während der Ausführung von Programmcode an scheinbar zufälligen Stellen generiert werden, häufig auch an Stellen, an denen das Auslösen einer Ausnahme nicht zu erwarten war.</span><span class="sxs-lookup"><span data-stu-id="a690e-110">A <xref:System.Threading.ThreadAbortException> can be generated from seemingly random points in the execution of code, often in places from which an exception is not expected to arise.</span></span> <span data-ttu-id="a690e-111">Der Code ist möglicherweise nicht in der Lage, so eine Ausnahme zu behandeln. Dies führt zu einem fehlerhaften Zustand.</span><span class="sxs-lookup"><span data-stu-id="a690e-111">The code might not be capable of handling such an exception, resulting in a corrupt state.</span></span>

 <span data-ttu-id="a690e-112">Die Symptome sind aufgrund der Zufälligkeit dieses Problems breit gefächert.</span><span class="sxs-lookup"><span data-stu-id="a690e-112">Symptoms can vary widely due to the randomness inherent to the problem.</span></span>

## <a name="cause"></a><span data-ttu-id="a690e-113">Ursache</span><span class="sxs-lookup"><span data-stu-id="a690e-113">Cause</span></span>
 <span data-ttu-id="a690e-114">Die <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>-Methode wurde aus dem Code in einem Thread für einen Zielthread aufgerufen, um einen asynchronen Threadabbruch hervorzurufen.</span><span class="sxs-lookup"><span data-stu-id="a690e-114">Code in one thread called the <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method on a target thread to introduce an asynchronous thread abort.</span></span> <span data-ttu-id="a690e-115">Der Threadabbruch ist asynchron, da der die <xref:System.Threading.Thread.Abort%2A>-Methode aufrufende Code in einem anderen Thread ausgeführt wird als das Ziel des Abbruchvorgangs.</span><span class="sxs-lookup"><span data-stu-id="a690e-115">The thread abort is asynchronous because the code that makes the call to <xref:System.Threading.Thread.Abort%2A> is running on a different thread than the target of the abort operation.</span></span> <span data-ttu-id="a690e-116">Synchrone Threadabbrüche stellen in der Regel kein Problem dar, da ein Thread die <xref:System.Threading.Thread.Abort%2A>-Methode dabei nur an einem sicheren Anhaltepunkt aufrufen sollte, an dem sich die Anwendung in einem konsistenten Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="a690e-116">Synchronous thread aborts should not cause a problem because the thread performing the <xref:System.Threading.Thread.Abort%2A> should have done so only at a safe checkpoint where application state is consistent.</span></span>

 <span data-ttu-id="a690e-117">Asynchrone Threadabbrüche führen zu Problemen, da sie an nicht vorhersagbaren Stellen der Ausführung des Zielthreads verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="a690e-117">Asynchronous thread aborts present a problem because they are processed at unpredictable points in the target thread's execution.</span></span> <span data-ttu-id="a690e-118">In einem Thread ausgeführter Code, der möglicherweise asynchron abgebrochen wird, müsste zum Vermeiden dieses Problems für jede einzelne Codezeile eine <xref:System.Threading.ThreadAbortException> abfangen können, um dafür zu sorgen, dass die Anwendungsdaten anschließend in einem konsistenten Zustand vorliegen.</span><span class="sxs-lookup"><span data-stu-id="a690e-118">To avoid this, code written to run on a thread that might be aborted in this manner would need to handle a <xref:System.Threading.ThreadAbortException> at almost every line of code, taking care to put application data back into a consistent state.</span></span> <span data-ttu-id="a690e-119">Es ist jedoch unrealistisch zu erwarten, dass Code unter Berücksichtigung dieses Problems erstellt wurde, oder selbst Code zu verfassen, der Schutz vor allen möglichen Umständen bietet.</span><span class="sxs-lookup"><span data-stu-id="a690e-119">It is not realistic to expect code to be written with this problem in mind or to write code that protects against all possible circumstances.</span></span>

 <span data-ttu-id="a690e-120">Aufrufe von nicht verwaltetem Code und von `finally`-Blöcken werden nicht asynchron abgebrochen, sondern sofort nach dem Verlassen einer dieser Kategorien.</span><span class="sxs-lookup"><span data-stu-id="a690e-120">Calls into unmanaged code and `finally` blocks will not be aborted asynchronously but immediately upon exit from one of these categories.</span></span>

 <span data-ttu-id="a690e-121">Aufgrund des willkürlichen Auftretens dieses Problems ist die Ursache möglicherweise schwer zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="a690e-121">The cause might be difficult to determine due to the randomness inherent to the problem.</span></span>

## <a name="resolution"></a><span data-ttu-id="a690e-122">Lösung</span><span class="sxs-lookup"><span data-stu-id="a690e-122">Resolution</span></span>
 <span data-ttu-id="a690e-123">Vermeiden Sie Codeentwürfe, die die Verwendung asynchroner Threadabbrüche erfordern.</span><span class="sxs-lookup"><span data-stu-id="a690e-123">Avoid code design that requires the use of asynchronous thread aborts.</span></span> <span data-ttu-id="a690e-124">Es gibt mehrere besser geeignete Verfahren zum Unterbrechen eines Zielthreads, die keinen Aufruf von <xref:System.Threading.Thread.Abort%2A> erfordern.</span><span class="sxs-lookup"><span data-stu-id="a690e-124">There are several approaches more appropriate for interruption of a target thread that do not require a call to <xref:System.Threading.Thread.Abort%2A>.</span></span> <span data-ttu-id="a690e-125">Am sichersten ist der Einsatz eines Mechanismus, z.B. eine gemeinsame Eigenschaft, mit der dem Zielprozess die Unterbrechungsanforderung signalisiert wird.</span><span class="sxs-lookup"><span data-stu-id="a690e-125">The safest is to introduce a mechanism, such as a common property, that signals the target thread to request an interrupt.</span></span> <span data-ttu-id="a690e-126">Der Zielthread prüft an bestimmten sicheren Anhaltepunkten, ob das Signal übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="a690e-126">The target thread checks the signal at certain safe checkpoints.</span></span> <span data-ttu-id="a690e-127">Wenn eine Unterbrechungsanforderung festgestellt wird, kann der Thread ordnungsgemäß beendet werden.</span><span class="sxs-lookup"><span data-stu-id="a690e-127">If it notices that an interrupt has been requested, it can shut down gracefully.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="a690e-128">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a690e-128">Effect on the Runtime</span></span>
 <span data-ttu-id="a690e-129">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="a690e-129">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="a690e-130">Es werden nur Angaben zu asynchronen Threadabbrüchen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="a690e-130">It only reports data about asynchronous thread aborts.</span></span>

## <a name="output"></a><span data-ttu-id="a690e-131">Output</span><span class="sxs-lookup"><span data-stu-id="a690e-131">Output</span></span>
 <span data-ttu-id="a690e-132">Der MDA meldet die ID des Threads, der den Abbruch durchführt, und die ID des Zielthreads für den Abbruch.</span><span class="sxs-lookup"><span data-stu-id="a690e-132">The MDA reports the ID of the thread performing the abort and the ID of the thread that is the target of the abort.</span></span> <span data-ttu-id="a690e-133">Diese sind niemals gleich, da dieses Problem auf asynchrone Abbrüche beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="a690e-133">These will never be the same because this is limited to asynchronous aborts.</span></span>

## <a name="configuration"></a><span data-ttu-id="a690e-134">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a690e-134">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <asynchronousThreadAbort />
  </assistants>
</mdaConfig>
```

## <a name="example"></a><span data-ttu-id="a690e-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a690e-135">Example</span></span>
 <span data-ttu-id="a690e-136">Zum Aktivieren des `asynchronousThreadAbort`-MDA genügt ein Aufruf von <xref:System.Threading.Thread.Abort%2A> für einen separaten laufenden Thread.</span><span class="sxs-lookup"><span data-stu-id="a690e-136">Activating the `asynchronousThreadAbort` MDA requires only a call to <xref:System.Threading.Thread.Abort%2A> on a separate running thread.</span></span> <span data-ttu-id="a690e-137">Bedenken Sie die Folgen, wenn der Inhalt der Threadstartfunktion aus einer Reihe komplexerer Vorgänge bestehen würde, die an jedem beliebigen Punkt durch den Abbruch unterbrochen werden können.</span><span class="sxs-lookup"><span data-stu-id="a690e-137">Consider the consequences if the contents of the thread start function were a set of more complex operations which might be interrupted at any arbitrary point by the abort.</span></span>

```csharp
using System.Threading;
void FireMda()
{
    Thread t = new Thread(delegate() { Thread.Sleep(1000); });
    t.Start();
    // The following line activates the MDA.
    t.Abort();
    t.Join();
}
```

## <a name="see-also"></a><span data-ttu-id="a690e-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a690e-138">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="a690e-139">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="a690e-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
