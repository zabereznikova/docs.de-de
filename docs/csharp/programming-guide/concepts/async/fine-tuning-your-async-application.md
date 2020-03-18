---
title: Feinabstimmung der Async-Anwendung (C#)
ms.date: 07/20/2015
ms.assetid: 97696eb9-81fc-4940-9655-84daa8eb4d5c
ms.openlocfilehash: cff50e62ff62b70e97e7ea6e03714326d774e407
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "73970243"
---
# <a name="fine-tuning-your-async-application-c"></a><span data-ttu-id="b6ea7-102">Feinabstimmung der Async-Anwendung (C#)</span><span class="sxs-lookup"><span data-stu-id="b6ea7-102">Fine-Tuning Your Async Application (C#)</span></span>
<span data-ttu-id="b6ea7-103">Sie können Genauigkeit und Flexibilität Ihren asynchronen Anwendungen hinzufügen, indem Sie die Methoden und Eigenschaften verwenden, die der <xref:System.Threading.Tasks.Task>-Typ bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b6ea7-103">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="b6ea7-104">Die Themen in diesem Abschnitt zeigen Beispiele, die das <xref:System.Threading.CancellationToken> und wichtige `Task`-Methoden wie <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> verwenden.</span><span class="sxs-lookup"><span data-stu-id="b6ea7-104">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="b6ea7-105">Mit `WhenAny` und `WhenAll` können Sie mehrere Aufgaben leichter starten und ihren Abschluss abwarten, indem Sie eine einzelne Aufgabe überwachen.</span><span class="sxs-lookup"><span data-stu-id="b6ea7-105">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
- <span data-ttu-id="b6ea7-106">`WhenAny` gibt eine Aufgabe zurück, die abgeschlossen wird, wenn jede Aufgabe in einer Auflistung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b6ea7-106">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="b6ea7-107">Beispiele für die Verwendung von `WhenAny` finden Sie unter [Cancel Remaining Async Tasks after One Is Complete (C#) (Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen (C#))](./cancel-remaining-async-tasks-after-one-is-complete.md) und [Start Multiple Async Tasks and Process Them As They Complete (C#) (Mehrere asynchrone Aufgaben starten und nach Abschluss verarbeiten (C#))](./start-multiple-async-tasks-and-process-them-as-they-complete.md).</span><span class="sxs-lookup"><span data-stu-id="b6ea7-107">For examples that use `WhenAny`, see [Cancel Remaining Async Tasks after One Is Complete (C#)](./cancel-remaining-async-tasks-after-one-is-complete.md) and [Start Multiple Async Tasks and Process Them As They Complete (C#)](./start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
- <span data-ttu-id="b6ea7-108">`WhenAll` gibt eine Aufgabe zurück, die abgeschlossen wird, wenn alle Aufgaben in einer Auflistung abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="b6ea7-108">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="b6ea7-109">Weitere Informationen und ein Beispiel, das `WhenAll` verwendet, finden Sie unter [How to extend the async Walkthrough by using Task.WhenAll (C#) (Vorgehensweise: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll (C#))](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="b6ea7-109">For more information and an example that uses `WhenAll`, see [How to extend the async walkthrough by using Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>
  
 <span data-ttu-id="b6ea7-110">Dieser Abschnitt enthält die folgenden Beispiele:</span><span class="sxs-lookup"><span data-stu-id="b6ea7-110">This section includes the following examples.</span></span>  
  
- <span data-ttu-id="b6ea7-111">[Cancel an Async Task or a List of Tasks (C#) (Eine asynchrone Aufgabe oder Aufgabenliste abbrechen (C#))](./cancel-an-async-task-or-a-list-of-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="b6ea7-111">[Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
- [<span data-ttu-id="b6ea7-112">Cancel Async Tasks after a Period of Time (C#) (Asynchrone Aufgaben nach einer Zeitperiode abbrechen (C#))</span><span class="sxs-lookup"><span data-stu-id="b6ea7-112">Cancel Async Tasks after a Period of Time (C#)</span></span>](./cancel-async-tasks-after-a-period-of-time.md)  
  
- [<span data-ttu-id="b6ea7-113">Cancel Remaining Async Tasks after One Is Complete (C#) (Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen (C#))</span><span class="sxs-lookup"><span data-stu-id="b6ea7-113">Cancel Remaining Async Tasks after One Is Complete (C#)</span></span>](./cancel-remaining-async-tasks-after-one-is-complete.md)  
  
- [<span data-ttu-id="b6ea7-114">Start Multiple Async Tasks and Process Them As They Complete (C#) (Mehrere asynchrone Aufgaben starten und nach Abschluss verarbeiten (C#))</span><span class="sxs-lookup"><span data-stu-id="b6ea7-114">Start Multiple Async Tasks and Process Them As They Complete (C#)</span></span>](./start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
> <span data-ttu-id="b6ea7-115">Zum Ausführen der Beispiele müssen Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="b6ea7-115">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="b6ea7-116">Die Projekte erstellen eine Benutzeroberfläche mit einer Schaltfläche zum Starten und einer Schaltfläche zum Abbrechen des Prozesses, wie in der folgenden Abbildung ersichtlich.</span><span class="sxs-lookup"><span data-stu-id="b6ea7-116">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="b6ea7-117">Die Schaltflächen werden mit `startButton` und `cancelButton` bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b6ea7-117">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="b6ea7-118">![WPF-Fenster mit Schaltfläche „Abbrechen“](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Dialogfeld mit einer Schaltfläche „Start“ und einer Schaltfläche „Beenden“")</span><span class="sxs-lookup"><span data-stu-id="b6ea7-118">![WPF window with Cancel button](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Dialog box with a Start and Stop button")</span></span>  
  
 <span data-ttu-id="b6ea7-119">Sie können alle Windows Presentation Foundation (WPF)-Projekte von [Async Sample: Fine Tuning Your Application (Async-Beispiel: Feinabstimmung der Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="b6ea7-119">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6ea7-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6ea7-120">See also</span></span>

- [<span data-ttu-id="b6ea7-121">Asynchrone Programmierung mit „async“ und „await“ (C#)</span><span class="sxs-lookup"><span data-stu-id="b6ea7-121">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
