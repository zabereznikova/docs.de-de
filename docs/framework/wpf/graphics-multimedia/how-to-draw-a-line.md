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
# <a name="how-to-draw-a-line"></a>Gewusst wie: Zeichnen einer Linie
Dieses Beispiel zeigt, wie Sie zum Zeichnen von Linien mit dem <xref:System.Windows.Shapes.Line> Element.  
  
 Um eine Linie zeichnen, erstellen Sie eine <xref:System.Windows.Shapes.Line> Element. Verwenden der <xref:System.Windows.Shapes.Line.X1%2A> und <xref:System.Windows.Shapes.Line.Y1%2A> Eigenschaften legen Sie dessen Startpunkt; und verwenden seiner <xref:System.Windows.Shapes.Line.X2%2A> und <xref:System.Windows.Shapes.Line.Y2%2A> Endpunkt festzulegenden Eigenschaften. Legen Sie schließlich die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> da eine Linie ohne einen Strich nicht sichtbar ist.  
  
 Festlegen der <xref:System.Windows.Shapes.Shape.Fill%2A> -Element für eine Zeile hat keine Auswirkungen, da eine Linie ohne innere aufweist.  
  
 Im folgende Beispiel zeichnet drei Zeilen innerhalb einer <xref:System.Windows.Controls.Canvas> Element.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Form-Elemente-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Shapes.Line>  
 [Beispiel für Form-Elemente](http://go.microsoft.com/fwlink/?LinkID=160037)
