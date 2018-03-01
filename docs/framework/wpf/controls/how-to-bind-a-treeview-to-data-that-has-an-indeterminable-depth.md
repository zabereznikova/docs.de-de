---
title: 'Gewusst wie: Binden einer TreeView an Daten mit nicht bestimmbarer Tiefe'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: be21ecb75420b6499e5b95d5f4d93a5f079f9646
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>Gewusst wie: Binden einer TreeView an Daten mit nicht bestimmbarer Tiefe
Gibt es möglicherweise vorkommen, dass Sie binden möchten, eine <xref:System.Windows.Controls.TreeView> mit einer Datenquelle, dessen Tiefe ist nicht bekannt.  Dies kann auftreten, wenn die Daten rekursiv sind, z. B. einem Dateisystem, in dem Ordner Ordner enthalten können, oder die Organisationsstruktur für ein Unternehmen sind, Mitarbeiter, für andere Mitarbeiter als direkt unterstellte Mitarbeiter haben.  
  
 Die angegebene Datenquelle muss ein hierarchisches Objektmodell verfügen. Angenommen, ein `Employee` Klasse enthält eine Auflistung von Employee-Objekten, die direkt unterstellten Mitarbeiter eines Mitarbeiters sind. Wenn die Daten auf eine Weise, die nicht hierarchische ist dargestellt werden, müssen Sie eine hierarchische Darstellung der Daten erstellen.  
  
 Beim Festlegen der <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> Eigenschaft und, wenn die <xref:System.Windows.Controls.ItemsControl> generiert eine <xref:System.Windows.Controls.ItemsControl> für jedes untergeordnete Element, und klicken Sie dann auf das untergeordnete Element <xref:System.Windows.Controls.ItemsControl> verwendet die gleiche <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> als übergeordnetes Element. Z. B., wenn Sie festlegen, die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> auf einem datengebundenen Eigenschaft <xref:System.Windows.Controls.TreeView>, die jeweils <xref:System.Windows.Controls.TreeViewItem> also generierten verwendet die <xref:System.Windows.DataTemplate> , zugewiesen wurde der <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Eigenschaft der <xref:System.Windows.Controls.TreeView>.  
  
 Die <xref:System.Windows.HierarchicalDataTemplate> ermöglicht Ihnen die Angabe der <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für eine <xref:System.Windows.Controls.TreeViewItem>, oder eine beliebige <xref:System.Windows.Controls.HeaderedItemsControl>, auf die Datenvorlage. Beim Festlegen der <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType> Eigenschaft, das Wert wird verwendet, wenn die <xref:System.Windows.HierarchicalDataTemplate> angewendet wird. Mithilfe einer <xref:System.Windows.HierarchicalDataTemplate>, können Sie rekursiv Festlegen der <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für jede <xref:System.Windows.Controls.TreeViewItem> in der <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Binden einer <xref:System.Windows.Controls.TreeView> hierarchische Daten und Verwenden einer <xref:System.Windows.HierarchicalDataTemplate> an die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für jede <xref:System.Windows.Controls.TreeViewItem>.  Die <xref:System.Windows.Controls.TreeView> bindet an XML-Daten, die die Mitarbeiter in einem Unternehmen darstellt.  Jede `Employee` Element kann andere enthalten `Employee` Elemente, um anzugeben, die an den gemeldet wird. Da die Daten rekursiv, ist die <xref:System.Windows.HierarchicalDataTemplate> kann auf jeder Ebene angewendet werden.  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)
