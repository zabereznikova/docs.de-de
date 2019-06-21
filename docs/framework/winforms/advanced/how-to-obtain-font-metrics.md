---
title: 'Vorgehensweise: Abrufen von Schriftarteigenschaften'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 7d7ad92199bb8a8f01290066f8ae023a14c2f9ce
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307427"
---
# <a name="how-to-obtain-font-metrics"></a>Vorgehensweise: Abrufen von Schriftarteigenschaften
Die <xref:System.Drawing.FontFamily> Klasse stellt die folgenden Methoden, die verschiedene Metriken für eine bestimmte Produktfamilie / "Style" abrufen:  
  
- <xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)  
  
- <xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)  
  
- <xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)  
  
- <xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)  
  
 Die von diesen Methoden zurückgegebene Werte sind in Schriftentwurfseinheiten, sodass sie unabhängig von Größe und Einheiten eines bestimmten sind <xref:System.Drawing.Font> Objekt.  
  
 Die folgende Abbildung zeigt die verschiedenen Metriken:
  
 ![Abbildung der Schriftarteigenschaften: Versalhöhe gradientenverfahren und Zeilenabstand.](./media/how-to-obtain-font-metrics/various-font-metrics.png)  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Metriken für den Schriftschnitt der Schriftart Arial-Familie. Der Code erstellt außerdem eine <xref:System.Drawing.Font> Objekt (basierend auf der Arial-Kategorie), mit der Größe von 16 Pixel und zeigt die Metriken (in Pixel) für die jeweilige <xref:System.Drawing.Font> Objekt.  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispielcodes:
  
 ![Ausgabe von Beispiel der Schriftart Arial Metriken.](./media/how-to-obtain-font-metrics/example-output-code-arial-font.png)  
  
 Beachten Sie die ersten beiden Zeilen der Ausgabe in der vorherigen Abbildung. Die <xref:System.Drawing.Font> -Objekt zurückgibt, eine Größe von 16, und die <xref:System.Drawing.FontFamily> Objekt eine Geviertgröße von 2.048 zurück. Diese beiden Zahlen (16 und 2.048) sind der Schlüssel zum Konvertieren zwischen Schriftentwurfseinheiten und die Einheiten (in diesem Fall Pixel), der die <xref:System.Drawing.Font> Objekt.  
  
 Beispielsweise können Sie die Versalhöhe aus Entwurfseinheiten an Pixeln wie folgt konvertieren:  
  
 ![Formel, die mit die Konvertierung von Entwurfseinheiten in Pixel](./media/how-to-obtain-font-metrics/convert-font-units-example.png)  
  
 Der folgende Code Text wird vertikal positioniert, durch Festlegen der <xref:System.Drawing.PointF.Y%2A> Datenmember einer <xref:System.Drawing.PointF> Objekt. Die y-Koordinate wird erhöht, `font.Height` für jede neue Zeile des Texts. Die <xref:System.Drawing.Font.Height%2A> Eigenschaft eine <xref:System.Drawing.Font> Objekts gibt den Zeilenabstand (in Pixel) für die jeweilige <xref:System.Drawing.Font> Objekt. In diesem Beispiel wird die Anzahl von zurückgegebenen <xref:System.Drawing.Font.Height%2A> ist 19. Beachten Sie, dass dies die Anzahl (in eine ganze Zahl aufgerundet) abgerufen, indem Sie die Metrik Zeilenabstand in Pixel konvertiert identisch ist.  
  
 Beachten Sie, dass die Gevierthöhe (auch als Größe oder die Em-Größe) nicht die Summe der Versalhöhe und die Unterlänge ist. Die Summe der Versalhöhe und die Unterlänge wird die Zellenhöhe aufgerufen. Die Zellenhöhe minus der internen vorangestellten ist die Gevierthöhe gleich. Die Zellenhöhe sowie der externe Abstand ist gleich den Zeilenabstand.  
  
 [!code-csharp[System.Drawing.FontsAndText#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch

- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Verwenden von Schriftarten und Text](using-fonts-and-text.md)
