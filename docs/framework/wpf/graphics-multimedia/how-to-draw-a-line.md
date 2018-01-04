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
ms.workload: dotnet
ms.openlocfilehash: 88d667e8654f72226dc609a14aec650effe2d5c8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="e0655-102">Gewusst wie: Zeichnen einer Linie</span><span class="sxs-lookup"><span data-stu-id="e0655-102">How to: Draw a Line</span></span>
<span data-ttu-id="e0655-103">Dieses Beispiel zeigt, wie Sie zum Zeichnen von Linien mit dem <xref:System.Windows.Shapes.Line> Element.</span><span class="sxs-lookup"><span data-stu-id="e0655-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="e0655-104">Um eine Linie zeichnen, erstellen Sie eine <xref:System.Windows.Shapes.Line> Element.</span><span class="sxs-lookup"><span data-stu-id="e0655-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="e0655-105">Verwenden der <xref:System.Windows.Shapes.Line.X1%2A> und <xref:System.Windows.Shapes.Line.Y1%2A> Eigenschaften legen Sie dessen Startpunkt; und verwenden seiner <xref:System.Windows.Shapes.Line.X2%2A> und <xref:System.Windows.Shapes.Line.Y2%2A> Endpunkt festzulegenden Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="e0655-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="e0655-106">Legen Sie schließlich die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> da eine Linie ohne einen Strich nicht sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="e0655-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="e0655-107">Festlegen der <xref:System.Windows.Shapes.Shape.Fill%2A> -Element für eine Zeile hat keine Auswirkungen, da eine Linie ohne innere aufweist.</span><span class="sxs-lookup"><span data-stu-id="e0655-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="e0655-108">Im folgende Beispiel zeichnet drei Zeilen innerhalb einer <xref:System.Windows.Controls.Canvas> Element.</span><span class="sxs-lookup"><span data-stu-id="e0655-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0655-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0655-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="e0655-110">Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Form-Elemente-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="e0655-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0655-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0655-111">See Also</span></span>  
 <xref:System.Windows.Shapes.Line>  
 [<span data-ttu-id="e0655-112">Beispiel für Form-Elemente</span><span class="sxs-lookup"><span data-stu-id="e0655-112">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)
