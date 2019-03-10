---
title: Übersicht über Vektorgrafiken
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
ms.openlocfilehash: a78030dd53f526e7d4403f4696ea54e881b60022
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720409"
---
# <a name="vector-graphics-overview"></a>Übersicht über Vektorgrafiken
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Zeichnet Linien, Rechtecke und andere Formen auf einem Koordinatensystem an. Sie können aus einer Vielzahl von Koordinatensysteme auswählen, aber das Standardkoordinatensystem ist des Ursprungs in der oberen linken Ecke, mit der x-Achse nach rechts und die y-Achse nach unten zeigender Pfeil zeigt. Die Maßeinheit in das Standardkoordinatensystem ist Pixel.  
  
## <a name="the-building-blocks-of-gdi"></a>Die Bausteine von GDI +  
 ![Vektorgrafik](./media/aboutgdip02-art01.gif "AboutGdip02_Art01")  
  
 Einem Computerbildschirm erstellt die Anzeige in einem rechteckigen Array von Punkten, die aufgerufen wird, Pixel. Die Anzahl der Pixel, die auf dem Bildschirm angezeigt werden, die von einem Monitor zur nächsten variiert, und die Anzahl der Pixel, die auf einem einzelnen Bildschirm angezeigt werden kann in der Regel zu einem gewissen Grad vom Benutzer konfiguriert werden.  
  
 ![Vektorgrafik](./media/aboutgdip02-art02.gif "AboutGdip02_Art02")  
  
 Bei Verwendung von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] um eine Linie, Rechteck oder in Kurve zu zeichnen, geben Sie bestimmte wichtige Informationen über das Element gezeichnet werden soll. Beispielsweise können Sie eine Zeile angeben, durch die Bereitstellung von zwei Punkten, und Sie können ein Rechteck angeben, durch die Bereitstellung von einem Punkt, eine Höhen- und eine Breite. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funktioniert in Verbindung mit dem Bildschirmtreiber um zu bestimmen, welche Pixel eingeschaltet bleiben müssen die Linie, Rechteck oder in Kurve angezeigt. Die folgende Abbildung zeigt die Pixel, die eingeschaltet sind, zu dem Punkt ("12", "8") eine Zeile aus der Punkt ("4", "2") angezeigt werden sollen.  
  
 ![Vektorgrafik](./media/aboutgdip02-art03.gif "AboutGdip02_Art03")  
  
 Im Laufe der Zeit haben sich bestimmte grundlegende Bausteine als besonders hilfreich für die Erstellung von zweidimensionaler Grafiken werden. Diese Bausteine, die alle von unterstützt werden [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], erhalten Sie in der folgenden Liste:  
  
-   Linien  
  
-   Rechtecke  
  
-   Ellipsen  
  
-   Bögen  
  
-   Polygone  
  
-   Kardinale splines  
  
-   Béziersplinekurven  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a>Methoden für das Zeichnen mit einem Graphikobjekt  
 Die <xref:System.Drawing.Graphics> -Klasse im [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet die folgenden Methoden zum Zeichnen der Elemente in der vorherigen Liste: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (für kardinale Splines), und <xref:System.Drawing.Graphics.DrawBezier%2A>. Jede dieser Methoden überladen wird. Jede Methode unterstützt, d. h. mehrere unterschiedliche Parameterlisten. Z. B. eine Variante der der <xref:System.Drawing.Graphics.DrawLine%2A> -Methode empfängt einen <xref:System.Drawing.Pen> -Objekt und vier ganzen Zahlen, während eine andere Variante der der <xref:System.Drawing.Graphics.DrawLine%2A> -Methode empfängt eine <xref:System.Drawing.Pen> Objekt und zwei <xref:System.Drawing.Point> Objekte.  
  
 Die Methoden zum Zeichnen von Linien, Rechtecke und Béziersplinekurven haben im plural Begleitmethoden, die mehrere Elemente in einem einzigen Aufruf gezeichnet: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, und <xref:System.Drawing.Graphics.DrawBeziers%2A>. Darüber hinaus die <xref:System.Drawing.Graphics.DrawCurve%2A> Methode verfügt über eine Begleitmethode, <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, zeigen Sie schließt eine Kurve durch das Verbinden des Endpunkts der Kurve ab.  
  
 Alle Zeichenmethoden der <xref:System.Drawing.Graphics> -Klasse funktionieren in Verbindung mit einem <xref:System.Drawing.Pen> Objekt. Um alles zu zeichnen, müssen Sie mindestens zwei Objekte erstellen: eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt. Die <xref:System.Drawing.Pen> Objekt speichert Attribute, z. B. Linienstärke und Farbe, der das Element gezeichnet werden soll. Die <xref:System.Drawing.Pen> Objekt als eines der Argumente an die Zeichnen-Methode übergeben wird. Z. B. eine Variante der der <xref:System.Drawing.Graphics.DrawLine%2A> -Methode empfängt einen <xref:System.Drawing.Pen> -Objekt und vier ganzen Zahlen wie im folgenden Beispiel gezeigt, die zeichnet ein Rechteck mit einer Breite von 100, eine Höhe von 50 und einen oberen linken Ecke des (20, 10):  
  
 [!code-csharp[LinesCurvesAndShapes#11](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [Linien, Kurven und Formen](lines-curves-and-shapes.md)
- [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](how-to-create-graphics-objects-for-drawing.md)
