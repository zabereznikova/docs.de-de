---
title: "Verwalten des Zustands eines Graphics-Objekts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Grafiken, Clipping"
  - "Grafiken, Verwalten des Zustands"
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Verwalten des Zustands eines Graphics-Objekts
Die <xref:System.Drawing.Graphics>\-Klasse ist eine zentrale Komponente von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  Zum Zeichnen rufen Sie ein <xref:System.Drawing.Graphics>\-Objekt ab, legen seine Eigenschaften fest und rufen die zugehörigen Methoden auf \(<xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A> u. ä.\).  
  
 Im folgenden Beispiel wird die <xref:System.Drawing.Graphics.DrawRectangle%2A>\-Methode eines <xref:System.Drawing.Graphics>\-Objekts aufgerufen.  Als erstes Argument wird ein <xref:System.Drawing.Pen>\-Objekt an die <xref:System.Drawing.Graphics.DrawRectangle%2A>\-Methode übergeben.  
  
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
  
## Grafikstatus  
 Ein <xref:System.Drawing.Graphics>\-Objekt stellt nicht nur Zeichenmethoden wie <xref:System.Drawing.Graphics.DrawLine%2A> und <xref:System.Drawing.Graphics.DrawRectangle%2A> bereit.  Das <xref:System.Drawing.Graphics>\-Objekt dient darüber hinaus zur Verwaltung des Grafikzustands, der in die folgenden Kategorien untergliedert werden kann:  
  
-   Qualitätseinstellungen  
  
-   Transformationen  
  
-   Clippingbereich  
  
### Qualitätseinstellungen  
 Ein <xref:System.Drawing.Graphics>\-Objekt verfügt über mehrere Eigenschaften, die die Qualität der gezeichneten Elemente beeinflussen.  Sie können beispielsweise die <xref:System.Drawing.Graphics.TextRenderingHint%2A>\-Eigenschaft festlegen, um den auf Text angewendeten Antialiasingtyp \(falls vorhanden\) anzugeben.  Andere Eigenschaften, die die Qualität beeinflussen, sind <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A> und <xref:System.Drawing.Graphics.InterpolationMode%2A>.  
  
 Im folgenden Beispiel werden zwei Ellipsen gezeichnet: eine mit dem Glättungsmodus <xref:System.Drawing.Drawing2D.SmoothingMode> und eine andere mit dem Glättungsmodus <xref:System.Drawing.Drawing2D.SmoothingMode>:  
  
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
  
### Transformationen  
 Durch ein <xref:System.Drawing.Graphics>\-Objekt werden zwei Transformationen verwaltet \(die globale Transformation und die Seitentransformation\), die auf alle von diesem <xref:System.Drawing.Graphics>\-Objekt gezeichneten Elemente angewendet werden.  In der globalen Transformation können alle affinen Transformationen gespeichert werden.  Zu den affinen Transformationen gehören Skalierung, Drehung, Spiegelung, Zerrung und Verschiebung.  Die Seitentransformation kann zum Skalieren sowie zum Ändern von Maßeinheiten \(z. B. von Pixel in Zoll\) verwendet werden.  Weitere Informationen finden Sie unter [Koordinatensysteme und Transformationen](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).  
  
 Im folgenden Beispiel werden die globale Transformation und die Seitentransformation eines <xref:System.Drawing.Graphics>\-Objekts festgelegt.  Die globale Transformation wird auf einen Drehwinkel von 30 Grad eingestellt.  Die Seitentransformation wird so definiert, dass die an die zweite <xref:System.Drawing.Graphics.DrawEllipse%2A>\-Methode übergebenen Koordinaten als Millimeter behandelt werden und nicht als Pixel.  Der Code enthält zwei identische Aufrufe der <xref:System.Drawing.Graphics.DrawEllipse%2A>\-Methode.  Die globale Transformation wird lediglich auf den ersten <xref:System.Drawing.Graphics.DrawEllipse%2A>\-Aufruf angewendet, während auf den zweiten <xref:System.Drawing.Graphics.DrawEllipse%2A>\-Aufruf beide Transformationen \(globale Transformation und Seitentransformation\) angewendet werden.  
  
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
  
 In der folgenden Abbildung sind die beiden Ellipsen dargestellt.  Beachten Sie, dass die 30\-Grad\-Drehung um den Ursprung des Koordinatensystems \(obere linke Ecke des Clientbereichs\) und nicht um die Mittelpunkte der Ellipsen erfolgt.  Außerdem bedeutet die Stiftbreite 1, dass für die erste Ellipse 1 Pixel und für die zweite Ellipse 1 Millimeter verwendet wird.  
  
 ![Ovale](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")  
  
### Clippingbereich  
 Durch das <xref:System.Drawing.Graphics>\-Objekt wird ein Clippingbereich verwaltet, der für alle von diesem <xref:System.Drawing.Graphics>\-Objekt gezeichneten Elemente gültig ist.  Der Clippingbereich kann durch Aufrufen der <xref:System.Drawing.Graphics.SetClip%2A>\-Methode festgelegt werden.  
  
 Im folgenden Beispiel wird ein Bereich in Form eines Pluszeichens gebildet, indem zwei Rechtecke zusammengeführt werden.  Dieser Bereich wird als Clippingbereich eines <xref:System.Drawing.Graphics>\-Objekts bezeichnet.  Anschließend werden durch den Code zwei Linien gezeichnet, die auf den Innenbereich des Clippingbereichs beschränkt sind.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](../../../../amples/snippets/visualbasic/VS_Snippets_Wpf/ToolBarOrient_snip/visualbasic/toolbargraphics/new.bmp Rectangle(50, 0, 50, 150))  
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
  
 In der folgenden Abbildung sind die abgeschnittenen Linien dargestellt.  
  
 ![Beschränkter Clip&#45;Bereich](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")  
  
## Siehe auch  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Verwenden geschachtelter Grafikcontainer](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)