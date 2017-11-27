---
title: Zuschneiden und Skalieren von Bildern in GDI+
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63e1e55e57d586cbbca87361b95c18f0f53b8c75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="cropping-and-scaling-images-in-gdi"></a>Zuschneiden und Skalieren von Bildern in GDI+
Können Sie die <xref:System.Drawing.Graphics.DrawImage%2A> Methode von der <xref:System.Drawing.Graphics> -Klasse gezeichnet werden soll, und Positionieren von Vektor- und Rasterbildern. <xref:System.Drawing.Graphics.DrawImage%2A>ist eine überladene Methode, damit es gibt mehrere Möglichkeiten, die sie mit Argumenten bereitstellen zu können.  
  
## <a name="drawimage-variations"></a>DrawImage-Varianten  
 Eine Variante der der <xref:System.Drawing.Graphics.DrawImage%2A> Methode empfängt einen <xref:System.Drawing.Bitmap> und ein <xref:System.Drawing.Rectangle>. Das Rechteck wird das Ziel für den Zeichenvorgang angibt; also gibt es das Rechteck in der das Bild gezeichnet werden soll. Wenn die Größe des Zielrechtecks von der Größe des dem ursprungsabbild unterscheidet, wird das Bild skaliert, um Zielrechtecks zu passen. Im folgenden Codebeispiel wird veranschaulicht, wie dasselbe Bild dreimal gezeichnet: einmal mit keine Skalierung, einmal mit einer Erweiterung und einmal mit einer Komprimierung:  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 Die folgende Abbildung zeigt die drei Bilder.  
  
 ![Skalierung](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")  
  
 Einige Varianten der der <xref:System.Drawing.Graphics.DrawImage%2A> Methode verfügen, einen Quellrechteck Parameter als auch ein Zielrechteck Parameter. Das Quellrechteck Parameter gibt an, die Teil des ursprünglichen Bilds gezeichnet werden soll. Das Zielrechteck gibt das Rechteck in der dieser Teil des Bilds gezeichnet werden soll. Wenn die Größe des Zielrechtecks von der Größe des Quellrechtecks abweicht, wird das Bild skaliert um Zielrechtecks zu passen.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen einer <xref:System.Drawing.Bitmap> aus der Datei Runner.jpg. Das gesamte Bild ohne Skalierung auf gezeichnet wird (0, 0). Und klicken Sie dann zweimal ein kleiner Teil des Bilds gezeichnet: einmal mit Komprimierung und einmal mit einer Erweiterung.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 Die folgende Abbildung zeigt nicht skalierten Bild und dem komprimierte und erweiterten Image Teile.  
  
 ![Zuschneiden und Skalieren von](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")  
  
## <a name="see-also"></a>Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
