---
title: 'Vorgehensweise: Verwenden des Interpolationsmodus zum Steuern der Bildqualität während der Skalierung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: ab0ff93b3ee26467c0de448efd31b698167f95c2
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505716"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a>Vorgehensweise: Verwenden des Interpolationsmodus zum Steuern der Bildqualität während der Skalierung
Der Interpolationsmodus eine <xref:System.Drawing.Graphics> Objekt beeinflusst die Möglichkeit GDI + (erstreckt und Verkleinerung) Bilder skaliert. Die <xref:System.Drawing.Drawing2D.InterpolationMode> -Enumeration definiert mehrere Interpolationsmodi, von denen einige sind in der folgenden Liste:  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 Um ein Bild ein stretching durchzuführen, muss jedes Pixel in das ursprüngliche Image für eine Gruppe von Pixel im größeren Bild zugeordnet werden. Um ein Bild zu verkleinern, müssen die Gruppen der Pixel in das ursprüngliche Bild auf einzelnen Pixel in die kleinere Grafik zugeordnet werden. Die Effektivität der Algorithmen, die diese Zuordnungen ausführen bestimmt die Qualität der einem skalierten Bild. Algorithmen, die skalierte Bilder von höherer Qualität produzieren tendenziell mehr Verarbeitungszeit erfordern. In der obigen Liste <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> ist der niedrigste Qualität-Modus und <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> ist der Modus mit der höchsten Qualität.  
  
 Zum Festlegen des Interpolationsmodus weisen Sie einem Mitglied des von der <xref:System.Drawing.Drawing2D.InterpolationMode> Enumeration, die <xref:System.Drawing.Graphics.InterpolationMode%2A> Eigenschaft eine <xref:System.Drawing.Graphics> Objekt.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel zeichnet ein Bild, und klicken Sie dann verkleinert das Image mit drei verschiedenen Interpolationsmodi.  
  
 Die folgende Abbildung zeigt das ursprüngliche Bild und drei kleinere Bilder.  
  
 ![Screenshot, der ein Bild mit interpolationseinstellungen anzeigt.](./media/how-to-use-interpolation-mode-to-control-image-quality-during-scaling/varied-interpolation-settings.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch

- [Bilder, Bitmaps und Metadateien](images-bitmaps-and-metafiles.md)
- [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](working-with-images-bitmaps-icons-and-metafiles.md)
