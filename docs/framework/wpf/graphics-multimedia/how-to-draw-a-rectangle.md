---
title: 'Gewusst wie: Zeichnen eines Rechtecks'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c163897af27c9b34c8cd87a3b197047f86d21ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-rectangle"></a><span data-ttu-id="485d8-102">Gewusst wie: Zeichnen eines Rechtecks</span><span class="sxs-lookup"><span data-stu-id="485d8-102">How to: Draw a Rectangle</span></span>
<span data-ttu-id="485d8-103">Dieses Beispiel zeigt, wie Sie ein Rechteck mit dem <xref:System.Windows.Shapes.Rectangle> Element.</span><span class="sxs-lookup"><span data-stu-id="485d8-103">This example shows how to draw a rectangle by using the <xref:System.Windows.Shapes.Rectangle> element.</span></span>  
  
 <span data-ttu-id="485d8-104">Erstellen Sie ein Rechteck, ein <xref:System.Windows.Shapes.Rectangle> Element, und geben Sie ihre <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="485d8-104">To draw a rectangle, create a <xref:System.Windows.Shapes.Rectangle> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="485d8-105">Um innerhalb des Rechtecks zeichnen, legen Sie dessen <xref:System.Windows.Shapes.Shape.Fill%2A>.</span><span class="sxs-lookup"><span data-stu-id="485d8-105">To paint the inside of the rectangle, set its <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="485d8-106">Um dem Rechteck eine Gliederung gewähren, verwenden Sie die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="485d8-106">To give the rectangle an outline, use its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties.</span></span>  
  
 <span data-ttu-id="485d8-107">So erteilen Sie das Rechteck abgerundete Ecken, geben Sie den optionalen <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> und <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="485d8-107">To give the rectangle rounded corners, specify the optional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="485d8-108">Die <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> und <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> Eigenschaften festlegen, die x- und y-Achse Radien der Ellipse, der zum Abrunden der Ecken des Rechtecks verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="485d8-108">The <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties set the x-axis and y-axis radii of the ellipse that is used to round the corners of the rectangle.</span></span>  
  
 <span data-ttu-id="485d8-109">Im folgenden Beispiel zwei <xref:System.Windows.Shapes.Rectangle> Elemente werden in gezeichnet eine <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="485d8-109">In the following example, two <xref:System.Windows.Shapes.Rectangle> elements are drawn in a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="485d8-110">Die erste Rechteck verfügt über eine <xref:System.Windows.Media.Brushes.Blue%2A> inneren.</span><span class="sxs-lookup"><span data-stu-id="485d8-110">The first rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior.</span></span> <span data-ttu-id="485d8-111">Das zweite Rechteck hat eine <xref:System.Windows.Media.Brushes.Blue%2A> inneren, eine <xref:System.Windows.Media.Brushes.Black%2A> Gliederung und abgerundete Ecken.</span><span class="sxs-lookup"><span data-stu-id="485d8-111">The second rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior, a <xref:System.Windows.Media.Brushes.Black%2A> outline, and rounded corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="485d8-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="485d8-112">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 <span data-ttu-id="485d8-113">Obwohl in diesem Beispiel verwendet eine <xref:System.Windows.Controls.Canvas> Rechtecke enthalten, können Sie Rechteck Elemente (und alle anderen Formelemente) mit einem <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> , die nicht-Text-Inhalt unterstützt.</span><span class="sxs-lookup"><span data-stu-id="485d8-113">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the rectangles, you can use rectangle elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span> <span data-ttu-id="485d8-114">In der Tat Rechtecke sind besonders nützlich für das Bereitstellen von Hintergründe für Teile der <xref:System.Windows.Controls.Grid> Bereiche.</span><span class="sxs-lookup"><span data-stu-id="485d8-114">In fact, rectangles are particularly useful for providing backgrounds for portions of <xref:System.Windows.Controls.Grid> panels.</span></span> <span data-ttu-id="485d8-115">Ein Beispiel finden Sie die [Table Overview](../../../../docs/framework/wpf/advanced/table-overview.md).</span><span class="sxs-lookup"><span data-stu-id="485d8-115">For an example, see the [Table Overview](../../../../docs/framework/wpf/advanced/table-overview.md).</span></span>  
  
 <span data-ttu-id="485d8-116">Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Form-Elemente-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="485d8-116">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="485d8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="485d8-117">See Also</span></span>  
 <xref:System.Windows.Shapes.Rectangle>  
 [<span data-ttu-id="485d8-118">Beispiel für Form-Elemente</span><span class="sxs-lookup"><span data-stu-id="485d8-118">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [<span data-ttu-id="485d8-119">Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF</span><span class="sxs-lookup"><span data-stu-id="485d8-119">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [<span data-ttu-id="485d8-120">Übersicht über Tabellen</span><span class="sxs-lookup"><span data-stu-id="485d8-120">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
