---
title: 'Exemplarische Vorgehensweise: Eine Drag & Drop-Vorgang in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: b582043b3b576b3750b897b17a5f6e0cbdeb84f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647633"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>Exemplarische Vorgehensweise: Eine Drag & Drop-Vorgang in Windows Forms
Zum Ausführen von Drag & Drop-Vorgängen in Windows-basierten Anwendungen müssen Sie insbesondere eine Reihe von Ereignissen, behandeln die <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, und <xref:System.Windows.Forms.Control.DragDrop> Ereignisse. Wenn Sie die Daten aus den Ereignisargumenten dieser Ereignisse verwenden, können Sie Drag & Drop-Vorgänge problemlos vereinfachen.  
  
## <a name="dragging-data"></a>Ziehen von Daten  
 Drag & Drop-Vorgänge beginnen immer mit dem Ziehen (Dragging). Die Funktionalität zum Aktivieren von Daten gesammelt werden sollen, wenn es sich bei Beginn des Ziehvorgangs wird implementiert, der <xref:System.Windows.Forms.Control.DoDragDrop%2A> Methode.  
  
 Im folgenden Beispiel die <xref:System.Windows.Forms.Control.MouseDown> Ereignis wird verwendet, um den Ziehvorgang gestartet werden, da es am intuitivsten ist (die meisten Drag & Drop-Aktionen beginnen mit der Maustaste gedrückt wird). Beachten Sie dabei jedoch, dass für das Starten des Drag & Drop-Vorgangs jedes beliebige Ereignis verwendet werden kann.  
  
> [!NOTE]
>  Bestimmte Steuerelemente verfügen über benutzerdefinierte für Ziehvorgänge spezifische Ereignisse. Die <xref:System.Windows.Forms.ListView> und <xref:System.Windows.Forms.TreeView> -Steuerelemente, z. B. haben eine <xref:System.Windows.Forms.TreeView.ItemDrag> Ereignis.  
  
#### <a name="to-start-a-drag-operation"></a>So starten Sie einen Zielvorgang  
  
1.  In der <xref:System.Windows.Forms.Control.MouseDown> Ereignis für das Steuerelement, in dem der Ziehvorgang beginnen, verwenden die `DoDragDrop` Methode, um die zu ziehenden Daten festzulegen und die zulässige Wirkung haben. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Data%2A> und <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
     Im folgenden Beispiel wird gezeigt, wie ein Ziehvorgang gestartet wird. Das Steuerelement, an dem der Ziehvorgang beginnt, eine <xref:System.Windows.Forms.Button> -Steuerelement die gezogenen Daten ist die Zeichenfolgendarstellung der <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft der <xref:System.Windows.Forms.Button> -Steuerelement und die zulässigen Auswirkungen sind entweder kopieren oder verschieben.  
  
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
    >  Können beliebige Daten verwendet werden, als Parameter in der `DoDragDrop` Methode; im obigen Beispiel ist die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft der <xref:System.Windows.Forms.Button> Steuerelement verwendet (anstatt einen Wert fest zu codieren oder Abrufen von Daten aus einem Dataset), da die Eigenschaft mit verbunden war die Position gezogen wurde (die <xref:System.Windows.Forms.Button> Steuerelement). Dies sollte bei der Integration von Drag & Drop-Vorgängen in Windows-basierte Anwendungen stets beachtet werden.  
  
 Während ein Ziehvorgangs aktiviert ist, können Sie behandeln die <xref:System.Windows.Forms.Control.QueryContinueDrag> -Ereignis, das "Erlaubnis fragt" des Systems, der der Ziehvorgang fortgesetzt. Bei der Behandlung von dieser Methode ist auch der entsprechenden Stelle an, Sie Methoden aufzurufen, die Auswirkungen auf den Ziehvorgang auswirken, z. B. das Erweitern einer <xref:System.Windows.Forms.TreeNode> in einem <xref:System.Windows.Forms.TreeView> steuern, wenn der Cursor darüber bewegt wird.  
  
## <a name="dropping-data"></a>Ablegen von Daten  
 Nachdem Sie begonnen haben, Daten von einer Stelle einer Windows Form oder eines Steuerelements zu ziehen, möchten Sie diese natürlich auch irgendwo ablegen (Dropping). Der Cursor verändert sich, wenn er über einen Bereich auf einem Formular oder Steuerelement bewegt wird, der für das Ablegen von Daten konfiguriert ist. Bereiche in einem Windows-Formular oder Steuerelement durch Festlegen von abgelegte Daten angenommen gestellt werden die <xref:System.Windows.Forms.Control.AllowDrop%2A> -Eigenschaft und die Behandlung der <xref:System.Windows.Forms.Control.DragEnter> und <xref:System.Windows.Forms.Control.DragDrop> Ereignisse.  
  
#### <a name="to-perform-a-drop"></a>So führen Sie einen Ablegevorgang aus  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.AllowDrop%2A> Eigenschaft auf "true".  
  
2.  In der `DragEnter` Ereignis für das Steuerelement, in dem der Ablegevorgang erfolgt, stellen Sie sicher, dass die gezogenen Daten einem zulässigen Typ ist (in diesem Fall <xref:System.Windows.Forms.Control.Text%2A>). Der Code legt dann die Auswirkungen, die durchgeführt werden, wenn das ablegen, auf einen Wert in geschieht der <xref:System.Windows.Forms.DragDropEffects> Enumeration. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
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
    >  Können Ihren eigenen definieren <xref:System.Windows.Forms.DataFormats> durch Angabe Ihrer eigenen Objekt als die <xref:System.Object> Parameter, der die <xref:System.Windows.Forms.DataObject.SetData%2A> Methode. Stellen Sie dabei sicher, dass das angegebene Objekt serialisierbar ist. Weitere Informationen finden Sie unter <xref:System.Runtime.Serialization.ISerializable>.  
  
3.  In der <xref:System.Windows.Forms.Control.DragDrop> Ereignis für das Steuerelement, in dem der Ablegevorgang erfolgt, verwenden die <xref:System.Windows.Forms.DataObject.GetData%2A> Methode, um die gezogenen Daten abzurufen. Weitere Informationen finden Sie unter <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.  
  
     Im folgenden Beispiel wird eine <xref:System.Windows.Forms.TextBox> ist das Steuerelement gezogene (und auf dem der Ablegevorgang erfolgt). Der Code legt die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft der <xref:System.Windows.Forms.TextBox> steuern die gezogenen Daten gleich.  
  
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
    >  Sie können darüber hinaus arbeiten, mit der <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> -Eigenschaft, je nach Schlüssel während des Drag & Drop-Vorgangs erschießen bestimmter Effekte auftreten (z. B. ist es standard, um die gezogenen Daten zu kopieren, wenn die STRG-Taste gedrückt wird).  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Hinzufügen von Daten in die Zwischenablage](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)
- [Vorgehensweise: Abrufen von Daten aus der Zwischenablage](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)
- [Drag & Drop-Vorgänge und Unterstützung der Zwischenablage](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)
