---
title: 'Gewusst wie: Binden einer TreeView an Daten mit nicht bestimmbarer Tiefe'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
ms.openlocfilehash: cd9a1ee015ebb707a7a06d1c062a1bb3003c96e8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458614"
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>Gewusst wie: Binden einer TreeView an Daten mit nicht bestimmbarer Tiefe
Es kann vorkommen, dass Sie eine <xref:System.Windows.Controls.TreeView> an eine Datenquelle binden möchten, deren Tiefe nicht bekannt ist.  Dies kann vorkommen, wenn die Daten rekursiv sind, z. b. ein Dateisystem, in dem Ordner Ordner enthalten können, oder die Organisationsstruktur eines Unternehmens, in der Mitarbeiter andere Mitarbeiter als direktberichte haben.  
  
 Die Datenquelle muss über ein hierarchisches Objektmodell verfügen. Beispielsweise kann eine `Employee` Klasse eine Auflistung von Employee-Objekten enthalten, bei denen es sich um die direkten Berichte eines Mitarbeiters handelt. Wenn die Daten auf eine nicht hierarchische Weise dargestellt werden, müssen Sie eine hierarchische Darstellung der Daten erstellen.  
  
 Wenn Sie die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType>-Eigenschaft festlegen und die <xref:System.Windows.Controls.ItemsControl> für jedes untergeordnete Element eine <xref:System.Windows.Controls.ItemsControl> generiert, verwendet das untergeordnete <xref:System.Windows.Controls.ItemsControl> denselben <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> wie das übergeordnete Element. Wenn Sie z. b. die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>-Eigenschaft für ein Daten gebundenes <xref:System.Windows.Controls.TreeView>festlegen, verwendet jedes generierte <xref:System.Windows.Controls.TreeViewItem> das <xref:System.Windows.DataTemplate>, das der <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>-Eigenschaft des <xref:System.Windows.Controls.TreeView>zugewiesen wurde.  
  
 Mit der <xref:System.Windows.HierarchicalDataTemplate> können Sie die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für eine <xref:System.Windows.Controls.TreeViewItem>oder eine beliebige <xref:System.Windows.Controls.HeaderedItemsControl>in der Daten Vorlage angeben. Wenn Sie die <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType>-Eigenschaft festlegen, wird dieser Wert verwendet, wenn die <xref:System.Windows.HierarchicalDataTemplate> angewendet wird. Mithilfe eines <xref:System.Windows.HierarchicalDataTemplate>können Sie die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für jedes <xref:System.Windows.Controls.TreeViewItem> in der <xref:System.Windows.Controls.TreeView>rekursiv festlegen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Controls.TreeView> an hierarchische Daten gebunden wird und ein <xref:System.Windows.HierarchicalDataTemplate> verwendet wird, um die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für jede <xref:System.Windows.Controls.TreeViewItem>anzugeben.  Der <xref:System.Windows.Controls.TreeView> bindet an XML-Daten, die die Mitarbeiter in einem Unternehmen darstellen.  Jedes `Employee` Element kann andere `Employee` Elemente enthalten, um anzugeben, wer an wen berichtet. Da die Daten rekursiv sind, können die <xref:System.Windows.HierarchicalDataTemplate> auf jede Ebene angewendet werden.  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über Datenvorlagen](../data/data-templating-overview.md)
