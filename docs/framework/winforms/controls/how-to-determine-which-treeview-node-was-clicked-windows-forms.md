---
title: "Gewusst wie: Ermitteln des per Mausklick ausgew&#228;hlten TreeView-Knotens (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TreeNode"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Beispiele [Windows Forms], TreeView-Steuerelement"
  - "Strukturknoten im TreeView-Steuerelement, Ermitteln von per Mausklick ausgewählten Knoten"
  - "TreeView-Steuerelement [Windows Forms], Ermitteln von per Mausklick ausgewählten Knoten"
ms.assetid: 06a4a191-d918-42af-9f49-956c93eff261
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Ermitteln des per Mausklick ausgew&#228;hlten TreeView-Knotens (Windows&#160;Forms)
Wenn Sie mit dem <xref:System.Windows.Forms.TreeView>\-Steuerelement von Windows Forms arbeiten, ist es häufig erforderlich, den per Mausklick ausgewählten Knoten zu ermitteln und entsprechend darauf zu reagieren.  
  
### So bestimmen Sie, welcher TreeView\-Knoten per Mausklick ausgewählt wurde  
  
1.  Verwenden Sie das <xref:System.EventArgs>\-Objekt, um einen Verweis auf das per Mausklick ausgewählte Knotenobjekt zurückzugeben.  
  
2.  Ermitteln Sie, auf welchen Knoten geklickt wurde, indem Sie die <xref:System.Windows.Forms.TreeViewEventArgs>\-Klasse überprüfen, die mit dem Ereignis verknüpfte Daten enthält.  
  
    ```vb  
    Private Sub TreeView1_AfterSelect(ByVal sender As System.Object, _  
    ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       ' Determine by checking the Node property of the TreeViewEventArgs.  
       MessageBox.Show(e.Node.Text)  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,   
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       // Determine by checking the Text property.  
       MessageBox.Show(e.Node.Text);  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          // Determine by checking the Text property.  
          MessageBox::Show(e->Node->Text);  
       }  
    ```  
  
    > [!NOTE]
    >  Alternativ können Sie <xref:System.Windows.Forms.MouseEventArgs> des Ereignisses <xref:System.Windows.Forms.Control.MouseDown> oder <xref:System.Windows.Forms.Control.MouseUp> verwenden, um die Koordinatenwerte <xref:System.Drawing.Point.X%2A> und <xref:System.Drawing.Point.Y%2A> von <xref:System.Drawing.Point> abzurufen, an denen der Mausklick aufgetreten ist.  Ermitteln Sie anschließend mit der <xref:System.Windows.Forms.TreeView.GetNodeAt%2A>\-Methode des <xref:System.Windows.Forms.TreeView>\-Steuerelements, auf welchen Knoten geklickt wurde.  
  
## Siehe auch  
 [TreeView\-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)