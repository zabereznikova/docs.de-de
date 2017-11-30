---
title: "Gewusst wie: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen"
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
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 49e03a8d886ccd4ed6e4b2a19692c1874f5928ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a><span data-ttu-id="4ebb9-102">Gewusst wie: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen</span><span class="sxs-lookup"><span data-stu-id="4ebb9-102">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="4ebb9-103">Viele Komponenten bieten Ihnen die Möglichkeit, ihre Arbeit asynchron ausführen.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-103">Many components provide you with the option of performing their work asynchronously.</span></span> <span data-ttu-id="4ebb9-104">Die <xref:System.Media.SoundPlayer> und <xref:System.Windows.Forms.PictureBox> Komponenten, z. B. aktivieren, die Sie laden sounds und Bilder "im Hintergrund", während der Hauptthread weiterhin ohne Unterbrechung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-104">The <xref:System.Media.SoundPlayer> and <xref:System.Windows.Forms.PictureBox> components, for example, enable you to load sounds and images "in the background" while your main thread continues running without interruption.</span></span>  
  
 <span data-ttu-id="4ebb9-105">Verwenden von asynchronen Methoden auf eine Klasse, unterstützt die [Übersicht über ereignisbasierte asynchrone Muster](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) kann so einfach wie einen Ereignishandler für der Komponente Anfügen *MethodName* `Completed` -Ereignis wie für jedes andere Ereignis.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-105">Using asynchronous methods on a class that supports the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) can be as simple as attaching an event handler to the component's *MethodName*`Completed` event, just as you would for any other event.</span></span> <span data-ttu-id="4ebb9-106">Beim Aufrufen der *MethodName* `Async` -Methode, Ihre Anwendung weiterhin ohne Unterbrechung bis ausgeführt der *MethodName* `Completed` Ereignis wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-106">When you call the *MethodName*`Async` method, your application will continue running without interruption until the *MethodName*`Completed` event is raised.</span></span> <span data-ttu-id="4ebb9-107">Im Ereignishandler, untersuchen Sie die <xref:System.ComponentModel.AsyncCompletedEventArgs> Parameter, um festzustellen, ob der asynchrone Vorgang erfolgreich abgeschlossen wurde oder wenn er abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-107">In your event handler, you can examine the <xref:System.ComponentModel.AsyncCompletedEventArgs> parameter to determine if the asynchronous operation successfully completed or if it was canceled.</span></span>  
  
 <span data-ttu-id="4ebb9-108">Weitere Informationen zur Verwendung von Ereignishandlern finden Sie unter [Übersicht über Ereignishandler](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4ebb9-108">For more information about using event handlers, see [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="4ebb9-109">Das folgende Verfahren zeigt, wie die asynchronen Laden von Images-Funktion von einem <xref:System.Windows.Forms.PictureBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-109">The following procedure shows how to use the asynchronous image-loading capability of a <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a><span data-ttu-id="4ebb9-110">So aktivieren Sie ein PictureBox-Steuerelement zum asynchronen Laden eines Bilds</span><span class="sxs-lookup"><span data-stu-id="4ebb9-110">To enable a PictureBox control to asynchronously load an image</span></span>  
  
1.  <span data-ttu-id="4ebb9-111">Erstellen Sie eine Instanz von der <xref:System.Windows.Forms.PictureBox> -Komponente in das Formular.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-111">Create an instance of the <xref:System.Windows.Forms.PictureBox> component in your form.</span></span>  
  
2.  <span data-ttu-id="4ebb9-112">Weisen Sie einen Ereignishandler an das <xref:System.Windows.Forms.PictureBox.LoadCompleted> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-112">Assign an event handler to the <xref:System.Windows.Forms.PictureBox.LoadCompleted> event.</span></span>  
  
     <span data-ttu-id="4ebb9-113">Überprüfen Sie nach Fehlern, die möglicherweise während der asynchronen Download hier ausgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-113">Check for any errors that may have occurred during the asynchronous download here.</span></span> <span data-ttu-id="4ebb9-114">Dies ist auch, wo Sie nach einem Abbruch gesucht.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-114">This is also where you check for cancellation.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  <span data-ttu-id="4ebb9-115">Fügen Sie zwei Schaltflächen, `loadButton` und `cancelLoadButton`, um das Formular.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-115">Add two buttons, called `loadButton` and `cancelLoadButton`, to your form.</span></span> <span data-ttu-id="4ebb9-116">Hinzufügen <xref:System.Windows.Forms.Control.Click> Ereignishandler zum Starten und Abbrechen des Downloads.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-116">Add <xref:System.Windows.Forms.Control.Click> event handlers to start and cancel the download.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  <span data-ttu-id="4ebb9-117">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-117">Run your application.</span></span>  
  
     <span data-ttu-id="4ebb9-118">Wie die Bilddownloads können Sie das Formular frei verschieben, minimieren und maximieren.</span><span class="sxs-lookup"><span data-stu-id="4ebb9-118">As the image download proceeds, you can move the form freely, minimize it, and maximize it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ebb9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ebb9-119">See Also</span></span>  
 [<span data-ttu-id="4ebb9-120">Gewusst wie: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="4ebb9-120">How to: Run an Operation in the Background</span></span>](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [<span data-ttu-id="4ebb9-121">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="4ebb9-121">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="4ebb9-122">NICHT im BUILD: Multithreading in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4ebb9-122">NOT IN BUILD: Multithreading in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)
