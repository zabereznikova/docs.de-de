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
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>Exemplarische Vorgehensweise: Ausführen von Drag & Drop-Vorgängen in Windows Forms
Um Drag & Drop-Vorgänge in Windows-basierten Anwendungen auszuführen, müssen Sie eine Reihe von Ereignissen verarbeiten, insbesondere die <xref:System.Windows.Forms.Control.DragEnter>-, <xref:System.Windows.Forms.Control.DragLeave>-und <xref:System.Windows.Forms.Control.DragDrop>-Ereignisse. Wenn Sie die Daten aus den Ereignisargumenten dieser Ereignisse verwenden, können Sie Drag & Drop-Vorgänge problemlos vereinfachen.  
  
## <a name="dragging-data"></a>Ziehen von Daten  
 Drag & Drop-Vorgänge beginnen immer mit dem Ziehen (Dragging). Die Funktion, mit der Daten beim Ziehen von Daten gesammelt werden können, wird in der <xref:System.Windows.Forms.Control.DoDragDrop%2A>-Methode implementiert.  
  
 Im folgenden Beispiel wird das <xref:System.Windows.Forms.Control.MouseDown> Ereignis verwendet, um den Zieh Vorgang zu starten, da es sich hierbei um die intuitivste Aktion handelt (die meisten Drag & Drop-Aktionen beginnen mit der Maus, die gedrückt ist). Beachten Sie dabei jedoch, dass für das Starten des Drag & Drop-Vorgangs jedes beliebige Ereignis verwendet werden kann.  
  
> [!NOTE]
> Bestimmte Steuerelemente verfügen über benutzerdefinierte für Ziehvorgänge spezifische Ereignisse. Die <xref:System.Windows.Forms.ListView>-und <xref:System.Windows.Forms.TreeView> Steuerelemente haben z. b. ein <xref:System.Windows.Forms.TreeView.ItemDrag> Ereignis.  
  
#### <a name="to-start-a-drag-operation"></a>So starten Sie einen Zielvorgang  
  
1. Verwenden Sie im <xref:System.Windows.Forms.Control.MouseDown>-Ereignis für das Steuerelement, bei dem der Zieh Vorgang beginnt, die `DoDragDrop`-Methode, um die Daten festzulegen, die gezogen werden sollen, und die zulässige Auswirkung der Zieh Kraft. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Data%2A> und <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
     Im folgenden Beispiel wird gezeigt, wie ein Ziehvorgang gestartet wird. Das Steuerelement, bei dem der Zieh Vorgang beginnt, ist ein <xref:System.Windows.Forms.Button>-Steuerelement, die gezogenen Daten sind die Zeichenfolge, die die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft des <xref:System.Windows.Forms.Button>-Steuer Elements darstellt, und die zulässigen Effekte sind entweder kopieren oder verschieben.  
  
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
    > Alle Daten können als Parameter in der `DoDragDrop`-Methode verwendet werden. im obigen Beispiel wurde die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft des <xref:System.Windows.Forms.Button> Steuer Elements verwendet (anstatt einen Wert hart codieren oder Daten aus einem Dataset abzurufen), da die-Eigenschaft mit dem Speicherort verknüpft war, von dem gezogen wird (das <xref:System.Windows.Forms.Button>-Steuerelement). Dies sollte bei der Integration von Drag & Drop-Vorgängen in Windows-basierte Anwendungen stets beachtet werden.  
  
 Während ein Zieh Vorgang wirksam ist, können Sie das <xref:System.Windows.Forms.Control.QueryContinueDrag>-Ereignis behandeln, das "die Berechtigung" des Systems zum Fortsetzen des Zieh Vorgangs anfordert. Wenn Sie diese Methode verarbeiten, können Sie auch Methoden aufzurufen, die Auswirkungen auf den Zieh Vorgang haben, z. b. das Erweitern eines <xref:System.Windows.Forms.TreeNode> in einem <xref:System.Windows.Forms.TreeView>-Steuerelement, wenn der Cursor darauf zeigt.  
  
## <a name="dropping-data"></a>Ablegen von Daten  
 Nachdem Sie begonnen haben, Daten von einer Stelle einer Windows Form oder eines Steuerelements zu ziehen, möchten Sie diese natürlich auch irgendwo ablegen (Dropping). Der Cursor verändert sich, wenn er über einen Bereich auf einem Formular oder Steuerelement bewegt wird, der für das Ablegen von Daten konfiguriert ist. Jeder Bereich innerhalb eines Windows Forms oder Steuer Elements kann zum Akzeptieren von gelöschten Daten durch Festlegen der <xref:System.Windows.Forms.Control.AllowDrop%2A>-Eigenschaft und Behandlung der Ereignisse <xref:System.Windows.Forms.Control.DragEnter> und <xref:System.Windows.Forms.Control.DragDrop> vorgenommen werden.  
  
#### <a name="to-perform-a-drop"></a>So führen Sie einen Ablegevorgang aus  
  
1. Legen Sie die <xref:System.Windows.Forms.Control.AllowDrop%2A>-Eigenschaft auf true fest.  
  
2. Stellen Sie im `DragEnter`-Ereignis für das Steuerelement, in dem der Ablage Vorgang auftritt, sicher, dass die gezogenen Daten einen zulässigen Typ haben (in diesem Fall <xref:System.Windows.Forms.Control.Text%2A>). Der Code legt dann den Effekt fest, der auftritt, wenn der Ablage Vorgang für einen Wert in der <xref:System.Windows.Forms.DragDropEffects> Enumeration auftritt. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
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
    > Sie können Ihre eigenen <xref:System.Windows.Forms.DataFormats> definieren, indem Sie ein eigenes-Objekt als <xref:System.Object> Parameter der <xref:System.Windows.Forms.DataObject.SetData%2A>-Methode angeben. Stellen Sie dabei sicher, dass das angegebene Objekt serialisierbar ist. Weitere Informationen finden Sie unter <xref:System.Runtime.Serialization.ISerializable>.  
  
3. Verwenden Sie im <xref:System.Windows.Forms.Control.DragDrop>-Ereignis für das Steuerelement, in dem der Ablage Vorgang auftritt, die <xref:System.Windows.Forms.DataObject.GetData%2A>-Methode, um die gezogenen Daten abzurufen. Weitere Informationen finden Sie unter <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.  
  
     Im folgenden Beispiel ist ein <xref:System.Windows.Forms.TextBox> Steuerelement das Steuerelement, zu dem gezogen wird (wo der Ablage auftritt). Der Code legt die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft des <xref:System.Windows.Forms.TextBox> Steuer Elements auf die gezogenen Daten fest.  
  
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
    > Außerdem können Sie mit der <xref:System.Windows.Forms.DragEventArgs.KeyState%2A>-Eigenschaft arbeiten, sodass abhängig von den Schlüsseln, die während des Drag & Drop-Vorgangs gedrückt werden, bestimmte Effekte auftreten (z. b. ist es Standard, die gezogenen Daten zu kopieren, wenn die STRG-Taste gedrückt wird).  
  
## <a name="see-also"></a>Weitere Informationen

- [Gewusst wie: Hinzufügen von Daten zur Zwischenablage](how-to-add-data-to-the-clipboard.md)
- [Gewusst wie: Abrufen von Daten aus der Zwischenablage](how-to-retrieve-data-from-the-clipboard.md)
- [Drag & Drop-Vorgänge und Unterstützung der Zwischenablage](drag-and-drop-operations-and-clipboard-support.md)
