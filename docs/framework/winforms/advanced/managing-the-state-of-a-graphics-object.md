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
ms.openlocfilehash: b81c3c8b25f13ac5791b5d2116b8536575f9ebcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525118"
---
# <a name="managing-the-state-of-a-graphics-object"></a>Verwalten des Zustands eines Graphics-Objekts
Die <xref:System.Drawing.Graphics> Klasse ist der Kern von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Zum Zeichnen, erhalten Sie eine <xref:System.Drawing.Graphics> Objekt, dessen Eigenschaften festlegen und ihre Methoden aufrufen <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, usw.).  
  
 Im folgenden Beispiel wird die <xref:System.Drawing.Graphics.DrawRectangle%2A> Methode von einem <xref:System.Drawing.Graphics> Objekt. Das erste Argument zu übergeben, um die <xref:System.Drawing.Graphics.DrawRectangle%2A> Methode ist ein <xref:System.Drawing.Pen> Objekt.  
  
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
 Ein <xref:System.Drawing.Graphics> Objekt bietet mehr als zeichnen Methoden wie z. B. <xref:System.Drawing.Graphics.DrawLine%2A> und <xref:System.Drawing.Graphics.DrawRectangle%2A>. Ein <xref:System.Drawing.Graphics> Objekt verwaltet auch Grafikzustand, die in die folgenden Kategorien unterteilt werden können:  
  
-   Quality-Einstellungen  
  
-   Transformationen  
  
-   Clippingbereichs  
  
### <a name="quality-settings"></a>Quality-Einstellungen  
 Ein <xref:System.Drawing.Graphics> Objekt verfügt über verschiedene Eigenschaften, die die Qualität der Elemente beeinflussen, die gezeichnet werden. Sie können z. B. Festlegen der <xref:System.Drawing.Graphics.TextRenderingHint%2A> Eigenschaft, um den Typ des Antialiasing (sofern vorhanden) auf einen Text angewendete anzugeben. Andere Eigenschaften, die Qualität beeinflussen, sind <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, und <xref:System.Drawing.Graphics.InterpolationMode%2A>.  
  
 Im folgende Beispiel werden zwei Ellipsen, eine mit das Glättungsmodus gezeichnet <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> und eine mit das Glättungsmodus <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:  
  
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
 Ein <xref:System.Drawing.Graphics> -Objekt verwaltet zwei Transformationen (Seite und www), die für alle Elemente, die gezeichnet wird, angewendet werden <xref:System.Drawing.Graphics> Objekt. Alle affinen Transformationen kann in der globalen Transformation gespeichert werden. Affine Transformationen gehören Skalierung, drehen, spiegeln, neigen und übersetzen. Die Seitentransformation kann für die Skalierung sowie zum Ändern der Einheiten (z. B. in Pixel in Zoll) verwendet werden. Weitere Informationen finden Sie unter [Koordinatensysteme und Transformationen](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).  
  
 Im folgenden Beispiel wird die World Transformation und der Seitentransformation ein <xref:System.Drawing.Graphics> Objekt. Die globale Transformation wird auf einen Drehwinkel von 30 Grad festgelegt. Die Seitentransformation wird festgelegt, sodass die Koordinaten der zweiten übergeben <xref:System.Drawing.Graphics.DrawEllipse%2A> als Millimeter statt Pixel behandelt werden. Der Code enthält zwei identische Aufrufe der <xref:System.Drawing.Graphics.DrawEllipse%2A> Methode. Die globale Transformation wird angewendet, mit dem ersten <xref:System.Drawing.Graphics.DrawEllipse%2A> Aufruf, und beide Transformationen (Seite und www) gelten für die zweite <xref:System.Drawing.Graphics.DrawEllipse%2A> aufrufen.  
  
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
  
 Die folgende Abbildung zeigt zwei Ellipsen. Beachten Sie, dass die Drehung von 30 Grad, über den Ursprung des Koordinatensystems (linke obere Ecke des Clientbereichs), nicht über die Ressourcen der Schaltfläche mit den Auslassungszeichen ist. Beachten Sie außerdem, dass die Stiftbreite 1 für die zweite Ellipse 1 Pixel für die erste Ellipse und 1 Millimeter bedeutet.  
  
 ![Ovale](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")  
  
### <a name="clipping-region"></a>Clippingbereichs  
 Ein <xref:System.Drawing.Graphics> -Objekt verwaltet einen Ausschneidebereich, die für alle Elemente, die gezeichnet wird, gilt <xref:System.Drawing.Graphics> Objekt. Sie können den Ausschneidebereich festlegen, durch Aufrufen der <xref:System.Drawing.Graphics.SetClip%2A> Methode.  
  
 Das folgende Beispiel erstellt eine Region Plus geformten durch, die die Vereinigung zweier Rechtecke bilden. Diese Region wird als den Ausschneidebereich festgelegt, dass ein <xref:System.Drawing.Graphics> Objekt. Der Code zeichnet dann zwei Zeilen, die auf das Innere des Clippingbereichs beschränkt sind.  
  
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
  
 Die folgende Abbildung zeigt die Zeilen abgeschnitten.  
  
 ![Clip-Bereich beschränkt](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")  
  
## <a name="see-also"></a>Siehe auch  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Verwenden geschachtelter Grafikcontainer](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)
