---
title: "Gewusst wie: Durchlaufen aller Knoten eines TreeView-Steuerelements in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Beispiele [Windows Forms], TreeView-Steuerelement"
  - "Strukturknoten im TreeView-Steuerelement, Durchlaufen"
  - "TreeView-Steuerelement [Windows Forms], Durchlaufen von Knoten"
ms.assetid: 427f8928-ebcf-4beb-887f-695b905d5134
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Durchlaufen aller Knoten eines TreeView-Steuerelements in Windows&#160;Forms
Manchmal ist es sinnvoll, alle Knoten in einem <xref:System.Windows.Forms.TreeView>\-Steuerelement von Windows Forms zu prüfen, um Berechnungen an den Knotenwerten durchzuführen.  Diese Operation kann mit einer rekursiven Prozedur \(rekursive Methode in C\# und C\+\+\) durchgeführt werden, die alle Knoten in allen Auflistungen der Struktur durchläuft.  
  
 Jedes <xref:System.Windows.Forms.TreeNode>\-Objekt in einer Strukturansicht verfügt über Eigenschaften, mit deren Hilfe Sie in der Strukturansicht navigieren können: <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A> und <xref:System.Windows.Forms.TreeNode.Parent%2A>.  Der Wert der <xref:System.Windows.Forms.TreeNode.Parent%2A>\-Eigenschaft entspricht dem Knoten, der dem aktuellen Knoten übergeordnet ist.  Die Knoten, die dem aktuellen Knoten untergeordnet sind \(falls vorhanden\), sind in dessen <xref:System.Windows.Forms.TreeNode.Nodes%2A>\-Eigenschaft aufgeführt.  Das <xref:System.Windows.Forms.TreeView>\-Steuerelement selbst verfügt über die <xref:System.Windows.Forms.TreeView.TopNode%2A>\-Eigenschaft, bei der es sich um den Stammknoten der gesamten Strukturansicht handelt.  
  
### So gehen Sie alle Knoten des TreeView\-Steuerelements durch  
  
1.  Erstellen Sie eine rekursive Prozedur \(rekursive Methode in C\# und C\+\+\), die jeden einzelnen Knoten testet.  
  
2.  Rufen Sie die Prozedur auf.  
  
     Das folgende Beispiel zeigt, wie die <xref:System.Windows.Forms.TreeNode.Text%2A>\-Eigenschaft der verschiedenen <xref:System.Windows.Forms.TreeNode>\-Objekte ausgegeben werden kann:  
  
    ```vb  
    Private Sub PrintRecursive(ByVal n As TreeNode)  
       System.Diagnostics.Debug.WriteLine(n.Text)  
       MessageBox.Show(n.Text)  
       Dim aNode As TreeNode  
       For Each aNode In n.Nodes  
          PrintRecursive(aNode)  
       Next  
    End Sub  
  
    ' Call the procedure using the top nodes of the treeview.  
    Private Sub CallRecursive(ByVal aTreeView As TreeView)  
       Dim n As TreeNode  
       For Each n In aTreeView.Nodes  
          PrintRecursive(n)  
       Next  
    End Sub  
  
    ```  
  
    ```csharp  
    private void PrintRecursive(TreeNode treeNode)  
    {  
       // Print the node.  
       System.Diagnostics.Debug.WriteLine(treeNode.Text);  
       MessageBox.Show(treeNode.Text);  
       // Print each node recursively.  
       foreach (TreeNode tn in treeNode.Nodes)  
       {  
          PrintRecursive(tn);  
       }  
    }  
  
    // Call the procedure using the TreeView.  
    private void CallRecursive(TreeView treeView)  
    {  
       // Print each node recursively.  
       TreeNodeCollection nodes = treeView.Nodes;  
       foreach (TreeNode n in nodes)  
       {  
          PrintRecursive(n);  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void PrintRecursive( TreeNode^ treeNode )  
       {  
          // Print the node.  
          System::Diagnostics::Debug::WriteLine( treeNode->Text );  
          MessageBox::Show( treeNode->Text );  
  
          // Print each node recursively.  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(treeNode->Nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ tn = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( tn );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
  
       // Call the procedure using the TreeView.  
       void CallRecursive( TreeView^ treeView )  
       {  
          // Print each node recursively.  
          TreeNodeCollection^ nodes = treeView->Nodes;  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ n = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( n );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
    ```  
  
## Siehe auch  
 [TreeView\-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [Recursive Procedures](../Topic/Recursive%20Procedures%20\(Visual%20Basic\).md)