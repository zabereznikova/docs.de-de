---
title: Polygone in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
ms.openlocfilehash: 3ac6b9b651e65a45612cf2bd8ff17990c5cfba0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525846"
---
# <a name="polygons-in-gdi"></a>Polygone in GDI+
Ein Polygon ist eine geschlossene Form mit drei oder mehr geraden Seiten. Z. B. einem Dreieck ist ein Polygon mit drei Seiten ein Rechteck ist ein Polygon mit vier Seiten und ein Fünfeck ist ein Polygon mit fünf Seiten. Die folgende Abbildung zeigt verschiedene Polygone.  
  
 ![Polygone](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")  
  
## <a name="drawing-a-polygon"></a>Zeichnen eines Polygons  
 Um ein Polygon zu zeichnen, müssen Sie eine <xref:System.Drawing.Graphics> -Objekt, eine <xref:System.Drawing.Pen> Objekt und ein Array von <xref:System.Drawing.Point> (oder <xref:System.Drawing.PointF>) Objekte. Die <xref:System.Drawing.Graphics> Objekt enthält die <xref:System.Drawing.Graphics.DrawPolygon%2A> Methode. Die <xref:System.Drawing.Pen> Objekt speichert Attribute, z. B. Breite und Farbe der Linie verwendet, um das Polygon, und das Array von Rendern <xref:System.Drawing.Point> -Objekte speichert die Punkte durch gerade Linien verbunden werden soll. Die <xref:System.Drawing.Pen> Objekt und das Array von <xref:System.Drawing.Point> Objekte werden als Argumente übergeben der <xref:System.Drawing.Graphics.DrawPolygon%2A> Methode. Im folgende Beispiel zeichnet ein Vieleck, drei Seiten. Beachten Sie, dass nur drei Punkten in `myPointArray`: (0, 0), (50, 30) und (30, 60). Die <xref:System.Drawing.Graphics.DrawPolygon%2A> Methode schließt automatisch das Polygon durch eine Linie von (30, 60) zurück zum Anfangspunkt (0, 0).  
  
 [!code-csharp[LinesCurvesAndShapes#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 Die folgende Abbildung zeigt das Polygon.  
  
 ![Polygon](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Gewusst wie: Erstellen eines Stifts](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
