---
title: 'Gewusst wie: Zeichnen von kardinalen Splines'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 3ad06eb28e1d8e6b5d5f4a77e545f174d8a68d9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-cardinal-splines"></a>Gewusst wie: Zeichnen von kardinalen Splines
Eine cardinal-Splinekurve ist eine Kurve, die einen bestimmten Satz von Punkten gleichmäßig zu durchlaufen. Um eine cardinal-Splinekurve zu zeichnen, erstellen Sie eine <xref:System.Drawing.Graphics> Objekts und übergeben Sie die Adresse des ein Array von Punkten um die <xref:System.Drawing.Graphics.DrawCurve%2A> Methode.  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a>Zeichnen eines Bell geformten kardinalen Splines  
  
-   Im folgende Beispiel zeichnet eine Bell geformten cardinal-Splinekurve, die fünf festgelegten Punkt durchlaufen. Die folgende Abbildung zeigt die Kurve und fünf Punkte.  
  
     ![Kardinaler Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a>Zeichnen eines geschlossenen kardinalen Splines  
  
-   Verwenden der <xref:System.Drawing.Graphics.DrawClosedCurve%2A> Methode der <xref:System.Drawing.Graphics> Klasse eine geschlossene cardinal-Splinekurve gezeichnet werden soll. In einer geschlossenen cardinal-Splinekurve die Kurve wird fortgesetzt, bis der letzte Punkt im Array und eine Verbindung herstellt, mit dem ersten Punkt im Array. Im folgende Beispiel zeichnet eine geschlossene cardinal-Splinekurve, die sechs festgelegten Punkt durchlaufen. Die folgende Abbildung zeigt die geschlossene Splinekurve zusammen mit den sechs Punkten.  
  
 ![Kardinaler Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a>Ändern der Krümmung eines kardinalen Splines  
  
-   Ändern Sie die Möglichkeit, eine cardinal-Splinekurve durch Übergeben eines Arguments Spannung, Kurven, die <xref:System.Drawing.Graphics.DrawCurve%2A> Methode. Im folgende Beispiel werden drei kardinale Splines, die den gleichen Satz von Punkten durchlaufen gezeichnet. Die folgende Abbildung zeigt die drei Splines zusammen mit ihren Spannungswerten. Beachten Sie, dass bei die Spannung 0 ist, die Punkte durch gerade Linien verbunden sind.  
  
 ![Kardinaler Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Siehe vorstehende Beispiele sind für die Verwendung mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch  
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Erstellen und Zeichnen von Kurven](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
