---
title: Feinabstimmung der Async-Anwendung
ms.date: 07/20/2015
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
ms.openlocfilehash: 6ad4f9a526e0497029ff8ddc3e93637a4f9acb00
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075433"
---
# <a name="fine-tuning-your-async-application-visual-basic"></a><span data-ttu-id="720a4-102">Fine-Tuning Your Async Application (Visual Basic) (Feinabstimmung der Async-Anwendung (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="720a4-102">Fine-Tuning Your Async Application (Visual Basic)</span></span>

<span data-ttu-id="720a4-103">Sie können Genauigkeit und Flexibilität Ihren asynchronen Anwendungen hinzufügen, indem Sie die Methoden und Eigenschaften verwenden, die der <xref:System.Threading.Tasks.Task>-Typ bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="720a4-103">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="720a4-104">Die Themen in diesem Abschnitt zeigen Beispiele, die das <xref:System.Threading.CancellationToken> und wichtige `Task`-Methoden wie <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> verwenden.</span><span class="sxs-lookup"><span data-stu-id="720a4-104">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="720a4-105">Mit `WhenAny` und `WhenAll` können Sie mehrere Aufgaben leichter starten und ihren Abschluss abwarten, indem Sie eine einzelne Aufgabe überwachen.</span><span class="sxs-lookup"><span data-stu-id="720a4-105">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
- <span data-ttu-id="720a4-106">`WhenAny` gibt eine Aufgabe zurück, die abgeschlossen wird, wenn jede Aufgabe in einer Auflistung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="720a4-106">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="720a4-107">Beispiele für die Verwendung von `WhenAny` finden Sie unter  [Abbrechen verbleibende asynchroner Aufgaben nach Abschluss eines Vorgangs (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md)und [Starten mehrerer asynchroner Aufgaben und Verarbeiten der Aufgaben nach Abschluss (Visual Basic)](start-multiple-async-tasks-and-process-them-as-they-complete.md).</span><span class="sxs-lookup"><span data-stu-id="720a4-107">For examples that use `WhenAny`, see  [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md)and [Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
- <span data-ttu-id="720a4-108">`WhenAll` gibt eine Aufgabe zurück, die abgeschlossen wird, wenn alle Aufgaben in einer Auflistung abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="720a4-108">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="720a4-109">Weitere Informationen und ein Beispiel, in dem verwendet wird, finden Sie unter Gewusst wie: Erweitern der asynchronen exemplarischen Vorgehensweise `WhenAll` [mithilfe von "Task. alle" (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="720a4-109">For more information and an example that uses `WhenAll`, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="720a4-110">Dieser Abschnitt enthält die folgenden Beispiele:</span><span class="sxs-lookup"><span data-stu-id="720a4-110">This section includes the following examples.</span></span>  
  
- <span data-ttu-id="720a4-111">[Abbrechen einer Async-Aufgabe oder einer Aufgabenliste (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="720a4-111">[Cancel an Async Task or a List of Tasks (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
- [<span data-ttu-id="720a4-112">Asynchrone Aufgaben nach einer Zeitperiode abbrechen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="720a4-112">Cancel Async Tasks after a Period of Time (Visual Basic)</span></span>](cancel-async-tasks-after-a-period-of-time.md)  
  
- <span data-ttu-id="720a4-113">[Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md) (Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="720a4-113">[Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md)</span></span>  
  
- <span data-ttu-id="720a4-114">[Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](start-multiple-async-tasks-and-process-them-as-they-complete.md) (Mehrere asynchrone Aufgaben starten und nach Abschluss verarbeiten (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="720a4-114">[Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](start-multiple-async-tasks-and-process-them-as-they-complete.md)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="720a4-115">Zum Ausführen der Beispiele müssen Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="720a4-115">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="720a4-116">Die Projekte erstellen eine Benutzeroberfläche mit einer Schaltfläche zum Starten und einer Schaltfläche zum Abbrechen des Prozesses, wie in der folgenden Abbildung ersichtlich.</span><span class="sxs-lookup"><span data-stu-id="720a4-116">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="720a4-117">Die Schaltflächen werden mit `startButton` und `cancelButton` bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="720a4-117">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="720a4-118">![WPF-Fenster mit Schaltfläche „Abbrechen“](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Dialogfeld mit einer Schaltfläche „Start“ und einer Schaltfläche „Beenden“")</span><span class="sxs-lookup"><span data-stu-id="720a4-118">![WPF window with Cancel button](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Dialog box with a Start and Stop button")</span></span>  
  
 <span data-ttu-id="720a4-119">Sie können alle Windows Presentation Foundation (WPF)-Projekte von [Async Sample: Fine Tuning Your Application (Asynchrones Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="720a4-119">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="720a4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="720a4-120">See also</span></span>

- [<span data-ttu-id="720a4-121">Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="720a4-121">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
