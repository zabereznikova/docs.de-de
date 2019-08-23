---
title: 'Vorgehensweise: Suchen eines TreeViewItem-Elements in einem TreeView-Objekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
ms.openlocfilehash: ad72c7a7fb11dfe605db4119dde831b47dd7c5a4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962097"
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a>Vorgehensweise: Suchen eines TreeViewItem-Elements in einem TreeView-Objekt
Das <xref:System.Windows.Controls.TreeView> -Steuerelement stellt eine bequeme Möglichkeit zum Anzeigen hierarchischer Daten dar. Wenn Ihr <xref:System.Windows.Controls.TreeView> an eine Datenquelle gebunden ist, stellt <xref:System.Windows.Controls.TreeView.SelectedItem%2A> die-Eigenschaft eine bequeme Methode zum schnellen Abrufen des ausgewählten Datenobjekts bereit. Es ist in der Regel am besten, mit dem zugrunde liegenden Datenobjekt zu arbeiten. manchmal müssen Sie jedoch möglicherweise die enthaltenden <xref:System.Windows.Controls.TreeViewItem>Daten Programm gesteuert bearbeiten. Beispielsweise müssen Sie möglicherweise Programm gesteuert erweitern <xref:System.Windows.Controls.TreeViewItem>oder ein anderes Element in der <xref:System.Windows.Controls.TreeView>auswählen.  
  
 Um einen <xref:System.Windows.Controls.TreeViewItem> zu suchen, der ein bestimmtes Datenobjekt enthält, müssen Sie jede Ebene <xref:System.Windows.Controls.TreeView>von durchlaufen. Die Elemente in einer <xref:System.Windows.Controls.TreeView> können auch virtualisiert werden, um die Leistung zu verbessern. Wenn Elemente virtualisiert werden können, müssen Sie auch einen <xref:System.Windows.Controls.TreeViewItem> erkennen, um zu überprüfen, ob das Datenobjekt enthalten ist.  
  
## <a name="example"></a>Beispiel  
  
## <a name="description"></a>Beschreibung  
 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.TreeView> -Objekt für ein bestimmtes-Objekt durchsucht und <xref:System.Windows.Controls.TreeViewItem>die enthaltende des Objekts zurückgegeben. Im Beispiel wird sichergestellt <xref:System.Windows.Controls.TreeViewItem> , dass jede instanziiert wird, sodass die untergeordneten Elemente durchsucht werden können. Dieses Beispiel <xref:System.Windows.Controls.TreeView> kann auch verwendet werden, wenn keine virtualisierten Elemente verwendet.  
  
> [!NOTE]
> Das folgende Beispiel funktioniert <xref:System.Windows.Controls.TreeView>unabhängig vom zugrunde liegenden Datenmodell, und sucht alle <xref:System.Windows.Controls.TreeViewItem> , bis das-Objekt gefunden wird. Ein weiteres Verfahren, das eine bessere Leistung bietet, ist das Durchsuchen des Datenmodells nach dem angegebenen Objekt, das Nachverfolgen seines Speicher Orts in der Daten Hierarchie und <xref:System.Windows.Controls.TreeView>das anschließende suchen der entsprechenden <xref:System.Windows.Controls.TreeViewItem> in der. Das Verfahren, das eine bessere Leistung bietet, erfordert jedoch Kenntnisse des Datenmodells und kann nicht für eine bestimmte <xref:System.Windows.Controls.TreeView>verallgemeinert werden.  
  
## <a name="code"></a>Code  
 [!code-csharp[TreeViewFindTVI#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 Der vorherige Code basiert auf einem Benutzer <xref:System.Windows.Controls.VirtualizingStackPanel> definierten, das eine Methode `BringIntoView`mit dem Namen verfügbar macht. Im folgenden Code wird der Benutzer <xref:System.Windows.Controls.VirtualizingStackPanel>definierte definiert.  
  
 [!code-csharp[TreeViewFindTVI#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 Der folgende XAML-Code zeigt, wie <xref:System.Windows.Controls.TreeView> Sie einen erstellen, <xref:System.Windows.Controls.VirtualizingStackPanel>der den benutzerdefinierten verwendet.  
  
 [!code-xaml[TreeViewFindTVI#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a>Siehe auch

- [Verbessern der Leistung von TreeView](how-to-improve-the-performance-of-a-treeview.md)
