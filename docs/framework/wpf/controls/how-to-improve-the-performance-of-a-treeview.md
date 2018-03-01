---
title: 'Gewusst wie: Verbessern der Leistung von TreeView'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2c13a9c89bdcb149df61f26177ea8705e502402f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a>Gewusst wie: Verbessern der Leistung von TreeView
Wenn eine <xref:System.Windows.Controls.TreeView> viele Elemente enthält, die Menge der zum Laden benötigte Zeit kann dazu führen, dass einen erheblichen Verzögerung in der Benutzeroberfläche. Sie können die Ladezeit verbessern, indem Sie die Einstellung der `VirtualizingStackPanel.IsVirtualizing` angefügten Eigenschaft, um `true`.  Die Benutzeroberfläche möglicherweise auch nur langsam reagiert, wenn ein Benutzer einen Bildlauf der <xref:System.Windows.Controls.TreeView> verwenden das Mausrad oder ziehen den Ziehpunkt einer Bildlaufleiste. Sie können die Leistung verbessern die <xref:System.Windows.Controls.TreeView> beim Bildlauf durch Festlegen der `VirtualizingStackPanel.VirtualizationMode` angefügten Eigenschaft, um <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.  
  
## <a name="example"></a>Beispiel  
  
## <a name="description"></a>Beschreibung  
Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.TreeView> festlegt, die `VirtualizingStackPanel.IsVirtualizing` -Eigenschaft auf "true" und die `VirtualizingStackPanel.VirtualizationMode` angefügten Eigenschaft, um <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> um die Leistung zu optimieren.  
  
## <a name="code"></a>Code  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 Das folgende Beispiel zeigt den Daten, die im vorherigen Beispiel verwendet.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
