---
title: 'Exemplarische Vorgehensweise: Ausführen eines Drag & Drop-Vorgangs'
description: Erfahren Sie, wie Sie einen Drag & Drop-Vorgang in Windows Forms ausführen, indem Sie eine Reihe von Ereignissen verarbeiten, insbesondere die DragEnter-, DragLeave-und DragDrop-Ereignisse.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 83bfda875e2fdec3981bbcb8f8f7be00db342440
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325812"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="98f62-103">Exemplarische Vorgehensweise: Ausführen von Drag & Drop-Operationen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="98f62-103">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="98f62-104">Um Drag & Drop-Vorgänge in Windows-basierten Anwendungen auszuführen, müssen Sie eine Reihe von Ereignissen verarbeiten, insbesondere die <xref:System.Windows.Forms.Control.DragEnter> Ereignisse, <xref:System.Windows.Forms.Control.DragLeave> und <xref:System.Windows.Forms.Control.DragDrop> .</span><span class="sxs-lookup"><span data-stu-id="98f62-104">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="98f62-105">Wenn Sie die Daten aus den Ereignisargumenten dieser Ereignisse verwenden, können Sie Drag & Drop-Vorgänge problemlos vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="98f62-105">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="98f62-106">Ziehen von Daten</span><span class="sxs-lookup"><span data-stu-id="98f62-106">Dragging Data</span></span>  
 <span data-ttu-id="98f62-107">Drag & Drop-Vorgänge beginnen immer mit dem Ziehen (Dragging).</span><span class="sxs-lookup"><span data-stu-id="98f62-107">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="98f62-108">Die Funktion, mit der Daten beim Ziehen von Daten gesammelt werden können, wird in der- <xref:System.Windows.Forms.Control.DoDragDrop%2A> Methode implementiert.</span><span class="sxs-lookup"><span data-stu-id="98f62-108">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="98f62-109">Im folgenden Beispiel wird das- <xref:System.Windows.Forms.Control.MouseDown> Ereignis verwendet, um den Zieh Vorgang zu starten, da es sich hierbei um die intuitivste Aktion handelt (die meisten Drag & Drop-Aktionen beginnen mit der Maustaste, wenn die Maustaste gedrückt ist).</span><span class="sxs-lookup"><span data-stu-id="98f62-109">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="98f62-110">Beachten Sie dabei jedoch, dass für das Starten des Drag & Drop-Vorgangs jedes beliebige Ereignis verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="98f62-110">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98f62-111">Bestimmte Steuerelemente verfügen über benutzerdefinierte für Ziehvorgänge spezifische Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="98f62-111">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="98f62-112">Die <xref:System.Windows.Forms.ListView> -und-Steuer <xref:System.Windows.Forms.TreeView> Elemente haben z. b. ein- <xref:System.Windows.Forms.TreeView.ItemDrag> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="98f62-112">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="98f62-113">So starten Sie einen Zielvorgang</span><span class="sxs-lookup"><span data-stu-id="98f62-113">To start a drag operation</span></span>  
  
1. <span data-ttu-id="98f62-114">Verwenden Sie im- <xref:System.Windows.Forms.Control.MouseDown> Ereignis für das Steuerelement, bei dem der Zieh Vorgang beginnt, die `DoDragDrop` -Methode, um die Daten festzulegen, die gezogen werden sollen, und die zulässige Auswirkung der Zieh Kraft.</span><span class="sxs-lookup"><span data-stu-id="98f62-114">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="98f62-115">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Data%2A> und <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span><span class="sxs-lookup"><span data-stu-id="98f62-115">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="98f62-116">Im folgenden Beispiel wird gezeigt, wie ein Ziehvorgang gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="98f62-116">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="98f62-117">Das Steuerelement, bei dem der Zieh Vorgang beginnt, ist ein- <xref:System.Windows.Forms.Button> Steuerelement, die gezogenen Daten sind die Zeichenfolge, die die <xref:System.Windows.Forms.Control.Text%2A> -Eigenschaft des Steuer Elements darstellt <xref:System.Windows.Forms.Button> , und die zulässigen Effekte sind entweder kopieren oder verschieben.</span><span class="sxs-lookup"><span data-stu-id="98f62-117">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
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
    > <span data-ttu-id="98f62-118">Alle Daten können als Parameter in der-Methode verwendet werden `DoDragDrop` . im obigen Beispiel wurde die- <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft des- <xref:System.Windows.Forms.Button> Steuer Elements verwendet (anstatt einen Wert hart zu codieren oder Daten aus einem Dataset abzurufen), da die-Eigenschaft mit dem Speicherort verknüpft war, der aus dem-Steuerelement gezogen wird <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="98f62-118">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="98f62-119">Dies sollte bei der Integration von Drag & Drop-Vorgängen in Windows-basierte Anwendungen stets beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="98f62-119">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="98f62-120">Während ein Zieh Vorgang wirksam ist, können Sie das- <xref:System.Windows.Forms.Control.QueryContinueDrag> Ereignis behandeln, das "die Berechtigung" für das System zum Fortsetzen des Zieh Vorgangs anfordert.</span><span class="sxs-lookup"><span data-stu-id="98f62-120">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="98f62-121">Wenn Sie diese Methode verarbeiten, können Sie auch Methoden aufzurufen, die Auswirkungen auf den Zieh Vorgang haben, z. b. das Erweitern eines <xref:System.Windows.Forms.TreeNode> in einem-Steuerelement, <xref:System.Windows.Forms.TreeView> Wenn der Cursor darauf bewegt wird.</span><span class="sxs-lookup"><span data-stu-id="98f62-121">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="98f62-122">Ablegen von Daten</span><span class="sxs-lookup"><span data-stu-id="98f62-122">Dropping Data</span></span>  
 <span data-ttu-id="98f62-123">Nachdem Sie begonnen haben, Daten von einer Stelle einer Windows Form oder eines Steuerelements zu ziehen, möchten Sie diese natürlich auch irgendwo ablegen (Dropping).</span><span class="sxs-lookup"><span data-stu-id="98f62-123">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="98f62-124">Der Cursor verändert sich, wenn er über einen Bereich auf einem Formular oder Steuerelement bewegt wird, der für das Ablegen von Daten konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="98f62-124">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="98f62-125">Alle Bereiche innerhalb eines Windows Forms oder Steuer Elements können so eingerichtet werden, dass Sie verworfene Daten akzeptieren, indem Sie die <xref:System.Windows.Forms.Control.AllowDrop%2A> -Eigenschaft festlegen und die <xref:System.Windows.Forms.Control.DragEnter> Ereignisse und behandeln <xref:System.Windows.Forms.Control.DragDrop> .</span><span class="sxs-lookup"><span data-stu-id="98f62-125">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="98f62-126">So führen Sie einen Ablegevorgang aus</span><span class="sxs-lookup"><span data-stu-id="98f62-126">To perform a drop</span></span>  
  
