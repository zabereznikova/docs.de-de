---
title: Kardinale Splines in GDI+
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
- splines [Windows Forms], cardinal
- GDI+, cardinal splines
- cardinal splines
ms.assetid: 09b3797a-6294-422d-9adf-a5a0a7695c0c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ad417ee61026f6573f19e70409511e0b28e4d78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="cardinal-splines-in-gdi"></a>Kardinale Splines in GDI+
Eine cardinal-Splinekurve ist eine Sequenz von einzelne Kurven verknüpft, um eine größere Kurve zu bilden. Die Splinekurve durch ein Array von Punkten und Spannungsparameter angegeben. Eine cardinal-Splinekurve durchläuft problemlos auf jedem Punkt im Array; Es gibt keine abgerundete Ecken und keine abrupten Änderungen in die Dichtigkeit der Kurve. Die folgende Abbildung zeigt eine Reihe von Punkten und eine cardinal-Splinekurve, die jeden Punkt in der Gruppe durchläuft.  
  
 ![Kardinaler Spline](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art09.gif "Aboutgdip02_art09")  
  
## <a name="physical-and-mathematical-splines"></a>Physikalische und mathematische Splines  
 Eine physische Splinekurve ist eine schlanke Holz oder anderen Materialien, die flexible. Vor der Einführung von mathematischen Splines verwendet Designer physischen Splines Kurven gezeichnet werden soll. Ein Designer würde die Splinekurve auf einem Blatt Papier platzieren und einem bestimmten Satz von Punkten zu verankern. Der Designer konnte eine Kurve klicken Sie dann mit einem Stift oder einem Zeichenstift Zeichnung entlang des Splines erstellen. Ein bestimmter Satz von Punkten kann eine Vielzahl von Kurven, je nach den Eigenschaften des physischen Splines ergeben. Ein Spline mit einem hohen Biegewiderstand erzeugt z. B. eine andere Kurve als ein äußerst flexibel Spline.  
  
 Die Formeln für mathematische Splines basieren auf die Eigenschaften von biegsamen, damit die Kurven von mathematischen Splines erzeugten Kurven ähneln, die einmal durch physische Splines erzeugt wurden. Ebenso wie physische Splines von verschiedenen Spannung Kurven über einen bestimmten Satz von Punkten erzeugt, erzeugt mathematische Splines mit verschiedenen Werten für den Spannungsparameter Kurven über einen bestimmten Satz von Punkten. Die folgende Abbildung zeigt vier kardinale Splines Umweg über den gleichen Satz von Punkten. Die Spannung wird für jeden Spline angezeigt. Eine Spannung von 0 entspricht unendlichen physikalischen-Spannung die Kurve auszuführenden der schnellste Weg (gerade Linien), die zwischen Punkten erzwingen. Keine physischen Spannung, die die Splinekurve, die den Weg des am wenigsten insgesamt Krümmung, sodass entspricht eine Spannung von 1. Verhält sich die Kurve mit Spannung Werte größer als 1 wie eine komprimierte Spring auszuführenden einen längeren Pfad abgelegt.  
  
 ![Kardinale Splines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art10.gif "Aboutgdip02_art10")  
  
 Die vier Splines in der vorherigen Abbildung gemeinsam die gleiche Tangente am Ausgangspunkt. Der Tangens ist die Zeile am Anfangspunkt der nächsten Punkt entlang der Kurve gezeichnet. Ebenso ist die gemeinsame Tangente an seinem Endpunkt der Zeile, die vom Endpunkt zum vorherigen Punkt auf der Kurve gezeichnet.  
  
 Um eine cardinal-Splinekurve zu zeichnen, benötigen Sie eine Instanz von der <xref:System.Drawing.Graphics> -Klasse, eine <xref:System.Drawing.Pen>, und ein Array von <xref:System.Drawing.Point> Objekte von der Instanz von der <xref:System.Drawing.Graphics> -Klasse stellt die <xref:System.Drawing.Graphics.DrawCurve%2A> -Methode, die die Splinekurve zeichnet, und die <xref:System.Drawing.Pen> speichert Attribute von den Spline an, z. B. Breite und Farbe. Das Array von <xref:System.Drawing.Point> -Objekte speichert die Punkte, die die Kurve weitergeleitet werden. Im folgenden Codebeispiel wird veranschaulicht, wie eine cardinal-Splinekurve gezeichnet werden soll, die den Positionen im durchlaufen `myPointArray`. Der dritte Parameter ist die Spannung.  
  
 [!code-csharp[LinesCurvesAndShapes#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#31)]
 [!code-vb[LinesCurvesAndShapes#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Siehe auch  
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Erstellen und Zeichnen von Kurven](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
