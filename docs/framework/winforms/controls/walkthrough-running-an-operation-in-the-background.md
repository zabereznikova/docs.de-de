---
title: 'Exemplarische Vorgehensweise: Ausführen eines Vorgangs im Hintergrund'
ms.date: 03/30/2017
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
ms.openlocfilehash: 6c705c6d6ff9bbd233bbddc3a73acf8aca13a547
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211526"
---
# <a name="walkthrough-running-an-operation-in-the-background"></a><span data-ttu-id="4f451-102">Exemplarische Vorgehensweise: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="4f451-102">Walkthrough: Running an Operation in the Background</span></span>

<span data-ttu-id="4f451-103">Gibt es einen Vorgang, der bis zu seinem Abschluss eine lange Zeit in Anspruch nimmt, und Sie möchten keine Verzögerungen in der Benutzeroberfläche verursachen, können Sie die <xref:System.ComponentModel.BackgroundWorker>-Klasse dazu verwenden, den Vorgang über einen anderen Thread auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4f451-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>

<span data-ttu-id="4f451-104">Eine vollständige Liste des Codes in diesem Beispiel verwendet, finden Sie unter [Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="4f451-104">For a complete listing of the code used in this example, see [How to: Run an Operation in the Background](how-to-run-an-operation-in-the-background.md).</span></span>

## <a name="run-an-operation-in-the-background"></a><span data-ttu-id="4f451-105">Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="4f451-105">Run an operation in the background</span></span>

1. <span data-ttu-id="4f451-106">Mit dem Formular in Windows Forms-Designer in Visual Studio aktiv ist, ziehen Sie zwei <xref:System.Windows.Forms.Button> -Steuerelemente aus der **Toolbox** auf das Formular, und legen Sie dann die `Name` und <xref:System.Windows.Forms.Control.Text%2A> Eigenschaften der Schaltflächen gemäß der in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4f451-106">With your form active in the Windows Forms Designer in Visual Studio, drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to the form, and then set the `Name` and <xref:System.Windows.Forms.Control.Text%2A> properties of the buttons according to the following table.</span></span>

    |<span data-ttu-id="4f451-107">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="4f451-107">Button</span></span>|<span data-ttu-id="4f451-108">Name</span><span class="sxs-lookup"><span data-stu-id="4f451-108">Name</span></span>|<span data-ttu-id="4f451-109">Text</span><span class="sxs-lookup"><span data-stu-id="4f451-109">Text</span></span>|
    |------------|----------|----------|
    |`button1`|`startBtn`|<span data-ttu-id="4f451-110">**Starten**</span><span class="sxs-lookup"><span data-stu-id="4f451-110">**Start**</span></span>|
    |`button2`|`cancelBtn`|<span data-ttu-id="4f451-111">**Kündigung**</span><span class="sxs-lookup"><span data-stu-id="4f451-111">**Cancel**</span></span>|

2. <span data-ttu-id="4f451-112">Öffnen der **Toolbox**, klicken Sie auf die **Komponenten** Registerkarte, und ziehen Sie dann die <xref:System.ComponentModel.BackgroundWorker> -Komponente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="4f451-112">Open the **Toolbox**, click the **Components** tab, and then drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span>

     <span data-ttu-id="4f451-113">Die `backgroundWorker1` Komponente angezeigt wird, der **Komponentenleiste**.</span><span class="sxs-lookup"><span data-stu-id="4f451-113">The `backgroundWorker1` component appears in the **Component Tray**.</span></span>

3. <span data-ttu-id="4f451-114">Legen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="4f451-114">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> property to `true`.</span></span>

4. <span data-ttu-id="4f451-115">In der **Eigenschaften** Fenster, klicken Sie auf die **Ereignisse** Schaltfläche, und doppelklicken Sie dann auf die <xref:System.ComponentModel.BackgroundWorker.DoWork> und <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> Ereignisse an den Ereignishandler zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4f451-115">In the **Properties** window, click on the **Events** button, and then double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span>

5. <span data-ttu-id="4f451-116">Fügen Sie den zeitaufwendigen Code in die <xref:System.ComponentModel.BackgroundWorker.DoWork> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="4f451-116">Insert your time-consuming code into the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>

6. <span data-ttu-id="4f451-117">Extrahieren Sie alle Parameter, die erforderlich sind, durch den Vorgang aus der <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> Eigenschaft der <xref:System.ComponentModel.DoWorkEventArgs> Parameter.</span><span class="sxs-lookup"><span data-stu-id="4f451-117">Extract any parameters required by the operation from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs> parameter.</span></span>

7. <span data-ttu-id="4f451-118">Weisen Sie das Ergebnis der Berechnung, die <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> Eigenschaft der <xref:System.ComponentModel.DoWorkEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="4f451-118">Assign the result of the computation to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span>

     <span data-ttu-id="4f451-119">Dies wird zur Verfügung, die <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="4f451-119">This is will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]

