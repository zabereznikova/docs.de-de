---
title: "Exemplarische Vorgehensweise: Ausführen eines Vorgangs im Hintergrund"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9be47fd57e49973c0f77a069c4f3371e4f63194
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-running-an-operation-in-the-background"></a><span data-ttu-id="a2fb7-102">Exemplarische Vorgehensweise: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="a2fb7-102">Walkthrough: Running an Operation in the Background</span></span>
<span data-ttu-id="a2fb7-103">Gibt es einen Vorgang, der bis zu seinem Abschluss eine lange Zeit in Anspruch nimmt, und Sie möchten keine Verzögerungen in der Benutzeroberfläche verursachen, können Sie die <xref:System.ComponentModel.BackgroundWorker>-Klasse dazu verwenden, den Vorgang über einen anderen Thread auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="a2fb7-104">Eine vollständige Liste des Codes in diesem Beispiel verwendet, finden Sie unter [Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="a2fb7-104">For a complete listing of the code used in this example, see [How to: Run an Operation in the Background](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2fb7-105">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a2fb7-106">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a2fb7-107">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="a2fb7-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-run-an-operation-in-the-background"></a><span data-ttu-id="a2fb7-108">Um einen Vorgang im Hintergrund ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-108">To run an operation in the background</span></span>  
  
1.  <span data-ttu-id="a2fb7-109">Mit dem Formular in Windows Forms-Designer aktiv ist, ziehen Sie zwei <xref:System.Windows.Forms.Button> -Steuerelemente aus der **Toolbox** auf das Formular, und legen Sie anschließend die `Name` und <xref:System.Windows.Forms.Control.Text%2A> Eigenschaften der Schaltflächen entsprechend der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-109">With your form active in the Windows Forms Designer, drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to the form, and then set the `Name` and <xref:System.Windows.Forms.Control.Text%2A> properties of the buttons according to the following table.</span></span>  
  
    |<span data-ttu-id="a2fb7-110">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="a2fb7-110">Button</span></span>|<span data-ttu-id="a2fb7-111">name</span><span class="sxs-lookup"><span data-stu-id="a2fb7-111">Name</span></span>|<span data-ttu-id="a2fb7-112">Text</span><span class="sxs-lookup"><span data-stu-id="a2fb7-112">Text</span></span>|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|<span data-ttu-id="a2fb7-113">**Start**</span><span class="sxs-lookup"><span data-stu-id="a2fb7-113">**Start**</span></span>|  
    |`button2`|`cancelBtn`|<span data-ttu-id="a2fb7-114">**Abbrechen**</span><span class="sxs-lookup"><span data-stu-id="a2fb7-114">**Cancel**</span></span>|  
  
2.  <span data-ttu-id="a2fb7-115">Öffnen der **Toolbox**, klicken Sie auf die **Komponenten** Registerkarte, und ziehen Sie dann die <xref:System.ComponentModel.BackgroundWorker> -Komponente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-115">Open the **Toolbox**, click the **Components** tab, and then drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span>  
  
     <span data-ttu-id="a2fb7-116">Die `backgroundWorker1` Komponente angezeigt wird, der **Komponentenleiste**.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-116">The `backgroundWorker1` component appears in the **Component Tray**.</span></span>  
  
3.  <span data-ttu-id="a2fb7-117">In der **Eigenschaften** legen die <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-117">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> property to `true`.</span></span>  
  
4.  <span data-ttu-id="a2fb7-118">In der **Eigenschaften** Fenster, klicken Sie auf die **Ereignisse** aus, und doppelklicken Sie dann auf die <xref:System.ComponentModel.BackgroundWorker.DoWork> und <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> Ereignisse, um Ereignishandler zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-118">In the **Properties** window, click on the **Events** button, and then double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span>  
  
5.  <span data-ttu-id="a2fb7-119">Fügen Sie den zeitaufwendigen Code in der <xref:System.ComponentModel.BackgroundWorker.DoWork> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-119">Insert your time-consuming code into the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
6.  <span data-ttu-id="a2fb7-120">Extrahieren Sie alle Parameter erforderlich, die für den Vorgang mithilfe der <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> Eigenschaft von der <xref:System.ComponentModel.DoWorkEventArgs> Parameter.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-120">Extract any parameters required by the operation from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs> parameter.</span></span>  
  
7.  <span data-ttu-id="a2fb7-121">Weisen Sie das Ergebnis der Berechnung auf der <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> Eigenschaft von der <xref:System.ComponentModel.DoWorkEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-121">Assign the result of the computation to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span>  
  
     <span data-ttu-id="a2fb7-122">Dies wird zur Verfügung, die <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-122">This is will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8.  <span data-ttu-id="a2fb7-123">Fügen Sie Code zum Abrufen von das Ergebnis des Vorgangs in der <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-123">Insert code for retrieving the result of your operation in the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. <span data-ttu-id="a2fb7-124">Implementieren Sie die `TimeConsumingOperation`-Methode.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-124">Implement the `TimeConsumingOperation` method.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. <span data-ttu-id="a2fb7-125">Doppelklicken Sie in Windows Forms-Designer auf `startButton` zum Erstellen der <xref:System.Windows.Forms.Control.Click> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-125">In the Windows Forms Designer, double-click `startButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
11. <span data-ttu-id="a2fb7-126">Rufen Sie die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> Methode in der <xref:System.Windows.Forms.Control.Click> -Ereignishandler für `startButton`.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-126">Call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `startButton`.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. <span data-ttu-id="a2fb7-127">Doppelklicken Sie in Windows Forms-Designer auf `cancelButton` zum Erstellen der <xref:System.Windows.Forms.Control.Click> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-127">In the Windows Forms Designer, double-click `cancelButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
13. <span data-ttu-id="a2fb7-128">Rufen Sie die <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> Methode in der <xref:System.Windows.Forms.Control.Click> -Ereignishandler für `cancelButton`.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-128">Call the <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `cancelButton`.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. <span data-ttu-id="a2fb7-129">Importieren Sie am Anfang der Datei die System.ComponentModel-Namespace und System.Threading-Namespaces ein.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-129">At the top of the file, import the System.ComponentModel and System.Threading namespaces.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. <span data-ttu-id="a2fb7-130">Drücken Sie F6, um die Projektmappe zu erstellen, und drücken Sie STRG + F5, um die Anwendung außerhalb des Debuggers ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-130">Press F6 to build the solution, and then press CTRL-F5 to run the application outside the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2fb7-131">Wenn Sie F5, um die Anwendung im Debugger auszuführen drücken, wird die Ausnahme ausgelöst, der `TimeConsumingOperation` Methode abgefangen und vom Debugger angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-131">If you press F5 to run the application under the debugger, the exception raised in the `TimeConsumingOperation` method is caught and displayed by the debugger.</span></span> <span data-ttu-id="a2fb7-132">Beim Ausführen der Anwendung außerhalb des Debuggers die <xref:System.ComponentModel.BackgroundWorker> Ausnahmen behandelt, und speichert es in der <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> Eigenschaft von der <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-132">When you run the application outside the debugger, the <xref:System.ComponentModel.BackgroundWorker> handles the exception and caches it in the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> property of the <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span></span>  
  
1.  <span data-ttu-id="a2fb7-133">Klicken Sie auf die **starten** Schaltfläche, um einen asynchronen Vorgang auszuführen, und klicken Sie dann auf die **"Abbrechen"** Schaltfläche, um einen laufenden asynchronen Vorgang zu beenden.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-133">Click the **Start** button to run an asynchronous operation, and then click the **Cancel** button to stop a running asynchronous operation.</span></span>  
  
     <span data-ttu-id="a2fb7-134">Das Ergebnis jedes Vorgangs wird in einem <xref:System.Windows.Forms.MessageBox>-Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-134">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a2fb7-135">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a2fb7-135">Next Steps</span></span>  
  
-   <span data-ttu-id="a2fb7-136">Implementieren eines Formulars, das Fortschrittsberichte, während ein asynchroner Vorgang durchführt.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-136">Implement a form that reports progress as an asynchronous operation proceeds.</span></span> <span data-ttu-id="a2fb7-137">Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="a2fb7-137">For more information, see [How to: Implement a Form That Uses a Background Operation](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
-   <span data-ttu-id="a2fb7-138">Implementieren Sie eine Klasse, die das asynchrone Muster für Komponenten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a2fb7-138">Implement a class that supports the Asynchronous Pattern for Components.</span></span> <span data-ttu-id="a2fb7-139">Weitere Informationen finden Sie unter [das ereignisbasierte asynchrone Muster implementieren](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="a2fb7-139">For more information, see [Implementing the Event-based Asynchronous Pattern](../../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2fb7-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2fb7-140">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [<span data-ttu-id="a2fb7-141">Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet</span><span class="sxs-lookup"><span data-stu-id="a2fb7-141">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [<span data-ttu-id="a2fb7-142">Gewusst wie: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="a2fb7-142">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [<span data-ttu-id="a2fb7-143">BackgroundWorker-Komponente</span><span class="sxs-lookup"><span data-stu-id="a2fb7-143">BackgroundWorker Component</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
