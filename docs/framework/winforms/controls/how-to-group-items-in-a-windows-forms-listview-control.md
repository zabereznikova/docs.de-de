---
title: "Gewusst wie: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Gruppieren"
  - "Gruppen"
  - "Gruppen, In Windows Forms-Steuerelementen"
  - "Listenansichten, Gruppieren von Elementen"
  - "Listen, Gruppieren von Elementen"
  - "ListView-Steuerelement [Windows Forms], Gruppieren von Elementen"
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms
Das Gruppierungsfeature des <xref:System.Windows.Forms.ListView>\-Steuerelements ermöglicht es Ihnen, verwandte Elemente in Gruppen anzuzeigen.  Diese Gruppen werden auf dem Bildschirm durch horizontale Gruppenheader getrennt, die die Gruppentitel enthalten.  Sie können <xref:System.Windows.Forms.ListView>\-Gruppen verwenden, um das Navigieren in umfangreichen Listen zu vereinfachen, indem Sie Elemente alphabetisch, nach Datum oder nach einem anderen logischen Gruppierungsmerkmal gruppieren.  In der folgenden Abbildung werden einige gruppierte Elemente angezeigt.  
  
 ![ListView&#45;Gruppen](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
ListView gruppierter Elemente  
  
 Zur Aktivierung der Gruppierung müssen Sie zunächst im Designer oder programmgesteuert eine oder mehrere Gruppen erstellen.  Nachdem eine Gruppe definiert wurde, können Sie Gruppen <xref:System.Windows.Forms.ListView>\-Elemente zuweisen.  Sie können auch programmgesteuert Elemente von einer Gruppe in eine andere verschieben.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView>\-Gruppen sind in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] nur verfügbar, wenn die Anwendung die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>\-Methode aufruft.  Auf älteren Betriebssystemen ist Code in Zusammenhang mit Gruppen unwirksam; folglich werden keine Gruppen angezeigt.  Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=fullName>.  
  
### So fügen Sie Gruppen hinzu  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A>\-Methode der <xref:System.Windows.Forms.ListView.Groups%2A>\-Auflistung.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### So entfernen Sie Gruppen  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A>\-Methode oder die <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A>\-Methode der <xref:System.Windows.Forms.ListView.Groups%2A>\-Auflistung.  
  
     Mit der <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A>\-Methode wird eine einzelne Gruppe entfernt. Die <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A>\-Methode entfernt alle Gruppen aus der Liste.  
  
    > [!NOTE]
    >  Durch das Entfernen einer Gruppe werden die in dieser Gruppe enthaltenen Elemente nicht entfernt.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### So ordnen Sie Gruppen Elemente zu oder verschieben Elemente zwischen Gruppen  
  
1.  Legen Sie die <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=fullName>\-Eigenschaft einzelner Elemente fest.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## Siehe auch  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ListViewGroup>   
 [ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Übersicht über das ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Windows XP Features and Windows Forms Controls](http://msdn.microsoft.com/de-de/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)   
 [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)