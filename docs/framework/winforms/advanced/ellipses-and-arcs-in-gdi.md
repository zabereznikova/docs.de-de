---
title: "Ellipsen und Bögen in GDI+"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71126942f4cde37cc5d26bfba029c5f50f1065a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ellipses-and-arcs-in-gdi"></a>Ellipsen und Bögen in GDI+
Sie können problemlos zeichnen Ellipsen und Bögen mit der <xref:System.Drawing.Graphics.DrawEllipse%2A> und <xref:System.Drawing.Graphics.DrawArc%2A> Methoden die <xref:System.Drawing.Graphics> Klasse.  
  
## <a name="drawing-an-ellipse"></a>Zeichnen einer Ellipse  
 Um eine Ellipse zu zeichnen, müssen Sie eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt. Die <xref:System.Drawing.Graphics> Objekt enthält die <xref:System.Drawing.Graphics.DrawEllipse%2A> -Methode, und die <xref:System.Drawing.Pen> Objekt speichert Attribute, z. B. Breite und Farbe der Linie, die zum Rendern der Ellipse verwendet. Die <xref:System.Drawing.Pen> Objekt als eines der Argumente zu übergeben der <xref:System.Drawing.Graphics.DrawEllipse%2A> Methode. Die übrigen Argumente zu übergeben, um die <xref:System.Drawing.Graphics.DrawEllipse%2A> Methode geben Sie das umschließende Rechteck für die Ellipse. Die folgende Abbildung zeigt eine Ellipse, die zusammen mit das umschließende Rechteck.  
  
 ![Ellipsen und Bögen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")  
  
 Im folgende Beispiel zeichnet eine Ellipse; das umschließende Rechteck hat eine Breite von 80, eine Höhe von 40 und einen oberen linken Ecke des (100, 50):  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <xref:System.Drawing.Graphics.DrawEllipse%2A>eine überladene Methode wird die <xref:System.Drawing.Graphics> Klasse, damit es gibt mehrere Möglichkeiten, die Sie Argumente angeben können. Sie können z. B. Erstellen einer <xref:System.Drawing.Rectangle> und übergeben Sie der <xref:System.Drawing.Rectangle> zu der <xref:System.Drawing.Graphics.DrawEllipse%2A> Methode als Argument:  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a>Zeichnen eines Bogens  
 Ein Bogen ist ein Teil einer Ellipse. Um einen Bogen zu zeichnen, rufen Sie die <xref:System.Drawing.Graphics.DrawArc%2A> Methode der <xref:System.Drawing.Graphics> Klasse. Die Parameter von der <xref:System.Drawing.Graphics.DrawArc%2A> Methode sind identisch mit den Parametern des der <xref:System.Drawing.Graphics.DrawEllipse%2A> -Methode, außer dass <xref:System.Drawing.Graphics.DrawArc%2A> erfordert eine Startwinkel und mittelpunktswinkel. Im folgende Beispiel zeichnet einen Bogen mit einem Startwinkel von 30 Grad und bei einem mittelpunktswinkel von 180 Grad:  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 Die folgende Abbildung zeigt den Bogen, das die Ellipse und das umschließende Rechteck.  
  
 ![Ellipsen und Bögen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Gewusst wie: Erstellen eines Stifts](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [Gewusst wie: Zeichnen der Kontur einer Form](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
