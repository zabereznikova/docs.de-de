---
title: Antialiasing bei Linien und Kurven
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
ms.openlocfilehash: cbc9033f18f1ab255862c8f8e2891aa9b68cf8d6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078497"
---
# <a name="antialiasing-with-lines-and-curves"></a>Antialiasing bei Linien und Kurven
Bei Verwendung von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] um eine Linie zu zeichnen, Sie geben Sie den Startpunkt und Endpunkt der Linie, aber Sie müssen keine Informationen zu den einzelnen Pixel in der Zeile zu bieten. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funktioniert in Verbindung mit dem Bildschirmtreiber um zu bestimmen, welche Pixel aktiviert werden, werden um die Zeile in der jeweiligen Ausgabegeräts angezeigt.  
  
## <a name="aliasing"></a>Aliasing  
 Erwägen Sie die gerade rote Linie, die ab dem Punkt ("4", "2") gesendet wird, zu dem Punkt ("16", "10"). Angenommen Sie das Koordinatensystem seinen Ursprung in der oberen linken Ecke hat und die Maßeinheit ist Pixel. Darüber hinaus vorausgesetzt, dass die x-Achse nach rechts und die Punkte für die y-Achse nach unten zeigt. Die folgende Abbildung zeigt eine vergrößerte Ansicht der roten Linie vor einem Hintergrund mehrfarbige.  
  
 ![Zeile, die ohne Antialiasing](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")  
  
 Die roten Pixel verwendet, um die Linie zu rendern sind nicht transparent. Es gibt keine teilweise transparente Pixel in der Zeile. Diese Art der Darstellung der Linie gibt der Zeile einer gezackten Darstellung, und die Zeile ähnelt einer Treppe. Dieses Verfahren für die Darstellung einer Linie mit einer Treppe wird Aliasing bezeichnet. der Treppe ist ein Alias für der theoretischen Linie.  
  
## <a name="antialiasing"></a>Antialiasing  
 Eine anspruchsvollere Technik für das Rendern einer Zeile umfasst die teilweise transparente Pixel zusammen mit nicht transparenten Pixel. Pixel auf reine Rot festgelegt, oder eine Mischung aus Red Team und die Farbe des Hintergrunds, je nachdem, wie weit sie sind in der Zeile. Dieser Typ, der Rendering Antialiasing wird aufgerufen, und führt eine Linie, die das menschliche Auge als glatter wahrgenommen. Die folgende Abbildung zeigt, wie bestimmte Pixel vermischt werden, mit dem Hintergrund, um eine Zeile mit Antialiasing zu erzeugen.  
  
 ![Antialiasing bei einer Linie](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")  
  
 Antialiasing, das auch als Glättung kann auch auf Kurven angewendet werden. Die folgende Abbildung zeigt eine vergrößerte Ansicht einer geglätteten Ellipse.  
  
 ![Antialiasing bei Kurven](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")  
  
 Die folgende Abbildung zeigt die gleiche Ellipse in die tatsächliche Größe ohne Antialiasing und einmal mit Antialiasing.  
  
 ![Antialiasingbeispiel](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")  
  
 Um Linien und Kurven mit Antialiasing zu zeichnen, erstellen Sie eine Instanz des der <xref:System.Drawing.Graphics> Klasse und legen Sie dessen <xref:System.Drawing.Graphics.SmoothingMode%2A> Eigenschaft <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> oder <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>. Dann rufen Sie eine der Zeichenmethoden der, die gleichen <xref:System.Drawing.Graphics> Klasse.  
  
 [!code-csharp[LinesCurvesAndShapes#81](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>
- [Linien, Kurven und Formen](lines-curves-and-shapes.md)
- [Vorgehensweise: Verwenden der Bildkantenglättung mit Text](how-to-use-antialiasing-with-text.md)
