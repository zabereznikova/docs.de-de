---
title: Kardinale Splines in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], cardinal
- GDI+, cardinal splines
- cardinal splines
ms.assetid: 09b3797a-6294-422d-9adf-a5a0a7695c0c
ms.openlocfilehash: f7d04f59e2424b71eb5bd0015f9496e6e67edbfa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589531"
---
# <a name="cardinal-splines-in-gdi"></a>Kardinale Splines in GDI+
Eine cardinal-Splinekurve ist eine Sequenz von einzelnen Kurven, um eine größere Kurve zu bilden. Die Spline wird durch ein Array von Punkten und Spannungsparameter angegeben. Eine cardinal-Splinekurve durchläuft reibungslos jeder Punkt im Array ab; Es gibt keine Ecken und keine abrupten Änderungen in die Dichtigkeit der Kurve. Die folgende Abbildung zeigt eine Reihe von Punkten und eine cardinal-Splinekurve, die jeden Punkt in der Gruppe durchläuft.  
  
 ![Kardinaler Spline](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art09.gif "Aboutgdip02_art09")  
  
## <a name="physical-and-mathematical-splines"></a>Physische und mathematische Splines  
 Ein physischer Spline ist eine schlanke Stück Holz oder anderen Materialien flexibel. Vor der Einführung von mathematischen Splines verwendet die Designer physischen Splines zum Zeichnen von Kurven. Ein Designer würde die Splinekurve auf ein Blatt Papier platzieren und Verankern sie die Anmerkung an eine bestimmte Anzahl von Punkten. Der Designer konnte klicken Sie dann eine Kurve durch Zeichnen entlang des Splines mit einem Stift oder einem ähnlichen erstellen. Ein bestimmter Satz von Punkten kann es sich um eine Vielzahl von Kurven, abhängig von den Eigenschaften des physischen Splines ergeben. Beispielsweise ergibt eine Splinekurve, die Anzahl von Krümmungen mit einem hohen eine andere Kurve als eine äußerst flexible Spline.  
  
 Die Formeln für mathematische Splines basieren auf den Eigenschaften des biegsamen, sodass die mathematische Splines erzeugten Kurven, die der Kurven ähneln, die von physischen Splines einmal erstellt wurden. Genau wie physische Splines von verschiedenen Spannung verschiedene Kurven, die über einen bestimmten Satz von Punkten erstellt, erzeugt mathematische Splines mit unterschiedlichen Werten für die Spannungsparameter über einen bestimmten Satz von Punkten Kurven. Die folgende Abbildung zeigt vier kardinale Splinekurven übergeben, die über den gleichen Satz von Punkten. Die Spannung wird für jeden Spline angezeigt. Eine Spannung von 0 entspricht unendlichen physikalischen-Spannung die Kurve der schnellste Weg (gerade Linien), die zwischen Punkten zu erzwingen. Spannung 1 entspricht keine physischen Spannung, Splines den Pfad der Krümmung des am wenigsten insgesamt zu ermöglichen. Verhält sich die Kurve mit Spannung Werte größer als 1 wie eine, einen längeren Pfad wird mithilfe von Push übertragen.  
  
 ![Kardinale Splines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art10.gif "Aboutgdip02_art10")  
  
 Die vier Splines in der vorherigen Abbildung teilen die gleiche Tangente am Startpunkt. Der Tangens ist der Zeile, die aus den Anfangspunkt des nächsten Punkts entlang der Kurve gezeichnet. Ebenso ist die freigegebene Tangente an den Endpunkt der Zeile, die vom Endpunkt bis zum vorherigen Punkt auf der Kurve gezeichnet.  
  
 Um eine cardinal-Splinekurve Zeichnen zu können, benötigen Sie eine Instanz von der <xref:System.Drawing.Graphics> -Klasse, eine <xref:System.Drawing.Pen>, und ein Array von <xref:System.Drawing.Point> Objekte von der Instanz von der <xref:System.Drawing.Graphics> -Klasse stellt die <xref:System.Drawing.Graphics.DrawCurve%2A> -Methode, die die Splinekurve verwendet und die <xref:System.Drawing.Pen> speichert Attribute für die Spline an, wie z. B. Linienstärke und Farbe. Das Array von <xref:System.Drawing.Point> -Objekte speichert, die Punkte, die die Kurve weitergeleitet werden. Im folgenden Codebeispiel wird veranschaulicht, wie eine cardinal-Splinekurve, die durch Punkte verläuft, zeichnen `myPointArray`. Der dritte Parameter ist die Spannung an.  
  
 [!code-csharp[LinesCurvesAndShapes#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#31)]
 [!code-vb[LinesCurvesAndShapes#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Siehe auch
- [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [Erstellen und Zeichnen von Kurven](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
