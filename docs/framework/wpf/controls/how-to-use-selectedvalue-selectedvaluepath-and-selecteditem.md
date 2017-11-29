---
title: 'Gewusst wie: Verwendung von SelectedValue, SelectedValuePath und SelectedItem'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fdc478d62ca97f8f61c26fbbf1ee6c3ea8b4e189
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a>Gewusst wie: Verwendung von SelectedValue, SelectedValuePath und SelectedItem
Dieses Beispiel zeigt, wie die <xref:System.Windows.Controls.TreeView.SelectedValue%2A> und <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Eigenschaften zur Angabe eines Werts für die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> von einem <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Eigenschaft bietet eine Möglichkeit zum Angeben einer <xref:System.Windows.Controls.TreeView.SelectedValue%2A> für die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in einer <xref:System.Windows.Controls.TreeView>. Die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> stellt ein Objekt in der <xref:System.Windows.Controls.ItemsControl.Items%2A> Auflistung und die <xref:System.Windows.Controls.TreeView> zeigt den Wert einer einzelnen Eigenschaft des ausgewählten Elements. Die <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Eigenschaft gibt den Pfad zu der Eigenschaft, die verwendet wird, um den Wert der Festlegen der <xref:System.Windows.Controls.TreeView.SelectedValue%2A> Eigenschaft. Die Beispiele in diesem Thema veranschaulichen dieses Konzept.  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Data.XmlDataProvider> , die Mitarbeiterinformationen enthält.  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 Das folgende Beispiel definiert eine <xref:System.Windows.HierarchicalDataTemplate> , anzeigt der `EmployeeName` und `EmployeeWorkDay` von der `Employee`. Beachten Sie, dass die <xref:System.Windows.HierarchicalDataTemplate> gibt keinen der `EmployeeNumber` als Teil der Vorlage.  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.TreeView> , verwendet die zuvor definierte <xref:System.Windows.HierarchicalDataTemplate> und legt sie fest, die die <xref:System.Windows.Controls.TreeView.SelectedValue%2A> Eigenschaft, um die `EmployeeNumber`. Bei Auswahl einer `EmployeeName` in der <xref:System.Windows.Controls.TreeView>, die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> -Eigenschaft gibt die `EmployeeInfo` Datenelement, das dem ausgewählten `EmployeeName`. Jedoch, da die <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> dieses <xref:System.Windows.Controls.TreeView> auf festgelegt ist `EmployeeNumber`, die <xref:System.Windows.Controls.TreeView.SelectedValue%2A> auf festgelegt ist die `EmployeeNumber`.  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [Übersicht über TreeView](../../../../docs/framework/wpf/controls/treeview-overview.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)
