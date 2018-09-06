---
title: Übersicht über die BackgroundWorker-Komponente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- BackgroundWorker
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 64e9b3ab-7443-4a77-ab17-b8b8c0cb3f62
ms.openlocfilehash: d7d99cf87507237b23cb40c58b2308643f7f1056
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43872191"
---
# <a name="backgroundworker-component-overview"></a><span data-ttu-id="a25d5-102">Übersicht über die BackgroundWorker-Komponente</span><span class="sxs-lookup"><span data-stu-id="a25d5-102">BackgroundWorker Component Overview</span></span>
<span data-ttu-id="a25d5-103">Es gibt viele häufig verwendete Operationen, deren Ausführung lange dauern kann.</span><span class="sxs-lookup"><span data-stu-id="a25d5-103">There are many commonly performed operations that can take a long time to execute.</span></span> <span data-ttu-id="a25d5-104">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a25d5-104">For example:</span></span>  
  
-   <span data-ttu-id="a25d5-105">Bilddownloads</span><span class="sxs-lookup"><span data-stu-id="a25d5-105">Image downloads</span></span>  
  
-   <span data-ttu-id="a25d5-106">Webdienstaufrufe</span><span class="sxs-lookup"><span data-stu-id="a25d5-106">Web service invocations</span></span>  
  
-   <span data-ttu-id="a25d5-107">Dateidownloads und -uploads (einschließlich für Peer-to-Peer-Anwendungen)</span><span class="sxs-lookup"><span data-stu-id="a25d5-107">File downloads and uploads (including for peer-to-peer applications)</span></span>  
  
-   <span data-ttu-id="a25d5-108">Komplexe lokale Berechnungen</span><span class="sxs-lookup"><span data-stu-id="a25d5-108">Complex local computations</span></span>  
  
-   <span data-ttu-id="a25d5-109">Datenbanktransaktionen</span><span class="sxs-lookup"><span data-stu-id="a25d5-109">Database transactions</span></span>  
  
