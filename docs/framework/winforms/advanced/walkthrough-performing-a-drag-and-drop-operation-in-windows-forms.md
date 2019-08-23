---
title: 'Exemplarische Vorgehensweise: Ausführen von Drag & Drop-Operationen in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: cda3e87a4b0eb680d374eb0419a6b6b3157dc4a7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957124"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>Exemplarische Vorgehensweise: Ausführen von Drag & Drop-Operationen in Windows Forms
Um Drag & Drop-Vorgänge in Windows-basierten Anwendungen auszuführen, müssen Sie eine Reihe von Ereignissen verarbeiten, insbesondere die <xref:System.Windows.Forms.Control.DragEnter>Ereignisse, <xref:System.Windows.Forms.Control.DragLeave>und. <xref:System.Windows.Forms.Control.DragDrop> Wenn Sie die Daten aus den Ereignisargumenten dieser Ereignisse verwenden, können Sie Drag & Drop-Vorgänge problemlos vereinfachen.  
  
## <a name="dragging-data"></a>Ziehen von Daten  
 Drag & Drop-Vorgänge beginnen immer mit dem Ziehen (Dragging). Die Funktion, mit der Daten beim Ziehen von Daten gesammelt werden können, wird <xref:System.Windows.Forms.Control.DoDragDrop%2A> in der-Methode implementiert.  
  
 Im folgenden Beispiel wird das <xref:System.Windows.Forms.Control.MouseDown> -Ereignis verwendet, um den Zieh Vorgang zu starten, da es sich hierbei um die intuitivste Aktion handelt (die meisten Drag & Drop-Aktionen beginnen mit der Maustaste, wenn die Maustaste gedrückt ist). Beachten Sie dabei jedoch, dass für das Starten des Drag & Drop-Vorgangs jedes beliebige Ereignis verwendet werden kann.  
  
> [!NOTE]
> Bestimmte Steuerelemente verfügen über benutzerdefinierte für Ziehvorgänge spezifische Ereignisse. Die <xref:System.Windows.Forms.ListView> - <xref:System.Windows.Forms.TreeView> und-Steuerelemente haben z. <xref:System.Windows.Forms.TreeView.ItemDrag> b. ein-Ereignis.  
  
#### <a name="to-start-a-drag-operation"></a>So starten Sie einen Zielvorgang  
  
1. Verwenden Sie im- `DoDragDrop` EreignisfürdasSteuerelement,beidemderZiehVorgangbeginnt,die-Methode,umdieDatenfestzulegen,diegezogenwerdensollen,unddiezulässigeAuswirkungderZiehKraft.<xref:System.Windows.Forms.Control.MouseDown> Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Data%2A> und <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
     Im folgenden Beispiel wird gezeigt, wie ein Ziehvorgang gestartet wird. Das Steuerelement, bei dem der Zieh <xref:System.Windows.Forms.Button> Vorgang beginnt, ist ein-Steuerelement, die gezogenen <xref:System.Windows.Forms.Control.Text%2A> Daten sind die <xref:System.Windows.Forms.Button> Zeichenfolge, die die-Eigenschaft des Steuer Elements darstellt, und die zulässigen Effekte sind entweder kopieren oder verschieben.  
  
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
    > Alle Daten können als Parameter in der `DoDragDrop` -Methode verwendet werden. im obigen Beispiel wurde die <xref:System.Windows.Forms.Control.Text%2A> -Eigenschaft des <xref:System.Windows.Forms.Button> -Steuer Elements verwendet (anstatt einen Wert hart zu codieren oder Daten aus einem Dataset abzurufen), da die-Eigenschaft mit dem der Speicherort, aus dem <xref:System.Windows.Forms.Button> gezogen wird (das Steuerelement). Dies sollte bei der Integration von Drag & Drop-Vorgängen in Windows-basierte Anwendungen stets beachtet werden.  
  
 Während ein Zieh Vorgang wirksam ist, können Sie das <xref:System.Windows.Forms.Control.QueryContinueDrag> -Ereignis behandeln, das "die Berechtigung" für das System zum Fortsetzen des Zieh Vorgangs anfordert. Wenn Sie diese Methode verarbeiten, können Sie auch Methoden aufzurufen, die Auswirkungen auf den Zieh Vorgang haben, z. b. das Erweitern eines <xref:System.Windows.Forms.TreeNode> in einem <xref:System.Windows.Forms.TreeView> -Steuerelement, wenn der Cursor darauf bewegt wird.  
  
