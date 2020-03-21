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
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>Exemplarische Vorgehensweise: Ausführen von Drag & Drop-Vorgängen in Windows Forms
Um Drag-and-Drop-Vorgänge in Windows-basierten Anwendungen auszuführen, müssen Sie <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragLeave>eine <xref:System.Windows.Forms.Control.DragDrop> Reihe von Ereignissen behandeln, insbesondere die , und Ereignisse. Wenn Sie die Daten aus den Ereignisargumenten dieser Ereignisse verwenden, können Sie Drag & Drop-Vorgänge problemlos vereinfachen.  
  
## <a name="dragging-data"></a>Ziehen von Daten  
 Drag & Drop-Vorgänge beginnen immer mit dem Ziehen (Dragging). Die Funktionalität, mit der Daten beim Ziehen <xref:System.Windows.Forms.Control.DoDragDrop%2A> gesammelt werden können, wird in der Methode implementiert.  
  
 Im folgenden Beispiel <xref:System.Windows.Forms.Control.MouseDown> wird das Ereignis verwendet, um den Ziehvorgang zu starten, da es die intuitivste ist (die meisten Drag-and-Drop-Aktionen beginnen damit, dass die Maustaste gedrückt wird). Beachten Sie dabei jedoch, dass für das Starten des Drag & Drop-Vorgangs jedes beliebige Ereignis verwendet werden kann.  
  
> [!NOTE]
> Bestimmte Steuerelemente verfügen über benutzerdefinierte für Ziehvorgänge spezifische Ereignisse. Die <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> und Steuerelemente haben <xref:System.Windows.Forms.TreeView.ItemDrag> z. B. ein Ereignis.  
  
#### <a name="to-start-a-drag-operation"></a>So starten Sie einen Zielvorgang  
  
1. Verwenden <xref:System.Windows.Forms.Control.MouseDown> Sie im Fall des Steuerelements, `DoDragDrop` an dem der Ziehvorgang beginnt, die Methode, um die zu ziehenden Daten festzulegen, und das zulässige Ziehen des Effekts. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Data%2A> und <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
     Im folgenden Beispiel wird gezeigt, wie ein Ziehvorgang gestartet wird. Das Steuerelement, an dem <xref:System.Windows.Forms.Button> der Ziehvorgang beginnt, ist ein <xref:System.Windows.Forms.Control.Text%2A> Steuerelement, <xref:System.Windows.Forms.Button> die gezogenen Daten ist die Zeichenfolge, die die Eigenschaft des Steuerelements darstellt, und die zulässigen Effekte werden entweder kopiert oder bewegt.  
  
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
    > Alle Daten können als Parameter `DoDragDrop` in der Methode verwendet werden. Im obigen Beispiel <xref:System.Windows.Forms.Control.Text%2A> wurde <xref:System.Windows.Forms.Button> die Eigenschaft des Steuerelements verwendet (anstatt einen Wert hart zu codieren oder Daten aus einem <xref:System.Windows.Forms.Button> Dataset abzurufen), da die Eigenschaft mit der Position verknüpft war, aus der gezogen wird (das Steuerelement). Dies sollte bei der Integration von Drag & Drop-Vorgängen in Windows-basierte Anwendungen stets beachtet werden.  
  
 Während ein Ziehvorgang in Kraft ist, können Sie das <xref:System.Windows.Forms.Control.QueryContinueDrag> Ereignis behandeln, das das System um Erlaubnis bittet, den Ziehvorgang fortzusetzen. Bei der Behandlung dieser Methode ist es auch der geeignete Punkt für Sie, Methoden aufzurufen, die sich auf den Ziehvorgang auswirken, z. B. das Erweitern eines <xref:System.Windows.Forms.TreeNode> in einem <xref:System.Windows.Forms.TreeView> Steuerelement, wenn der Cursor darüber schwebt.  
  
## <a name="dropping-data"></a>Ablegen von Daten  
 Nachdem Sie begonnen haben, Daten von einer Stelle einer Windows Form oder eines Steuerelements zu ziehen, möchten Sie diese natürlich auch irgendwo ablegen (Dropping). Der Cursor verändert sich, wenn er über einen Bereich auf einem Formular oder Steuerelement bewegt wird, der für das Ablegen von Daten konfiguriert ist. Jeder Bereich innerhalb eines Windows-Formulars oder Steuerelements <xref:System.Windows.Forms.Control.AllowDrop%2A> kann so <xref:System.Windows.Forms.Control.DragEnter> gemacht <xref:System.Windows.Forms.Control.DragDrop> werden, dass gelöschte Daten akzeptiert werden, indem die Eigenschaft und die Ereignisse behandelt werden.  
  
#### <a name="to-perform-a-drop"></a>So führen Sie einen Ablegevorgang aus  
  
1. Legen <xref:System.Windows.Forms.Control.AllowDrop%2A> Sie die Eigenschaft auf true fest.  
  
2. Stellen `DragEnter` Sie im Fall des Steuerelements, bei dem der Abwurf auftritt, sicher, <xref:System.Windows.Forms.Control.Text%2A>dass die gezogenen Daten einen akzeptablen Typ haben (in diesem Fall). Der Code legt dann den Effekt fest, der auftritt, wenn der Drop auf einen Wert in der <xref:System.Windows.Forms.DragDropEffects> Enumeration erfolgt. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
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
    > Sie können Ihr <xref:System.Windows.Forms.DataFormats> eigenes Objekt definieren, <xref:System.Object> indem Sie <xref:System.Windows.Forms.DataObject.SetData%2A> ein eigenes Objekt als Parameter der Methode angeben. Stellen Sie dabei sicher, dass das angegebene Objekt serialisierbar ist. Weitere Informationen finden Sie unter <xref:System.Runtime.Serialization.ISerializable>.  
  
3. Verwenden <xref:System.Windows.Forms.Control.DragDrop> Sie im Fall des Steuerelements, <xref:System.Windows.Forms.DataObject.GetData%2A> in dem der Drop auftritt, die Methode, um die gezogenen Daten abzurufen. Weitere Informationen finden Sie unter <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.  
  
     Im folgenden Beispiel <xref:System.Windows.Forms.TextBox> ist ein Steuerelement das Steuerelement, an das gezogen wird (wo der Drop auftritt). Der Code <xref:System.Windows.Forms.Control.Text%2A> legt die <xref:System.Windows.Forms.TextBox> Eigenschaft des Steuerelements gleich den gezogenen Daten fest.  
  
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
    > Darüber hinaus können Sie <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> mit der Eigenschaft arbeiten, sodass je nach gedrückten Tasten während des Drag-and-Drop-Vorgangs bestimmte Effekte auftreten (z. B. ist es Standard, die gezogenen Daten zu kopieren, wenn die STRG-Taste gedrückt wird).  
  
## <a name="see-also"></a>Weitere Informationen

- [Gewusst wie: Hinzufügen von Daten zur Zwischenablage](how-to-add-data-to-the-clipboard.md)
- [Gewusst wie: Abrufen von Daten aus der Zwischenablage](how-to-retrieve-data-from-the-clipboard.md)
- [Drag & Drop-Vorgänge und Unterstützung der Zwischenablage](drag-and-drop-operations-and-clipboard-support.md)
