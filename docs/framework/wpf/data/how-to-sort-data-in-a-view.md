---
title: "Gewusst wie: Sortieren von Daten in einer Ansicht | Microsoft Docs"
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
  - "Datenbindung, Gruppieren von Daten in Ansichten"
  - "Datenbindung, Sortieren von Daten in Ansichten"
  - "Gruppieren von Daten in Ansichten"
  - "Sortieren von Daten in Ansichten"
  - "Ansichten, Gruppieren von Daten"
  - "Ansichten, Sortieren von Daten"
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Sortieren von Daten in einer Ansicht
In diesem Beispiel wird beschrieben, wie Daten in einer Ansicht sortiert werden.  
  
## Beispiel  
 Im folgenden Beispiel werden ein einfaches <xref:System.Windows.Controls.ListBox>\-Element und ein <xref:System.Windows.Controls.Button>\-Element erstellt:  
  
 [!code-xml[ListBoxSort_snip#HowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 Der <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignishandler der Schaltfläche enthält die Logik für das Sortieren der Elemente im <xref:System.Windows.Controls.ListBox>\-Steuerelement in absteigender Reihenfolge.  Dies ist möglich, da beim Hinzufügen von Elementen zu einem <xref:System.Windows.Controls.ListBox>\-Steuerelement auf diese Weise die Elemente auch zur <xref:System.Windows.Controls.ItemCollection> des <xref:System.Windows.Controls.ListBox>\-Elements hinzugefügt werden und da <xref:System.Windows.Controls.ItemCollection> von der <xref:System.Windows.Data.CollectionView>\-Klasse abgeleitet wird.  Wenn Sie das <xref:System.Windows.Controls.ListBox>\-Element mithilfe der <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>\-Eigenschaft an eine Auflistung binden, können Sie das gleiche Verfahren zum Sortieren verwenden.  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 Solange ein Verweis auf das Ansichtsobjekt besteht, können Sie das gleiche Verfahren zum Sortieren des Inhalts anderer Auflistungsansichten verwenden.  Ein Beispiel zum Abrufen von Ansichten finden Sie unter [Abrufen der Standardansicht einer Datenauflistung](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).  Ein weiteres Beispiel finden Sie unter [Sortieren einer GridView\-Spalte beim Klicken auf einen Header](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).  Weitere Informationen über Ansichten finden Sie im Abschnitt Binden an Auflistungen in [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Ein Beispiel dafür, wie Sortierfunktionen in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] angewendet werden, finden Sie in [Sortieren und Gruppieren von Daten mit einer Ansicht in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).  
  
## Siehe auch  
 <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>   
 [Sortieren einer GridView\-Spalte beim Klicken auf einen Header](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Filtern von Daten in einer Ansicht](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)