---
title: 'Gewusst wie: Verwendung von SelectedValue, SelectedValuePath und SelectedItem'
description: Erfahren Sie, wie Sie mit den Eigenschaften SelectedValue und SelectedValuePath einen Wert für das SelectedItem-Element einer Windows Presentation Foundation TreeView angeben.
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
ms.openlocfilehash: ddac2455dee0bf69d25307340eddd5364e43e823
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166272"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a>Gewusst wie: Verwendung von SelectedValue, SelectedValuePath und SelectedItem
In diesem Beispiel wird gezeigt, wie die-Eigenschaft und die-Eigenschaft verwendet werden <xref:System.Windows.Controls.TreeView.SelectedValue%2A> <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> , um einen Wert für den einer anzugeben <xref:System.Windows.Controls.TreeView.SelectedItem%2A> <xref:System.Windows.Controls.TreeView> .  
  
## <a name="example"></a>Beispiel  
 Die- <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Eigenschaft stellt eine Möglichkeit zum Angeben eines <xref:System.Windows.Controls.TreeView.SelectedValue%2A> für den <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in einer bereit <xref:System.Windows.Controls.TreeView> . <xref:System.Windows.Controls.TreeView.SelectedItem%2A>Stellt ein Objekt in der Auflistung dar <xref:System.Windows.Controls.ItemsControl.Items%2A> und <xref:System.Windows.Controls.TreeView> zeigt den Wert einer einzelnen Eigenschaft des ausgewählten Elements an. Die- <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Eigenschaft gibt den Pfad zu der Eigenschaft an, die verwendet wird, um den Wert der-Eigenschaft zu bestimmen <xref:System.Windows.Controls.TreeView.SelectedValue%2A> . In den Beispielen in diesem Thema wird dieses Konzept veranschaulicht.  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Data.XmlDataProvider> , die Mitarbeiter Informationen enthält.  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 Im folgenden Beispiel wird eine definiert <xref:System.Windows.HierarchicalDataTemplate> , `EmployeeName` mit der und der angezeigt werden `EmployeeWorkDay` `Employee` . Beachten Sie, dass die <xref:System.Windows.HierarchicalDataTemplate> nicht `EmployeeNumber` als Teil der Vorlage angibt.  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 Das folgende Beispiel zeigt einen <xref:System.Windows.Controls.TreeView> , der den zuvor definierten verwendet <xref:System.Windows.HierarchicalDataTemplate> und die- <xref:System.Windows.Controls.TreeView.SelectedValue%2A> Eigenschaft auf festlegt `EmployeeNumber` . Wenn Sie ein `EmployeeName` in der auswählen <xref:System.Windows.Controls.TreeView> , gibt die- <xref:System.Windows.Controls.TreeView.SelectedItem%2A> Eigenschaft das `EmployeeInfo` Datenelement zurück, das dem ausgewählten entspricht `EmployeeName` . Da jedoch <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> <xref:System.Windows.Controls.TreeView> auf festgelegt ist `EmployeeNumber` , <xref:System.Windows.Controls.TreeView.SelectedValue%2A> wird der auf festgelegt `EmployeeNumber` .  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Übersicht über TreeView](treeview-overview.md)
- [Artikel zu Vorgehensweisen](treeview-how-to-topics.md)
