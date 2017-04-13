---
title: "Exemplarische Vorgehensweise: Ausf&#252;hren von Drag&#160;&amp;&#160;Drop-Operationen in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Drag & Drop, Windows Forms"
  - "Windows Forms, Drag & Drop-Operationen"
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Exemplarische Vorgehensweise: Ausf&#252;hren von Drag&#160;&amp;&#160;Drop-Operationen in Windows&#160;Forms
Um eine Drag & Drop\-Operation in Windows\-basierten Anwendungen auszuführen, müssen Sie eine Reihe von Ereignissen behandeln, insbesondere die Ereignisse <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave> und <xref:System.Windows.Forms.Control.DragDrop>.  Wenn Sie die Daten aus den Ereignisargumenten dieser Ereignisse verwenden, können Sie Drag & Drop\-Operationen problemlos vereinfachen.  
  
## Ziehen von Daten  
 Drag & Drop\-Operationen beginnen immer mit dem Ziehen \(Dragging\).  Die Funktionalität, mit der Daten bei Beginn des Ziehvorgangs erfasst werden können, ist in der <xref:System.Windows.Forms.Control.DoDragDrop%2A>\-Methode implementiert.  
  
 Im folgenden Beispiel wird das <xref:System.Windows.Forms.Control.MouseDown>\-Ereignis zum Starten des Ziehvorgangs verwendet, da es am intuitivsten ist. \(Die meisten Drag & Drop\-Operationen beginnen mit dem Drücken der Maustaste.\)  Beachten Sie dabei jedoch, dass für das Starten des Drag & Drop\-Vorgangs jedes beliebige Ereignis verwendet werden kann.  
  
> [!NOTE]
>  Bestimmte Steuerelemente verfügen über benutzerdefinierte, für den Ziehvorgang typische Ereignisse.  Das <xref:System.Windows.Forms.ListView>\-Steuerelement und das <xref:System.Windows.Forms.TreeView>\-Steuerelement verfügen beispielsweise über ein <xref:System.Windows.Forms.TreeView.ItemDrag>\-Ereignis.  
  
#### So starten Sie einen Ziehvorgang  
  
1.  Im <xref:System.Windows.Forms.Control.MouseDown>Ereignis für das Steuerelement, in dem das Ziehen beginnt, verwenden Sie die `DoDragDrop`\-Methode, um die Daten gezogen werden festgelegt, und das zulässige Wirkung ziehen.  Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Data%2A> und <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
     Im folgenden Beispiel wird demonstriert, wie ein Ziehvorgang gestartet wird.  Das Steuerelement, in dem der Ziehvorgang beginnt, ist ein <xref:System.Windows.Forms.Button>\-Steuerelement, die gezogenen Daten sind die Zeichenfolge, die die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements darstellen, und die zulässigen Auswirkungen sind entweder Kopieren oder Verschieben.  
  
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
    >  In der `DoDragDrop`\-Methode können beliebige Daten als Parameter verwendet werden. Im Beispiel oben wurde die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements verwendet \(anstatt einen Wert fest zu codieren oder Daten aus einem Dataset abzurufen\), da die Eigenschaft mit der Position verbunden war, von der gezogen wurde \(das <xref:System.Windows.Forms.Button>\-Steuerelement\).  Dass generell jedoch beliebige Daten verwendet werden können, sollte bei der Integration von Drag & Drop\-Operationen in Windows\-basierte Anwendungen stets beachtet werden.  
  
 Während ein Ziehvorgang durchgeführt wird, können Sie das <xref:System.Windows.Forms.Control.QueryContinueDrag>\-Ereignis behandeln, das beim System rückfragt, ob der Ziehvorgang fortgesetzt werden kann.  Die Behandlung dieser Methode bietet außerdem die Gelegenheit, Methoden aufzurufen, die sich auf den Ziehvorgang auswirken, z. B. das Erweitern eines <xref:System.Windows.Forms.TreeNode> in einem <xref:System.Windows.Forms.TreeView>\-Steuerelement, wenn mit dem Cursor darauf gezeigt wird.  
  
## Ablegen von Daten  
 Wenn Sie begonnen haben, Daten von einer Stelle einer Windows Form oder eines Steuerelements zu ziehen, möchten Sie diese natürlich auch an einer Stelle ablegen \(Dropping\).  Der Cursor verändert sich, wenn er über einen Bereich auf einem Formular oder Steuerelement bewegt wird, der für das Ablegen von Daten konfiguriert ist.  Um Bereiche in Windows Forms oder Steuerelementen so zu konfigurieren, dass abgelegte Daten angenommen werden, richten Sie die <xref:System.Windows.Forms.Control.AllowDrop%2A>\-Eigenschaft ein, und behandeln Sie das <xref:System.Windows.Forms.Control.DragEnter>\-Ereignis und das <xref:System.Windows.Forms.Control.DragDrop>\-Ereignis.  
  
#### So führen Sie das Ablegen aus  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.AllowDrop%2A>\-Eigenschaft auf true fest.  
  
2.  Stellen Sie im `DragEnter`\-Ereignis für das Steuerelement, in dem Sie die gezogenen Daten ablegen, sicher, dass diese einem zulässigen Typ entsprechen \(in diesem Fall <xref:System.Windows.Forms.Control.Text%2A>\).  Der Code legt nun die Wirkung fest, die eintritt, wenn der Ablegevorgang für einen Wert in der <xref:System.Windows.Forms.DragDropEffects>\-Enumeration auftritt.  Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
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
    >  Sie können Ihre eigenen <xref:System.Windows.Forms.DataFormats> definieren, indem Sie Objekte als <xref:System.Object>\-Parameter der <xref:System.Windows.Forms.DataObject.SetData%2A>\-Methode angeben.  Stellen Sie dabei sicher, dass das angegebene Objekt serilisierbar ist.  Weitere Informationen finden Sie unter [ISerializable\-Schnittstelle](frlrfSystemRuntimeSerializationISerializableClassTopic).  
  
3.  Verwenden Sie im <xref:System.Windows.Forms.Control.DragDrop>\-Ereignis für das Steuerelement, in dem der Ablegevorgang erfolgt, die <xref:System.Windows.Forms.DataObject.GetData%2A>\-Methode, um die gezogenen Daten abzurufen.  Weitere Informationen finden Sie unter [DtaObject.Data\-Eigenschaft](frlrfSystemSecurityCryptographyXmlDataObjectClassDataTopic).  
  
     Im folgenden Beispiel ist das Steuerelement, auf das die Daten gezogen werden \(und auf dem der Ablegevorgang erfolgt\), ein <xref:System.Windows.Forms.TextBox>\-Steuerelement.  Durch den Code wird die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft des <xref:System.Windows.Forms.TextBox>\-Steuerelements genauso festgelegt wie die gezogenen Daten.  
  
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
    >  Darüber hinaus können Sie die <xref:System.Windows.Forms.DragEventArgs.KeyState%2A>\-Eigenschaft verwenden, sodass in Abhängigkeit von den während der Drag & Drop\-Operation gedrückten Tasten bestimmte Wirkungen erzielt werden. \(So werden die gezogenen Daten beispielsweise beim Drücken der STRG\-TASTE standardmäßig in die Zwischenablage kopiert.\)  
  
## Siehe auch  
 [Gewusst wie: Hinzufügen von Daten zur Zwischenablage](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)   
 [Gewusst wie: Abrufen von Daten aus der Zwischenablage](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)   
 [Drag & Drop\-Operationen und Unterstützung der Zwischenablage](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)