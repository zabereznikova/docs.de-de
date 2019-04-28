---
title: 'Vorgehensweise: Verbessern der Leistung eines TreeView-Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: de1b46da2a7c6c3db0c0c19cdbb654fcf2fbbd6c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771006"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a>Vorgehensweise: Verbessern der Leistung eines TreeView-Objekts
Wenn eine <xref:System.Windows.Controls.TreeView> viele Elemente enthält, die Zeitspanne, die zum Laden benötigt möglicherweise eine erhebliche Verzögerung eintreten, in der Benutzeroberfläche. Sie können die Ladezeit verbessern, indem Sie die Einstellung der `VirtualizingStackPanel.IsVirtualizing` angefügte Eigenschaft zu `true`.  Die Benutzeroberfläche langsam reagiert, wenn ein Benutzer einen Bildlauf möglicherweise auch die <xref:System.Windows.Controls.TreeView> durch das Mausrad verwenden, oder ziehen das Thumb-Steuerelement eine Bildlaufleiste. Sie können die Leistung verbessern die <xref:System.Windows.Controls.TreeView> Wenn der Benutzer scrollt durch Festlegen der `VirtualizingStackPanel.VirtualizationMode` angefügte Eigenschaft zu <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.  
  
## <a name="example"></a>Beispiel  
  
## <a name="description"></a>Beschreibung  
Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.TreeView> festlegt, die die `VirtualizingStackPanel.IsVirtualizing` angefügte Eigenschaft auf "true" und die `VirtualizingStackPanel.VirtualizationMode` angefügte Eigenschaft zu <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> zur leistungsoptimierung.  
  
## <a name="code"></a>Code  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 Das folgende Beispiel zeigt den Daten, die im vorherigen Beispiel verwendet.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a>Siehe auch

- [Steuerelemente](../advanced/optimizing-performance-controls.md)
