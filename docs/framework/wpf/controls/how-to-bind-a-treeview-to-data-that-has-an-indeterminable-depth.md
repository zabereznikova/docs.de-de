---
title: 'Vorgehensweise: Binden einer TreeView an Daten mit nicht bestimmbarer Tiefe'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
ms.openlocfilehash: 702a86f049635423a31e554d205dcc3cf4aa799d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605366"
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>Vorgehensweise: Binden einer TreeView an Daten mit nicht bestimmbarer Tiefe
Es kann möglicherweise vorkommen, wenn Sie binden möchten, eine <xref:System.Windows.Controls.TreeView> mit einer Datenquelle, deren Tiefe ist nicht bekannt.  Dies kann auftreten, wenn die Daten rekursiv sind, z. B. ein Dateisystem, in dem Ordner Ordner enthalten kann, oder eines Unternehmens Organisationsstruktur, auf dem Mitarbeiter andere Mitarbeiter unterstellt sind.  
  
 Die Datenquelle muss es sich um eine hierarchische Objektmodell aufweisen. Z. B. eine `Employee` Klasse kann eine Auflistung von Employee-Objekten, die direkt unterstellten Mitarbeiter eines Mitarbeiters sind, enthalten. Wenn die Daten auf eine Weise, die nicht hierarchisch ist dargestellt werden, müssen Sie eine hierarchische Darstellung der Daten erstellen.  
  
 Beim Festlegen der <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> Eigenschaft und, wenn die <xref:System.Windows.Controls.ItemsControl> generiert eine <xref:System.Windows.Controls.ItemsControl> für jedes untergeordnete Element, und klicken Sie dann auf das untergeordnete Element <xref:System.Windows.Controls.ItemsControl> verwendet die gleichen <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> als übergeordnetes Element. Wenn Sie festlegen, z. B. die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Eigenschaft für ein datengebundenes <xref:System.Windows.Controls.TreeView>, die jeweils <xref:System.Windows.Controls.TreeViewItem> , generierten verwendet die <xref:System.Windows.DataTemplate> , zugewiesen wurde die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Eigenschaft der <xref:System.Windows.Controls.TreeView>.  
  
 Die <xref:System.Windows.HierarchicalDataTemplate> ermöglicht Ihnen die Angabe der <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für eine <xref:System.Windows.Controls.TreeViewItem>, oder ein beliebiges <xref:System.Windows.Controls.HeaderedItemsControl>, in der Datenvorlage. Beim Festlegen der <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType> Eigenschaft, die Wert wird verwendet, wenn die <xref:System.Windows.HierarchicalDataTemplate> angewendet wird. Mithilfe einer <xref:System.Windows.HierarchicalDataTemplate>, können Sie rekursiv den <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für jede <xref:System.Windows.Controls.TreeViewItem> in die <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel veranschaulicht das Binden einer <xref:System.Windows.Controls.TreeView> hierarchische Daten und Verwenden einer <xref:System.Windows.HierarchicalDataTemplate> an die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für jede <xref:System.Windows.Controls.TreeViewItem>.  Die <xref:System.Windows.Controls.TreeView> bindet an XML-Daten, die die Mitarbeiter in einem Unternehmen darstellt.  Jede `Employee` Element möglicherweise andere `Employee` Elemente, um anzugeben, die die Berichte. Da die Daten rekursiv ist die <xref:System.Windows.HierarchicalDataTemplate> kann auf jeder Ebene angewendet werden.  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)
