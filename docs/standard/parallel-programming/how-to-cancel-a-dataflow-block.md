---
title: 'Gewusst wie: Abbrechen eines Datenflussblocks'
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
- Task Parallel Library, dataflows
- dataflow blocks, canceling in TPL
- TPL dataflow library,canceling dataflow blocks
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4d6fbde31cd4b4b5d0c6404b8baf23230f2bda77
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-cancel-a-dataflow-block"></a><span data-ttu-id="b2aaf-102">Gewusst wie: Abbrechen eines Datenflussblocks</span><span class="sxs-lookup"><span data-stu-id="b2aaf-102">How to: Cancel a Dataflow Block</span></span>
<span data-ttu-id="b2aaf-103">Dieses Dokument veranschaulicht, wie Sie das Abbrüche in der Anwendung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-103">This document demonstrates how to enable cancellation in your application.</span></span> <span data-ttu-id="b2aaf-104">In diesem Beispiel wird Windows Forms verwendet, um anzuzeigen, wo in einer Datenflusspipeline Arbeitsaufgaben aktiv sind, und um die Auswirkungen eines Abbruchs zu verdeutlichen.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-104">This example uses Windows Forms to show where work items are active in a dataflow pipeline and also the effects of cancellation.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="b2aaf-105">Die TPL-Datenflussbibliothek (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>-Namespace) ist nicht in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthalten.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-105">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="b2aaf-106">Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow` -Paket.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-106">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
### <a name="to-create-the-windows-forms-application"></a><span data-ttu-id="b2aaf-107">Erstellen der Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="b2aaf-107">To Create the Windows Forms Application</span></span>  
  
1.  <span data-ttu-id="b2aaf-108">Erstellen Sie ein C#- oder Visual Basic-**Windows Forms**-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-108">Create a C# or Visual Basic **Windows Forms Application** project.</span></span> <span data-ttu-id="b2aaf-109">In den folgenden Schritten wird das Projekt `CancellationWinForms` benannt.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-109">In the following steps, the project is named `CancellationWinForms`.</span></span>  
  
