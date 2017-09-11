---
title: Feinabstimmung der Async-Anwendung (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e031c2e23430a62629424ee57a140a7d8da41777
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="fine-tuning-your-async-application-visual-basic"></a><span data-ttu-id="f8261-102">Feinabstimmung der Async-Anwendung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8261-102">Fine-Tuning Your Async Application (Visual Basic)</span></span>
<span data-ttu-id="f8261-103">Sie können Genauigkeit und Flexibilität Ihren asynchronen Anwendungen hinzufügen, indem Sie mit den Methoden und Eigenschaften, die die <xref:System.Threading.Tasks.Task>Typ zur Verfügung.</xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="f8261-103">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="f8261-104">Die Themen in diesem Abschnitt zeigen Beispiele, in denen <xref:System.Threading.CancellationToken>und wichtige `Task` Methoden wie z. B. <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>und <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> </xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> </xref:System.Threading.CancellationToken></span><span class="sxs-lookup"><span data-stu-id="f8261-104">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="f8261-105">Mit `WhenAny` und `WhenAll` können Sie mehrere Aufgaben leichter starten und ihren Abschluss abwarten, indem Sie eine einzelne Aufgabe überwachen.</span><span class="sxs-lookup"><span data-stu-id="f8261-105">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
-   <span data-ttu-id="f8261-106">`WhenAny` gibt eine Aufgabe zurück, die abgeschlossen wird, wenn jede Aufgabe in einer Auflistung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f8261-106">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="f8261-107">Beispiele für die Verwendung `WhenAny`, finden Sie unter [Abbrechen verbleibende asynchrone Aufgaben nach einem abgeschlossen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)und [mehrere asynchrone Aufgaben starten und verarbeiten Sie als sie vollständige (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span><span class="sxs-lookup"><span data-stu-id="f8261-107">For examples that use `WhenAny`, see  [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)and [Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
-   <span data-ttu-id="f8261-108">`WhenAll` gibt eine Aufgabe zurück, die abgeschlossen wird, wenn alle Aufgaben in einer Auflistung abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="f8261-108">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="f8261-109">Weitere Informationen und ein Beispiel, `WhenAll`, finden Sie unter [Gewusst wie: Erweitern der asynchronen Walkthrough durch Verwendung Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="f8261-109">For more information and an example that uses `WhenAll`, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="f8261-110">Dieser Abschnitt enthält die folgenden Beispiele:</span><span class="sxs-lookup"><span data-stu-id="f8261-110">This section includes the following examples.</span></span>  
  
-   <span data-ttu-id="f8261-111">[Eine asynchrone Aufgabe oder eine Liste von Aufgaben (Visual Basic) Abbrechen](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="f8261-111">[Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
-   [<span data-ttu-id="f8261-112">Brechen Sie asynchrone Aufgaben ab, nachdem eine bestimmte Zeitspanne (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8261-112">Cancel Async Tasks after a Period of Time (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [<span data-ttu-id="f8261-113">Abbrechen Sie verbleibende asynchrone Aufgaben nach einer vollständigen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8261-113">Cancel Remaining Async Tasks after One Is Complete (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [<span data-ttu-id="f8261-114">Mehrere asynchrone Aufgaben starten und Abschließen von (Visual Basic) verarbeiten</span><span class="sxs-lookup"><span data-stu-id="f8261-114">Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  <span data-ttu-id="f8261-115">Zum Ausführen der Beispiele müssen Sie Visual Studio 2012 oder höher und .NET Framework 4.5 oder höher auf Ihrem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="f8261-115">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="f8261-116">Die Projekte erstellen eine Benutzeroberfläche mit einer Schaltfläche zum Starten und einer Schaltfläche zum Abbrechen des Prozesses, wie in der folgenden Abbildung ersichtlich.</span><span class="sxs-lookup"><span data-stu-id="f8261-116">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="f8261-117">Die Schaltflächen werden mit `startButton` und `cancelButton` bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f8261-117">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="f8261-118">![WPF-Fenster mit Schaltfläche "Abbrechen"](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "Abbruch")</span><span class="sxs-lookup"><span data-stu-id="f8261-118">![WPF window with Cancel button](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "Cancellation")</span></span>  
  
 <span data-ttu-id="f8261-119">Sie können die vollständige Windows Presentation Foundation (WPF)-Projekte von [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span><span class="sxs-lookup"><span data-stu-id="f8261-119">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8261-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8261-120">See Also</span></span>  
 [<span data-ttu-id="f8261-121">Asynchrone Programmierung mit Async und Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8261-121">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)
