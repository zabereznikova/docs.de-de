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
ms.openlocfilehash: 7a8286fb741effaf668b87e90da04f79d1490de2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715996"
---
# <a name="alpha-blending-lines-and-fills"></a>Alphablending von Linien und Füllungen
In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], eine Farbe ist ein 32-Bit-Wert, mit jeweils 8 Bit für Alpha, Rot, Grün und Blau. Der alpha-Wert gibt an, die Transparenz der Farbe, den Umfang, der die Farbe mit der Hintergrundfarbe vermischt wird. Alpha-Werte-Bereich von 0 bis 255, wobei 0 für eine vollständig transparente Farbe darstellt, und 255 stellt eine vollständig deckende Farbe dar.  
  
 Alphablending ist eine x-Pixel-Kombination von der Quell- und Hintergrund Farbdaten. Jede der drei Komponenten (Rot, Grün, Blau) eine Farbe für die angegebene Quelle wird mit der entsprechenden Komponente der Farbe des Hintergrunds, gemäß der folgenden Formel gemischt:  
  
 displayColor = sourceColor × alpha / 255 + backgroundColor × (255 – alpha) / 255  
  
 Nehmen wir beispielsweise an der roten Anteil der Quellfarbe 150 und Rotanteils der Farbe des Hintergrunds ist 100. Wenn der alpha-Wert 200 ist, wird Rotanteils der die resultierende Farbe wie folgt berechnet:  
  
 150 × 200 / 255 + 100 × (255 – 200) / 255 = 139  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Zeichnen Sie deckender und halbtransparente Linien](how-to-draw-opaque-and-semitransparent-lines.md)  
 Veranschaulicht, wie Bereiche mit Alphablending von Linien zu zeichnen.  
  
 [Vorgehensweise: Zeichnen Sie mit nicht transparenten und halb transparenten Pinseln](how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 Alpha-Blend mit Pinseln erläutert.  
  
 [Vorgehensweise: Verwenden des Mischmodus zum Steuern des Alphablendings](how-to-use-compositing-mode-to-control-alpha-blending.md)  
 Beschreibt, wie Sie steuern die Alphablending mit <xref:System.Drawing.Drawing2D.CompositingMode>.  
  
 [Vorgehensweise: Verwenden einer Farbmatrix zum Festlegen von Alphawerten in Bildern](how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 Erläutert, wie eine <xref:System.Drawing.Imaging.ColorMatrix> Objekt zum Steuern des Alphablendings.
