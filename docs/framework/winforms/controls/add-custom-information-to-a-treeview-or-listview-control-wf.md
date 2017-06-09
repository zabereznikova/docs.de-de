---
title: "Gewusst wie: Hinzuf&#252;gen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ListItem"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Beispiele [Windows Forms], ListView-Steuerelement"
  - "Beispiele [Windows Forms], TreeView-Steuerelement"
  - "ListView-Steuerelement [Windows Forms], Hinzufügen von benutzerdefinierten Informationen"
  - "Tag-Eigenschaft"
  - "TreeView-Steuerelement [Windows Forms], Hinzufügen von benutzerdefinierten Informationen"
ms.assetid: 68be11de-1d5b-430e-901f-cfbe48d14b19
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Hinzuf&#252;gen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows&#160;Forms)
Sie können einen abgeleiteten Knoten in einem <xref:System.Windows.Forms.TreeView>\-Steuerelement von Windows Forms oder ein abgeleitetes Element in einem <xref:System.Windows.Forms.ListView>\-Steuerelement erstellen.  Bei einer Ableitung können Sie alle erforderlichen Felder sowie benutzerdefinierten Methoden und Konstruktoren für deren Behandlung hinzufügen.  Sie könnten z. B. ein **Customer**\-Objekt an alle Strukturknoten oder Listenelemente anhängen.  Die genannten Beispiele beziehen sich zwar auf ein <xref:System.Windows.Forms.TreeView>\-Steuerelement, derselbe Ansatz kann aber auch für ein <xref:System.Windows.Forms.ListView>\-Steuerelement verwendet werden.  
  
### So leiten Sie einen Strukturknoten ab  
  
-   Erstellen Sie eine neue Knotenklasse, die von der <xref:System.Windows.Forms.TreeNode>\-Klasse abgeleitet ist und über ein benutzerdefiniertes Feld für einen Dateipfad verfügt.  
  
    ```vb  
    Class myTreeNode  
       Inherits TreeNode  
  
       Public FilePath As String  
  
       Sub New(ByVal fp As String)  
          MyBase.New()  
          FilePath = fp  
          Me.Text = fp.Substring(fp.LastIndexOf("\"))  
       End Sub  
    End Class  
  
    ```  
  
    ```csharp  
    class myTreeNode : TreeNode  
    {  
       public string FilePath;  
  
       public myTreeNode(string fp)  
       {  
          FilePath = fp;  
          this.Text = fp.Substring(fp.LastIndexOf("\\"));  
       }  
    }  
  
    ```  
  
    ```cpp  
    ref class myTreeNode : public TreeNode  
    {  
    public:  
       System::String ^ FilePath;  
  
       myTreeNode(System::String ^ fp)  
       {  
          FilePath = fp;  
          this->Text = fp->Substring(fp->LastIndexOf("\\"));  
       }  
    };  
    ```  
  
### So verwenden Sie einen abgeleiteten Strukturknoten  
  
1.  Sie können den neuen abgeleiteten Strukturknoten als Parameter für Funktionsaufrufe verwenden.  
  
     Im unten stehenden Beispiel wurde als Speicherort für die Textdatei der Ordner **Eigene Dateien** festgelegt.  Dieser Speicherort wird verwendet, weil vorausgesetzt werden kann, dass die meisten Computer mit dem Betriebssystem Windows über dieses Verzeichnis verfügen.  Auf diese Weise können auch Benutzer mit minimalen Systemzugriffsberechtigungen die Anwendung sicher ausführen.  
  
    ```vb  
    ' You should replace the bold text file   
    ' in the sample below with a text file of your own choosing.  
    TreeView1.Nodes.Add(New myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\ TextFile.txt ") )  
  
    ```  
  
    ```csharp  
    // You should replace the bold text file   
    // in the sample below with a text file of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    treeView1.Nodes.Add(new myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\TextFile.txt") );  
  
    ```  
  
    ```cpp  
    // You should replace the bold text file   
    // in the sample below with a text file of your own choosing.  
    treeView1->Nodes->Add(new myTreeNode(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\TextFile.txt")));  
    ```  
  
2.  Wenn der Strukturknoten an Sie übergeben wurde und als <xref:System.Windows.Forms.TreeNode>\-Klasse festgelegt ist, müssen Sie eine Umwandlung in Ihre abgeleitete Klasse vornehmen.  Die Umwandlung ist eine explizite Konvertierung eines Objekttyps in einen anderen Objekttyp.  Weitere Informationen zum Umwandeln finden Sie unter [Implicit and Explicit Conversions](../Topic/Implicit%20and%20Explicit%20Conversions%20\(Visual%20Basic\).md) \([!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\), [Operator \(\)](../Topic/\(\)%20Operator%20\(C%23%20Reference\).md) \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\) oder [Umwandlungsoperator: \(\)](../../../../amples/snippets/visualbasic/VS_Snippets_Wpf/DocumentStructure/visualbasic/spec_withstructure-xps/_rels/.rels) \([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\).  
  
    ```vb  
    Public Sub TreeView1_AfterSelect(ByVal sender As Object, ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       Dim mynode As myTreeNode  
       mynode = CType(e.node, myTreeNode)  
       MessageBox.Show("Node selected is " & mynode.filepath)  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,  
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       myTreeNode myNode = (myTreeNode)e.Node;  
       MessageBox.Show("Node selected is " + myNode.FilePath);  
    }  
  
    ```  
  
    ```cpp  
    private:  
       System::Void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          myTreeNode ^ myNode = safe_cast<myTreeNode^>(e->Node);  
          MessageBox::Show(String::Concat("Node selected is ",   
             myNode->FilePath));  
       }  
    ```  
  
## Siehe auch  
 [TreeView\-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)