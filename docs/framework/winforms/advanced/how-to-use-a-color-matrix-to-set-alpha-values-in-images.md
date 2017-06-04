---
title: "Gewusst wie: Verwenden einer Farbmatrix zum Festlegen von Alphawerten in Bildern | Microsoft Docs"
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
  - "Bitmaps [Windows Forms], Verwenden von Farbmatrizen für halbtransparente"
  - "Bilder [Windows Forms], Verwenden von Farbmatrizen für halbtransparente"
  - "Matrizen, Alphawerte"
  - "Transparenz, Farbmatrizen"
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Verwenden einer Farbmatrix zum Festlegen von Alphawerten in Bildern
Die <xref:System.Drawing.Bitmap>\-Klasse \(die von der <xref:System.Drawing.Image>\-Klasse erbt\) und die <xref:System.Drawing.Imaging.ImageAttributes>\-Klasse bieten Funktionen zum Abrufen und Festlegen von Pixelwerten.  Mithilfe der <xref:System.Drawing.Imaging.ImageAttributes>\-Klasse können Sie die Alphawerte für ein vollständiges Bild ändern. Alternativ können Sie auch die <xref:System.Drawing.Bitmap.SetPixel%2A>\-Methode der <xref:System.Drawing.Bitmap>\-Klasse aufrufen, um einzelne Pixelwerte zu ändern.  
  
## Beispiel  
 Die <xref:System.Drawing.Imaging.ImageAttributes>\-Klasse verfügt über zahlreiche Eigenschaften, mit denen Sie Bilder beim Rendern ändern können.  Im folgenden Beispiel wird für alle Alphawerte mithilfe eines <xref:System.Drawing.Imaging.ImageAttributes>\-Objekts 80 Prozent ihres Originalwerts festgelegt.  Dazu wird eine Farbmatrix initialisiert und als Wert für die Alphaskalierung in der Matrix 0,8 festgelegt.  Die Adresse der Farbmatrix wird an die <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A>\-Methode des <xref:System.Drawing.Imaging.ImageAttributes>\-Objekts und das <xref:System.Drawing.Imaging.ImageAttributes>\-Objekt an die <xref:System.Drawing.Graphics.DrawString%2A>\-Methode des <xref:System.Drawing.Graphics>\-Objekts übergeben.  
  
 Beim Rendern werden die Alphawerte in der Bitmap in den 80\-prozentigen Wert des Originals konvertiert.  Dies ergibt ein Bild, dessen Farben mit den Hintergrundfarben gemischt sind.  Wie in der folgenden Abbildung dargestellt, ist das Bitmapbild transparent; die durchgehende schwarze Linie scheint also durch.  
  
 ![Alphablending mit einer Matrix](../../../../docs/framework/winforms/advanced/media/image2.png "image2")  
  
 In Bereichen, in denen sich das Bild über dem weißen Bereich des Hintergrunds befindet, wurde das Bild mit der Farbe Weiß gemischt.  Dort, wo das Bild auf der schwarzen Linie liegt, wird es mit der Farbe Schwarz gemischt.  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Siehe auch  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Alphablending von Linien und Füllungen](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)