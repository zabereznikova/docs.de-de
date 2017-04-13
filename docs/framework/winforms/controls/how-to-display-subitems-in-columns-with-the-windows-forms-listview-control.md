---
title: "Gewusst wie: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "Detailansicht"
  - "Listenelemente"
  - "ListView-Steuerelement [Windows Forms], Hinzufügen von ListSubItems"
  - "Unterelemente"
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows&#160;Forms
Mit dem <xref:System.Windows.Forms.ListView>\-Steuerelement in Windows Forms können zusätzlicher Text oder Unterelemente für jedes Element in der Details\-Ansicht angezeigt werden.  In der ersten Spalte erfolgt die Anzeige des Elementtextes, z.B. einer Mitarbeiternummer.  In der zweiten, dritten und den folgenden Spalten werden das erste, zweite und die folgenden verbundenen Unterelemente angezeigt.  
  
### So fügen Sie einem Listenelement Unterelemente hinzu  
  
1.  Fügen Sie beliebige erforderliche Spalten hinzu.  Da in der ersten Spalte die <xref:System.Windows.Forms.ListView.Text%2A>\-Eigenschaft des Elements angezeigt wird, benötigen Sie eine Spalte mehr als Unterelemente vorhanden sind.  Weitere Informationen zum Hinzufügen von Spalten finden Sie unter [Gewusst wie: Hinzufügen von Spalten zum ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).  
  
2.  Rufen Sie die <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A>\-Methode der Auflistung auf, die von der <xref:System.Windows.Forms.ListViewItem.SubItems%2A>\-Eigenschaft eines Elements zurückgegeben wird.  Im folgenden Codebeispiel werden Mitarbeitername und Abteilung für ein Listenelement festgelegt.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## Siehe auch  
 [Übersicht über das ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [Gewusst wie: Hinzufügen von Spalten zum ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)   
 [Gewusst wie: Anzeigen von Symbolen für das ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)   
 [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView\- oder ListView\-Steuerelement \(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)