---
title: "Gewusst wie: Hinzuf&#252;gen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "Listenansichten, Hinzufügen von Listenelementen"
  - "ListView-Steuerelement [Windows Forms], Hinzufügen von Listenelementen"
  - "ListView-Steuerelement [Windows Forms], Auffüllen"
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Hinzuf&#252;gen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows&#160;Forms
Das Hinzufügen eines Elements zu einem <xref:System.Windows.Forms.ListView>\-Steuerelement in Windows Forms besteht hauptsächlich darin, das Element anzugeben und ihm Eigenschaften zuzuweisen.  Das Hinzufügen oder Entfernen von Listenelementen kann zu einem beliebigen Zeitpunkt erfolgen.  
  
### So fügen Sie Elemente programmgesteuert hinzu  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A>\-Methode der <xref:System.Windows.Forms.ListView.Items%2A>\-Eigenschaft.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### So entfernen Sie Elemente programmgesteuert  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A>\-Methode oder die <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A>\-Methode der <xref:System.Windows.Forms.ListView.Items%2A>\-Eigenschaft.  Mit der <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A>\-Methode wird ein einzelnes Element entfernt, und mit der <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A>\-Methode werden alle Elemente aus der Liste gelöscht.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## Siehe auch  
 <xref:System.Windows.Forms.ListView>   
 [ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Übersicht über das ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)