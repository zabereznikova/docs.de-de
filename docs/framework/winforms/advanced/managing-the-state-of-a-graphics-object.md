---
title: Verwalten des Zustands eines Graphics-Objekts
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: d1e7e6eac775ca779fb68605adcc9bc2b9915e49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182453"
---
# <a name="managing-the-state-of-a-graphics-object"></a>Verwalten des Zustands eines Graphics-Objekts
Die <xref:System.Drawing.Graphics> Klasse ist das Herzstück von GDI+. Um etwas zu zeichnen, erhalten Sie <xref:System.Drawing.Graphics> ein Objekt, <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Graphics.DrawImage%2A>legen <xref:System.Drawing.Graphics.DrawString%2A>seine Eigenschaften fest und rufen seine Methoden , , und dergleichen auf.  
  
 Im folgenden Beispiel <xref:System.Drawing.Graphics.DrawRectangle%2A> wird <xref:System.Drawing.Graphics> die Methode eines Objekts auf. Das erste Argument, <xref:System.Drawing.Graphics.DrawRectangle%2A> das <xref:System.Drawing.Pen> an die Methode übergeben wird, ist ein Objekt.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a>Grafikzustand  
 Ein <xref:System.Drawing.Graphics> Objekt stellt mehr als nur <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Graphics.DrawRectangle%2A>Zeichenmethoden bereit, z. B. und . Ein <xref:System.Drawing.Graphics> Objekt behält auch den Grafikstatus bei, der in die folgenden Kategorien unterteilt werden kann:  
  
- Qualitätseinstellungen  
  
- Transformationen  
  
- Clipping-Bereich  
  
### <a name="quality-settings"></a>Qualitätseinstellungen  
 Ein <xref:System.Drawing.Graphics> Objekt verfügt über mehrere Eigenschaften, die die Qualität der gezeichneten Elemente beeinflussen. Sie können die <xref:System.Drawing.Graphics.TextRenderingHint%2A> Eigenschaft beispielsweise so festlegen, dass der Typ der Antialiasing (falls vorhanden) angegeben wird, die auf Text angewendet wird. Andere Eigenschaften, die <xref:System.Drawing.Graphics.SmoothingMode%2A> <xref:System.Drawing.Graphics.CompositingMode%2A>die <xref:System.Drawing.Graphics.CompositingQuality%2A>Qualität <xref:System.Drawing.Graphics.InterpolationMode%2A>beeinflussen, sind , , und .  
  
 Im folgenden Beispiel werden zwei Ellipsen gezeichnet, <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> eine mit dem Glättungsmodus und eine mit dem <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>Aufglättungsmodus:  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a>Transformationen  
 Ein <xref:System.Drawing.Graphics> Objekt verwaltet zwei Transformationen (Welt und Seite), die <xref:System.Drawing.Graphics> auf alle von diesem Objekt gezeichneten Elemente angewendet werden. Jede affine Transformation kann in der Welttransformation gespeichert werden. Zu den feinen Transformationen gehören Skalierung, Drehen, Reflektieren, Verzerren und Übersetzen. Die Seitentransformation kann zum Skalieren und zum Ändern von Einheiten (z. B. Pixel in Zoll) verwendet werden. Weitere Informationen finden Sie unter [Koordinatensysteme und Transformationen](coordinate-systems-and-transformations.md).  
  
 Im folgenden Beispiel werden die Welt- <xref:System.Drawing.Graphics> und Seitentransformationen eines Objekts festgelegt. Die Welttransformation ist auf eine 30-Grad-Rotation eingestellt. Die Seitentransformation ist so eingestellt, dass <xref:System.Drawing.Graphics.DrawEllipse%2A> die an die Zweite übergebenen Koordinaten als Millimeter anstelle von Pixeln behandelt werden. Der Code führt zwei <xref:System.Drawing.Graphics.DrawEllipse%2A> identische Aufrufe der Methode aus. Die Welttransformation wird auf <xref:System.Drawing.Graphics.DrawEllipse%2A> den ersten Aufruf angewendet, und beide Transformationen <xref:System.Drawing.Graphics.DrawEllipse%2A> (Welt und Seite) werden auf den zweiten Aufruf angewendet.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 Die folgende Abbildung zeigt die beiden Ellipsen. Beachten Sie, dass es bei der 30-Grad-Drehung um den Ursprung des Koordinatensystems (obere linke Ecke des Clientbereichs) und nicht um die Mittelpunkte der Ellipsen geht. Beachten Sie auch, dass die Stiftbreite von 1 1 Pixel für die erste Ellipse und 1 Millimeter für die zweite Ellipse bedeutet.  
  
 ![Abbildung, die zwei Ellipsen zeigt: Drehung und Stiftbreite.](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a>Clipping-Region  
 Ein <xref:System.Drawing.Graphics> Objekt verwaltet einen Zuschneidebereich, der <xref:System.Drawing.Graphics> für alle von diesem Objekt gezeichneten Elemente gilt. Sie können den Clipping-Bereich <xref:System.Drawing.Graphics.SetClip%2A> festlegen, indem Sie die Methode aufrufen.  
  
 Im folgenden Beispiel wird ein plusförmiger Bereich erstellt, indem die Vereinigung von zwei Rechtecken gebildet wird. Dieser Bereich wird als Clipping-Bereich eines <xref:System.Drawing.Graphics> Objekts festgelegt. Anschließend zeichnet der Code zwei Zeilen, die auf das Innere des Clipping-Bereichs beschränkt sind.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 Die folgende Abbildung zeigt die abgeschnittenen Linien:  
  
 ![Diagramm, das den begrenzten Clipbereich anzeigt.](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a>Weitere Informationen

- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Verwenden geschachtelter Grafikcontainer](using-nested-graphics-containers.md)
