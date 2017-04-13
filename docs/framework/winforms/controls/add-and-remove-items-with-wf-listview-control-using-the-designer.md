---
title: "Gewusst wie: Hinzuf&#252;gen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows&#160;Forms mithilfe des Designers | Microsoft Docs"
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
  - "ListView-Steuerelement [Windows Forms], Hinzufügen von Listenelementen"
  - "ListView-Steuerelement [Windows Forms], Auffüllen"
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Hinzuf&#252;gen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows&#160;Forms mithilfe des Designers
Das Hinzufügen eines Elements zu einem <xref:System.Windows.Forms.ListView>\-Steuerelement in Windows Forms besteht hauptsächlich darin, das Element anzugeben und ihm Eigenschaften zuzuweisen.  Das Hinzufügen oder Entfernen von Listenelementen kann zu einem beliebigen Zeitpunkt erfolgen.  
  
 Für das folgende Verfahren wird ein Projekt vom Typ **Windows\-Anwendung** mit einem Formular benötigt, das ein <xref:System.Windows.Forms.ListView>\-Steuerelement enthält.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So fügen Sie Elemente mit dem Designer hinzu oder entfernen sie  
  
1.  Wählen Sie das <xref:System.Windows.Forms.ListView>\-Steuerelement aus.  
  
2.  Klicken Sie im **Eigenschaftenfenster** auf die Schaltfläche mit dem **Auslassungszeichen** \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), die sich neben der <xref:System.Windows.Forms.ListView.Items%2A>\-Eigenschaft befindet.  
  
     Der **ListViewItem**\-Auflistungs\-Editor wird angezeigt.  
  
3.  Klicken Sie auf die Schaltfläche **Hinzufügen**, um ein Element hinzuzufügen.  Im Anschluss können Sie die Eigenschaften des neuen Elements festlegen, z. B. <xref:System.Windows.Forms.ListView.Text%2A> und <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.  
  
4.  Um ein Element zu entfernen, wählen Sie es aus und klicken auf die Schaltfläche **Entfernen**.  
  
## Siehe auch  
 [Übersicht über das ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Gewusst wie: Hinzufügen von Spalten zum ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)   
 [Gewusst wie: Anzeigen von Unterelementen in Spalten mit dem ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)   
 [Gewusst wie: Anzeigen von Symbolen für das ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)   
 [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView\- oder ListView\-Steuerelement \(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)   
 [Gewusst wie: Gruppieren von Elementen in einem ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)