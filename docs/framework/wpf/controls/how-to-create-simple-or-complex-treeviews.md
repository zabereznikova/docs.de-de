---
title: "Gewusst wie: Erstellen einfacher und komplexer TreeViews | Microsoft Docs"
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
  - "Control-Klasse, TreeView, Erstellen"
  - "TreeView-Steuerelement, Erstellen"
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Erstellen einfacher und komplexer TreeViews
In diesem Beispiel wird das Erstellen von einfachen und komplexen <xref:System.Windows.Controls.TreeView>\-Steuerelementen dargestellt.  
  
 Ein <xref:System.Windows.Controls.TreeView> setzt sich aus einer Hierarchie von <xref:System.Windows.Controls.TreeViewItem>\-Steuerelementen zusammen, die einfache Textzeichenfolgen oder komplexeren Inhalt enthalten können, z. B. <xref:System.Windows.Controls.Button>\-Steuerelemente oder ein <xref:System.Windows.Controls.StackPanel> mit eingebettetem Inhalt.  Sie können den <xref:System.Windows.Controls.TreeView>\-Inhalt explizit definieren, oder der Inhalt kann von einer Datenquelle bereitgestellt werden.  In diesem Thema finden Sie Beispiele für diese Konzepte.  
  
## Beispiel  
 Die <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>\-Eigenschaft des <xref:System.Windows.Controls.TreeViewItem> enthält den Inhalt, der im <xref:System.Windows.Controls.TreeView> für dieses Element angezeigt wird.  Ein <xref:System.Windows.Controls.TreeViewItem> kann auch über <xref:System.Windows.Controls.TreeViewItem>\-Steuerelemente als untergeordnete Elemente verfügen. Sie können diese untergeordneten Elemente mithilfe der <xref:System.Windows.Controls.ItemsControl.Items%2A>\-Eigenschaft definieren.  
  
 Im folgenden Beispiel wird das explizite Definieren des <xref:System.Windows.Controls.TreeViewItem>\-Inhalts durch Festlegen der <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>\-Eigenschaft auf eine Zeichenfolge dargestellt.  
  
 [!code-xml[TreeViewSimple#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 Im folgenden Beispiel wird das Definieren von untergeordneten Elementen eines <xref:System.Windows.Controls.TreeViewItem> durch Definieren von <xref:System.Windows.Controls.ItemsControl.Items%2A> dargestellt, bei denen es sich um <xref:System.Windows.Controls.Button>\-Steuerelemente handelt.  
  
 [!code-xml[TreeViewSimple#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 Im folgenden Beispiel wird dargestellt, wie Sie ein <xref:System.Windows.Controls.TreeView> erstellen, in dem ein <xref:System.Windows.Data.XmlDataProvider> den <xref:System.Windows.Controls.TreeViewItem>\-Inhalt bereitstellt und eine <xref:System.Windows.HierarchicalDataTemplate> die Darstellung des Inhalts definiert.  
  
 [!code-xml[TreeViewSimple#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xml[TreeViewSimple#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xml[TreeViewSimple#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 Im folgenden Beispiel wird dargestellt, wie Sie ein <xref:System.Windows.Controls.TreeView> erstellen, in dem der <xref:System.Windows.Controls.TreeViewItem>\-Inhalt <xref:System.Windows.Controls.DockPanel>\-Steuerelemente mit eingebettetem Inhalt enthält.  
  
 [!code-xml[TreeViewSimple#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.TreeView>   
 <xref:System.Windows.Controls.TreeViewItem>   
 [Übersicht über TreeView](../../../../docs/framework/wpf/controls/treeview-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)