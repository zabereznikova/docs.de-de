---
title: "Gewusst wie: Zeichnen einer vorhandenen Bitmap auf dem Bildschirm | Microsoft Docs"
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
  - "Bitmaps [Windows Forms], Anzeigen in Windows Forms"
  - "Bitmaps [Windows Forms], Laden in Windows Forms-Anwendungen"
  - "Bilder [Windows Forms], Anzeigen in Windows Forms"
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Zeichnen einer vorhandenen Bitmap auf dem Bildschirm
Sie können leicht ein vorhandenes Bild auf dem Bildschirm zeichnen.  Zuerst müssen Sie ein <xref:System.Drawing.Bitmap>\-Objekt mit dem Bitmapkonstruktor erstellen, der einen Dateinamen erhält \(<xref:System.Drawing.Bitmap.%23ctor%28System.String%29>\).  Der Konstruktor akzeptiert Bilder in unterschiedlichen Dateiformaten, darunter BMP, GIF, JPEG, JPG, PNG und TIFF.  Erstellen Sie das <xref:System.Drawing.Bitmap>\-Objekt, und übergeben Sie dieses <xref:System.Drawing.Bitmap>\-Objekt an die <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode eines <xref:System.Drawing.Graphics>\-Objekts.  
  
## Beispiel  
 In diesem Beispiel wird erst ein <xref:System.Drawing.Bitmap>\-Objekt aus einer JPEG\-Datei erstellt, und anschließend wird die Bitmap mit der oberen linken Ecke an der Position \(60, 10\) gezeichnet.  
  
 In der folgenden Abbildung wird gezeigt, wie die Bitmap an der angegebenen Position gezeichnet wird.  
  
 ![Bildposition](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  
  
## Siehe auch  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)