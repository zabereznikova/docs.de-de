---
title: "Gewusst wie: Änderung der Zeilengröße mit einem GridSplitter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6621cc0048270b97c42ff4c4e646b0ddd9ca3477
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a><span data-ttu-id="90b6a-102">Gewusst wie: Änderung der Zeilengröße mit einem GridSplitter</span><span class="sxs-lookup"><span data-stu-id="90b6a-102">How to: Resize Rows with a GridSplitter</span></span>
<span data-ttu-id="90b6a-103">Dieses Beispiel zeigt, wie eine horizontale <xref:System.Windows.Controls.GridSplitter> erneut zu verteilende den Abstand zwischen den zwei Zeilen in einer <xref:System.Windows.Controls.Grid> ohne Änderung der Dimensionen des der <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="90b6a-103">This example shows how to use a horizontal <xref:System.Windows.Controls.GridSplitter> to redistribute the space between two rows in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90b6a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90b6a-104">Example</span></span>  
 <span data-ttu-id="90b6a-105">**Erstellen eines GridSplitter-Elements, das den Rand einer Zeile überlagert**</span><span class="sxs-lookup"><span data-stu-id="90b6a-105">**How to create a GridSplitter that overlays the edge of a row**</span></span>  
  
 <span data-ttu-id="90b6a-106">Angeben einer <xref:System.Windows.Controls.GridSplitter> , die Größe angrenzenden Zeilen in eine <xref:System.Windows.Controls.Grid>, legen die <xref:System.Windows.Controls.Grid.Row%2A> angefügte Eigenschaft auf eine der Zeilen, die Sie anpassen möchten.</span><span class="sxs-lookup"><span data-stu-id="90b6a-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="90b6a-107">Wenn Ihre <xref:System.Windows.Controls.Grid> verfügt über mehr als eine Spalte Festlegen der <xref:System.Windows.Controls.Grid.ColumnSpan%2A> -Eigenschaft, um die Anzahl der Spalten angeben.</span><span class="sxs-lookup"><span data-stu-id="90b6a-107">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to specify the number of columns.</span></span> <span data-ttu-id="90b6a-108">Legen Sie dann die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> auf <xref:System.Windows.VerticalAlignment.Top> oder <xref:System.Windows.VerticalAlignment.Bottom> (die Ausrichtung, die Sie festlegen, je nach den beiden Zeilen Sie anpassen möchten).</span><span class="sxs-lookup"><span data-stu-id="90b6a-108">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Top> or <xref:System.Windows.VerticalAlignment.Bottom> (which alignment you set depends on which two rows you want to resize).</span></span> <span data-ttu-id="90b6a-109">Legen Sie schließlich die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft <xref:System.Windows.HorizontalAlignment.Stretch>.</span><span class="sxs-lookup"><span data-stu-id="90b6a-109">Finally, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>.</span></span>  
  
 <span data-ttu-id="90b6a-110">Das folgende Beispiel zeigt, wie eine horizontale definiert <xref:System.Windows.Controls.GridSplitter> , die angrenzende Zeilen ändert.</span><span class="sxs-lookup"><span data-stu-id="90b6a-110">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 <span data-ttu-id="90b6a-111">Ein <xref:System.Windows.Controls.GridSplitter> beansprucht, die keinen eine eigene Zeile kann von anderen Steuerelementen im verdeckt werden die <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="90b6a-111">A <xref:System.Windows.Controls.GridSplitter> that does not occupy its own row may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="90b6a-112">Weitere Informationen zum Vermeiden dieses Problems finden Sie unter [Sicherstellen, dass ein GridSplitter sichtbar ist](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).</span><span class="sxs-lookup"><span data-stu-id="90b6a-112">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="90b6a-113">**Erstellen eines GridSplitter-Elements, das eine Zeile einnimmt**</span><span class="sxs-lookup"><span data-stu-id="90b6a-113">**How to create a GridSplitter that occupies a row**</span></span>  
  
 <span data-ttu-id="90b6a-114">Angeben einer <xref:System.Windows.Controls.GridSplitter> , die belegt einer Zeile in einer <xref:System.Windows.Controls.Grid>legen die <xref:System.Windows.Controls.Grid.Row%2A> angefügte Eigenschaft auf eine der Zeilen, die Sie anpassen möchten.</span><span class="sxs-lookup"><span data-stu-id="90b6a-114">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a row in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="90b6a-115">Wenn Ihre <xref:System.Windows.Controls.Grid> verfügt über mehr als eine Spalte Festlegen der <xref:System.Windows.Controls.Grid.ColumnSpan%2A> -Eigenschaft auf die Anzahl der Spalten.</span><span class="sxs-lookup"><span data-stu-id="90b6a-115">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to the number of columns.</span></span> <span data-ttu-id="90b6a-116">Legen Sie dann die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> auf <xref:System.Windows.VerticalAlignment.Center>, legen die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft, um <xref:System.Windows.HorizontalAlignment.Stretch>, und legen Sie die <xref:System.Windows.Controls.RowDefinition.Height%2A> der Zeile, die enthält die <xref:System.Windows.Controls.GridSplitter> auf <xref:System.Windows.GridLength.Auto%2A>.</span><span class="sxs-lookup"><span data-stu-id="90b6a-116">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>, and set the <xref:System.Windows.Controls.RowDefinition.Height%2A> of the row that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="90b6a-117">Das folgende Beispiel zeigt, wie eine horizontale definiert <xref:System.Windows.Controls.GridSplitter> , die eine Zeile einnimmt, und ändert die Größe der Zeilen auf beiden Seiten des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="90b6a-117">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that occupies a row and resizes the rows on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="90b6a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90b6a-118">See Also</span></span>  
 <xref:System.Windows.Controls.GridSplitter>  
 [<span data-ttu-id="90b6a-119">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="90b6a-119">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
