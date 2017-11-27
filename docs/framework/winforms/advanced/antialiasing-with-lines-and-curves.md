---
title: Antialiasing bei Linien und Kurven
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
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d69d635fbdd8720937cd189826c1496b8126ddef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="antialiasing-with-lines-and-curves"></a>Antialiasing bei Linien und Kurven
Bei Verwendung von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] um eine Linie zeichnen, Sie geben Sie den Startpunkt und den Endpunkt der Linie, aber Sie müssen keine keine Informationen zu den einzelnen Pixel in der Zeile bereit. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]funktioniert in Verbindung mit dem Bildschirmtreiber um zu bestimmen, welche Pixel aktiviert werden, werden um die Zeile auf die jeweiligen Ausgabegeräts angezeigt.  
  
## <a name="aliasing"></a>Aliasing  
 Betrachten Sie die gerade rote Linie, die an dem Punkt (4, 2) auf den Punkt (16, 10) geht. Angenommen Sie, das Koordinatensystem seinen Ursprung in der oberen linken Ecke hat und dass die Maßeinheit Pixel ist. Darüber hinaus vorausgesetzt, dass die x-Achse nach rechts und die y-Achse Punkte nach unten. Die folgende Abbildung zeigt eine vergrößerte Ansicht der die rote Linie, die auf einem mehrfarbigen Hintergrund gezeichnet wird.  
  
 ![Befehlszeile, ohne Antialiasing](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.gif "AboutGdip02_Art33")  
  
 Die roten Pixel, die zum Rendern der Zeile verwendeten sind nicht transparent. Es gibt keine teilweise transparenten Pixel in der Zeile ein. Diese Art der Darstellung der Linie gibt der Zeile einer gezackten Darstellung und sieht sich ähnlich wie eine Treppe. Dieses Verfahren, um eine Zeile mit einer Treppe darzustellen Aliasing aufgerufen wird. Treppe ist ein Alias für die theoretische Linie.  
  
## <a name="antialiasing"></a>Antialiasing (Antialiasing)  
 Eine komplexere Technik zum Rendern einer Zeile wird teilweise transparente Pixel zusammen mit nicht transparenten Pixel. Reines Rot Pixel festgelegt werden oder eine Mischung aus Rot und die Farbe des Hintergrunds, je nachdem, wie weit sie sind in der Zeile. Diese Art des Renderings Antialiasing aufgerufen wird und führt zu einer Zeile, die als glatter Tabellenlayout wahrgenommen. Die folgende Abbildung zeigt, wie bestimmte Pixel mit Hintergrund aus, um eine Zeile mit Antialiasing erzeugen gemischt werden.  
  
 ![Antialiasing bei einer Linie](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.gif "AboutGdip02_Art34")  
  
 Antialiasing (Antialiasing), das auch als Glättung kann auch auf Kurven angewendet werden. Die folgende Abbildung zeigt eine vergrößerte Ansicht einer geglätteten Ellipse.  
  
 ![Antialiasing bei Kurven](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.gif "AboutGdip02_Art35")  
  
 Die folgende Abbildung zeigt die gleiche Ellipse in der Originalgröße an, ohne Antialiasing (Antialiasing) und einmal mit Antialiasing (Antialiasing).  
  
 ![Antialiasingbeispiel](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02_Art36")  
  
 Zum Zeichnen von Linien und Kurven mit Antialiasing, erstellen Sie eine Instanz von der <xref:System.Drawing.Graphics> Klasse, und legen seine <xref:System.Drawing.Graphics.SmoothingMode%2A> Eigenschaft <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> oder <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>. Dann rufen Sie eine der Zeichnung Methoden, die gleichen <xref:System.Drawing.Graphics> Klasse.  
  
 [!code-csharp[LinesCurvesAndShapes#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>  
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Gewusst wie: Verwenden der Bildkantenglättung mit Text](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)
