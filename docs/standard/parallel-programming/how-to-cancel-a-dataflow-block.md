---
title: 'Vorgehensweise: Abbrechen eines Datenflussblocks'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- dataflow blocks, canceling in TPL
- TPL dataflow library,canceling dataflow blocks
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
ms.openlocfilehash: aa175d95f27fcbf28c3f3da3eaa7b8f7988681e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140093"
---
# <a name="how-to-cancel-a-dataflow-block"></a><span data-ttu-id="8e2f9-102">Vorgehensweise: Abbrechen eines Datenflussblocks</span><span class="sxs-lookup"><span data-stu-id="8e2f9-102">How to: Cancel a Dataflow Block</span></span>
<span data-ttu-id="8e2f9-103">Dieses Dokument veranschaulicht, wie Sie das Abbrüche in der Anwendung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-103">This document demonstrates how to enable cancellation in your application.</span></span> <span data-ttu-id="8e2f9-104">In diesem Beispiel wird Windows Forms verwendet, um anzuzeigen, wo in einer Datenflusspipeline Arbeitselemente aktiv sind, und um die Auswirkungen eines Abbruchs zu verdeutlichen.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-104">This example uses Windows Forms to show where work items are active in a dataflow pipeline and also the effects of cancellation.</span></span>  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="to-create-the-windows-forms-application"></a><span data-ttu-id="8e2f9-105">Erstellen der Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="8e2f9-105">To Create the Windows Forms Application</span></span>  
  
1. <span data-ttu-id="8e2f9-106">Erstellen Sie ein C#- oder Visual Basic-**Windows Forms**-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-106">Create a C# or Visual Basic **Windows Forms Application** project.</span></span> <span data-ttu-id="8e2f9-107">In den folgenden Schritten wird das Projekt `CancellationWinForms` benannt.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-107">In the following steps, the project is named `CancellationWinForms`.</span></span>  
  
2. <span data-ttu-id="8e2f9-108">Fügen Sie im Formulardesigner für das Hauptformular „Form1.cs“ („Form1.vb“ in Visual Basic) ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-108">On the form designer for the main form, Form1.cs (Form1.vb for Visual Basic), add a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
3. <span data-ttu-id="8e2f9-109">Fügen Sie dem <xref:System.Windows.Forms.ToolStrip>-Steuerelement ein <xref:System.Windows.Forms.ToolStripButton>-Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-109">Add a <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="8e2f9-110">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>-Eigenschaft auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> und die <xref:System.Windows.Forms.ToolStripItem.Text%2A>-Eigenschaft auf **Arbeitselemente hinzufügen** fest.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-110">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> and the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Add Work Items**.</span></span>  
  
4. <span data-ttu-id="8e2f9-111">Fügen Sie dem <xref:System.Windows.Forms.ToolStrip>-Steuerelement ein zweites <xref:System.Windows.Forms.ToolStripButton>-Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-111">Add a second <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="8e2f9-112">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>-Eigenschaft auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, die <xref:System.Windows.Forms.ToolStripItem.Text%2A>-Eigenschaft auf **Abbrechen** und die <xref:System.Windows.Forms.ToolStripItem.Enabled%2A>-Eigenschaft auf `False` fest.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-112">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Cancel**, and the <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> property to `False`.</span></span>  
  
5. <span data-ttu-id="8e2f9-113">Fügen Sie vier <xref:System.Windows.Forms.ToolStripProgressBar> -Objekte zum <xref:System.Windows.Forms.ToolStrip>-Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-113">Add four <xref:System.Windows.Forms.ToolStripProgressBar> objects to the <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="creating-the-dataflow-pipeline"></a><span data-ttu-id="8e2f9-114">Erstellen der Datenflusspipeline</span><span class="sxs-lookup"><span data-stu-id="8e2f9-114">Creating the Dataflow Pipeline</span></span>  
 <span data-ttu-id="8e2f9-115">In diesem Abschnitt wird beschrieben, wie Sie die Datenflusspipeline erstellen, die Arbeitselemente verarbeitet und Statusanzeigen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-115">This section describes how to create the dataflow pipeline that processes work items and updates the progress bars.</span></span>  
  
