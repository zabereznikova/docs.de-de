---
title: 'Vorgehensweise: Verbessern der Leistung von TreeView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: d04d5997e6f02a4227704b668fdf19324ea20f26
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364735"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a><span data-ttu-id="45935-102">Vorgehensweise: Verbessern der Leistung von TreeView</span><span class="sxs-lookup"><span data-stu-id="45935-102">How to: Improve the Performance of a TreeView</span></span>
<span data-ttu-id="45935-103">Wenn eine <xref:System.Windows.Controls.TreeView> viele Elemente enthält, die Zeitspanne, die zum Laden benötigt möglicherweise eine erhebliche Verzögerung eintreten, in der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="45935-103">If a <xref:System.Windows.Controls.TreeView> contains many items, the amount of time it takes to load may cause a significant delay in the user interface.</span></span> <span data-ttu-id="45935-104">Sie können die Ladezeit verbessern, indem Sie die Einstellung der `VirtualizingStackPanel.IsVirtualizing` angefügte Eigenschaft zu `true`.</span><span class="sxs-lookup"><span data-stu-id="45935-104">You can improve the load time by setting the `VirtualizingStackPanel.IsVirtualizing` attached property to `true`.</span></span>  <span data-ttu-id="45935-105">Die Benutzeroberfläche langsam reagiert, wenn ein Benutzer einen Bildlauf möglicherweise auch die <xref:System.Windows.Controls.TreeView> durch das Mausrad verwenden, oder ziehen das Thumb-Steuerelement eine Bildlaufleiste.</span><span class="sxs-lookup"><span data-stu-id="45935-105">The UI might also be slow to react when a user scrolls the <xref:System.Windows.Controls.TreeView> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="45935-106">Sie können die Leistung verbessern die <xref:System.Windows.Controls.TreeView> Wenn der Benutzer scrollt durch Festlegen der `VirtualizingStackPanel.VirtualizationMode` angefügte Eigenschaft zu <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="45935-106">You can improve the performance of the <xref:System.Windows.Controls.TreeView> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45935-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="45935-107">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="45935-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45935-108">Description</span></span>  
<span data-ttu-id="45935-109">Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.TreeView> festlegt, die die `VirtualizingStackPanel.IsVirtualizing` angefügte Eigenschaft auf "true" und die `VirtualizingStackPanel.VirtualizationMode` angefügte Eigenschaft zu <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> zur leistungsoptimierung.</span><span class="sxs-lookup"><span data-stu-id="45935-109">The following example creates a <xref:System.Windows.Controls.TreeView> that sets the `VirtualizingStackPanel.IsVirtualizing` attached property to true and the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to optimize its performance.</span></span>  
  
## <a name="code"></a><span data-ttu-id="45935-110">Code</span><span class="sxs-lookup"><span data-stu-id="45935-110">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 <span data-ttu-id="45935-111">Das folgende Beispiel zeigt den Daten, die im vorherigen Beispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="45935-111">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a><span data-ttu-id="45935-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45935-112">See also</span></span>
- [<span data-ttu-id="45935-113">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="45935-113">Controls</span></span>](../advanced/optimizing-performance-controls.md)
