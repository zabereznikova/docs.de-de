---
title: Durchlaufen aller Knoten des TreeView-Steuer Elements
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], iterating through nodes
- tree nodes in TreeView control [Windows Forms], iterating through
ms.assetid: 427f8928-ebcf-4beb-887f-695b905d5134
ms.openlocfilehash: 010932fa3fdfaa907325b9934682dcbf889265c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736365"
---
# <a name="how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control"></a>Gewusst wie: Durchlaufen aller Knoten eines TreeView-Steuerelements in Windows Forms
Es ist manchmal hilfreich, jeden Knoten in einem Windows Forms <xref:System.Windows.Forms.TreeView>-Steuerelement zu untersuchen, um eine Berechnung der Knotenwerte durchzuführen. Dieser Vorgang kann über eine rekursive Prozedur (rekursive Methode in C# und C++) ausgeführt werden, die jeden Knoten in jeder Auflistung der Struktur durchläuft.  
  
 Jedes <xref:System.Windows.Forms.TreeNode> Objekt in einer Strukturansicht verfügt über Eigenschaften, mit denen Sie in der Strukturansicht navigieren können: <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A>und <xref:System.Windows.Forms.TreeNode.Parent%2A>. Der Wert der <xref:System.Windows.Forms.TreeNode.Parent%2A>-Eigenschaft ist der übergeordnete Knoten des aktuellen Knotens. Die untergeordneten Knoten des aktuellen Knotens (sofern vorhanden) werden in der <xref:System.Windows.Forms.TreeNode.Nodes%2A>-Eigenschaft aufgelistet. Das <xref:System.Windows.Forms.TreeView> Steuerelement selbst verfügt über die <xref:System.Windows.Forms.TreeView.TopNode%2A>-Eigenschaft, die der Stamm Knoten der gesamten Strukturansicht ist.  
  
### <a name="to-iterate-through-all-nodes-of-the-treeview-control"></a>So durchlaufen Sie alle Knoten des TreeView-Steuerelements  
  
1. Erstellen Sie eine rekursive Prozedur (rekursive Methode in C# und C++), die jeden einzelnen Knoten testet.  
  
2. Rufen Sie die Prozedur auf.  
  
     Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Forms.TreeNode.Text%2A> Eigenschaft jedes <xref:System.Windows.Forms.TreeNode> Objekts gedruckt wird:  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [TreeView-Steuerelement](treeview-control-windows-forms.md)
- [Rekursive Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)
