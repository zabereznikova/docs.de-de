---
title: 'Gewusst wie: Implementieren eines Clients des ereignisbasierten asynchronen Musters'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET], asynchronous features
- components [.NET], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
ms.openlocfilehash: 14d515ba84a9437499f4d5a75b1112990df05de6
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830375"
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a><span data-ttu-id="69431-102">Gewusst wie: Implementieren eines Clients des ereignisbasierten asynchronen Musters</span><span class="sxs-lookup"><span data-stu-id="69431-102">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="69431-103">Im folgenden Codebeispiel wird veranschaulicht, wie Sie eine Komponente entsprechend der [Übersicht über ereignisbasierte asynchrone Muster](event-based-asynchronous-pattern-overview.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="69431-103">The following code example demonstrates how to use a component that adheres to the [Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md).</span></span> <span data-ttu-id="69431-104">Das Formular für dieses Beispiel verwendet die `PrimeNumberCalculator`-Komponente, die unter [Gewusst wie: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt](component-that-supports-the-event-based-asynchronous-pattern.md) beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="69431-104">The form for this example uses the `PrimeNumberCalculator` component described in [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>  
  
 <span data-ttu-id="69431-105">Wenn Sie ein Projekt mit diesem Beispiel ausführen, wird ein Formular namens „Primzahlenrechner“ mit einem Raster und zwei Schaltflächen angezeigt: **Neuen Task starten** und **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="69431-105">When you run a project that uses this example, you will see a "Prime Number Calculator" form with a grid and two buttons: **Start New Task** and **Cancel**.</span></span> <span data-ttu-id="69431-106">Klicken Sie mehrmals hintereinander auf die Schaltfläche **Neuen Task starten**. Bei jedem Klick wird durch einen asynchronen Vorgang eine Berechnung gestartet, um festzustellen, ob es sich bei einer zufällig generierten Testzahl um eine Primzahl handelt.</span><span class="sxs-lookup"><span data-stu-id="69431-106">You can click the **Start New Task** button several times in succession, and for each click, an asynchronous operation will begin a computation to determine if a randomly generated test number is prime.</span></span> <span data-ttu-id="69431-107">Das Formular zeigt in regelmäßigen Abständen den Status und inkrementelle Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="69431-107">The form will periodically display progress and incremental results.</span></span> <span data-ttu-id="69431-108">Jeder Vorgang ist einer eindeutige Aufgaben-ID zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="69431-108">Each operation is assigned a unique task ID.</span></span> <span data-ttu-id="69431-109">Das Ergebnis der Berechnung wird in der Spalte **Ergebnis** angezeigt. Wenn es sich bei der Testzahl nicht um eine Primzahl handelt, wird sie als **Zusammengesetzt** bezeichnet, und der erste Divisor wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69431-109">The result of the computation is displayed in the **Result** column; if the test number is not prime, it is labeled as **Composite,** and its first divisor is displayed.</span></span>  
  
 <span data-ttu-id="69431-110">Alle ausstehenden Vorgänge können mit der Schaltfläche **Abbrechen** abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="69431-110">Any pending operation can be canceled with the **Cancel** button.</span></span> <span data-ttu-id="69431-111">Es kann eine Mehrfachauswahl vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="69431-111">Multiple selections can be made.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69431-112">Bei den meisten Zahlen handelt es sich nicht um Primzahlen.</span><span class="sxs-lookup"><span data-stu-id="69431-112">Most numbers will not be prime.</span></span> <span data-ttu-id="69431-113">Wenn Sie nicht nach mehreren abgeschlossenen Vorgänge eine Primzahl ermittelt haben, starten Sie einfach weitere Aufgaben, bis sie schließlich einige Primzahlen ermittelt haben.</span><span class="sxs-lookup"><span data-stu-id="69431-113">If you have not found a prime number after several completed operations, simply start more tasks, and eventually you will find some prime numbers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69431-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="69431-114">Example</span></span>  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="69431-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69431-115">See also</span></span>

- <xref:System.ComponentModel.AsyncOperation>
- <xref:System.ComponentModel.AsyncOperationManager>
- <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
