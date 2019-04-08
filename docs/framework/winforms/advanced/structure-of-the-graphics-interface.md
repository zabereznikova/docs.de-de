---
title: Struktur der grafischen Oberfläche
ms.date: 03/30/2017
helpviewer_keywords:
- GDI+, using managed interface
- graphics [Windows Forms], class structure
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
ms.openlocfilehash: 9dfffe8ea3f76d89823dfe2ef6bd0e4f3accf8f1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106781"
---
# <a name="structure-of-the-graphics-interface"></a>Struktur der grafischen Oberfläche
Die Schnittstelle für verwaltete Klassen zu [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] enthält ca. 60 Klassen, 50 Enumerationen und Strukturen von 8. Die <xref:System.Drawing.Graphics> Klasse bildet den Kern der [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Funktionen; Dies ist die Klasse, die tatsächlich Linien, Kurven, Abbildungen, Bilder und Text zeichnet.  
  
## <a name="important-classes"></a>Wichtige Klassen  
 Viele Klassen funktionieren in Verbindung mit der <xref:System.Drawing.Graphics> Klasse. Z. B. die <xref:System.Drawing.Graphics.DrawLine%2A> -Methode empfängt einen <xref:System.Drawing.Pen> -Objekt, das Attribute, die der Linie gezeichnet werden soll (Farbe, Breite, Strichstil und ähnliches) enthält. Die <xref:System.Drawing.Graphics.FillRectangle%2A> Methode erhalten einen Zeiger auf eine <xref:System.Drawing.Drawing2D.LinearGradientBrush> -Objekt, das mit der <xref:System.Drawing.Graphics> Objekt, das ein Rechteck mit einem Farbverlauf zu füllen. <xref:System.Drawing.Font> und <xref:System.Drawing.StringFormat> Objekte beeinflussen, wie eine <xref:System.Drawing.Graphics> Objekt zeichnet Text. Ein <xref:System.Drawing.Drawing2D.Matrix> -Objekt speichert und bearbeitet die globale Transformation für einen <xref:System.Drawing.Graphics> -Objekt, das zum Drehen, skalieren und Kippen von Bildern verwendet wird.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] stellt mehrere Strukturen bereit (z. B. <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Point>, und <xref:System.Drawing.Size>) zum Organisieren von Grafikdaten. Darüber hinaus dienen bestimmte Klassen in erster Linie als strukturierte Datentypen, die. Z. B. die <xref:System.Drawing.Imaging.BitmapData> Klasse ist eine Hilfsklasse für die <xref:System.Drawing.Bitmap> -Klasse, und die <xref:System.Drawing.Drawing2D.PathData> Klasse ist eine Hilfsklasse für die <xref:System.Drawing.Drawing2D.GraphicsPath> Klasse.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] definiert mehrere Enumerationen, die Sammlungen verwandter Konstanten sind. Z. B. die <xref:System.Drawing.Drawing2D.LineJoin> Enumeration enthält die Elemente <xref:System.Drawing.Drawing2D.LineJoin.Bevel>, <xref:System.Drawing.Drawing2D.LineJoin.Miter>, und <xref:System.Drawing.Drawing2D.LineJoin.Round>, geben Sie die Stile an, die zum Verbinden von zwei Linien verwendet werden können.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Grafiken](graphics-overview-windows-forms.md)
- [Verwalteter Code in GDI+](about-gdi-managed-code.md)
- [Verwenden von verwalteten Grafikklassen](using-managed-graphics-classes.md)
