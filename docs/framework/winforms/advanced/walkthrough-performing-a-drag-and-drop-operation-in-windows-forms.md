---
title: "Exemplarische Vorgehensweise: Ausführen von Drag & Drop-Vorgängen in Windows Forms"
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
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fe2b54123e117f21f3bda7bc78bc9c5b45fc9ae3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="88009-102">Exemplarische Vorgehensweise: Ausführen von Drag & Drop-Vorgängen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="88009-102">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="88009-103">Drag & Drop-Operationen in Windows-basierten Anwendungen müssen Sie insbesondere eine Reihe von Ereignissen, behandeln die <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, und <xref:System.Windows.Forms.Control.DragDrop> Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="88009-103">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="88009-104">Wenn Sie die Daten aus den Ereignisargumenten dieser Ereignisse verwenden, können Sie Drag & Drop-Vorgänge problemlos vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="88009-104">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="88009-105">Ziehen von Daten</span><span class="sxs-lookup"><span data-stu-id="88009-105">Dragging Data</span></span>  
 <span data-ttu-id="88009-106">Drag & Drop-Vorgänge beginnen immer mit dem Ziehen (Dragging).</span><span class="sxs-lookup"><span data-stu-id="88009-106">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="88009-107">Die Funktionalität zum Aktivieren der Daten erfasst werden, bei Beginn des Ziehvorgangs wird implementiert, der <xref:System.Windows.Forms.Control.DoDragDrop%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="88009-107">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="88009-108">Im folgenden Beispiel die <xref:System.Windows.Forms.Control.MouseDown> Ereignis wird verwendet, um den Ziehvorgang gestartet werden, da es die intuitivste ist (die meisten Drag-and-Drop-Aktionen beginnen mit der Maustaste gedrückt wird).</span><span class="sxs-lookup"><span data-stu-id="88009-108">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="88009-109">Beachten Sie dabei jedoch, dass für das Starten des Drag & Drop-Vorgangs jedes beliebige Ereignis verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="88009-109">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88009-110">Bestimmte Steuerelemente verfügen über benutzerdefinierte für Ziehvorgänge spezifische Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="88009-110">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="88009-111">Die <xref:System.Windows.Forms.ListView> und <xref:System.Windows.Forms.TreeView> haben Sie Steuerelemente, z. B. ein <xref:System.Windows.Forms.TreeView.ItemDrag> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="88009-111">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="88009-112">So starten Sie einen Zielvorgang</span><span class="sxs-lookup"><span data-stu-id="88009-112">To start a drag operation</span></span>  
  
1.  <span data-ttu-id="88009-113">In der <xref:System.Windows.Forms.Control.MouseDown> -Ereignis für das Steuerelement, in dem der Ziehvorgang beginnt, verwenden die `DoDragDrop` Methode, um die Daten zu ziehende festgelegt und der zulässigen Effekt darstellt, das gezogen haben.</span><span class="sxs-lookup"><span data-stu-id="88009-113">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="88009-114">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Data%2A> und <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span><span class="sxs-lookup"><span data-stu-id="88009-114">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="88009-115">Im folgenden Beispiel wird gezeigt, wie ein Ziehvorgang gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="88009-115">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="88009-116">Ist das Steuerelement, an der der Ziehvorgang beginnt, ein <xref:System.Windows.Forms.Button> -Steuerelement, die gezogenen Daten ist die Zeichenfolge darstellt. die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft von der <xref:System.Windows.Forms.Button> -Steuerelement, und die zulässigen Auswirkungen entweder kopieren oder verschieben.</span><span class="sxs-lookup"><span data-stu-id="88009-116">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
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
    >  <span data-ttu-id="88009-117">Alle Daten verwendet werden können, als Parameter in der `DoDragDrop` Methode; im Beispiel oben, die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft der <xref:System.Windows.Forms.Button> Steuerelement wurde (anstatt einen Wert fest zu codieren, oder Abrufen von Daten aus einem Dataset) verwendet, da die Eigenschaft in Verbindung wurde der Speicherort von gezogenen (die <xref:System.Windows.Forms.Button> Steuerelement).</span><span class="sxs-lookup"><span data-stu-id="88009-117">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="88009-118">Dies sollte bei der Integration von Drag & Drop-Vorgängen in Windows-basierte Anwendungen stets beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="88009-118">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="88009-119">Während ein Ziehvorgangs aktiviert ist, können Sie behandeln die <xref:System.Windows.Forms.Control.QueryContinueDrag> Ereignis, das "Berechtigung fordert" des Systems, der Ziehvorgang fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="88009-119">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="88009-120">Bei der Behandlung von dieser Methode wird auch der entsprechenden Stelle Sie Methoden aufrufen, die Auswirkungen auf die Ziehvorgangs wird, beispielsweise bei der Erweiterung wird eine <xref:System.Windows.Forms.TreeNode> in einem <xref:System.Windows.Forms.TreeView> steuern, wenn der Cursor darüber bewegt wird.</span><span class="sxs-lookup"><span data-stu-id="88009-120">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="88009-121">Ablegen von Daten</span><span class="sxs-lookup"><span data-stu-id="88009-121">Dropping Data</span></span>  
 <span data-ttu-id="88009-122">Nachdem Sie begonnen haben, Daten von einer Stelle einer Windows Form oder eines Steuerelements zu ziehen, möchten Sie diese natürlich auch irgendwo ablegen (Dropping).</span><span class="sxs-lookup"><span data-stu-id="88009-122">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="88009-123">Der Cursor verändert sich, wenn er über einen Bereich auf einem Formular oder Steuerelement bewegt wird, der für das Ablegen von Daten konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="88009-123">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="88009-124">Ein Bereich innerhalb eines Windows-Formulars oder Steuerelements kann erfolgen, damit akzeptieren abgelegte Daten durch Festlegen der <xref:System.Windows.Forms.Control.AllowDrop%2A> -Eigenschaft und die Behandlung der <xref:System.Windows.Forms.Control.DragEnter> und <xref:System.Windows.Forms.Control.DragDrop> Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="88009-124">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="88009-125">So führen Sie einen Ablegevorgang aus</span><span class="sxs-lookup"><span data-stu-id="88009-125">To perform a drop</span></span>  
  
