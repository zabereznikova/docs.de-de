---
title: "Zeichnen, Positionieren und Klonen von Bildern in GDI+ | Microsoft Docs"
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
  - "Zeichnen, Bilder"
  - "Zeichnen, Rasterbilder"
  - "GDI+, Klonen von Bildern"
  - "GDI+, Zeichnen von Bildern"
  - "GDI+, Positionieren von Bildern"
  - "Bilder [Windows Forms], Klonen"
  - "Bilder [Windows Forms], Zeichnen"
  - "Bilder [Windows Forms], Positionieren"
  - "Rasterbilder"
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Zeichnen, Positionieren und Klonen von Bildern in GDI+
Zum Laden und Anzeigen von Rasterbildern verwenden Sie die <xref:System.Drawing.Bitmap>\-Klasse und zum Laden und Anzeigen von Vektorbildern die <xref:System.Drawing.Imaging.Metafile>\-Klasse.  Die Klassen <xref:System.Drawing.Bitmap> und <xref:System.Drawing.Imaging.Metafile> erben von der <xref:System.Drawing.Image>\-Klasse.  Zum Anzeigen eines Vektorbildes benötigen Sie eine Instanz der <xref:System.Drawing.Graphics>\-Klasse und <xref:System.Drawing.Imaging.Metafile>.  Zum Anzeigen eines Rasterbildes benötigen Sie eine Instanz der <xref:System.Drawing.Graphics>\-Klasse und <xref:System.Drawing.Bitmap>.  Die Instanz der <xref:System.Drawing.Graphics>\-Klasse stellt die <xref:System.Drawing.Graphics.DrawImage%2A>\-Methode bereit, die <xref:System.Drawing.Imaging.Metafile> oder <xref:System.Drawing.Bitmap> als Argument erhält.  
  
## Dateitypen und Klonen  
 Das folgende Codebeispiel veranschaulicht, wie Sie aus der Datei Climber.jpg eine <xref:System.Drawing.Bitmap> erstellen und die Bitmap anzeigen.  Der Zielpunkt \(10, 10\) für die linke obere Ecke des Bildes wird im zweiten und dritten Parameter angegeben.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 Die folgende Abbildung zeigt dieses Bild.  
  
 ![Bildbeispiel](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.png "AboutGdip03\_Art04")  
  
 Sie können <xref:System.Drawing.Bitmap>\-Objekte aus einer Vielzahl von Grafikdateiformaten erstellen: BMP, GIF, JPEG, EXIF, PNG, TIFF und ICON.  
  
 Im folgenden Codebeispiel wird die Erstellung von <xref:System.Drawing.Bitmap>\-Objekten aus einer Vielzahl von Dateitypen sowie die Anzeige der Bitmaps veranschaulicht.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 Die <xref:System.Drawing.Bitmap>\-Klasse stellt eine <xref:System.Drawing.Bitmap.Clone%2A>\-Methode bereit, mit der Sie eine Kopie eines vorhandenen <xref:System.Drawing.Bitmap>\-Objekts erstellen können.  Die <xref:System.Drawing.Bitmap.Clone%2A>\-Methode weist einen Parameter für ein Quellrechteck auf, mit dem Sie den Teil der ursprünglichen Bitmap angeben können, der kopiert werden soll.  Im folgenden Codebeispiel wird veranschaulicht, wie Sie ein <xref:System.Drawing.Bitmap>\-Objekt erstellen, indem Sie die obere Hälfte eines vorhandenen <xref:System.Drawing.Bitmap>\-Objekts klonen.  Anschließend werden beide Bilder gezeichnet.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 Die folgende Abbildung zeigt die beiden Bilder.  
  
 ![Zuschneiden](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.png "AboutGdip03\_Art05")  
  
## Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Gewusst wie: Erstellen von Graphics\-Objekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)