## <a name="dropping-data"></a>Ablegen von Daten  
 Nachdem Sie begonnen haben, Daten von einer Stelle einer Windows Form oder eines Steuerelements zu ziehen, möchten Sie diese natürlich auch irgendwo ablegen (Dropping). Der Cursor verändert sich, wenn er über einen Bereich auf einem Formular oder Steuerelement bewegt wird, der für das Ablegen von Daten konfiguriert ist. Alle Bereiche innerhalb eines Windows Forms oder Steuer Elements können so eingerichtet werden, dass Sie verworfene Daten akzeptieren, indem <xref:System.Windows.Forms.Control.DragDrop> Sie die <xref:System.Windows.Forms.Control.AllowDrop%2A> -Eigenschaft festlegen und die <xref:System.Windows.Forms.Control.DragEnter> Ereignisse und behandeln.  
  
#### <a name="to-perform-a-drop"></a>So führen Sie einen Ablegevorgang aus  
  
1. Legen Sie <xref:System.Windows.Forms.Control.AllowDrop%2A> die-Eigenschaft auf true fest.  
  
2. Stellen Sie im- <xref:System.Windows.Forms.Control.Text%2A> EreignisfürdasSteuerelement,indemderAblageVorgangauftritt,sicher,dassdiegezogenenDateneinenzulässigenTyphaben(indiesemFall).`DragEnter` Der Code legt dann den Effekt fest, der auftritt, wenn der Ablage Vorgang auf einen Wert <xref:System.Windows.Forms.DragDropEffects> in der-Enumeration angewendet wird. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
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
    > Sie können Ihre eigenen <xref:System.Windows.Forms.DataFormats> definieren, indem Sie ein eigenes-Objekt <xref:System.Object> als Parameter der <xref:System.Windows.Forms.DataObject.SetData%2A> -Methode angeben. Stellen Sie dabei sicher, dass das angegebene Objekt serialisierbar ist. Weitere Informationen finden Sie unter <xref:System.Runtime.Serialization.ISerializable>.  
  
3. Verwenden Sie im- <xref:System.Windows.Forms.DataObject.GetData%2A> Ereignisfürdas-Steuerelement,indemderLöschvorgangausgeführtwird,die-Methode,umdiegezogenenDatenabzurufen.<xref:System.Windows.Forms.Control.DragDrop> Weitere Informationen finden Sie unter <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.  
  
     Im folgenden Beispiel ist ein <xref:System.Windows.Forms.TextBox> -Steuerelement das Steuerelement, zu dem gezogen wird (wo der Ablage auftritt). Der Code legt die <xref:System.Windows.Forms.Control.Text%2A> -Eigenschaft <xref:System.Windows.Forms.TextBox> des-Steuer Elements auf die gezogenen Daten fest.  
  
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
    > Außerdem können Sie mit der <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> -Eigenschaft arbeiten, sodass abhängig von den Schlüsseln, die während des Drag & Drop-Vorgangs gedrückt werden, bestimmte Effekte auftreten (z. b. ist es Standard, die gezogenen Daten zu kopieren, wenn die STRG-Taste gedrückt wird).  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Hinzufügen von Daten zur Zwischenablage](how-to-add-data-to-the-clipboard.md)
- [Vorgehensweise: Abrufen von Daten aus der Zwischenablage](how-to-retrieve-data-from-the-clipboard.md)
- [Drag & Drop-Vorgänge und Unterstützung der Zwischenablage](drag-and-drop-operations-and-clipboard-support.md)
