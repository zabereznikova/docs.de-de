---
title: 'Vorgehensweise: Zuschneiden und Skalieren von Bildern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
ms.openlocfilehash: 95343ad2c7bc6a83bc4d935f33712ab910d658ff
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705817"
---
# <a name="how-to-crop-and-scale-images"></a>Vorgehensweise: Zuschneiden und Skalieren von Bildern
Die <xref:System.Drawing.Graphics> Klasse bietet mehrere <xref:System.Drawing.Graphics.DrawImage%2A> Methoden, von denen einige über die Parameter für Quell- und Ziel, die Sie zum Zuschneiden und Skalieren von Bildern verwenden können.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datenträgerdatei Apple.gif. Der Code zeichnet das gesamte Apple-Bild in seiner ursprünglichen Größe. Der Code ruft dann die <xref:System.Drawing.Graphics.DrawImage%2A> Methode eine <xref:System.Drawing.Graphics> Objekt, das einen Teil des Apple-Images in einem Zielrechteck zu zeichnen, die größer als das Originalbild von Apple.  
  
 Die <xref:System.Drawing.Graphics.DrawImage%2A> Methode bestimmt, welcher Teil der Apple zu zeichnenden unter Verwendung des fünften und sechsten Argumente. In diesem Fall wird die Apple 75 Prozent der Breite und 75 Prozent seiner Höhe zugeschnitten.  
  
 Die <xref:System.Drawing.Graphics.DrawImage%2A> -Methode bestimmt, wo Sie zugeschnittene Apple gezeichnet werden soll und wie groß, um die zugeschnittenen Apfels anhand des Zielrechtecks, dies ist durch das zweite Argument angegeben. In diesem Fall ist das Zielrechteck, 30 Prozent breiter und 30 Prozent höher als das Originalbild.  
  
 Die folgende Abbildung zeigt die ursprünglichen Apple und die skalierte Apple zugeschnitten.  
  
 ![Zuschneiden und skalieren](./media/cscropscale1.png "csCropScale1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers. Achten Sie darauf, ersetzen Sie dies `Apple.gif` mit einer Bilddateinamen und den Pfad, die auf Ihrem System gültig sind.  
  
## <a name="see-also"></a>Siehe auch
- [Bilder, Bitmaps und Metadateien](images-bitmaps-and-metafiles.md)
- [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](working-with-images-bitmaps-icons-and-metafiles.md)
