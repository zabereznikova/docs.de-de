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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153438"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a><span data-ttu-id="a37d2-102">Vorgehensweise: Verbessern der Leistung eines TreeView-Objekts</span><span class="sxs-lookup"><span data-stu-id="a37d2-102">How to: Improve the Performance of a TreeView</span></span>
<span data-ttu-id="a37d2-103">Wenn eine <xref:System.Windows.Controls.TreeView> viele Elemente enthält, die Zeitspanne, die zum Laden benötigt möglicherweise eine erhebliche Verzögerung eintreten, in der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="a37d2-103">If a <xref:System.Windows.Controls.TreeView> contains many items, the amount of time it takes to load may cause a significant delay in the user interface.</span></span> <span data-ttu-id="a37d2-104">Sie können die Ladezeit verbessern, indem Sie die Einstellung der `VirtualizingStackPanel.IsVirtualizing` angefügte Eigenschaft zu `true`.</span><span class="sxs-lookup"><span data-stu-id="a37d2-104">You can improve the load time by setting the `VirtualizingStackPanel.IsVirtualizing` attached property to `true`.</span></span>  <span data-ttu-id="a37d2-105">Die Benutzeroberfläche langsam reagiert, wenn ein Benutzer einen Bildlauf möglicherweise auch die <xref:System.Windows.Controls.TreeView> durch das Mausrad verwenden, oder ziehen das Thumb-Steuerelement eine Bildlaufleiste.</span><span class="sxs-lookup"><span data-stu-id="a37d2-105">The UI might also be slow to react when a user scrolls the <xref:System.Windows.Controls.TreeView> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="a37d2-106">Sie können die Leistung verbessern die <xref:System.Windows.Controls.TreeView> Wenn der Benutzer scrollt durch Festlegen der `VirtualizingStackPanel.VirtualizationMode` angefügte Eigenschaft zu <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a37d2-106">You can improve the performance of the <xref:System.Windows.Controls.TreeView> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a37d2-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a37d2-107">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="a37d2-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a37d2-108">Description</span></span>  
<span data-ttu-id="a37d2-109">Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.TreeView> festlegt, die die `VirtualizingStackPanel.IsVirtualizing` angefügte Eigenschaft auf "true" und die `VirtualizingStackPanel.VirtualizationMode` angefügte Eigenschaft zu <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> zur leistungsoptimierung.</span><span class="sxs-lookup"><span data-stu-id="a37d2-109">The following example creates a <xref:System.Windows.Controls.TreeView> that sets the `VirtualizingStackPanel.IsVirtualizing` attached property to true and the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to optimize its performance.</span></span>  
  
## <a name="code"></a><span data-ttu-id="a37d2-110">Code</span><span class="sxs-lookup"><span data-stu-id="a37d2-110">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 <span data-ttu-id="a37d2-111">Das folgende Beispiel zeigt den Daten, die im vorherigen Beispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="a37d2-111">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a><span data-ttu-id="a37d2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a37d2-112">See also</span></span>

- [<span data-ttu-id="a37d2-113">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="a37d2-113">Controls</span></span>](../advanced/optimizing-performance-controls.md)
