---
title: 'Gewusst wie: Zeichnen einer geschlossener Form mithilfe des Polygon-Elements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0cf842c22238105510b13407d55c8c9773f84a70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="d4f54-102">Gewusst wie: Zeichnen einer geschlossener Form mithilfe des Polygon-Elements</span><span class="sxs-lookup"><span data-stu-id="d4f54-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="d4f54-103">Dieses Beispiel zeigt, wie eine geschlossene Form gezeichnet wird, mithilfe der <xref:System.Windows.Shapes.Polygon> Element.</span><span class="sxs-lookup"><span data-stu-id="d4f54-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="d4f54-104">Um eine geschlossene Form zu zeichnen, erstellen eine <xref:System.Windows.Shapes.Polygon> Element und verwenden seiner <xref:System.Windows.Shapes.Polygon.Points%2A> Eigenschaft, um den Scheitelpunkten einer Form anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d4f54-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="d4f54-105">Automatisch wird eine Linie gezeichnet, die die erste und letzte Punkt eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="d4f54-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="d4f54-106">Geben Sie schließlich an einen <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>, oder beides.</span><span class="sxs-lookup"><span data-stu-id="d4f54-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4f54-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d4f54-107">Example</span></span>  
 <span data-ttu-id="d4f54-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], gültiger Syntax für Punkte ist eine durch Leerzeichen getrennte Liste von Paaren von durch Trennzeichen getrennten x- und y-Koordinate.</span><span class="sxs-lookup"><span data-stu-id="d4f54-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="d4f54-109">Obwohl das Beispiel verwendet eine <xref:System.Windows.Controls.Canvas> um die Polygone enthalten, können Sie Polygon Elemente (und alle anderen Formelemente) mit allen <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> , die nicht-Text-Inhalt unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d4f54-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="d4f54-110">Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Form-Elemente-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="d4f54-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>
