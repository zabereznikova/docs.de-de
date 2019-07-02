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
ms.openlocfilehash: 06d2351ffa7d7f009d7b049f4689df7038b4d202
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505354"
---
# <a name="pens-lines-and-rectangles-in-gdi"></a>Stifte, Linien und Rechtecke in GDI+
Um Zeilen mit GDI + zu zeichnen, Sie erstellen müssen, eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt. Die <xref:System.Drawing.Graphics> Objekt bietet Methoden, die den Zeichenvorgang, ausführen und die <xref:System.Drawing.Pen> Objekt speichert Attribute, z. B. Farbe, Breite und Stil.  
  
## <a name="drawing-a-line"></a>Zeichnen einer Linie  
 Um eine Linie zu zeichnen, rufen Sie die <xref:System.Drawing.Graphics.DrawLine%2A> -Methode der der <xref:System.Drawing.Graphics> Objekt. Die <xref:System.Drawing.Pen> Objekt als eines der Argumente zum Übergeben der <xref:System.Drawing.Graphics.DrawLine%2A> Methode. Im folgende Beispiel zeichnet eine Linie von der Punkt ("4", "2"), zu dem Punkt ("12", "6"):  
  
 [!code-csharp[LinesCurvesAndShapes#41](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <xref:System.Drawing.Graphics.DrawLine%2A> ist eine überladene Methode, der die <xref:System.Drawing.Graphics> Klasse, damit es mehrere Möglichkeiten gibt, können Sie es mit Argumenten angeben. Sie können z. B. erstellen zwei <xref:System.Drawing.Point> Objekte und übergeben Sie die <xref:System.Drawing.Point> -Objekte als Argumente an die <xref:System.Drawing.Graphics.DrawLine%2A> Methode:  
  
 [!code-csharp[LinesCurvesAndShapes#42](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a>Erstellen eines Stifts  
 Sie können bestimmte Attribute angeben, beim Erstellen einer <xref:System.Drawing.Pen> Objekt. Z. B. eine `Pen` Konstruktor ermöglicht das Angeben von Farbe und Breite. Das folgende Beispiel zeichnet eine blaue Linie der Stärke von 2 aus (0, 0), (60, 30):  
  
 [!code-csharp[LinesCurvesAndShapes#43](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a>Gestrichelte Linien und Linienenden  
 Die <xref:System.Drawing.Pen> Objekt macht auch Eigenschaften, z. B. <xref:System.Drawing.Pen.DashStyle%2A>, dass Sie angeben, die Funktionen der Zeile verwenden können. Das folgende Beispiel zeichnet eine gestrichelte Linie von (100, 50), (300, 80):  
  
 [!code-csharp[LinesCurvesAndShapes#44](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 Können Sie die Eigenschaften der <xref:System.Drawing.Pen> Objekt, das die Zeile zahlreicher weiterer Attribute festgelegt. Die <xref:System.Drawing.Pen.StartCap%2A> und <xref:System.Drawing.Pen.EndCap%2A> Eigenschaften angeben, die Darstellung der Enden der Linie, die Enden können Flatfile, Square, gerundet, dreieckig, oder eine benutzerdefinierte Form. Die <xref:System.Drawing.Pen.LineJoin%2A> -Eigenschaft können Sie angeben, ob miteinander verbundenen Linien Gehrung (verknüpft mit Ecken), abgeschrägt, gerundet oder abgeschnitten werden. Die folgende Abbildung zeigt die Zeilen mit verschiedenen Arten von Cap und Join.  
  
 ![Lines](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")  
  
## <a name="drawing-a-rectangle"></a>Zeichnen eines Rechtecks  
 Zeichnen von Rechtecken in GDI + ist ähnlich wie Zeichnen von Linien. Um ein Rechteck zu zeichnen, müssen Sie eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt. Die <xref:System.Drawing.Graphics> -Objekt ermöglicht eine <xref:System.Drawing.Graphics.DrawRectangle%2A> -Methode, und die <xref:System.Drawing.Pen> Objekt speichert Attribute, z. B. Linienstärke und Farbe. Die <xref:System.Drawing.Pen> Objekt als eines der Argumente zum Übergeben der <xref:System.Drawing.Graphics.DrawRectangle%2A> Methode. Im folgende Beispiel zeichnet ein Rechteck mit der linken oberen Ecke an (100, 50), einer Breite von 80 und einer Höhe von 40:  
  
 [!code-csharp[LinesCurvesAndShapes#45](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <xref:System.Drawing.Graphics.DrawRectangle%2A> ist eine überladene Methode, der die <xref:System.Drawing.Graphics> Klasse, damit es mehrere Möglichkeiten gibt, können Sie es mit Argumenten angeben. Sie können z. B. Erstellen einer <xref:System.Drawing.Rectangle> Objekt, und übergeben die <xref:System.Drawing.Rectangle> -Objekt an die <xref:System.Drawing.Graphics.DrawRectangle%2A> Methode als Argument:  
  
 [!code-csharp[LinesCurvesAndShapes#46](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 Ein <xref:System.Drawing.Rectangle> Objekt enthält Methoden und Eigenschaften zum Bearbeiten und Sammeln von Informationen über das Rechteck. Z. B. die <xref:System.Drawing.Rectangle.Inflate%2A> und <xref:System.Drawing.Rectangle.Offset%2A> Methoden ändern die Größe und Position des Rechtecks. Die <xref:System.Drawing.Rectangle.IntersectsWith%2A> Methode erfahren Sie, ob das Rechteck für einen anderen überschneidet angegebenen Rechteck, und die <xref:System.Drawing.Rectangle.Contains%2A> Methode erfahren Sie, ob ein bestimmter Punkt innerhalb des Rechtecks befindet.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- [Vorgehensweise: Erstellen eines Stifts](how-to-create-a-pen.md)
- [Vorgehensweise: Zeichnen einer Linie in einem Windows Form](how-to-draw-a-line-on-a-windows-form.md)
- [Vorgehensweise: Zeichnen der Kontur eine Form](how-to-draw-an-outlined-shape.md)
