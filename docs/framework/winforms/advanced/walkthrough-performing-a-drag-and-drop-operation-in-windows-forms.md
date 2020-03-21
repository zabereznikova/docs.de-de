---
title: 'Exemplarische Vorgehensweise: Führen Sie einen Drag-and-Drop-Vorgang aus'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: b5e4bf753733cb9bd010672f40e8fbeb0cf036bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182442"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="12c3d-102">Exemplarische Vorgehensweise: Ausführen von Drag & Drop-Vorgängen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12c3d-102">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="12c3d-103">Um Drag-and-Drop-Vorgänge in Windows-basierten Anwendungen auszuführen, müssen Sie <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragLeave>eine <xref:System.Windows.Forms.Control.DragDrop> Reihe von Ereignissen behandeln, insbesondere die , und Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="12c3d-103">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="12c3d-104">Wenn Sie die Daten aus den Ereignisargumenten dieser Ereignisse verwenden, können Sie Drag & Drop-Vorgänge problemlos vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="12c3d-104">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="12c3d-105">Ziehen von Daten</span><span class="sxs-lookup"><span data-stu-id="12c3d-105">Dragging Data</span></span>  
 <span data-ttu-id="12c3d-106">Drag & Drop-Vorgänge beginnen immer mit dem Ziehen (Dragging).</span><span class="sxs-lookup"><span data-stu-id="12c3d-106">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="12c3d-107">Die Funktionalität, mit der Daten beim Ziehen <xref:System.Windows.Forms.Control.DoDragDrop%2A> gesammelt werden können, wird in der Methode implementiert.</span><span class="sxs-lookup"><span data-stu-id="12c3d-107">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="12c3d-108">Im folgenden Beispiel <xref:System.Windows.Forms.Control.MouseDown> wird das Ereignis verwendet, um den Ziehvorgang zu starten, da es die intuitivste ist (die meisten Drag-and-Drop-Aktionen beginnen damit, dass die Maustaste gedrückt wird).</span><span class="sxs-lookup"><span data-stu-id="12c3d-108">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="12c3d-109">Beachten Sie dabei jedoch, dass für das Starten des Drag & Drop-Vorgangs jedes beliebige Ereignis verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="12c3d-109">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12c3d-110">Bestimmte Steuerelemente verfügen über benutzerdefinierte für Ziehvorgänge spezifische Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="12c3d-110">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="12c3d-111">Die <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> und Steuerelemente haben <xref:System.Windows.Forms.TreeView.ItemDrag> z. B. ein Ereignis.</span><span class="sxs-lookup"><span data-stu-id="12c3d-111">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="12c3d-112">So starten Sie einen Zielvorgang</span><span class="sxs-lookup"><span data-stu-id="12c3d-112">To start a drag operation</span></span>  
  
