---
title: 'Gewusst wie: Zeichnen einer Linie'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4911aea91416fb84e9a18d54c145b494737ef9dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="a045a-102">Gewusst wie: Zeichnen einer Linie</span><span class="sxs-lookup"><span data-stu-id="a045a-102">How to: Draw a Line</span></span>
<span data-ttu-id="a045a-103">Dieses Beispiel zeigt, wie Sie zum Zeichnen von Linien mit dem <xref:System.Windows.Shapes.Line> Element.</span><span class="sxs-lookup"><span data-stu-id="a045a-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="a045a-104">Um eine Linie zeichnen, erstellen Sie eine <xref:System.Windows.Shapes.Line> Element.</span><span class="sxs-lookup"><span data-stu-id="a045a-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="a045a-105">Verwenden der <xref:System.Windows.Shapes.Line.X1%2A> und <xref:System.Windows.Shapes.Line.Y1%2A> Eigenschaften legen Sie dessen Startpunkt; und verwenden seiner <xref:System.Windows.Shapes.Line.X2%2A> und <xref:System.Windows.Shapes.Line.Y2%2A> Endpunkt festzulegenden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a045a-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="a045a-106">Legen Sie schließlich die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> da eine Linie ohne einen Strich nicht sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="a045a-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="a045a-107">Festlegen der <xref:System.Windows.Shapes.Shape.Fill%2A> -Element für eine Zeile hat keine Auswirkungen, da eine Linie ohne innere aufweist.</span><span class="sxs-lookup"><span data-stu-id="a045a-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="a045a-108">Im folgende Beispiel zeichnet drei Zeilen innerhalb einer <xref:System.Windows.Controls.Canvas> Element.</span><span class="sxs-lookup"><span data-stu-id="a045a-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a045a-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a045a-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="a045a-110">Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Form-Elemente-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="a045a-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a045a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a045a-111">See Also</span></span>  
 <xref:System.Windows.Shapes.Line>  
 [<span data-ttu-id="a045a-112">Beispiel für Form-Elemente</span><span class="sxs-lookup"><span data-stu-id="a045a-112">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)