2.  <span data-ttu-id="b2aaf-110">Im Formular-Designer für das Hauptformular "Form1.cs" ("Form1.vb" [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), Hinzufügen einer <xref:System.Windows.Forms.ToolStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-110">On the form designer for the main form, Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), add a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
3.  <span data-ttu-id="b2aaf-111">Hinzufügen einer <xref:System.Windows.Forms.ToolStripButton> die Steuerung an die <xref:System.Windows.Forms.ToolStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-111">Add a <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="b2aaf-112">Festlegen der <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> Eigenschaft <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> und die <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaft, um **Arbeitsaufgaben hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-112">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> and the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Add Work Items**.</span></span>  
  
4.  <span data-ttu-id="b2aaf-113">Fügen Sie eine zweite <xref:System.Windows.Forms.ToolStripButton> die Steuerung an die <xref:System.Windows.Forms.ToolStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-113">Add a second <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="b2aaf-114">Festlegen der <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> Eigenschaft, um <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, die <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaft, um **"Abbrechen"**, und die <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> Eigenschaft `False`.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-114">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Cancel**, and the <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> property to `False`.</span></span>  
  
5.  <span data-ttu-id="b2aaf-115">Fügen Sie vier <xref:System.Windows.Forms.ToolStripProgressBar> -Objekte und die <xref:System.Windows.Forms.ToolStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-115">Add four <xref:System.Windows.Forms.ToolStripProgressBar> objects to the <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="creating-the-dataflow-pipeline"></a><span data-ttu-id="b2aaf-116">Erstellen der Datenflusspipeline</span><span class="sxs-lookup"><span data-stu-id="b2aaf-116">Creating the Dataflow Pipeline</span></span>  
 <span data-ttu-id="b2aaf-117">In diesem Abschnitt wird beschrieben, wie Sie die Datenflusspipeline erstellen, die Arbeitsaufgaben verarbeitet und Statusanzeigen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-117">This section describes how to create the dataflow pipeline that processes work items and updates the progress bars.</span></span>  
  
#### <a name="to-create-the-dataflow-pipeline"></a><span data-ttu-id="b2aaf-118">So erstellen Sie die Datenflusspipeline</span><span class="sxs-lookup"><span data-stu-id="b2aaf-118">To Create the Dataflow Pipeline</span></span>  
  
1.  <span data-ttu-id="b2aaf-119">Fügen Sie dem Projekt einen Verweis auf „System.Threading.Tasks.Dataflow.dll“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-119">In your project, add a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
2.  <span data-ttu-id="b2aaf-120">Stellen Sie sicher, dass „Form1.cs“ („Form1.vb“ bei [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) die folgenden `using`-Anweisungen (`Imports` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) enthält.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-120">Ensure that Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) contains the following `using` statements (`Imports` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3.  <span data-ttu-id="b2aaf-121">Fügen Sie die `WorkItem`-Klasse als einen inneren Typ der `Form1`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-121">Add the `WorkItem` class as an inner type of the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4.  <span data-ttu-id="b2aaf-122">Fügen Sie der `Form1`-Klasse die folgenden Datenmember hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-122">Add the following data members to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5.  <span data-ttu-id="b2aaf-123">Fügen Sie der `Form1`-Klasse die folgende `CreatePipeline`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="b2aaf-123">Add the following method, `CreatePipeline`, to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 <span data-ttu-id="b2aaf-124">Da sich die `incrementProgress`- und `decrementProgress`-Datenflussblöcke auf die Benutzeroberfläche auswirken, ist es wichtig, dass diese Aktionen im Benutzeroberflächenthread erfolgen.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-124">Because the `incrementProgress` and `decrementProgress` dataflow blocks act on the user interface, it is important that these actions occur on the user-interface thread.</span></span> <span data-ttu-id="b2aaf-125">Während der Erstellung hierzu diese Objekte bieten jeweils eine <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> Objekt mit der <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> -Eigenschaftensatz auf <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-125">To accomplish this, during construction these objects each provide a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b2aaf-126">Die <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>-Methode erstellt ein <xref:System.Threading.Tasks.TaskScheduler>-Objekt, das Arbeiten im aktuellen Synchronisierungskontext durchführt.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-126">The <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> method creates a <xref:System.Threading.Tasks.TaskScheduler> object that performs work on the current synchronization context.</span></span> <span data-ttu-id="b2aaf-127">Da der `Form1`-Konstruktor über den Benutzeroberflächenthread aufgerufen wird, werden die Aktionen für den `incrementProgress`- und den `decrementProgress`-Datenflussblock ebenfalls im Benutzeroberflächenthread ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-127">Because the `Form1` constructor is called from the user-interface thread, the actions for the `incrementProgress` and `decrementProgress` dataflow blocks also run on the user-interface thread.</span></span>  
  
 <span data-ttu-id="b2aaf-128">In diesem Beispiel wird die <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> Eigenschaft, wenn sie die Elemente der Pipeline erstellt.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-128">This example sets the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property when it constructs the members of the pipeline.</span></span> <span data-ttu-id="b2aaf-129">Da die <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> Eigenschaft bricht dauerhaft Dataflow-Ausführung melden Block ab, die gesamte Pipeline muss neu erstellt werden, nachdem der Benutzer bricht den Vorgang ab und dann möchte mehr Arbeitsaufgaben in die Pipeline hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-129">Because the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property permanently cancels dataflow block execution, the whole pipeline must be recreated after the user cancels the operation and then wants to add more work items to the pipeline.</span></span> <span data-ttu-id="b2aaf-130">Ein Beispiel für eine alternative Möglichkeit zum Abbrechen eines Datenflussblocks, die erlaubt, dass nach dem Abbrechen eines Vorgangs andere Arbeit ausgeführt wird, finden Sie unter [Exemplarische Vorgehensweise: Verwenden eines Datenflusses in einer Windows Forms-Anwendung](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span><span class="sxs-lookup"><span data-stu-id="b2aaf-130">For an example that demonstrates an alternative way to cancel a dataflow block so that other work can be performed after an operation is canceled, see [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span></span>  
  
## <a name="connecting-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="b2aaf-131">Verbinden der Datenflusspipeline mit der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="b2aaf-131">Connecting the Dataflow Pipeline to the User Interface</span></span>  
 <span data-ttu-id="b2aaf-132">In diesem Abschnitt wird beschrieben, wie Sie die Datenflusspipeline mit der Benutzeroberfläche verbinden.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-132">This section describes how to connect the dataflow pipeline to the user interface.</span></span> <span data-ttu-id="b2aaf-133">Sowohl das Erstellen der Pipeline als auch das Hinzufügen von Arbeitsaufgaben zur Pipeline werden vom Ereignishandler für die Schaltfläche **Arbeitselemente hinzufügen** gesteuert.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-133">Both creating the pipeline and adding work items to the pipeline are controlled by the event handler for the **Add Work Items** button.</span></span> <span data-ttu-id="b2aaf-134">Der Abbruch wird durch die Schaltfläche **Abbrechen** initiiert.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-134">Cancellation is initiated by the **Cancel** button.</span></span> <span data-ttu-id="b2aaf-135">Wenn der Benutzer auf eine dieser Schaltflächen klickt, wird die entsprechende Aktion auf asynchrone Weise initiiert.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-135">When the user clicks either of these buttons, the appropriate action is initiated in an asynchronous manner.</span></span>  
  
#### <a name="to-connect-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="b2aaf-136">So verbinden Sie die Datenflusspipeline mit der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="b2aaf-136">To Connect the Dataflow Pipeline to the User Interface</span></span>  
  
1.  <span data-ttu-id="b2aaf-137">Erstellen Sie auf dem Formulardesigner für das Hauptformular einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignis für die **Add Work Items** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-137">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
2.  <span data-ttu-id="b2aaf-138">Implementieren der <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignis für die **Add Work Items** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-138">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3.  <span data-ttu-id="b2aaf-139">Erstellen Sie auf dem Formulardesigner für das Hauptformular einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignishandler für das **"Abbrechen"** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-139">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="b2aaf-140">Implementieren der <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignishandler für das **"Abbrechen"** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-140">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="b2aaf-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2aaf-141">Example</span></span>  
 <span data-ttu-id="b2aaf-142">Das folgende Beispiel zeigt den vollständigen Code für „Form1.cs“ („Form1.vb“ in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="b2aaf-142">The following example shows the complete code for Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 <span data-ttu-id="b2aaf-143">Die folgende Abbildung zeigt die ausgeführte Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b2aaf-143">The following illustration shows the running application.</span></span>  
  
 <span data-ttu-id="b2aaf-144">![Windows Forms-Anwendung](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span><span class="sxs-lookup"><span data-stu-id="b2aaf-144">![The Windows Forms Application](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b2aaf-145">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="b2aaf-145">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2aaf-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2aaf-146">See Also</span></span>  
 [<span data-ttu-id="b2aaf-147">Dataflow (Datenfluss)</span><span class="sxs-lookup"><span data-stu-id="b2aaf-147">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
