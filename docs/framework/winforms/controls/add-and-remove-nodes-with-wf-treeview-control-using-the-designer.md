---
title: "Gewusst wie: Hinzuf&#252;gen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows&#160;Forms mithilfe des Designers | Microsoft Docs"
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
  - "Beispiele [Windows Forms], TreeView-Steuerelement"
  - "Strukturknoten im TreeView-Steuerelement"
  - "TreeView-Steuerelement [Windows Forms], Hinzufügen von Knoten"
  - "TreeView-Steuerelement [Windows Forms], Entfernen von Knoten"
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Hinzuf&#252;gen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows&#160;Forms mithilfe des Designers
Da Knoten vom <xref:System.Windows.Forms.TreeView>\-Steuerelement in Windows Forms hierarchisch angezeigt werden, muss beim Hinzufügen eines Knotens sorgfältig darauf geachtet werden, welcher Knoten der übergeordnete ist.  
  
 Für das folgende Verfahren wird ein Projekt vom Typ **Windows\-Anwendung** mit einem Formular benötigt, das ein <xref:System.Windows.Forms.TreeView>\-Steuerelement enthält.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So fügen Sie im Designer Knoten hinzu oder entfernen sie  
  
1.  Wählen Sie das <xref:System.Windows.Forms.TreeView>\-Steuerelement aus.  
  
2.  Klicken Sie im **Eigenschaftenfenster** auf die Schaltfläche mit den **Auslassungspunkten** \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), die sich neben der <xref:System.Windows.Forms.TreeView.Nodes%2A>\-Eigenschaft befindet.  
  
     Der **TreeNode\-Editor** wird angezeigt.  
  
3.  Zum Hinzufügen eines Knotens muss ein Stammknoten vorhanden sein. Wenn das nicht der Fall ist, müssen Sie zunächst ein Stammverzeichnis hinzufügen, indem Sie auf die Schaltfläche **Stamm hinzufügen** klicken.  Anschließend können Sie untergeordnete Knoten hinzufügen, indem Sie dem Stammverzeichnis oder einen anderen Knoten auswählen und auf die Schaltfläche **Untergeordnetes Element hinzufügen** klicken.  
  
4.  Zum Löschen von Knoten wählen Sie den entsprechenden Knoten aus und klicken anschließend auf die Schaltfläche **Löschen**.  
  
## Siehe auch  
 [TreeView\-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [Übersicht über das TreeView\-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)   
 [Gewusst wie: Festlegen von Symbolen für das TreeView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)   
 [Gewusst wie: Durchlaufen aller Knoten eines TreeView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)   
 [Gewusst wie: Ermitteln des per Mausklick ausgewählten TreeView\-Knotens](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)   
 [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView\- oder ListView\-Steuerelement \(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)