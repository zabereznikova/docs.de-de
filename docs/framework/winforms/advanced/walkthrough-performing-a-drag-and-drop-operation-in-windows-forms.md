---
title: 'Exemplarische Vorgehensweise: Ausführen eines Drag & Drop-Vorgangs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 265e6d4f9e3370d28a18b86dea983bb0b556be41
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746796"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="df32f-102">Exemplarische Vorgehensweise: Ausführen von Drag & Drop-Operationen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="df32f-102">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="df32f-103">Um Drag & Drop-Vorgänge in Windows-basierten Anwendungen auszuführen, müssen Sie eine Reihe von Ereignissen verarbeiten, insbesondere die <xref:System.Windows.Forms.Control.DragEnter>-, <xref:System.Windows.Forms.Control.DragLeave>-und <xref:System.Windows.Forms.Control.DragDrop>-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="df32f-103">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="df32f-104">Wenn Sie die Daten aus den Ereignisargumenten dieser Ereignisse verwenden, können Sie Drag & Drop-Vorgänge problemlos vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="df32f-104">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="df32f-105">Ziehen von Daten</span><span class="sxs-lookup"><span data-stu-id="df32f-105">Dragging Data</span></span>  
 <span data-ttu-id="df32f-106">Drag & Drop-Vorgänge beginnen immer mit dem Ziehen (Dragging).</span><span class="sxs-lookup"><span data-stu-id="df32f-106">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="df32f-107">Die Funktion, mit der Daten beim Ziehen von Daten gesammelt werden können, wird in der <xref:System.Windows.Forms.Control.DoDragDrop%2A>-Methode implementiert.</span><span class="sxs-lookup"><span data-stu-id="df32f-107">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="df32f-108">Im folgenden Beispiel wird das <xref:System.Windows.Forms.Control.MouseDown> Ereignis verwendet, um den Zieh Vorgang zu starten, da es sich hierbei um die intuitivste Aktion handelt (die meisten Drag & Drop-Aktionen beginnen mit der Maus, die gedrückt ist).</span><span class="sxs-lookup"><span data-stu-id="df32f-108">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="df32f-109">Beachten Sie dabei jedoch, dass für das Starten des Drag & Drop-Vorgangs jedes beliebige Ereignis verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="df32f-109">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df32f-110">Bestimmte Steuerelemente verfügen über benutzerdefinierte für Ziehvorgänge spezifische Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="df32f-110">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="df32f-111">Die <xref:System.Windows.Forms.ListView>-und <xref:System.Windows.Forms.TreeView> Steuerelemente haben z. b. ein <xref:System.Windows.Forms.TreeView.ItemDrag> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="df32f-111">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="df32f-112">So starten Sie einen Zielvorgang</span><span class="sxs-lookup"><span data-stu-id="df32f-112">To start a drag operation</span></span>  
  
1. <span data-ttu-id="df32f-113">Verwenden Sie im <xref:System.Windows.Forms.Control.MouseDown>-Ereignis für das Steuerelement, bei dem der Zieh Vorgang beginnt, die `DoDragDrop`-Methode, um die Daten festzulegen, die gezogen werden sollen, und die zulässige Auswirkung der Zieh Kraft.</span><span class="sxs-lookup"><span data-stu-id="df32f-113">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="df32f-114">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Data%2A> und <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span><span class="sxs-lookup"><span data-stu-id="df32f-114">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="df32f-115">Im folgenden Beispiel wird gezeigt, wie ein Ziehvorgang gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="df32f-115">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="df32f-116">Das Steuerelement, bei dem der Zieh Vorgang beginnt, ist ein <xref:System.Windows.Forms.Button>-Steuerelement, die gezogenen Daten sind die Zeichenfolge, die die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuer Elements darstellt, und die zulässigen Effekte sind entweder kopieren oder verschieben.</span><span class="sxs-lookup"><span data-stu-id="df32f-116">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
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
    > <span data-ttu-id="df32f-117">Alle Daten können als Parameter in der `DoDragDrop`-Methode verwendet werden. im obigen Beispiel wurde die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft des <xref:System.Windows.Forms.Button> Steuer Elements verwendet (anstatt einen Wert hart codieren oder Daten aus einem Dataset abzurufen), da die-Eigenschaft mit dem Speicherort verknüpft war, von dem gezogen wird (das <xref:System.Windows.Forms.Button>-Steuerelement).</span><span class="sxs-lookup"><span data-stu-id="df32f-117">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="df32f-118">Dies sollte bei der Integration von Drag & Drop-Vorgängen in Windows-basierte Anwendungen stets beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="df32f-118">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="df32f-119">Während ein Zieh Vorgang wirksam ist, können Sie das <xref:System.Windows.Forms.Control.QueryContinueDrag>-Ereignis behandeln, das "die Berechtigung" des Systems zum Fortsetzen des Zieh Vorgangs anfordert.</span><span class="sxs-lookup"><span data-stu-id="df32f-119">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="df32f-120">Wenn Sie diese Methode verarbeiten, können Sie auch Methoden aufzurufen, die Auswirkungen auf den Zieh Vorgang haben, z. b. das Erweitern eines <xref:System.Windows.Forms.TreeNode> in einem <xref:System.Windows.Forms.TreeView>-Steuerelement, wenn der Cursor darauf zeigt.</span><span class="sxs-lookup"><span data-stu-id="df32f-120">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="df32f-121">Ablegen von Daten</span><span class="sxs-lookup"><span data-stu-id="df32f-121">Dropping Data</span></span>  
 <span data-ttu-id="df32f-122">Nachdem Sie begonnen haben, Daten von einer Stelle einer Windows Form oder eines Steuerelements zu ziehen, möchten Sie diese natürlich auch irgendwo ablegen (Dropping).</span><span class="sxs-lookup"><span data-stu-id="df32f-122">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="df32f-123">Der Cursor verändert sich, wenn er über einen Bereich auf einem Formular oder Steuerelement bewegt wird, der für das Ablegen von Daten konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="df32f-123">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="df32f-124">Jeder Bereich innerhalb eines Windows Forms oder Steuer Elements kann zum Akzeptieren von gelöschten Daten durch Festlegen der <xref:System.Windows.Forms.Control.AllowDrop%2A>-Eigenschaft und Behandlung der Ereignisse <xref:System.Windows.Forms.Control.DragEnter> und <xref:System.Windows.Forms.Control.DragDrop> vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="df32f-124">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="df32f-125">So führen Sie einen Ablegevorgang aus</span><span class="sxs-lookup"><span data-stu-id="df32f-125">To perform a drop</span></span>  
  
