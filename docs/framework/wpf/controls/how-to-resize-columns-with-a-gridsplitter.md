---
title: "Gewusst wie: Änderung der Spaltengröße mit einem GridSplitter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5c8299a3f4885618601c8087a61c21dc5d989813
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a><span data-ttu-id="d37d1-102">Gewusst wie: Änderung der Spaltengröße mit einem GridSplitter</span><span class="sxs-lookup"><span data-stu-id="d37d1-102">How to: Resize Columns with a GridSplitter</span></span>
<span data-ttu-id="d37d1-103">In diesem Beispiel wird gezeigt, wie zum Erstellen einer vertikales <xref:System.Windows.Controls.GridSplitter> zum Verteilen des Abstand zwischen zwei Spalten in einem <xref:System.Windows.Controls.Grid> ohne Änderung der Dimensionen des der <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="d37d1-103">This example shows how to create a vertical <xref:System.Windows.Controls.GridSplitter> in order to redistribute the space between two columns in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d37d1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d37d1-104">Example</span></span>  
 <span data-ttu-id="d37d1-105">**Erstellen eines GridSplitter-Elements, das den Rand einer Spalte überlagert**</span><span class="sxs-lookup"><span data-stu-id="d37d1-105">**How to create a GridSplitter that overlays the edge of a column**</span></span>  
  
 <span data-ttu-id="d37d1-106">Angeben einer <xref:System.Windows.Controls.GridSplitter> , die Größe der angrenzenden Spalten in einer <xref:System.Windows.Controls.Grid>legen die <xref:System.Windows.Controls.Grid.Column%2A> angefügte Eigenschaft auf eine der Spalten, die Sie anpassen möchten.</span><span class="sxs-lookup"><span data-stu-id="d37d1-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent columns in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="d37d1-107">Wenn Ihre <xref:System.Windows.Controls.Grid> verfügt über mehr als eine Zeile legen Sie die <xref:System.Windows.Controls.Grid.RowSpan%2A> -Eigenschaft, um die Anzahl der Zeilen.</span><span class="sxs-lookup"><span data-stu-id="d37d1-107">If your <xref:System.Windows.Controls.Grid> has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="d37d1-108">Legen Sie dann die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft <xref:System.Windows.HorizontalAlignment.Left> oder <xref:System.Windows.HorizontalAlignment.Right> (die Ausrichtung, die Sie festlegen, je nach den zwei Spalten Sie anpassen möchten).</span><span class="sxs-lookup"><span data-stu-id="d37d1-108">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Left> or <xref:System.Windows.HorizontalAlignment.Right> (which alignment you set depends on which two columns you want to resize).</span></span> <span data-ttu-id="d37d1-109">Legen Sie schließlich die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaft <xref:System.Windows.VerticalAlignment.Stretch>.</span><span class="sxs-lookup"><span data-stu-id="d37d1-109">Finally, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 <span data-ttu-id="d37d1-110">Ein <xref:System.Windows.Controls.GridSplitter> , die keine eigene Spalte möglicherweise von anderen Steuerelementen im verdeckt werden die <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="d37d1-110">A <xref:System.Windows.Controls.GridSplitter> that does not have its own column may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="d37d1-111">Weitere Informationen zum Vermeiden dieses Problems finden Sie unter [Sicherstellen, dass ein GridSplitter sichtbar ist](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).</span><span class="sxs-lookup"><span data-stu-id="d37d1-111">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="d37d1-112">**Erstellen eines GridSplitter-Elements, das eine Spalte einnimmt**</span><span class="sxs-lookup"><span data-stu-id="d37d1-112">**How to create a GridSplitter that occupies a column**</span></span>  
  
 <span data-ttu-id="d37d1-113">Angeben einer <xref:System.Windows.Controls.GridSplitter> , die belegt, dass einer Spalteninhalts in einer <xref:System.Windows.Controls.Grid>legen die <xref:System.Windows.Controls.Grid.Column%2A> angefügte Eigenschaft auf eine der Spalten, die Sie anpassen möchten.</span><span class="sxs-lookup"><span data-stu-id="d37d1-113">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a column in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="d37d1-114">Wenn das Raster mehrere Zeilen verfügt, legen Sie die <xref:System.Windows.Controls.Grid.RowSpan%2A> -Eigenschaft, um die Anzahl der Zeilen.</span><span class="sxs-lookup"><span data-stu-id="d37d1-114">If your Grid has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="d37d1-115">Legen Sie dann die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> auf <xref:System.Windows.HorizontalAlignment.Center>, legen die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaft, um <xref:System.Windows.VerticalAlignment.Stretch>, und legen Sie die <xref:System.Windows.Controls.ColumnDefinition.Width%2A> der Spalte, die enthält die <xref:System.Windows.Controls.GridSplitter> auf <xref:System.Windows.GridLength.Auto%2A>.</span><span class="sxs-lookup"><span data-stu-id="d37d1-115">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> to <xref:System.Windows.HorizontalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>, and set the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of the column that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="d37d1-116">Das folgende Beispiel zeigt, wie eine vertikalen definiert <xref:System.Windows.Controls.GridSplitter> , die eine Spalte einnimmt, und ändert die Größe der Spalten auf beiden Seiten des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="d37d1-116">The following example shows how to define a vertical <xref:System.Windows.Controls.GridSplitter> that occupies a column and resizes the columns on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="d37d1-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d37d1-117">See Also</span></span>  
 <xref:System.Windows.Controls.GridSplitter>  
 [<span data-ttu-id="d37d1-118">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="d37d1-118">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