### <a name="to-create-the-dataflow-pipeline"></a><span data-ttu-id="8e2f9-116">So erstellen Sie die Datenflusspipeline</span><span class="sxs-lookup"><span data-stu-id="8e2f9-116">To Create the Dataflow Pipeline</span></span>  
  
1. <span data-ttu-id="8e2f9-117">Fügen Sie dem Projekt einen Verweis auf „System.Threading.Tasks.Dataflow.dll“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-117">In your project, add a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
2. <span data-ttu-id="8e2f9-118">Stellen Sie sicher, dass „Form1.cs“ („Form1.vb“ für Visual Basic) die folgenden `using`-Anweisungen (`Imports` in Visual Basic) enthält.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-118">Ensure that Form1.cs (Form1.vb for Visual Basic) contains the following `using` statements (`Imports` in Visual Basic).</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3. <span data-ttu-id="8e2f9-119">Fügen Sie die `WorkItem`-Klasse als einen inneren Typ der `Form1`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-119">Add the `WorkItem` class as an inner type of the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4. <span data-ttu-id="8e2f9-120">Fügen Sie der `Form1`-Klasse die folgenden Datenmember hinzu.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-120">Add the following data members to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5. <span data-ttu-id="8e2f9-121">Fügen Sie der `Form1`-Klasse die folgende `CreatePipeline`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="8e2f9-121">Add the following method, `CreatePipeline`, to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 <span data-ttu-id="8e2f9-122">Da sich die `incrementProgress`- und `decrementProgress`-Datenflussblöcke auf die Benutzeroberfläche auswirken, ist es wichtig, dass diese Aktionen im Benutzeroberflächenthread erfolgen.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-122">Because the `incrementProgress` and `decrementProgress` dataflow blocks act on the user interface, it is important that these actions occur on the user-interface thread.</span></span> <span data-ttu-id="8e2f9-123">Um dies zu erreichen, stellen diese Objekte während der Erstellung ein <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions>-Objekt bereit, für das die <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A>-Eigenschaft auf <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-123">To accomplish this, during construction these objects each provide a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8e2f9-124">Die <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>-Methode erstellt ein <xref:System.Threading.Tasks.TaskScheduler>-Objekt, das Arbeiten im aktuellen Synchronisierungskontext durchführt.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-124">The <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> method creates a <xref:System.Threading.Tasks.TaskScheduler> object that performs work on the current synchronization context.</span></span> <span data-ttu-id="8e2f9-125">Da der `Form1`-Konstruktor über den Benutzeroberflächenthread aufgerufen wird, werden die Aktionen für den `incrementProgress`- und den `decrementProgress`-Datenflussblock ebenfalls im Benutzeroberflächenthread ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-125">Because the `Form1` constructor is called from the user-interface thread, the actions for the `incrementProgress` and `decrementProgress` dataflow blocks also run on the user-interface thread.</span></span>  
  
 <span data-ttu-id="8e2f9-126">In diesem Beispiel wird die <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A>-Eigenschaft festgelegt, wenn sie die Elemente der Pipeline erstellt.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-126">This example sets the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property when it constructs the members of the pipeline.</span></span> <span data-ttu-id="8e2f9-127">Da die <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A>-Eigenschaft die Ausführung des Datenflussblocks dauerhaft abbricht, muss die gesamte Pipeline neu erstellt werden, wenn der Benutzer den Vorgang abbricht und anschließend weitere Arbeitselemente zur Pipeline hinzufügen möchte.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-127">Because the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property permanently cancels dataflow block execution, the whole pipeline must be recreated after the user cancels the operation and then wants to add more work items to the pipeline.</span></span> <span data-ttu-id="8e2f9-128">Ein Beispiel für eine alternative Möglichkeit zum Abbrechen eines Datenflussblocks, die erlaubt, dass nach dem Abbrechen eines Vorgangs andere Arbeit ausgeführt wird, finden Sie unter [Exemplarische Vorgehensweise: Using Dataflow in a Windows Forms Application (Exemplarische Vorgehensweise: Verwenden von Datenflüssen in einer Windows Forms-Anwendung)](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span><span class="sxs-lookup"><span data-stu-id="8e2f9-128">For an example that demonstrates an alternative way to cancel a dataflow block so that other work can be performed after an operation is canceled, see [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span></span>  
  
## <a name="connecting-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="8e2f9-129">Verbinden der Datenflusspipeline mit der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="8e2f9-129">Connecting the Dataflow Pipeline to the User Interface</span></span>  
 <span data-ttu-id="8e2f9-130">In diesem Abschnitt wird beschrieben, wie Sie die Datenflusspipeline mit der Benutzeroberfläche verbinden.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-130">This section describes how to connect the dataflow pipeline to the user interface.</span></span> <span data-ttu-id="8e2f9-131">Sowohl das Erstellen der Pipeline als auch das Hinzufügen von Arbeitselementen zur Pipeline werden vom Ereignishandler für die Schaltfläche **Arbeitselemente hinzufügen** gesteuert.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-131">Both creating the pipeline and adding work items to the pipeline are controlled by the event handler for the **Add Work Items** button.</span></span> <span data-ttu-id="8e2f9-132">Der Abbruch wird durch die Schaltfläche **Abbrechen** initiiert.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-132">Cancellation is initiated by the **Cancel** button.</span></span> <span data-ttu-id="8e2f9-133">Wenn der Benutzer auf eine dieser Schaltflächen klickt, wird die entsprechende Aktion auf asynchrone Weise initiiert.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-133">When the user clicks either of these buttons, the appropriate action is initiated in an asynchronous manner.</span></span>  
  
### <a name="to-connect-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="8e2f9-134">So verbinden Sie die Datenflusspipeline mit der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="8e2f9-134">To Connect the Dataflow Pipeline to the User Interface</span></span>  
  
1. <span data-ttu-id="8e2f9-135">Erstellen Sie im Formulardesigner für das Hauptformular einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click>-Ereignis der Schaltfläche **Arbeitselemente hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-135">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
2. <span data-ttu-id="8e2f9-136">Implementieren Sie das <xref:System.Windows.Forms.ToolStripItem.Click>-Ereignis für die Schaltfläche **Arbeitselemente hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-136">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3. <span data-ttu-id="8e2f9-137">Erstellen Sie im Formulardesigner für das Hauptformular einen Ereignishandler für den <xref:System.Windows.Forms.ToolStripItem.Click>-Ereignishandler der Schaltfläche **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-137">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
4. <span data-ttu-id="8e2f9-138">Implementieren Sie den <xref:System.Windows.Forms.ToolStripItem.Click>-Ereignishandler für die Schaltfläche **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-138">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="8e2f9-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8e2f9-139">Example</span></span>  
 <span data-ttu-id="8e2f9-140">Im folgenden Beispiel wird der vollständige Code für „Form1.cs“ („Form1.vb“ in Visual Basic) gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-140">The following example shows the complete code for Form1.cs (Form1.vb for Visual Basic).</span></span>  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 <span data-ttu-id="8e2f9-141">Die folgende Abbildung zeigt die ausgeführte Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8e2f9-141">The following illustration shows the running application.</span></span>  
  
 <span data-ttu-id="8e2f9-142">![Die Windows Forms-Anwendung](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span><span class="sxs-lookup"><span data-stu-id="8e2f9-142">![The Windows Forms Application](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span></span>  

## <a name="see-also"></a><span data-ttu-id="8e2f9-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e2f9-143">See also</span></span>

- [<span data-ttu-id="8e2f9-144">Dataflow (Datenfluss)</span><span class="sxs-lookup"><span data-stu-id="8e2f9-144">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