1. <span data-ttu-id="98f62-127">Legen Sie die- <xref:System.Windows.Forms.Control.AllowDrop%2A> Eigenschaft auf true fest.</span><span class="sxs-lookup"><span data-stu-id="98f62-127">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="98f62-128">Stellen Sie im-Ereignis für das Steuerelement, in dem der Ablage Vorgang `DragEnter` auftritt, sicher, dass die gezogenen Daten einen zulässigen Typ haben (in diesem Fall <xref:System.Windows.Forms.Control.Text%2A> ).</span><span class="sxs-lookup"><span data-stu-id="98f62-128">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="98f62-129">Der Code legt dann den Effekt fest, der auftritt, wenn der Ablage Vorgang auf einen Wert in der- <xref:System.Windows.Forms.DragDropEffects> Enumeration angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="98f62-129">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="98f62-130">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="98f62-130">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
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
    > <span data-ttu-id="98f62-131">Sie können Ihre eigenen definieren, indem Sie ein <xref:System.Windows.Forms.DataFormats> eigenes-Objekt als <xref:System.Object> Parameter der-Methode angeben <xref:System.Windows.Forms.DataObject.SetData%2A> .</span><span class="sxs-lookup"><span data-stu-id="98f62-131">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="98f62-132">Stellen Sie dabei sicher, dass das angegebene Objekt serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="98f62-132">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="98f62-133">Weitere Informationen finden Sie unter <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="98f62-133">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="98f62-134">Verwenden Sie im-Ereignis für das-Steuerelement, in dem der Löschvorgang ausgeführt <xref:System.Windows.Forms.Control.DragDrop> wird, die- <xref:System.Windows.Forms.DataObject.GetData%2A> Methode, um die gezogenen Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="98f62-134">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="98f62-135">Weitere Informationen finden Sie unter <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span><span class="sxs-lookup"><span data-stu-id="98f62-135">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="98f62-136">Im folgenden Beispiel ist ein- <xref:System.Windows.Forms.TextBox> Steuerelement das Steuerelement, zu dem gezogen wird (wo der Ablage auftritt).</span><span class="sxs-lookup"><span data-stu-id="98f62-136">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="98f62-137">Der Code legt die- <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft des- <xref:System.Windows.Forms.TextBox> Steuer Elements auf die gezogenen Daten fest.</span><span class="sxs-lookup"><span data-stu-id="98f62-137">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
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
    > <span data-ttu-id="98f62-138">Außerdem können Sie mit der- <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> Eigenschaft arbeiten, sodass abhängig von den Schlüsseln, die während des Drag & Drop-Vorgangs gedrückt werden, bestimmte Effekte auftreten (z. b. ist es Standard, die gezogenen Daten zu kopieren, wenn die STRG-Taste gedrückt wird).</span><span class="sxs-lookup"><span data-stu-id="98f62-138">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f62-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98f62-139">See also</span></span>

- [<span data-ttu-id="98f62-140">Vorgehensweise: Hinzufügen von Daten zur Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="98f62-140">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="98f62-141">Vorgehensweise: Abrufen von Daten aus der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="98f62-141">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="98f62-142">Drag &amp;amp; Drop-Operationen und Unterstützung der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="98f62-142">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