8. <span data-ttu-id="4f451-120">Fügen Sie Code für das Ergebnis des Vorgangs im Abrufen der <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="4f451-120">Insert code for retrieving the result of your operation in the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]

9. <span data-ttu-id="4f451-121">Implementieren Sie die `TimeConsumingOperation`-Methode.</span><span class="sxs-lookup"><span data-stu-id="4f451-121">Implement the `TimeConsumingOperation` method.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]

10. <span data-ttu-id="4f451-122">Doppelklicken Sie in der Windows Forms-Designer auf `startButton` zum Erstellen der <xref:System.Windows.Forms.Control.Click> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="4f451-122">In the Windows Forms Designer, double-click `startButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>

11. <span data-ttu-id="4f451-123">Rufen Sie die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> -Methode in der die <xref:System.Windows.Forms.Control.Click> -Ereignishandler für `startButton`.</span><span class="sxs-lookup"><span data-stu-id="4f451-123">Call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `startButton`.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]

12. <span data-ttu-id="4f451-124">Doppelklicken Sie in der Windows Forms-Designer auf `cancelButton` zum Erstellen der <xref:System.Windows.Forms.Control.Click> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="4f451-124">In the Windows Forms Designer, double-click `cancelButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>

13. <span data-ttu-id="4f451-125">Rufen Sie die <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> -Methode in der die <xref:System.Windows.Forms.Control.Click> -Ereignishandler für `cancelButton`.</span><span class="sxs-lookup"><span data-stu-id="4f451-125">Call the <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `cancelButton`.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]

14. <span data-ttu-id="4f451-126">Importieren Sie am Anfang der Datei die System.ComponentModel-Namespace und den System.Threading-Namespaces.</span><span class="sxs-lookup"><span data-stu-id="4f451-126">At the top of the file, import the System.ComponentModel and System.Threading namespaces.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]

15. <span data-ttu-id="4f451-127">Drücken Sie die **F6** zum Erstellen der Projektmappe, und drücken dann die **STRG**+**F5** zum Ausführen der Anwendung außerhalb des Debuggers.</span><span class="sxs-lookup"><span data-stu-id="4f451-127">Press **F6** to build the solution, and then press **Ctrl**+**F5** to run the application outside the debugger.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4f451-128">Wenn Sie drücken **F5** um die Anwendung im Debugger ausführen, die Ausnahme ausgelöst hat, der `TimeConsumingOperation` Methode abgefangen und vom Debugger angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4f451-128">If you press **F5** to run the application under the debugger, the exception raised in the `TimeConsumingOperation` method is caught and displayed by the debugger.</span></span> <span data-ttu-id="4f451-129">Beim Ausführen der Anwendung außerhalb des Debuggers der <xref:System.ComponentModel.BackgroundWorker> wird die Ausnahme behandelt und speichert Sie in der <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> Eigenschaft der <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="4f451-129">When you run the application outside the debugger, the <xref:System.ComponentModel.BackgroundWorker> handles the exception and caches it in the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> property of the <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span></span>

16. <span data-ttu-id="4f451-130">Klicken Sie auf die **starten** Schaltfläche, um einen asynchronen Vorgang auszuführen, und klicken Sie dann auf die **Abbrechen** Schaltfläche, um einen aktiven asynchronen Vorgang zu beenden.</span><span class="sxs-lookup"><span data-stu-id="4f451-130">Click the **Start** button to run an asynchronous operation, and then click the **Cancel** button to stop a running asynchronous operation.</span></span>

     <span data-ttu-id="4f451-131">Das Ergebnis jedes Vorgangs wird in einem <xref:System.Windows.Forms.MessageBox>-Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4f451-131">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4f451-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4f451-132">Next steps</span></span>

- <span data-ttu-id="4f451-133">Implementieren eines Formulars, das einen Status meldet, wie ein asynchroner Vorgang wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4f451-133">Implement a form that reports progress as an asynchronous operation proceeds.</span></span> <span data-ttu-id="4f451-134">Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](how-to-implement-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="4f451-134">For more information, see [How to: Implement a Form That Uses a Background Operation](how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>

- <span data-ttu-id="4f451-135">Implementieren Sie eine Klasse, die das asynchrone Muster für Komponenten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4f451-135">Implement a class that supports the Asynchronous Pattern for Components.</span></span> <span data-ttu-id="4f451-136">Weitere Informationen finden Sie unter [Implementieren des ereignisbasierten asynchronen Entwurfsmusters](../../../standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="4f451-136">For more information, see [Implementing the Event-based Asynchronous Pattern](../../../standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4f451-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f451-137">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="4f451-138">Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet</span><span class="sxs-lookup"><span data-stu-id="4f451-138">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="4f451-139">Vorgehensweise: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="4f451-139">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="4f451-140">BackgroundWorker-Komponente</span><span class="sxs-lookup"><span data-stu-id="4f451-140">BackgroundWorker Component</span></span>](backgroundworker-component.md)
