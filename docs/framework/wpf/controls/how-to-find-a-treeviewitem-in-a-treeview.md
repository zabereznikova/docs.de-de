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
ms.openlocfilehash: 034ec2e57fb3b6a9b3a81f66f6888a68e2c113d7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219043"
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a>Vorgehensweise: Suchen eines TreeViewItem-Elements in einem TreeView-Objekt
Die <xref:System.Windows.Controls.TreeView> Steuerelement bietet eine bequeme Möglichkeit zum Anzeigen hierarchischer Daten. Wenn Ihre <xref:System.Windows.Controls.TreeView> an eine Datenquelle gebunden ist die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> Eigenschaft bietet eine bequeme Möglichkeit, schnell auf ausgewählten Datenobjekts abzurufen. Es empfiehlt sich in der Regel mit der zugrunde liegende Datenobjekt funktioniert, aber manchmal müssen u. u. zur programmgesteuerten Bearbeitung der Daten mit <xref:System.Windows.Controls.TreeViewItem>. Angenommen, Sie müssen möglicherweise programmgesteuert erweitern die <xref:System.Windows.Controls.TreeViewItem>, oder wählen Sie ein anderes Element in der <xref:System.Windows.Controls.TreeView>.  
  
 Finden einer <xref:System.Windows.Controls.TreeViewItem> , die ein bestimmtes Objekt enthält, müssen Sie jede Ebene der Traversieren der <xref:System.Windows.Controls.TreeView>. Die Elemente in einem <xref:System.Windows.Controls.TreeView> können auch virtualisiert werden, um die Leistung zu verbessern. Im Fall, in denen Elemente virtualisiert werden können. Außerdem müssen sehen Sie eine <xref:System.Windows.Controls.TreeViewItem> zu überprüfen, ob es sich um das Datenobjekt enthält.  
  
## <a name="example"></a>Beispiel  
  
## <a name="description"></a>Beschreibung  
 Das folgende Beispiel sucht eine <xref:System.Windows.Controls.TreeView> für ein bestimmtes Objekt und gibt das Objekt der enthaltenden <xref:System.Windows.Controls.TreeViewItem>. Im Beispiel wird sichergestellt, dass jedes <xref:System.Windows.Controls.TreeViewItem> instanziiert wird, damit die untergeordneten Elemente durchsucht werden können. Dieses Beispiel funktioniert auch, wenn die <xref:System.Windows.Controls.TreeView> virtualisierte Elemente nicht verwendet.  
  
> [!NOTE]
>  Das folgende Beispiel funktioniert für alle <xref:System.Windows.Controls.TreeView>, unabhängig von der zugrunde liegenden Datenmodell und sucht alle <xref:System.Windows.Controls.TreeViewItem> bis das Objekt gefunden wird. Ein anderes Verfahren, die eine bessere Leistung ist das Datenmodell für das angegebene Objekt zu suchen, Nachverfolgen seine Position in der Datenhierarchie, und suchen Sie dann auf den entsprechenden <xref:System.Windows.Controls.TreeViewItem> in die <xref:System.Windows.Controls.TreeView>. Allerdings die Technik, die eine bessere Leistung erfordert Kenntnisse des Datenmodells und kann nicht generalisiert werden, für jeden angegebenen <xref:System.Windows.Controls.TreeView>.  
  
## <a name="code"></a>Code  
 [!code-csharp[TreeViewFindTVI#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 Der vorherige Code basiert auf einem benutzerdefinierten <xref:System.Windows.Controls.VirtualizingStackPanel> , verfügbar macht, eine Methode namens `BringIntoView`. Der folgende Code definiert die benutzerdefinierte <xref:System.Windows.Controls.VirtualizingStackPanel>.  
  
 [!code-csharp[TreeViewFindTVI#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 Der folgende XAML zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.TreeView> , verwendet die benutzerdefinierte <xref:System.Windows.Controls.VirtualizingStackPanel>.  
  
 [!code-xaml[TreeViewFindTVI#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a>Siehe auch

- [Verbessern der Leistung eines TreeView-Objekts](how-to-improve-the-performance-of-a-treeview.md)
