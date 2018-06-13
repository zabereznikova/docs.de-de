---
title: Alphablending von Linien und Füllungen
ms.date: 03/30/2017
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
ms.openlocfilehash: f58fa2d105492c6c72d3d6906c3c35f89130fe91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517685"
---
# <a name="alpha-blending-lines-and-fills"></a>Alphablending von Linien und Füllungen
In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], eine Farbe ist ein 32-Bit-Wert mit jeweils 8 Bit für Alpha, Rot, Grün und Blau. Der alphanumerische Wert gibt an, die Transparenz der Farbe – das Ausmaß, der die Farbe wird mit der Hintergrundfarbe gemischt. Alpha Werte reichen von 0 bis 255, wobei 0 für eine vollständig transparent Farbe darstellt, und 255 stellt eine vollständig deckende Farbe dar.  
  
 Alphablending ist eine x-Pixel-Mischen von Quell- und Hintergrund Farbdaten. Jede der drei Komponenten (Rot, Grün, Blau) eine Farbe für die angegebene Quelle wird mit den entsprechenden Komponenten von der Hintergrundfarbe gemäß der folgenden Formel gemischt:  
  
 Anzeigefarbe = Quellfarbe × Alpha / 255 + BackgroundColor × (255-Alpha) / 255  
  
 Nehmen wir beispielsweise an die rote Komponente der Quellfarbe 150 und Rotanteils der Farbe des Hintergrunds ist 100. Wenn der alphanumerische Wert 200 ist, wird die rote Komponente der resultierenden Farbe wie folgt berechnet:  
  
 150 × 200 / 255 + 100 × (255 – 200) / 255 = 139  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Zeichnen deckender und halbtransparenter Linien](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)  
 Zeigt, wie Alphablending von Linien gezeichnet werden soll.  
  
 [Gewusst wie: Zeichnen mit nicht transparenten und halb transparenten Pinseln](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 Alpha-Blend mit Pinseln erläutert.  
  
 [Gewusst wie: Verwenden des Mischmodus zum Steuern des Alphablendings](../../../../docs/framework/winforms/advanced/how-to-use-compositing-mode-to-control-alpha-blending.md)  
 Beschreibt, wie Sie steuern, Alphablending mit <xref:System.Drawing.Drawing2D.CompositingMode>.  
  
 [Gewusst wie: Verwenden einer Farbmatrix zum Festlegen von Alphawerten in Bildern](../../../../docs/framework/winforms/advanced/how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 Erklärt, wie ein <xref:System.Drawing.Imaging.ColorMatrix> Objekt Alphablending steuern.
