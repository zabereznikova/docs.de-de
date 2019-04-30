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
ms.openlocfilehash: 8fc92bf84def50bed54a054ae634a8a08c8835c2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936875"
---
# <a name="managing-the-state-of-a-graphics-object"></a>Verwalten des Zustands eines Graphics-Objekts
Die <xref:System.Drawing.Graphics> -Klasse ist das Herzstück von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Um alles zu zeichnen, Sie erhalten eine <xref:System.Drawing.Graphics> Objekt, dessen Eigenschaften festlegen und seine Methoden aufrufen <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, usw.).  
  
 Im folgenden Beispiel wird die <xref:System.Drawing.Graphics.DrawRectangle%2A> Methode eine <xref:System.Drawing.Graphics> Objekt. Das erste Argument zu übergeben, um die <xref:System.Drawing.Graphics.DrawRectangle%2A> Methode ist eine <xref:System.Drawing.Pen> Objekt.  
  
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
 Ein <xref:System.Drawing.Graphics> Objekt bietet mehr als Zeichenmethoden wie z. B. <xref:System.Drawing.Graphics.DrawLine%2A> und <xref:System.Drawing.Graphics.DrawRectangle%2A>. Ein <xref:System.Drawing.Graphics> -Objekt verwaltet auch den Grafikstatus, die in der folgenden Kategorien unterteilt werden können:  
  
- Einstellungen für die Qualität  
  
- Transformationen  
  
- Ausschneidebereich  
  
### <a name="quality-settings"></a>Einstellungen für die Qualität  
 Ein <xref:System.Drawing.Graphics> Objekt verfügt über mehrere Eigenschaften, die die Qualität der Elemente beeinflussen, die gezeichnet werden. Sie können z. B. Festlegen der <xref:System.Drawing.Graphics.TextRenderingHint%2A> Eigenschaft, um den Typ des Antialiasing (sofern vorhanden), die auf einen Text angewendeten anzugeben. Andere Eigenschaften, die Qualität beeinflussen sind <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, und <xref:System.Drawing.Graphics.InterpolationMode%2A>.  
  
 Im folgende Beispiel werden zwei Ellipsen mit den Glättungsmodus gezeichnet <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> und eine mit der Glättungsmodus <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:  
  
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
 Ein <xref:System.Drawing.Graphics> -Objekt verwaltet zwei Transformationen ("World" und "Seite"), die für alle Elemente, die vom, die angewendet werden <xref:System.Drawing.Graphics> Objekt. Eine affine Transformation kann in der globalen Transformation gespeichert werden. Affine Transformationen enthalten, skalieren, drehen, spiegeln, neigen und übersetzen. Die Seitentransformation kann für die Skalierung sowie zum Ändern von Einheiten (z. B. Pixel, Zoll) verwendet werden. Weitere Informationen finden Sie unter [Koordinatensysteme und Transformationen](coordinate-systems-and-transformations.md).  
  
 Im folgenden Beispiel wird die Seite "und" World Transformationen von einem <xref:System.Drawing.Graphics> Objekt. Die globale Transformation wird auf eine 30-Grad-Drehung festgelegt. Die Seitentransformation wird festgelegt, sodass die Koordinaten für die zweite übergeben <xref:System.Drawing.Graphics.DrawEllipse%2A> als Millimeter anstelle von Pixel behandelt werden. Der Code führt zwei identische Aufrufe der <xref:System.Drawing.Graphics.DrawEllipse%2A> Methode. Die globale Transformation angewendet wird, mit dem ersten <xref:System.Drawing.Graphics.DrawEllipse%2A> Aufruf, und beide Transformationen ("World" und "Seite") gelten für die zweite <xref:System.Drawing.Graphics.DrawEllipse%2A> aufrufen.  
  
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
  
 Die folgende Abbildung zeigt zwei Ellipsen. Beachten Sie, dass die 30-Grad-Drehung um den Ursprung des Koordinatensystems (linke obere Ecke des Clientbereichs), nicht jedoch zu den Mittelpunkten die Auslassungspunkte. Beachten Sie außerdem, dass mit der die Stiftbreite 1 1-Pixel für die erste Ellipse und 1 mm für die zweite Ellipse.  
  
 ![Abbildung der zwei Ellipsen: Drehung und Stift-Breite.](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a>Ausschneidebereich  
 Ein <xref:System.Drawing.Graphics> -Objekt verwaltet einen Ausschneidebereich, der für alle Elemente, die von diesem gilt <xref:System.Drawing.Graphics> Objekt. Sie können den Ausschneidebereich festlegen, durch den Aufruf der <xref:System.Drawing.Graphics.SetClip%2A> Methode.  
  
 Das folgende Beispiel erstellt eine Region Plus gestalteten durch Bildung der Union von zwei Rechtecken. Diese Region als der Ausschneidebereich festgelegt wurde eine <xref:System.Drawing.Graphics> Objekt. Der Code zeichnet dann zwei Zeilen, die auf das Innere des Clippingbereichs beschränkt sind.  
  
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
  
 Die folgende Abbildung zeigt die abgeschnittenen Zeilen:  
  
 ![Diagramm der beschränkter Clip-Bereich zeigt.](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a>Siehe auch

- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Verwenden geschachtelter Grafikcontainer](using-nested-graphics-containers.md)
