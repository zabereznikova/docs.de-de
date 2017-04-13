---
title: "Gewusst wie: Suchen eines TreeViewItem-Elements in TreeView | Microsoft Docs"
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
  - "TreeView-Steuerelement [WPF], Suchen nach einem TreeViewItem"
  - "TreeViewItem [WPF], Suchen"
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Suchen eines TreeViewItem-Elements in TreeView
Das <xref:System.Windows.Controls.TreeView>\-Steuerelement bietet eine bequeme Möglichkeit zum Anzeigen hierarchischer Daten.  Wenn die <xref:System.Windows.Controls.TreeView> an eine Datenquelle gebunden ist, können Sie das ausgewählte Datenobjekt mit der <xref:System.Windows.Controls.TreeView.SelectedItem%2A>\-Eigenschaft schnell und einfach abrufen.  In der Regel empfiehlt es sich, mit dem zugrunde liegenden Datenobjekt zu arbeiten. Mitunter kann es jedoch erforderlich sein, dass enthaltende <xref:System.Windows.Controls.TreeViewItem> der Daten programmgesteuert zu bearbeiten.  Möglicherweise müssen Sie z. B. programmgesteuert das <xref:System.Windows.Controls.TreeViewItem> erweitern oder ein anderes Element in der <xref:System.Windows.Controls.TreeView> auswählen.  
  
 Um ein <xref:System.Windows.Controls.TreeViewItem> zu finden, das ein bestimmtes Datenobjekt enthält, müssen Sie jede Ebene der <xref:System.Windows.Controls.TreeView> durchlaufen.  Die Elemente in einer <xref:System.Windows.Controls.TreeView> können auch virtualisiert werden, um die Leistung zu verbessern.  Wenn Elemente virtualisiert werden können, muss ein <xref:System.Windows.Controls.TreeViewItem> auch überprüfen, ob es das Datenobjekt enthält.  
  
## Beispiel  
  
## Beschreibung  
 Im folgenden Beispiel wird in einer <xref:System.Windows.Controls.TreeView> nach einem bestimmten Objekt gesucht, und das enthaltende <xref:System.Windows.Controls.TreeViewItem> des Objekts wird zurückgegeben.  Im Beispiel wird sichergestellt, dass jedes <xref:System.Windows.Controls.TreeViewItem> instanziiert wird, sodass seine untergeordneten Elemente durchsucht werden können.  Dieses Beispiel funktioniert auch, wenn die <xref:System.Windows.Controls.TreeView> keine virtualisierten Elemente verwendet.  
  
> [!NOTE]
>  Das folgende Beispiel, bei dem jedes <xref:System.Windows.Controls.TreeViewItem> durchsucht wird, bis das Objekt gefunden wird, funktioniert unabhängig vom zugrunde liegenden Datenmodell für jede <xref:System.Windows.Controls.TreeView>.  Eine andere Technik mit besserer Leistung besteht darin, das Datenmodell nach dem angegebenen Objekt zu durchsuchen, die Position innerhalb der Datenhierarchie nachzuverfolgen und dann nach dem entsprechenden <xref:System.Windows.Controls.TreeViewItem> in der <xref:System.Windows.Controls.TreeView> zu suchen.  Die Technik mit der besseren Leistung setzt jedoch Kenntnisse des Datenmodells voraus, und kann nicht für jede <xref:System.Windows.Controls.TreeView> generalisiert werden.  
  
## Code  
 [!code-csharp[TreeViewFindTVI#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 Der vorherige Code basiert auf einem benutzerdefinierten <xref:System.Windows.Controls.VirtualizingStackPanel>, der eine Methode mit dem Namen `BringIntoView` verfügbar macht.  Im folgenden Code wird der benutzerdefinierte <xref:System.Windows.Controls.VirtualizingStackPanel> definiert.  
  
 [!code-csharp[TreeViewFindTVI#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 Der folgende XAML\-Code zeigt, wie eine <xref:System.Windows.Controls.TreeView> mit dem benutzerdefinierten <xref:System.Windows.Controls.VirtualizingStackPanel> erstellt wird.  
  
 [!code-xml[TreeViewFindTVI#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## Siehe auch  
 [Verbessern der Leistung von TreeView](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md)