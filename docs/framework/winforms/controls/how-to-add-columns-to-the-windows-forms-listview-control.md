---
title: "Gewusst wie: Hinzuf&#252;gen von Spalten zum ListView-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "Spalten [Windows Forms], Hinzufügen zu ListView-Steuerelementen"
  - "Listenansichten, Hinzufügen von Spalten"
  - "ListView-Steuerelement [Windows Forms], Hinzufügen von Spaltenkopfzeilen"
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Hinzuf&#252;gen von Spalten zum ListView-Steuerelement in Windows&#160;Forms
In der Detailsansicht kann das <xref:System.Windows.Forms.ListView>\-Steuerelement mehrere Spalten für jedes Listenelement anzeigen.  Unter Verwendung der Spalten können verschiedene Arten von Informationen über jedes Listenelement angezeigt werden.  So können in einer Dateiliste beispielsweise der Dateiname, der Dateityp, die Größe und das Datum der letzten Dateiänderung aufgenommen werden.  Weitere Informationen dazu, wie Sie Spalten nach dem Erstellen auffüllen, finden Sie unter [Gewusst wie: Anzeigen von Unterelementen in Spalten mit dem ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).  
  
### So fügen Sie Spalten programmgesteuert hinzu  
  
1.  Legen Sie die <xref:System.Windows.Forms.ListView.View%2A>\-Eigenschaft des Steuerelements auf <xref:System.Windows.Forms.View> fest.  
  
2.  Verwenden Sie die <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A>\-Methode der <xref:System.Windows.Forms.ListView.Columns%2A>\-Eigenschaft der Listenansicht.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## Siehe auch  
 <xref:System.Windows.Forms.ListView>   
 [ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Übersicht über das ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)