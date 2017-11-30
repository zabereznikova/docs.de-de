---
title: 'Gewusst wie: Erstellen einfacher und komplexer TreeViews'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TreeView control [WPF], creating
- Control class [WPF], TreeView [WPF], creating
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5e09f0f39d0c9a40a0e91299d308921917067166
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-simple-or-complex-treeviews"></a>Gewusst wie: Erstellen einfacher und komplexer TreeViews
In diesem Beispiel wird gezeigt, wie zum Erstellen von einfachen oder komplexen <xref:System.Windows.Controls.TreeView> Steuerelemente.  
  
 Ein <xref:System.Windows.Controls.TreeView> besteht aus einer Hierarchie von <xref:System.Windows.Controls.TreeViewItem> Steuerelemente, die einfache Textzeichenfolgen und auch komplexere Inhalte, z. B. enthalten können <xref:System.Windows.Controls.Button> Steuerelemente oder ein <xref:System.Windows.Controls.StackPanel> mit eingebetteter Inhalt. Sie können explizit definieren die <xref:System.Windows.Controls.TreeView> Inhalt oder eine Datenquelle kann der Inhalt bereitgestellt. Dieses Thema enthält Beispiele für diese Konzepte.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Eigenschaft von der <xref:System.Windows.Controls.TreeViewItem> enthält den Inhalt, der <xref:System.Windows.Controls.TreeView> für dieses Element angezeigt. Ein <xref:System.Windows.Controls.TreeViewItem> auch <xref:System.Windows.Controls.TreeViewItem> Steuerelemente als seinen untergeordneten Elementen und Sie können diese untergeordneten Elemente definieren, mit der <xref:System.Windows.Controls.ItemsControl.Items%2A> Eigenschaft.  
  
 Im folgende Beispiel wird gezeigt, wie explizit definieren <xref:System.Windows.Controls.TreeViewItem> Inhalt durch Festlegen der <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Eigenschaft in eine Textzeichenfolge.  
  
 [!code-xaml[TreeViewSimple#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 Im folgende Beispiel wird gezeigt, wie untergeordnete Elemente des definieren eine <xref:System.Windows.Controls.TreeViewItem> durch die Definition <xref:System.Windows.Controls.ItemsControl.Items%2A> sind <xref:System.Windows.Controls.Button> Steuerelemente.  
  
 [!code-xaml[TreeViewSimple#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Controls.TreeView> , in dem ein <xref:System.Windows.Data.XmlDataProvider> bietet <xref:System.Windows.Controls.TreeViewItem> Inhalt und ein <xref:System.Windows.HierarchicalDataTemplate> definiert die Darstellung des Inhalts.  
  
 [!code-xaml[TreeViewSimple#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xaml[TreeViewSimple#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xaml[TreeViewSimple#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Controls.TreeView> , in dem die <xref:System.Windows.Controls.TreeViewItem> Inhalt enthält <xref:System.Windows.Controls.DockPanel> Steuerelemente, die eingebettete Inhalte zu haben.  
  
 [!code-xaml[TreeViewSimple#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [Übersicht über TreeView](../../../../docs/framework/wpf/controls/treeview-overview.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)
