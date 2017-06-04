---
title: "Gewusst wie: Binden einer TreeView an Daten mit nicht bestimmbarer Tiefe | Microsoft Docs"
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
  - "TreeView-Steuerelement [WPF], Binden an Daten mit nicht bestimmbarer Tiefe"
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Binden einer TreeView an Daten mit nicht bestimmbarer Tiefe
In einigen Fällen müssen Sie möglicherweise eine <xref:System.Windows.Controls.TreeView> an eine Datenquelle mit unbekannter Tiefe binden.  Dies ist z. B. der Fall, wenn Daten rekursiv sind, wie bei Dateisystemen mit Ordnern und Unterordnern oder bei der Organisationsstruktur eines Unternehmens mit Mitarbeitern und direkten Vorgesetzten.  
  
 Die Datenquelle muss ein hierarchisches Objektmodell aufweisen.  Beispiel: Eine `Employee`\-Klasse enthält eine Auflistung von Employee\-Objekten, bei denen es sich um die direkten Vorgesetzten eines Mitarbeiters handelt.  Wenn die Daten nicht hierarchisch dargestellt werden, müssen Sie eine hierarchische Darstellung der Daten erstellen.  
  
 Wenn Sie die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=fullName>\-Eigenschaft festlegen und das <xref:System.Windows.Controls.ItemsControl> ein <xref:System.Windows.Controls.ItemsControl> für jedes untergeordnete Element generiert, wird für das untergeordnete <xref:System.Windows.Controls.ItemsControl> dieselbe <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> verwendet wie für das übergeordnete Element.  Wenn Sie z. B. die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>\-Eigenschaft für eine datengebundene <xref:System.Windows.Controls.TreeView> festlegen, verwendet jedes generierte <xref:System.Windows.Controls.TreeViewItem> die <xref:System.Windows.DataTemplate>, die der <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>\-Eigenschaft der <xref:System.Windows.Controls.TreeView> zugewiesen wurde.  
  
 Die <xref:System.Windows.HierarchicalDataTemplate> ermöglicht Ihnen, die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für ein <xref:System.Windows.Controls.TreeViewItem> oder ein beliebiges <xref:System.Windows.Controls.HeaderedItemsControl> in der Datenvorlage anzugeben.  Wenn Sie die <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=fullName>\-Eigenschaft festlegen, wird dieser Wert bei Anwendung der <xref:System.Windows.HierarchicalDataTemplate> verwendet.  Indem Sie eine <xref:System.Windows.HierarchicalDataTemplate> verwenden, können Sie die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für jedes <xref:System.Windows.Controls.TreeViewItem> in der <xref:System.Windows.Controls.TreeView> rekursiv festlegen.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Sie eine <xref:System.Windows.Controls.TreeView> an hierarchische Daten binden und mit einer <xref:System.Windows.HierarchicalDataTemplate> die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für jedes <xref:System.Windows.Controls.TreeViewItem> angeben.  Die <xref:System.Windows.Controls.TreeView> wird an XML\-Daten gebunden, die die Mitarbeiter in einem Unternehmen darstellen.  Jedes `Employee`\-Element kann weitere `Employee`\-Elemente enthalten, um die hierarchischen Strukturen im Unternehmen wiederzugeben.  Da die Daten rekursiv sind, kann die <xref:System.Windows.HierarchicalDataTemplate> auf jede Ebene angewendet werden.  
  
 [!code-xml[TreeViewWithUnknownDepth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## Siehe auch  
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)