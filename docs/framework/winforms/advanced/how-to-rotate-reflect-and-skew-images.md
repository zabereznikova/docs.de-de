---
title: 'Vorgehensweise: Drehen, Spiegeln und Neigen von Bildern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 80ac92d545d9be7a4a611038eaaadbbdbe2e8ecf
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590323"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>Vorgehensweise: Drehen, Spiegeln und Neigen von Bildern
Sie können zu drehen, spiegeln und neigen ein Image, indem Zielpunkte für die oberen linken, oberen rechten und unteren linken Ecke des ursprünglichen Bilds. Die drei Zielpunkte bestimmen eine affine Transformation, die ein Parallelogramm das Originalbild rechteckige zuordnet.  
  
## <a name="example"></a>Beispiel  
 Nehmen wir beispielsweise an, die das ursprüngliche Bild ist ein Rechteck mit der linken oberen Ecke auf (0, 0) oben rechts auf (100, 0), und der unteren linken Ecke an ("0", "50"). Jetzt angenommen, das Sie zuordnen, die Punkte drei Zielpunkte wie folgt.  
  
|Ursprüngliche Punkt|Ziel|  
|--------------------|-----------------------|  
|Linke obere (0, 0)|(200, 20)|  
|Rechts ("100", "0")|(110, 100)|  
|Unteren linken ("0", "50")|(250, 30)|  
  
 Die folgende Abbildung zeigt das ursprüngliche Bild und das Bild, das dem Parallelogramm zugeordnet. Das ursprüngliche Bild hat verzerrt, wiedergegeben, gedreht, übersetzt und. Die Zeile, die ausgeführt, über wird die x-Achse entlang des oberen Randes des ursprünglichen Bilds zugeordnet ist ("200", "20") und (110, 100). Die Zeile, die ausgeführt, über wird die y-Achse entlang des linken Randes des ursprünglichen Bilds zugeordnet ist ("200", "20") und (250, 30).  
  
 ![Das ursprüngliche Bild und das Bild, das dem Parallelogramm zugeordnet.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-illustration.gif)  
  
 Die folgende Abbildung zeigt eine ähnliche Transformation angewendet auf ein Foto an:  
  
 ![Das Bild, der einen Anstieg und das Bild, das dem Parallelogramm zugeordnet werden soll.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-photo.png)  
  
 Die folgende Abbildung zeigt eine ähnliche Transformation, die auf einer Metadatei angewendet:  
  
 ![Abbildung von Formen, Text und dem Parallelogramm zugeordnet.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-metafile.png)  
  
 Im folgenden Beispiel wird die Bilder in der ersten Abbildung gezeigt.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler. Achten Sie darauf, ersetzen Sie dies `Stripes.bmp` durch den Pfad zu einem Bild, das auf Ihrem System gültig ist.  
  
## <a name="see-also"></a>Siehe auch

- [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](working-with-images-bitmaps-icons-and-metafiles.md)
