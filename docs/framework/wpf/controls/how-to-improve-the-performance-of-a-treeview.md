---
title: 'Gewusst wie: Verbessern der Leistung von TreeView'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 209f2c5645758aba4d1e10fc36fe773faa975e6b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a><span data-ttu-id="cccfa-102">Gewusst wie: Verbessern der Leistung von TreeView</span><span class="sxs-lookup"><span data-stu-id="cccfa-102">How to: Improve the Performance of a TreeView</span></span>
<span data-ttu-id="cccfa-103">Wenn eine <xref:System.Windows.Controls.TreeView> viele Elemente enthält, die Menge der zum Laden benötigte Zeit kann dazu führen, dass einen erheblichen Verzögerung in der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="cccfa-103">If a <xref:System.Windows.Controls.TreeView> contains many items, the amount of time it takes to load may cause a significant delay in the user interface.</span></span> <span data-ttu-id="cccfa-104">Sie können die Ladezeit verbessern, indem Sie die Einstellung der `VirtualizingStackPanel.IsVirtualizing` angefügten Eigenschaft, um `true`.</span><span class="sxs-lookup"><span data-stu-id="cccfa-104">You can improve the load time by setting the `VirtualizingStackPanel.IsVirtualizing` attached property to `true`.</span></span>  <span data-ttu-id="cccfa-105">Die Benutzeroberfläche möglicherweise auch nur langsam reagiert, wenn ein Benutzer einen Bildlauf der <xref:System.Windows.Controls.TreeView> verwenden das Mausrad oder ziehen den Ziehpunkt einer Bildlaufleiste.</span><span class="sxs-lookup"><span data-stu-id="cccfa-105">The UI might also be slow to react when a user scrolls the <xref:System.Windows.Controls.TreeView> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="cccfa-106">Sie können die Leistung verbessern die <xref:System.Windows.Controls.TreeView> beim Bildlauf durch Festlegen der `VirtualizingStackPanel.VirtualizationMode` angefügten Eigenschaft, um <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cccfa-106">You can improve the performance of the <xref:System.Windows.Controls.TreeView> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cccfa-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cccfa-107">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="cccfa-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cccfa-108">Description</span></span>  
<span data-ttu-id="cccfa-109">Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.TreeView> festlegt, die `VirtualizingStackPanel.IsVirtualizing` -Eigenschaft auf "true" und die `VirtualizingStackPanel.VirtualizationMode` angefügten Eigenschaft, um <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> um die Leistung zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="cccfa-109">The following example creates a <xref:System.Windows.Controls.TreeView> that sets the `VirtualizingStackPanel.IsVirtualizing` attached property to true and the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to optimize its performance.</span></span>  
  
## <a name="code"></a><span data-ttu-id="cccfa-110">Code</span><span class="sxs-lookup"><span data-stu-id="cccfa-110">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 <span data-ttu-id="cccfa-111">Das folgende Beispiel zeigt den Daten, die im vorherigen Beispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="cccfa-111">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a><span data-ttu-id="cccfa-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cccfa-112">See Also</span></span>  
 [<span data-ttu-id="cccfa-113">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="cccfa-113">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