1.  <span data-ttu-id="88009-126">Legen Sie die <xref:System.Windows.Forms.Control.AllowDrop%2A> Eigenschaft auf "true".</span><span class="sxs-lookup"><span data-stu-id="88009-126">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2.  <span data-ttu-id="88009-127">In der `DragEnter` -Ereignis für das Steuerelement, auf denen die Drop erfolgt, stellen Sie sicher, dass die gezogenen Daten einen zulässigen Typ ist (in diesem Fall <xref:System.Windows.Forms.Control.Text%2A>).</span><span class="sxs-lookup"><span data-stu-id="88009-127">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="88009-128">Der Code legt dann die Auswirkungen, die bei einem Wert in die Dropdownliste geschieht die <xref:System.Windows.Forms.DragDropEffects> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="88009-128">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="88009-129">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="88009-129">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
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
    >  <span data-ttu-id="88009-130">Können eigene definieren <xref:System.Windows.Forms.DataFormats> durch Angabe Ihres eigenen Objekts als die <xref:System.Object> Parameter von der <xref:System.Windows.Forms.DataObject.SetData%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="88009-130">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="88009-131">Stellen Sie dabei sicher, dass das angegebene Objekt serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="88009-131">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="88009-132">Weitere Informationen finden Sie unter <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="88009-132">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3.  <span data-ttu-id="88009-133">In der <xref:System.Windows.Forms.Control.DragDrop> -Ereignis für das Steuerelement, auf denen die Drop erfolgt, verwenden die <xref:System.Windows.Forms.DataObject.GetData%2A> Methode, um die gezogenen Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="88009-133">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="88009-134">Weitere Informationen finden Sie unter <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span><span class="sxs-lookup"><span data-stu-id="88009-134">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="88009-135">Im folgenden Beispiel wird eine <xref:System.Windows.Forms.TextBox> ist das Steuerelement gezogene (wobei die Drop erfolgt).</span><span class="sxs-lookup"><span data-stu-id="88009-135">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="88009-136">Der Code legt die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft von der <xref:System.Windows.Forms.TextBox> steuern die gezogenen Daten gleich.</span><span class="sxs-lookup"><span data-stu-id="88009-136">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
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
    >  <span data-ttu-id="88009-137">Darüber hinaus können Sie arbeiten mit der <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> -Eigenschaft, je nach Schlüssel während des Drag-and-Drop-Vorgangs gedrückt bestimmte Auswirkungen auftreten (z. B. ist es die gezogenen Daten kopiert werden, wenn die STRG-Taste gedrückt wird, standard).</span><span class="sxs-lookup"><span data-stu-id="88009-137">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88009-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88009-138">See Also</span></span>  
 [<span data-ttu-id="88009-139">Gewusst wie: Hinzufügen von Daten zur Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="88009-139">How to: Add Data to the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 [<span data-ttu-id="88009-140">Gewusst wie: Abrufen von Daten aus der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="88009-140">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 [<span data-ttu-id="88009-141">Drag & Drop-Vorgänge und Unterstützung der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="88009-141">Drag-and-Drop Operations and Clipboard Support</span></span>](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)
