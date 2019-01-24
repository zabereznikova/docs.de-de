---
title: 'Vorgehensweise: Drehen, spiegeln und Zerren von Bildern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 2150e7797095b88227b499ec5481a3ce521270e9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667910"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>Vorgehensweise: Drehen, spiegeln und Zerren von Bildern
Sie können zu drehen, spiegeln und neigen ein Image, indem Zielpunkte für die oberen linken, oberen rechten und unteren linken Ecke des ursprünglichen Bilds. Die drei Zielpunkte bestimmen eine affine Transformation, die ein Parallelogramm das Originalbild rechteckige zuordnet.  
  
## <a name="example"></a>Beispiel  
 Nehmen wir beispielsweise an, die das ursprüngliche Bild ist ein Rechteck mit der linken oberen Ecke auf (0, 0) oben rechts auf (100, 0), und der unteren linken Ecke an ("0", "50"). Jetzt angenommen, das Sie zuordnen, die Punkte drei Zielpunkte wie folgt.  
  
|Ursprüngliche Punkt|Ziel|  
|--------------------|-----------------------|  
|Linke obere (0, 0)|(200, 20)|  
|Rechts ("100", "0")|(110, 100)|  
|Unteren linken ("0", "50")|(250, 30)|  
  
 Die folgende Abbildung zeigt das ursprüngliche Bild und das Bild, das dem Parallelogramm zugeordnet. Das ursprüngliche Bild hat verzerrt, wiedergegeben, gedreht, übersetzt und. Die Zeile, die ausgeführt, über wird die x-Achse entlang des oberen Randes des ursprünglichen Bilds zugeordnet ist ("200", "20") und (110, 100). Die Zeile, die ausgeführt, über wird die y-Achse entlang des linken Randes des ursprünglichen Bilds zugeordnet ist ("200", "20") und (250, 30).  
  
 ![Streifen](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")  
  
 Die folgende Abbildung zeigt eine ähnliche Transformation angewendet auf ein Foto.  
  
 ![Transformiert Anstieg](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")  
  
 Die folgende Abbildung zeigt eine ähnliche Transformation angewendet auf einer Metadatei an.  
  
 ![Transformiert die Metadatei](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")  
  
 Im folgenden Beispiel wird die Bilder in der ersten Abbildung gezeigt.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler. Achten Sie darauf, ersetzen Sie dies `Stripes.bmp` durch den Pfad zu einem Bild, das auf Ihrem System gültig ist.  
  
## <a name="see-also"></a>Siehe auch
- [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
