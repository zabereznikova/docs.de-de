---
title: 'Gewusst wie: Verwenden des Interpolationsmodus zum Steuern der Bildqualität während der Skalierung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: 72a9cb3a19f0d449dcb376a65f1734b79ed61ab9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a>Gewusst wie: Verwenden des Interpolationsmodus zum Steuern der Bildqualität während der Skalierung
Der Interpolationsmodus eine <xref:System.Drawing.Graphics> Objekt beeinflusst die Möglichkeit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Bilder skaliert (gestreckt bzw. verkleinert). Die <xref:System.Drawing.Drawing2D.InterpolationMode> -Enumeration definiert mehrere Interpolationsmodi, von denen einige sind in der folgenden Liste:  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 Um ein Bild gestreckt wird, muss jedes Pixels in das ursprüngliche Image für eine Gruppe von Pixel im größeren Bild zugeordnet werden. Um ein Bild zu verkleinern, müssen Gruppen von Pixeln in das ursprüngliche Image auf einzelnen Pixel im kleineren Bild zugeordnet werden. Die Effektivität der Algorithmen, die diese Zuordnungen ausführen bestimmt die Qualität eines skalierte Images. Algorithmen, die skalierte Bilder von höherer Qualität produzieren tendenziell mehr Verarbeitungszeit erfordern. In der vorangehenden Liste <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> ist der niedrigste Qualität-Modus und <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> Modus mit der höchsten Qualität ist.  
  
 Um den Interpolationsmodus festzulegen, weisen Sie einem der Mitglieder von der <xref:System.Drawing.Drawing2D.InterpolationMode> -Enumeration der <xref:System.Drawing.Graphics.InterpolationMode%2A> Eigenschaft ein <xref:System.Drawing.Graphics> Objekt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel zeichnet ein Bild, und klicken Sie dann mit drei verschiedenen Interpolationsmodi verkleinert wird.  
  
 Die folgende Abbildung zeigt das ursprüngliche Bild und die drei kleinere Bilder.  
  
 ![Bild mit Interpolationseinstellungen](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
