---
title: "Gewusst wie: Gruppieren von Elementen in einem ListView, in dem ein GridView implementiert ist | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GridView-Steuerelemente, Gruppieren von Elementen"
  - "Gruppieren von Elementen in ListViews, die GridViews implementieren"
  - "ListView-Steuerelemente, Gruppieren von Elementen mit GridViews"
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Gruppieren von Elementen in einem ListView, in dem ein GridView implementiert ist
In diesem Beispiel wird dargestellt, wie im <xref:System.Windows.Controls.GridView>\-Ansichtsmodus eines <xref:System.Windows.Controls.ListView>\-Steuerelements Elementgruppen angezeigt werden können.  
  
## Beispiel  
 Zum Anzeigen von Elementgruppen in einer <xref:System.Windows.Controls.ListView>, definieren Sie eine <xref:System.Windows.Data.CollectionViewSource>.  In folgendem Beispiel wird eine <xref:System.Windows.Data.CollectionViewSource> dargestellt, die Datenelemente entsprechend dem Wert des `Catalog` \-Datenfelds gruppiert.  
  
 [!code-xml[GridViewWithGroups#GroupingCollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für die <xref:System.Windows.Controls.ListView> auf die <xref:System.Windows.Data.CollectionViewSource> festgelegt, die im vorherigen Beispiel definiert wurde.  Im Beispiel wird außerdem ein <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> definiert, der ein <xref:System.Windows.Controls.Expander>\-Steuerelement implementiert.  
  
 [!code-xml[GridViewWithGroups#ListViewGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xml[GridViewWithGroups#ListViewEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)