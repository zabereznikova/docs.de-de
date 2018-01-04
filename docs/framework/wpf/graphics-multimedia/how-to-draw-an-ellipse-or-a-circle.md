---
title: 'Gewusst wie: Zeichnen einer Ellipse oder eines Kreises'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f03fd8cea706e2927ed8e14b4f89a94a208e266
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>Gewusst wie: Zeichnen einer Ellipse oder eines Kreises
In diesem Beispiel wird gezeigt, wie zum Zeichnen von Ellipsen und Kreise mithilfe der <xref:System.Windows.Shapes.Ellipse> Element. Erstellen Sie zum Zeichnen einer Ellipse, die eine <xref:System.Windows.Shapes.Ellipse> Element, und geben Sie ihre <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A>. Verwenden der <xref:System.Windows.Shapes.Shape.Fill%2A> -Eigenschaft an die <xref:System.Windows.Media.Brush> , wird verwendet, um das Innere der Ellipse gezeichnet. Verwenden der <xref:System.Windows.Shapes.Shape.Stroke%2A> -Eigenschaft an die <xref:System.Windows.Media.Brush> , die zum Zeichnen der Umrisslinie der Ellipse verwendet wird. Die <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaft gibt die Stärke der Kontur Ellipse.  
  
 Zeichnen eines Kreises stellen die <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> von der <xref:System.Windows.Shapes.Ellipse> Element gleich sind.  
  
 Im folgende Beispiel zeichnet vier <xref:System.Windows.Shapes.Ellipse> Elemente innerhalb einer <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Obwohl in diesem Beispiel verwendet eine <xref:System.Windows.Controls.Canvas> um die Auslassungspunkte enthalten, können Sie Ellipse Elemente (und alle anderen Formelemente) mit allen <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> , die nicht-Text-Inhalt unterstützt.  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Form-Elemente-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Shapes.Ellipse>  
 <xref:System.Windows.Shapes.Shape>  
 [Beispiel für Form-Elemente](http://go.microsoft.com/fwlink/?LinkID=160037)
