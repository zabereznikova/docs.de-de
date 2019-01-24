---
title: 'Vorgehensweise: Verwendung von SelectedValue, SelectedValuePath und SelectedItem'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], SelectedValue properties
- Control class [WPF], SelectedItem properties
- Control class [WPF], TreeView properties
- Control class [WPF], SelectedValue properties
- TreeView control [WPF], SelectedItem properties
- SelectedValue [WPF], SelectedValuePath properties
- TreeView control [WPF], SelectedValuePath properties
- Control class [WPF], SelectedValuePath properties
- SelectedValue [WPF], SelectedItem properties
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
ms.openlocfilehash: 1bb307009586a5bbf4e9accefb633b97dc837528
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637822"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a>Vorgehensweise: Verwendung von SelectedValue, SelectedValuePath und SelectedItem
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.TreeView.SelectedValue%2A> und <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Eigenschaften, die einen Wert für die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> von einem <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Eigenschaft bietet eine Möglichkeit zum Angeben einer <xref:System.Windows.Controls.TreeView.SelectedValue%2A> für die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in eine <xref:System.Windows.Controls.TreeView>. Die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> stellt ein Objekt in der <xref:System.Windows.Controls.ItemsControl.Items%2A> Auflistung und die <xref:System.Windows.Controls.TreeView> zeigt den Wert einer einzelnen Eigenschaft des ausgewählten Elements. Die <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> -Eigenschaft gibt den Pfad der Eigenschaft, die verwendet wird, um zu bestimmen, den Wert des der <xref:System.Windows.Controls.TreeView.SelectedValue%2A> Eigenschaft. In die Beispielen in diesem Thema veranschaulichen dieses Konzept.  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Data.XmlDataProvider> , die Mitarbeiterinformationen enthält.  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 Das folgende Beispiel definiert eine <xref:System.Windows.HierarchicalDataTemplate> angezeigt, die die `EmployeeName` und `EmployeeWorkDay` von der `Employee`. Beachten Sie, dass die <xref:System.Windows.HierarchicalDataTemplate> gibt keinen der `EmployeeNumber` als Teil der Vorlage.  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.TreeView> , verwendet die zuvor definierte <xref:System.Windows.HierarchicalDataTemplate> und legt sie fest, die die <xref:System.Windows.Controls.TreeView.SelectedValue%2A> Eigenschaft, um die `EmployeeNumber`. Bei der Auswahl einer `EmployeeName` in die <xref:System.Windows.Controls.TreeView>, <xref:System.Windows.Controls.TreeView.SelectedItem%2A> -Eigenschaft gibt die `EmployeeInfo` Datenelement, das dem ausgewählten `EmployeeName`. Allerdings da die <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> dieses <xref:System.Windows.Controls.TreeView> nastaven NA hodnotu `EmployeeNumber`, <xref:System.Windows.Controls.TreeView.SelectedValue%2A> nastaven NA hodnotu der `EmployeeNumber`.  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Übersicht über TreeView](../../../../docs/framework/wpf/controls/treeview-overview.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)