1. <span data-ttu-id="12c3d-113">Verwenden <xref:System.Windows.Forms.Control.MouseDown> Sie im Fall des Steuerelements, `DoDragDrop` an dem der Ziehvorgang beginnt, die Methode, um die zu ziehenden Daten festzulegen, und das zulässige Ziehen des Effekts.</span><span class="sxs-lookup"><span data-stu-id="12c3d-113">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="12c3d-114">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Data%2A> und <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span><span class="sxs-lookup"><span data-stu-id="12c3d-114">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="12c3d-115">Im folgenden Beispiel wird gezeigt, wie ein Ziehvorgang gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="12c3d-115">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="12c3d-116">Das Steuerelement, an dem <xref:System.Windows.Forms.Button> der Ziehvorgang beginnt, ist ein <xref:System.Windows.Forms.Control.Text%2A> Steuerelement, <xref:System.Windows.Forms.Button> die gezogenen Daten ist die Zeichenfolge, die die Eigenschaft des Steuerelements darstellt, und die zulässigen Effekte werden entweder kopiert oder bewegt.</span><span class="sxs-lookup"><span data-stu-id="12c3d-116">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
    ```vb  
    Private Sub Button1_MouseDown(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles Button1.MouseDown  
       Button1.DoDragDrop(Button1.Text, DragDropEffects.Copy Or DragDropEffects.Move)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_MouseDown(object sender,
    System.Windows.Forms.MouseEventArgs e)  
    {  
       button1.DoDragDrop(button1.Text, DragDropEffects.Copy |
          DragDropEffects.Move);  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="12c3d-117">Alle Daten können als Parameter `DoDragDrop` in der Methode verwendet werden. Im obigen Beispiel <xref:System.Windows.Forms.Control.Text%2A> wurde <xref:System.Windows.Forms.Button> die Eigenschaft des Steuerelements verwendet (anstatt einen Wert hart zu codieren oder Daten aus einem <xref:System.Windows.Forms.Button> Dataset abzurufen), da die Eigenschaft mit der Position verknüpft war, aus der gezogen wird (das Steuerelement).</span><span class="sxs-lookup"><span data-stu-id="12c3d-117">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="12c3d-118">Dies sollte bei der Integration von Drag & Drop-Vorgängen in Windows-basierte Anwendungen stets beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="12c3d-118">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="12c3d-119">Während ein Ziehvorgang in Kraft ist, können Sie das <xref:System.Windows.Forms.Control.QueryContinueDrag> Ereignis behandeln, das das System um Erlaubnis bittet, den Ziehvorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="12c3d-119">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="12c3d-120">Bei der Behandlung dieser Methode ist es auch der geeignete Punkt für Sie, Methoden aufzurufen, die sich auf den Ziehvorgang auswirken, z. B. das Erweitern eines <xref:System.Windows.Forms.TreeNode> in einem <xref:System.Windows.Forms.TreeView> Steuerelement, wenn der Cursor darüber schwebt.</span><span class="sxs-lookup"><span data-stu-id="12c3d-120">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="12c3d-121">Ablegen von Daten</span><span class="sxs-lookup"><span data-stu-id="12c3d-121">Dropping Data</span></span>  
 <span data-ttu-id="12c3d-122">Nachdem Sie begonnen haben, Daten von einer Stelle einer Windows Form oder eines Steuerelements zu ziehen, möchten Sie diese natürlich auch irgendwo ablegen (Dropping).</span><span class="sxs-lookup"><span data-stu-id="12c3d-122">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="12c3d-123">Der Cursor verändert sich, wenn er über einen Bereich auf einem Formular oder Steuerelement bewegt wird, der für das Ablegen von Daten konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="12c3d-123">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="12c3d-124">Jeder Bereich innerhalb eines Windows-Formulars oder Steuerelements <xref:System.Windows.Forms.Control.AllowDrop%2A> kann so <xref:System.Windows.Forms.Control.DragEnter> gemacht <xref:System.Windows.Forms.Control.DragDrop> werden, dass gelöschte Daten akzeptiert werden, indem die Eigenschaft und die Ereignisse behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="12c3d-124">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="12c3d-125">So führen Sie einen Ablegevorgang aus</span><span class="sxs-lookup"><span data-stu-id="12c3d-125">To perform a drop</span></span>  
  
1. <span data-ttu-id="12c3d-126">Legen <xref:System.Windows.Forms.Control.AllowDrop%2A> Sie die Eigenschaft auf true fest.</span><span class="sxs-lookup"><span data-stu-id="12c3d-126">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="12c3d-127">Stellen `DragEnter` Sie im Fall des Steuerelements, bei dem der Abwurf auftritt, sicher, <xref:System.Windows.Forms.Control.Text%2A>dass die gezogenen Daten einen akzeptablen Typ haben (in diesem Fall).</span><span class="sxs-lookup"><span data-stu-id="12c3d-127">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="12c3d-128">Der Code legt dann den Effekt fest, der auftritt, wenn der Drop auf einen Wert in der <xref:System.Windows.Forms.DragDropEffects> Enumeration erfolgt.</span><span class="sxs-lookup"><span data-stu-id="12c3d-128">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="12c3d-129">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="12c3d-129">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
    ```vb  
    Private Sub TextBox1_DragEnter(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
         e.Effect = DragDropEffects.Copy  
       Else  
         e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragEnter(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="12c3d-130">Sie können Ihr <xref:System.Windows.Forms.DataFormats> eigenes Objekt definieren, <xref:System.Object> indem Sie <xref:System.Windows.Forms.DataObject.SetData%2A> ein eigenes Objekt als Parameter der Methode angeben.</span><span class="sxs-lookup"><span data-stu-id="12c3d-130">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="12c3d-131">Stellen Sie dabei sicher, dass das angegebene Objekt serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="12c3d-131">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="12c3d-132">Weitere Informationen finden Sie unter <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="12c3d-132">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="12c3d-133">Verwenden <xref:System.Windows.Forms.Control.DragDrop> Sie im Fall des Steuerelements, <xref:System.Windows.Forms.DataObject.GetData%2A> in dem der Drop auftritt, die Methode, um die gezogenen Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="12c3d-133">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="12c3d-134">Weitere Informationen finden Sie unter <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span><span class="sxs-lookup"><span data-stu-id="12c3d-134">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="12c3d-135">Im folgenden Beispiel <xref:System.Windows.Forms.TextBox> ist ein Steuerelement das Steuerelement, an das gezogen wird (wo der Drop auftritt).</span><span class="sxs-lookup"><span data-stu-id="12c3d-135">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="12c3d-136">Der Code <xref:System.Windows.Forms.Control.Text%2A> legt die <xref:System.Windows.Forms.TextBox> Eigenschaft des Steuerelements gleich den gezogenen Daten fest.</span><span class="sxs-lookup"><span data-stu-id="12c3d-136">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
    ```vb  
    Private Sub TextBox1_DragDrop(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragDrop  
       TextBox1.Text = e.Data.GetData(DataFormats.Text).ToString  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragDrop(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       textBox1.Text = e.Data.GetData(DataFormats.Text).ToString();  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="12c3d-137">Darüber hinaus können Sie <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> mit der Eigenschaft arbeiten, sodass je nach gedrückten Tasten während des Drag-and-Drop-Vorgangs bestimmte Effekte auftreten (z. B. ist es Standard, die gezogenen Daten zu kopieren, wenn die STRG-Taste gedrückt wird).</span><span class="sxs-lookup"><span data-stu-id="12c3d-137">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12c3d-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12c3d-138">See also</span></span>

- [<span data-ttu-id="12c3d-139">Gewusst wie: Hinzufügen von Daten zur Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="12c3d-139">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="12c3d-140">Gewusst wie: Abrufen von Daten aus der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="12c3d-140">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="12c3d-141">Drag & Drop-Vorgänge und Unterstützung der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="12c3d-141">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