-   <span data-ttu-id="a25d5-110">Lokaler Festplattenzugriff, angesichts der langsamen Geschwindigkeit relativ zum Arbeitsspeicherzugriff</span><span class="sxs-lookup"><span data-stu-id="a25d5-110">Local disk access, given its slow speed relative to memory access</span></span>  
  
 <span data-ttu-id="a25d5-111">Operationen wie diese können bewirken, dass die Benutzeroberfläche während der Ausführung der Operation nicht mehr reagiert.</span><span class="sxs-lookup"><span data-stu-id="a25d5-111">Operations like these can cause your user interface to hang while they are running.</span></span> <span data-ttu-id="a25d5-112">Wenn Sie dies vermeiden möchten und bei solchen Operationen lange Verzögerungen auftreten, stellt die <xref:System.ComponentModel.BackgroundWorker>-Komponente eine geeignete Alternative dar.</span><span class="sxs-lookup"><span data-stu-id="a25d5-112">When you want a responsive UI and you are faced with long delays associated with such operations, the <xref:System.ComponentModel.BackgroundWorker> component provides a convenient solution.</span></span>  
  
 <span data-ttu-id="a25d5-113">Die <xref:System.ComponentModel.BackgroundWorker>-Komponente ermöglicht es Ihnen, zeitaufwändige Operationen asynchron ("im Hintergrund") auf einem anderen Thread als dem primären UI-Thread der Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a25d5-113">The <xref:System.ComponentModel.BackgroundWorker> component gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span> <span data-ttu-id="a25d5-114">Um einen <xref:System.ComponentModel.BackgroundWorker> zu verwenden, müssen Sie lediglich festlegen, welche zeitaufwändige Workermethode im Hintergrund ausgeführt werden soll, und anschließend die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a25d5-114">To use a <xref:System.ComponentModel.BackgroundWorker>, you simply tell it what time-consuming worker method to execute in the background, and then you call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="a25d5-115">Der aufrufende Thread wird weiterhin wie gewohnt ausgeführt, während die Workermethode asynchron ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a25d5-115">Your calling thread continues to run normally while the worker method runs asynchronously.</span></span> <span data-ttu-id="a25d5-116">Nach Abschluss der Methode gibt der <xref:System.ComponentModel.BackgroundWorker> eine Warnung an den aufrufenden Thread aus, indem er das <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>-Ereignis auslöst, das optional die Ergebnisse der Operation enthält.</span><span class="sxs-lookup"><span data-stu-id="a25d5-116">When the method is finished, the <xref:System.ComponentModel.BackgroundWorker> alerts the calling thread by firing the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event, which optionally contains the results of the operation.</span></span>  
  
 <span data-ttu-id="a25d5-117">Die <xref:System.ComponentModel.BackgroundWorker> Komponente steht der **Toolbox**in die **Komponenten** Registerkarte. Um dem Formular einen <xref:System.ComponentModel.BackgroundWorker> hinzuzufügen, ziehen Sie die <xref:System.ComponentModel.BackgroundWorker>-Komponente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="a25d5-117">The <xref:System.ComponentModel.BackgroundWorker> component is available from the **Toolbox**, in the **Components** tab. To add a <xref:System.ComponentModel.BackgroundWorker> to your form, drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span> <span data-ttu-id="a25d5-118">Es wird in der Komponentenleiste angezeigt, und seine Eigenschaften werden der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="a25d5-118">It appears in the component tray, and its properties appear in the **Properties** window.</span></span>  
  
 <span data-ttu-id="a25d5-119">Um die asynchrone Operation zu starten, verwenden Sie die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="a25d5-119">To start your asynchronous operation, use the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="a25d5-120"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> akzeptiert ein optionales `object` -Parameter, der verwendet werden kann, um Argumente an die Workermethode übergeben.</span><span class="sxs-lookup"><span data-stu-id="a25d5-120"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> takes an optional `object` parameter, which can be used to pass arguments to your worker method.</span></span> <span data-ttu-id="a25d5-121">Die <xref:System.ComponentModel.BackgroundWorker>-Klasse macht das <xref:System.ComponentModel.BackgroundWorker.DoWork>-Ereignis verfügbar, mit dem der Workerthread über einen <xref:System.ComponentModel.BackgroundWorker.DoWork>-Ereignishandler verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="a25d5-121">The <xref:System.ComponentModel.BackgroundWorker> class exposes the <xref:System.ComponentModel.BackgroundWorker.DoWork> event, to which your worker thread is attached through a <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
 <span data-ttu-id="a25d5-122">Der <xref:System.ComponentModel.BackgroundWorker.DoWork>-Ereignishandler verwendet einen <xref:System.ComponentModel.DoWorkEventArgs>-Parameter, der über eine <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>-Eigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="a25d5-122">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler takes a <xref:System.ComponentModel.DoWorkEventArgs> parameter, which has an <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property.</span></span> <span data-ttu-id="a25d5-123">Diese Eigenschaft empfängt den Parameter von <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> und kann an die Workermethode übergeben werden, die im <xref:System.ComponentModel.BackgroundWorker.DoWork>-Ereignishandler aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a25d5-123">This property receives the parameter from <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and can be passed to your worker method, which will be called in the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="a25d5-124">Im folgenden Beispiel wird gezeigt, wie ein Ergebnis von einer Workermethode mit dem Namen `ComputeFibonacci` zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a25d5-124">The following example shows how to assign a result from a worker method called `ComputeFibonacci`.</span></span> <span data-ttu-id="a25d5-125">Es ist Teil eines größeren Beispiels, finden Sie unter [Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="a25d5-125">It is part of a larger example, which you can find at [How to: Implement a Form That Uses a Background Operation](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 <span data-ttu-id="a25d5-126">Weitere Informationen zur Verwendung von Ereignishandlern finden Sie unter [Ereignisse](../../../../docs/standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="a25d5-126">For more information on using event handlers, see [Events](../../../../docs/standard/events/index.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a25d5-127">Wenn Sie Multithreading verwenden, setzen Sie sich möglicherweise sehr ernsten und komplexen Problemen aus.</span><span class="sxs-lookup"><span data-stu-id="a25d5-127">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="a25d5-128">Beachten Sie die Informationen unter [Empfohlene Vorgehensweise für das verwaltete Threading](../../../../docs/standard/threading/managed-threading-best-practices.md), bevor Sie eine Projektmappe implementieren, die Multithreading verwendet.</span><span class="sxs-lookup"><span data-stu-id="a25d5-128">Consult the [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
 <span data-ttu-id="a25d5-129">Weitere Informationen zur Verwendung der <xref:System.ComponentModel.BackgroundWorker> Klasse, finden Sie unter [wie: Ausführen eines Vorgangs im Hintergrund](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="a25d5-129">For more information on using the <xref:System.ComponentModel.BackgroundWorker> class, see [How to: Run an Operation in the Background](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a25d5-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a25d5-130">See also</span></span>

- [<span data-ttu-id="a25d5-131">Verwaltetes Threading</span><span class="sxs-lookup"><span data-stu-id="a25d5-131">Managed Threading</span></span>](../../../../docs/standard/threading/index.md)
- [<span data-ttu-id="a25d5-132">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="a25d5-132">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="a25d5-133">Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet</span><span class="sxs-lookup"><span data-stu-id="a25d5-133">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
