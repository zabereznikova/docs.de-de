---
title: 'Vorgehensweise: Erstellen von einfachen oder komplexen TreeViews'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], creating
- Control class [WPF], TreeView [WPF], creating
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
ms.openlocfilehash: 9b19443c80818809122b0bbfc7c7dae7b4b40da5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368915"
---
# <a name="how-to-create-simple-or-complex-treeviews"></a>Vorgehensweise: Erstellen von einfachen oder komplexen TreeViews
In diesem Beispiel wird gezeigt, wie zum Erstellen von einfachen oder komplexen <xref:System.Windows.Controls.TreeView> Steuerelemente.  
  
 Ein <xref:System.Windows.Controls.TreeView> besteht aus einer Hierarchie von <xref:System.Windows.Controls.TreeViewItem> -Steuerelemente, die einfache Textzeichenfolgen und auch eine komplexere Inhalte, z. B. darf <xref:System.Windows.Controls.Button> Steuerelemente oder ein <xref:System.Windows.Controls.StackPanel> mit eingebetteter Inhalt. Sie können explizit definieren, die <xref:System.Windows.Controls.TreeView> Inhalt oder eine Datenquelle kann der Inhalt bereitgestellt. Dieses Thema enthält Beispiele für diese Konzepte.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Eigenschaft der <xref:System.Windows.Controls.TreeViewItem> enthält den Inhalt, der die <xref:System.Windows.Controls.TreeView> für dieses Element angezeigt. Ein <xref:System.Windows.Controls.TreeViewItem> haben auch <xref:System.Windows.Controls.TreeViewItem> Steuerelemente als seine untergeordneten Elemente und Sie können diese untergeordneten Elemente definieren, indem Sie mit der <xref:System.Windows.Controls.ItemsControl.Items%2A> Eigenschaft.  
  
 Das folgende Beispiel zeigt, wie Sie explizit definieren <xref:System.Windows.Controls.TreeViewItem> Inhalt durch Festlegen der <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Eigenschaft, um eine Textzeichenfolge.  
  
 [!code-xaml[TreeViewSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 Das folgende Beispiel zeigt die untergeordneten Elemente definieren eine <xref:System.Windows.Controls.TreeViewItem> definieren <xref:System.Windows.Controls.ItemsControl.Items%2A> sind <xref:System.Windows.Controls.Button> Steuerelemente.  
  
 [!code-xaml[TreeViewSimple#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.TreeView> , in denen ein <xref:System.Windows.Data.XmlDataProvider> bietet <xref:System.Windows.Controls.TreeViewItem> Inhalt und einem <xref:System.Windows.HierarchicalDataTemplate> definiert die Darstellung des Inhalts.  
  
 [!code-xaml[TreeViewSimple#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xaml[TreeViewSimple#7](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xaml[TreeViewSimple#5](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.TreeView> , in denen die <xref:System.Windows.Controls.TreeViewItem> Inhalt enthält <xref:System.Windows.Controls.DockPanel> Steuerelemente, die eingebettete Inhalte zu haben.  
  
 [!code-xaml[TreeViewSimple#9](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Übersicht über TreeView](treeview-overview.md)
- [Themen zu Vorgehensweisen](treeview-how-to-topics.md)
