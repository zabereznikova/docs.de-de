---
title: Struktur der grafischen Oberfläche
ms.date: 03/30/2017
helpviewer_keywords:
- GDI+, using managed interface
- graphics [Windows Forms], class structure
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
ms.openlocfilehash: 625bd5818d58fd659af69d4985d629f055123e54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="structure-of-the-graphics-interface"></a>Struktur der grafischen Oberfläche
Die Schnittstelle für verwaltete Klassen zu [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ca. 60 Klassen, 50 Enumerationen und 8 Strukturen enthält. Die <xref:System.Drawing.Graphics> Klasse bildet den Kern der [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Funktionen wird die Klasse, die tatsächlich Linien, Kurven, Formen, Bilder und Text zeichnet.  
  
## <a name="important-classes"></a>Wichtige Klassen  
 Viele Klassen arbeiten zusammen mit der <xref:System.Drawing.Graphics> Klasse. Z. B. die <xref:System.Drawing.Graphics.DrawLine%2A> Methode empfängt einen <xref:System.Drawing.Pen> -Objekt, das Attribute, die der Linie gezeichnet werden (Farbe, Breite, linienstrichstil und Like) enthält. Die <xref:System.Drawing.Graphics.FillRectangle%2A> Methode erhalten einen Zeiger auf eine <xref:System.Drawing.Drawing2D.LinearGradientBrush> -Objekt, das mit der <xref:System.Drawing.Graphics> Objekt, das ein Rechteck mit einem Farbverlauf zu füllen. <xref:System.Drawing.Font> und <xref:System.Drawing.StringFormat> Objekte beeinflussen, wie ein <xref:System.Drawing.Graphics> -Objekt Text zeichnet. Ein <xref:System.Drawing.Drawing2D.Matrix> -Objekt speichert und bearbeitet die globale Transformation für ein <xref:System.Drawing.Graphics> -Objekt, das zum Drehen, zu skalieren und zu kippen von Bildern verwendet wird.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] stellt mehrere Strukturen (z. B. <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Point>, und <xref:System.Drawing.Size>) zum Organisieren von Daten für die Grafiken. Darüber hinaus dienen bestimmte Klassen primär als strukturierte Datentypen. Z. B. die <xref:System.Drawing.Imaging.BitmapData> Klasse ist ein Hilfsprogramm für die <xref:System.Drawing.Bitmap> -Klasse, und die <xref:System.Drawing.Drawing2D.PathData> Klasse ist ein Hilfsprogramm für die <xref:System.Drawing.Drawing2D.GraphicsPath> Klasse.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] definiert mehrere Enumerationen, die Auflistungen von verwandten Konstanten sind. Z. B. die <xref:System.Drawing.Drawing2D.LineJoin> Enumeration enthält die Elemente <xref:System.Drawing.Drawing2D.LineJoin.Bevel>, <xref:System.Drawing.Drawing2D.LineJoin.Miter>, und <xref:System.Drawing.Drawing2D.LineJoin.Round>, angeben, welche Formate, die zum Verbinden von zwei Linien verwendet werden können.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Grafiken](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 [Verwalteter Code in GDI+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 [Verwenden von verwalteten Grafikklassen](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
