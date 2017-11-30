---
title: 'Gewusst wie: Implementieren eines Clients des ereignisbasierten asynchronen Musters'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b70d4ba205d39ad8fcbc7c7f6fa1f5b34a36c98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a><span data-ttu-id="20b9d-102">Gewusst wie: Implementieren eines Clients des ereignisbasierten asynchronen Musters</span><span class="sxs-lookup"><span data-stu-id="20b9d-102">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="20b9d-103">Im folgenden Codebeispiel wird veranschaulicht, wie Sie eine Komponente, die entspricht der [Übersicht über ereignisbasierte asynchrone Muster](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="20b9d-103">The following code example demonstrates how to use a component that adheres to the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span> <span data-ttu-id="20b9d-104">Das Formular für dieses Beispiel verwendet die `PrimeNumberCalculator` Komponente, die in beschriebenen [wie: implementieren eine Komponente, die das ereignisbasierte asynchrone Muster unterstützt](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="20b9d-104">The form for this example uses the `PrimeNumberCalculator` component described in [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>  
  
 <span data-ttu-id="20b9d-105">Wenn Sie ein Projekt, die in diesem Beispiel verwendet ausführen, wird ein Formular "Primzahl Calculator" mit zwei Schaltflächen und ein Raster angezeigt: **neuen Task starten** und **"Abbrechen"**.</span><span class="sxs-lookup"><span data-stu-id="20b9d-105">When you run a project that uses this example, you will see a "Prime Number Calculator" form with a grid and two buttons: **Start New Task** and **Cancel**.</span></span> <span data-ttu-id="20b9d-106">Klicken Sie auf die **neuen Task starten** mehrmals nacheinander die Schaltfläche, und klicken, startet ein asynchroner Vorgang eine Berechnung aus, um festzustellen, ob eine zufällig generierter Testzahl eine Primzahl ist.</span><span class="sxs-lookup"><span data-stu-id="20b9d-106">You can click the **Start New Task** button several times in succession, and for each click, an asynchronous operation will begin a computation to determine if a randomly generated test number is prime.</span></span> <span data-ttu-id="20b9d-107">Das Formular wird in regelmäßigen Abständen und inkrementelle Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="20b9d-107">The form will periodically display progress and incremental results.</span></span> <span data-ttu-id="20b9d-108">Jeder Vorgang ist eine eindeutige Aufgaben-ID zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="20b9d-108">Each operation is assigned a unique task ID.</span></span> <span data-ttu-id="20b9d-109">Das Ergebnis der Berechnung wird angezeigt, der **Ergebnis** Spalte; Wenn die Anzahl der Tests keine Primzahl ist, wird Sie als beschriftet **zusammengesetzt –** und seine erste Divisor wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20b9d-109">The result of the computation is displayed in the **Result** column; if the test number is not prime, it is labeled as **Composite,** and its first divisor is displayed.</span></span>  
  
 <span data-ttu-id="20b9d-110">Alle ausstehenden Vorgang abgebrochen werden kann, mit der **"Abbrechen"** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="20b9d-110">Any pending operation can be canceled with the **Cancel** button.</span></span> <span data-ttu-id="20b9d-111">Mehrfachauswahl können vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="20b9d-111">Multiple selections can be made.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20b9d-112">Die meisten Zahlen ist es sich um Primzahlen nicht.</span><span class="sxs-lookup"><span data-stu-id="20b9d-112">Most numbers will not be prime.</span></span> <span data-ttu-id="20b9d-113">Wenn Sie nicht nach mehreren abgeschlossenen Vorgänge eine Primzahl gefunden haben, einfach weitere Aufgaben starten und schließlich finden Sie einige Primzahlen.</span><span class="sxs-lookup"><span data-stu-id="20b9d-113">If you have not found a prime number after several completed operations, simply start more tasks, and eventually you will find some prime numbers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20b9d-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="20b9d-114">Example</span></span>  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="20b9d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20b9d-115">See Also</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
