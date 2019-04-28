---
title: Ellipsen und Bögen in GDI+
ms.date: 03/30/2017
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
ms.openlocfilehash: 8bbc2eda6450128eac55576259880e83f07099ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756637"
---
# <a name="ellipses-and-arcs-in-gdi"></a>Ellipsen und Bögen in GDI+
Sie können problemlos zeichnen, Ellipsen und Bögen mithilfe der <xref:System.Drawing.Graphics.DrawEllipse%2A> und <xref:System.Drawing.Graphics.DrawArc%2A> Methoden der <xref:System.Drawing.Graphics> Klasse.  
  
## <a name="drawing-an-ellipse"></a>Zeichnen einer Ellipse  
 Um eine Ellipse Zeichnen zu können, benötigen Sie eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt. Die <xref:System.Drawing.Graphics> -Objekt ermöglicht die <xref:System.Drawing.Graphics.DrawEllipse%2A> -Methode, und die <xref:System.Drawing.Pen> -Objekt speichert Attribute, z. B. Breite und Farbe der Linie verwendet, um die Ellipse zu rendern. Die <xref:System.Drawing.Pen> Objekt als eines der Argumente zum Übergeben der <xref:System.Drawing.Graphics.DrawEllipse%2A> Methode. Die übrigen Argumente übergeben werden, um die <xref:System.Drawing.Graphics.DrawEllipse%2A> Methode geben Sie das umschließende Rechteck für die Ellipse. Die folgende Abbildung zeigt eine Ellipse zusammen mit seinem umschließenden Rechteck.  
  
 ![Ellipsen und Bögen](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")  
  
 Im folgende Beispiel zeichnet eine Ellipse; das umschließende Rechteck hat eine Breite von 80 und eine Höhe von 40 und einen oberen linken Ecke von (100, 50):  
  
 [!code-csharp[LinesCurvesAndShapes#51](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <xref:System.Drawing.Graphics.DrawEllipse%2A> ist eine überladene Methode, der die <xref:System.Drawing.Graphics> Klasse, damit es mehrere Möglichkeiten gibt, können Sie es mit Argumenten angeben. Sie können z. B. Erstellen einer <xref:System.Drawing.Rectangle> und übergeben Sie die <xref:System.Drawing.Rectangle> auf die <xref:System.Drawing.Graphics.DrawEllipse%2A> Methode als Argument:  
  
 [!code-csharp[LinesCurvesAndShapes#52](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a>Zeichnen einen Bogen  
 Ein Bogen ist ein Teil einer Ellipse an. Um einen Bogen zu zeichnen, rufen Sie die <xref:System.Drawing.Graphics.DrawArc%2A> Methode der <xref:System.Drawing.Graphics> Klasse. Die Parameter der <xref:System.Drawing.Graphics.DrawArc%2A> Methode sind identisch mit den Parametern der der <xref:System.Drawing.Graphics.DrawEllipse%2A> -Methode, außer dass <xref:System.Drawing.Graphics.DrawArc%2A> erfordert einen Startwinkel und mittelpunktswinkel. Das folgende Beispiel zeichnet einen Bogen mit einem Startwinkel von 30 Grad und bei einem mittelpunktswinkel von 180 Grad:  
  
 [!code-csharp[LinesCurvesAndShapes#53](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 Die folgende Abbildung zeigt den Bogen mit Strichen, das die Ellipse und das umgebende Rechteck.  
  
 ![Ellipsen und Bögen](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [Linien, Kurven und Formen](lines-curves-and-shapes.md)
- [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](how-to-create-graphics-objects-for-drawing.md)
- [Vorgehensweise: Erstellen eines Stifts](how-to-create-a-pen.md)
- [Vorgehensweise: Zeichnen der Kontur eine Form](how-to-draw-an-outlined-shape.md)
