---
title: 'Gewusst wie: Suchen eines TreeViewItem-Elements in TreeView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
ms.openlocfilehash: cff931312e6bc6db5ae5f26c0db80ad2f43825f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a>Gewusst wie: Suchen eines TreeViewItem-Elements in TreeView
Die <xref:System.Windows.Controls.TreeView> Steuerelement stellt eine einfache Möglichkeit zum Anzeigen von hierarchischen Daten. Wenn Ihre <xref:System.Windows.Controls.TreeView> an eine Datenquelle gebunden ist die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> Eigenschaft bietet eine einfache Möglichkeit für Sie die ausgewählten Daten-Objekt schnell abgerufen werden. Es wird in der Regel empfohlen, das zugrunde liegende Datenobjekt arbeiten, aber in einigen Fällen müssen Sie möglicherweise programmgesteuert zu bearbeiten, die der Daten enthält <xref:System.Windows.Controls.TreeViewItem>. Sie möchten z. B. programmgesteuert erweitern die <xref:System.Windows.Controls.TreeViewItem>, oder wählen Sie ein anderes Element in der <xref:System.Windows.Controls.TreeView>.  
  
 Zum Suchen einer <xref:System.Windows.Controls.TreeViewItem> , die ein bestimmtes Datenobjekt enthält, müssen Sie jede Ebene der durchlaufen die <xref:System.Windows.Controls.TreeView>. Die Elemente in einem <xref:System.Windows.Controls.TreeView> können auch virtualisiert werden, um die Leistung zu verbessern. In Fällen, in denen Elemente virtualisiert werden können, Sie auch müssen umsetzen einer <xref:System.Windows.Controls.TreeViewItem> zu überprüfen, ob sie das Datenobjekt enthält.  
  
## <a name="example"></a>Beispiel  
  
## <a name="description"></a>Beschreibung  
 Das folgende Beispiel sucht eine <xref:System.Windows.Controls.TreeView> für ein bestimmtes Objekt und gibt das Objekt der enthaltenden <xref:System.Windows.Controls.TreeViewItem>. Im Beispiel wird sichergestellt, dass jedes <xref:System.Windows.Controls.TreeViewItem> instanziiert wird, damit die untergeordneten Elemente gesucht werden können. Dieses Beispiel funktioniert auch, wenn die <xref:System.Windows.Controls.TreeView> nicht virtualisierten Elemente verwendet.  
  
> [!NOTE]
>  Das folgende Beispiel funktioniert für alle <xref:System.Windows.Controls.TreeView>unabhängig von der zugrunde liegenden Datenmodell und sucht alle <xref:System.Windows.Controls.TreeViewItem> bis das Objekt gefunden wird. Eine andere Technik, die eine bessere Leistung wird das Datenmodell für das angegebene Objekt zu suchen, Nachverfolgen von ihrem Speicherort in der Datenhierarchie und suchen Sie dann auf den entsprechenden <xref:System.Windows.Controls.TreeViewItem> in der <xref:System.Windows.Controls.TreeView>. Jedoch das Verfahren, die eine bessere Leistung erfordert Kenntnisse des Datenmodells und kann nicht für jedes verallgemeinert werden <xref:System.Windows.Controls.TreeView>.  
  
## <a name="code"></a>Code  
 [!code-csharp[TreeViewFindTVI#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 Der vorherige Code basiert auf einem benutzerdefinierten <xref:System.Windows.Controls.VirtualizingStackPanel> , verfügbar macht eine Methode namens `BringIntoView`. Der folgende Code definiert die benutzerdefinierte <xref:System.Windows.Controls.VirtualizingStackPanel>.  
  
 [!code-csharp[TreeViewFindTVI#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 Der folgende XAML-Code zeigt, wie eine <xref:System.Windows.Controls.TreeView> , verwendet die benutzerdefinierte <xref:System.Windows.Controls.VirtualizingStackPanel>.  
  
 [!code-xaml[TreeViewFindTVI#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verbessern der Leistung von TreeView](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md)
