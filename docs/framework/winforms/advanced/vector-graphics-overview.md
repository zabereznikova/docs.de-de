---
title: "Übersicht über Vektorgrafiken"
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
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7bb3247f531a0dac83657e118fb53ebaf708ec9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="vector-graphics-overview"></a>Übersicht über Vektorgrafiken
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]Zeichnet Linien, Rechtecke und andere Formen auf einem Koordinatensystem. Sie können aus einer Vielzahl von Koordinatensysteme auswählen, aber das Standard-Koordinatensystem verfügt über den Ursprung in der oberen linken Ecke mit der x-Achse nach rechts und die y-Achse nach unten zeigendes verweist. Die Maßeinheit in der Standard-Koordinatensystem wird das Pixel.  
  
## <a name="the-building-blocks-of-gdi"></a>Die Bausteine von GDI +  
 ![Vektorgrafik](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.gif "AboutGdip02_Art01")  
  
 Computermonitor erstellt seine Anzeige auf ein rechteckiges Array von Punkten Bildelemente oder Pixel bezeichnet. Die Anzahl der Pixel, die auf dem Bildschirm angezeigt werden, die von einem Monitor zum nächsten variiert, und die Anzahl der Pixel, die auf einem einzelnen Monitor angezeigt werden kann in der Regel zu einem gewissen Grad vom Benutzer konfiguriert werden.  
  
 ![Vektorgrafik](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.gif "AboutGdip02_Art02")  
  
 Bei Verwendung von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] um eine Linie, Rechteck oder in Kurve zu zeichnen, geben Sie bestimmte wichtige Informationen über das Element, gezeichnet werden soll. Beispielsweise können Sie eine Linie durch die Bereitstellung von zwei Punkten angeben, und können Sie durch die Bereitstellung von einem Punkt, eine Höhen- und eine Breite ein Rechtecks angeben. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]funktioniert in Verbindung mit dem Bildschirmtreiber um zu bestimmen, welche Pixel eingeschaltet bleiben müssen auf die Linie, Rechteck oder in Kurve anzeigen. Die folgende Abbildung zeigt die Pixel, die eingeschaltet sind, um eine Linie an dem Punkt (4, 2) auf den Punkt ("12", "8") anzuzeigen.  
  
 ![Vektorgrafik](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.gif "AboutGdip02_Art03")  
  
 Im Laufe der Zeit haben bestimmte grundlegenden Bausteine erwiesen besonders hilfreich für zweidimensionale Grafiken erstellen. Diese Bausteine, die alle von unterstützt werden [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], sind in der folgenden Liste angegeben:  
  
-   Linien  
  
-   Rechtecke  
  
-   Ellipsen  
  
-   Bögen  
  
-   Polygone  
  
-   Kardinale Splinekurven  
  
-   Béziersplinekurven  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a>Methoden zum Zeichnen mit einem Graphics-Objekts  
 Die <xref:System.Drawing.Graphics> -Klasse im [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet die folgenden Methoden zum Zeichnen der Elemente in der vorherigen Liste: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (bei kardinale Splines) und <xref:System.Drawing.Graphics.DrawBezier%2A>. Jede dieser Methoden ist überladen wird. Jede Methode unterstützt, also mehrere unterschiedliche Parameterlisten. Z. B. eine Variation des der <xref:System.Drawing.Graphics.DrawLine%2A> Methode empfängt einen <xref:System.Drawing.Pen> Objekt und vier ganzen Zahlen, während eine andere Variante der der <xref:System.Drawing.Graphics.DrawLine%2A> Methode empfängt eine <xref:System.Drawing.Pen> Objekt und zwei <xref:System.Drawing.Point> Objekte.  
  
 Die Methoden zum Zeichnen von Linien, Rechtecke und Bézier-Splines verfügen im plural Begleitmethoden, die mehrere Elemente in einem einzigen Aufruf abgerufen: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, und <xref:System.Drawing.Graphics.DrawBeziers%2A>. Darüber hinaus die <xref:System.Drawing.Graphics.DrawCurve%2A> Methode verfügt über eine Methode Companion <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, zeigen Sie geschlossen wird, wird eine Kurve durch Herstellen einer Verbindung den Endpunkt der Kurve ab.  
  
 Alle Methoden von zeichnen die <xref:System.Drawing.Graphics> -Klasse funktionieren in Verbindung mit einer <xref:System.Drawing.Pen> Objekt. Zum Zeichnen, müssen Sie mindestens zwei Objekte erstellen: eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt. Die <xref:System.Drawing.Pen> Objekt speichert Attribute, z. B. Breite und Farbe des Elements, gezeichnet werden soll. Die <xref:System.Drawing.Pen> Objekt als eines der Argumente an die Zeichnen-Methode übergeben wird. Z. B. eine Variation des der <xref:System.Drawing.Graphics.DrawLine%2A> Methode empfängt einen <xref:System.Drawing.Pen> Objekt und vier ganzen Zahlen wie im folgenden Beispiel gezeigt wird, die mit einer Breite von 100, eine Höhe von 50 und einen oberen linken Ecke des Rechtecks zeichnet (20, 10):  
  
 [!code-csharp[LinesCurvesAndShapes#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
