---
title: 'Gewusst wie: Verbessern der Leistung durch das Vermeiden der automatischen Skalierung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
ms.openlocfilehash: e1c46f805b7ba2e2f2a1eb52042cc2ca08e63e03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523041"
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a>Gewusst wie: Verbessern der Leistung durch das Vermeiden der automatischen Skalierung
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ein Bild kann automatisch skaliert werden, wie Sie es zeichnen. Alternativ können Sie steuern, die Skalierung des Bilds durch Übergeben der Dimensionen des Zielrechtecks an die <xref:System.Drawing.Graphics.DrawImage%2A> Methode.  
  
 Beispielsweise beim folgenden Aufruf der <xref:System.Drawing.Graphics.DrawImage%2A> Methode gibt einen oberen linken Ecke des (50, 30) aber keine Zielrechtecks an.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 Obwohl dies die einfachste Version ist die <xref:System.Drawing.Graphics.DrawImage%2A> Methode im Hinblick auf die Anzahl der erforderlichen Argumente, es ist nicht unbedingt die effizienteste. Wenn die Auflösung von verwendet [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] (in der Regel 96 dpi) unterscheidet sich von der Auflösung, die in gespeicherten der <xref:System.Drawing.Image> -Objekt, und klicken Sie dann die <xref:System.Drawing.Graphics.DrawImage%2A> Methode wird das Bild skaliert. Nehmen wir beispielsweise an ein <xref:System.Drawing.Image> Objekt verfügt über eine Breite von 216 Pixel und einen Wert gespeicherte horizontalen Auflösung von 72 Punkte pro Zoll. Da 216/72 3, ist <xref:System.Drawing.Graphics.DrawImage%2A> wird skaliert das Bild, sodass er eine Breite von 3 Zoll bei einer Auflösung von 96 DPI-Wert aufweist. D. h. <xref:System.Drawing.Graphics.DrawImage%2A> zeigt ein Image mit einer Breite von 96 × 3 = 288 Pixel.  
  
 Selbst wenn die Bildschirmauflösung von 96 dpi unterscheidet [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] wahrscheinlich Skalierung das Bild als wären die Bildschirmauflösung 96 dpi. Grund hierfür ist, eine [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> Objekt bezieht sich auf einen Gerätekontext und wann [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Abfragen, die der Gerätekontext für die Auflösung des Bildschirms, das Ergebnis wird in der Regel 96, unabhängig von der tatsächlichen Bildschirmauflösung. Sie können die automatische Skalierung durch Angabe des Zielrechtecks im Vermeiden der <xref:System.Drawing.Graphics.DrawImage%2A> Methode.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel werden zweimal dasselbe Bild gezeichnet. Im ersten Fall die Breite und Höhe des Zielrechtecks nicht angegeben wurden, und das Bild wird automatisch skaliert. Im zweiten Fall sind die Breite und Höhe (gemessen in Pixel) des Zielrechtecks identisch sein, als die Breite und Höhe des ursprünglichen Bilds angegeben. Die folgende Abbildung zeigt das Bild zweimal gerendert.  
  
 ![Skalierte Struktur](../../../../docs/framework/winforms/advanced/media/csscaledtexture1.png "csscaledtexture1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers. Ersetzen Sie Texture.jpg durch ein Image-Name und Pfad, die auf Ihrem System gültig sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
