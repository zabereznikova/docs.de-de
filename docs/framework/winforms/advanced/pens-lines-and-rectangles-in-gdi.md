---
title: Stifte, Linien und Rechtecke in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
ms.openlocfilehash: 86cc51006361d5628dc12999588520e28e62f166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="pens-lines-and-rectangles-in-gdi"></a>Stifte, Linien und Rechtecke in GDI+
Zum Zeichnen von Linien mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] müssen Sie erstellen eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt. Die <xref:System.Drawing.Graphics> Objekt enthält die Methoden, die den Zeichenvorgang ausführen und die <xref:System.Drawing.Pen> Objekt speichert Attribute, z. B. Farbe, Breite und Stil.  
  
## <a name="drawing-a-line"></a>Zeichnen einer Linie  
 Aufrufen, um eine Linie zeichnen, die <xref:System.Drawing.Graphics.DrawLine%2A> Methode der <xref:System.Drawing.Graphics> Objekt. Die <xref:System.Drawing.Pen> Objekt als eines der Argumente zu übergeben der <xref:System.Drawing.Graphics.DrawLine%2A> Methode. Im folgende Beispiel zeichnet eine verbindende Linie ab dem Punkt (4, 2) auf den Punkt ("12", "6"):  
  
 [!code-csharp[LinesCurvesAndShapes#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <xref:System.Drawing.Graphics.DrawLine%2A> eine überladene Methode wird die <xref:System.Drawing.Graphics> Klasse, damit es gibt mehrere Möglichkeiten, die Sie Argumente angeben können. Beispielsweise können Sie konstruieren zwei <xref:System.Drawing.Point> Objekte und übergeben Sie die <xref:System.Drawing.Point> -Objekte als Argumente an die <xref:System.Drawing.Graphics.DrawLine%2A> Methode:  
  
 [!code-csharp[LinesCurvesAndShapes#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a>Erstellen eines Stifts  
 Sie können bestimmte Attribute angeben, beim Erstellen einer <xref:System.Drawing.Pen> Objekt. Z. B. eine `Pen` Konstruktor können Sie die Farbe und Breite angeben. Im folgende Beispiel zeichnet eine blaue Linie der Breite 2 aus (0, 0), (60, 30):  
  
 [!code-csharp[LinesCurvesAndShapes#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a>Gestrichelte Linien und Linienenden  
 Die <xref:System.Drawing.Pen> Objekt auch macht Eigenschaften verfügbar, z. B. <xref:System.Drawing.Pen.DashStyle%2A>, dass Sie angeben, die Funktionen der Zeile verwenden können. Im folgende Beispiel zeichnet eine gestrichelte Linie aus (100, 50), (300, 80):  
  
 [!code-csharp[LinesCurvesAndShapes#44](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 Können Sie die Eigenschaften der <xref:System.Drawing.Pen> Objekt, das viele weitere Attribute der Zeile festgelegt. Die <xref:System.Drawing.Pen.StartCap%2A> und <xref:System.Drawing.Pen.EndCap%2A> Eigenschaften angeben, die Darstellung der am Ende der Zeile, die Enden können sein, Flatfiles, quadratische, gerundet, dreieckig, oder eine benutzerdefinierte Form. Die <xref:System.Drawing.Pen.LineJoin%2A> -Eigenschaft können Sie angeben, ob der miteinander verbundenen Linien Gehrung (verknüpft mit abgerundete Ecken), abgeschrägt, gerundet oder abgeschnitten werden. Die folgende Abbildung zeigt die Zeilen mit verschiedenen Cap und Join-Formate.  
  
 ![Zeilen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art04.gif "Aboutgdip02_art04")  
  
## <a name="drawing-a-rectangle"></a>Zeichnen eines Rechtecks  
 Zeichnen von Rechtecken mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ähnelt dem Zeichnen von Linien. Um ein Rechteck gezeichnet werden soll, müssen Sie eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt. Die <xref:System.Drawing.Graphics> -Objekt bietet eine <xref:System.Drawing.Graphics.DrawRectangle%2A> -Methode, und die <xref:System.Drawing.Pen> Objekt speichert Attribute, z. B. Breite und Farbe. Die <xref:System.Drawing.Pen> Objekt als eines der Argumente zu übergeben der <xref:System.Drawing.Graphics.DrawRectangle%2A> Methode. Im folgende Beispiel zeichnet ein Rechteck mit der linken oberen Ecke an (100, 50), einer Breite von 80 und einer Höhe von 40:  
  
 [!code-csharp[LinesCurvesAndShapes#45](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <xref:System.Drawing.Graphics.DrawRectangle%2A> eine überladene Methode wird die <xref:System.Drawing.Graphics> Klasse, damit es gibt mehrere Möglichkeiten, die Sie Argumente angeben können. Sie können z. B. Erstellen einer <xref:System.Drawing.Rectangle> Objekts und übergeben der <xref:System.Drawing.Rectangle> -Objekt an die <xref:System.Drawing.Graphics.DrawRectangle%2A> Methode als Argument:  
  
 [!code-csharp[LinesCurvesAndShapes#46](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 Ein <xref:System.Drawing.Rectangle> Objekt verfügt über Methoden und Eigenschaften zum Bearbeiten und Sammeln von Informationen über das Rechteck. Z. B. die <xref:System.Drawing.Rectangle.Inflate%2A> und <xref:System.Drawing.Rectangle.Offset%2A> Methoden ändern, die Größe und Position des Rechtecks. Die <xref:System.Drawing.Rectangle.IntersectsWith%2A> Methode gibt Aufschluss darüber, ob das Rechteck eine andere überlappt Rechteck und die <xref:System.Drawing.Rectangle.Contains%2A> Methode gibt Aufschluss darüber, ob ein bestimmter Punkt innerhalb des Rechtecks ist.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Rectangle?displayProperty=nameWithType>  
 [Gewusst wie: Erstellen eines Stifts](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [Gewusst wie: Zeichnen einer Linie in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)  
 [Gewusst wie: Zeichnen der Kontur einer Form](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