1. <span data-ttu-id="df32f-126">Legen Sie die <xref:System.Windows.Forms.Control.AllowDrop%2A>-Eigenschaft auf true fest.</span><span class="sxs-lookup"><span data-stu-id="df32f-126">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="df32f-127">Stellen Sie im `DragEnter`-Ereignis für das Steuerelement, in dem der Ablage Vorgang auftritt, sicher, dass die gezogenen Daten einen zulässigen Typ haben (in diesem Fall <xref:System.Windows.Forms.Control.Text%2A>).</span><span class="sxs-lookup"><span data-stu-id="df32f-127">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="df32f-128">Der Code legt dann den Effekt fest, der auftritt, wenn der Ablage Vorgang für einen Wert in der <xref:System.Windows.Forms.DragDropEffects> Enumeration auftritt.</span><span class="sxs-lookup"><span data-stu-id="df32f-128">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="df32f-129">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="df32f-129">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
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
    > <span data-ttu-id="df32f-130">Sie können Ihre eigenen <xref:System.Windows.Forms.DataFormats> definieren, indem Sie ein eigenes-Objekt als <xref:System.Object> Parameter der <xref:System.Windows.Forms.DataObject.SetData%2A>-Methode angeben.</span><span class="sxs-lookup"><span data-stu-id="df32f-130">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="df32f-131">Stellen Sie dabei sicher, dass das angegebene Objekt serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="df32f-131">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="df32f-132">Weitere Informationen finden Sie unter <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="df32f-132">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="df32f-133">Verwenden Sie im <xref:System.Windows.Forms.Control.DragDrop>-Ereignis für das Steuerelement, in dem der Ablage Vorgang auftritt, die <xref:System.Windows.Forms.DataObject.GetData%2A>-Methode, um die gezogenen Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="df32f-133">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="df32f-134">Weitere Informationen finden Sie unter <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span><span class="sxs-lookup"><span data-stu-id="df32f-134">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="df32f-135">Im folgenden Beispiel ist ein <xref:System.Windows.Forms.TextBox> Steuerelement das Steuerelement, zu dem gezogen wird (wo der Ablage auftritt).</span><span class="sxs-lookup"><span data-stu-id="df32f-135">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="df32f-136">Der Code legt die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft des <xref:System.Windows.Forms.TextBox> Steuer Elements auf die gezogenen Daten fest.</span><span class="sxs-lookup"><span data-stu-id="df32f-136">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
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
    > <span data-ttu-id="df32f-137">Außerdem können Sie mit der <xref:System.Windows.Forms.DragEventArgs.KeyState%2A>-Eigenschaft arbeiten, sodass abhängig von den Schlüsseln, die während des Drag & Drop-Vorgangs gedrückt werden, bestimmte Effekte auftreten (z. b. ist es Standard, die gezogenen Daten zu kopieren, wenn die STRG-Taste gedrückt wird).</span><span class="sxs-lookup"><span data-stu-id="df32f-137">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df32f-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df32f-138">See also</span></span>

- [<span data-ttu-id="df32f-139">Gewusst wie: Hinzufügen von Daten zur Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="df32f-139">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="df32f-140">Gewusst wie: Abrufen von Daten aus der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="df32f-140">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="df32f-141">Drag & Drop-Vorgänge und Unterstützung der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="df32f-141">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
