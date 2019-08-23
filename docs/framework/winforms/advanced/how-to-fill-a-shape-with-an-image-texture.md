---
title: 'Vorgehensweise: Ausfüllen einer Form mit einer Bildstruktur'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: 42c456137f84c6fa657ba5a09727eae052a45376
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911688"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a>Vorgehensweise: Ausfüllen einer Form mit einer Bildstruktur
Sie können eine geschlossene Form mithilfe der <xref:System.Drawing.Image> -Klasse und der <xref:System.Drawing.TextureBrush> -Klasse mit einer Textur auffüllen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Ellipse mit einem Bild gefüllt. Der Code erstellt ein <xref:System.Drawing.Image> -Objekt und übergibt dann die Adresse dieses <xref:System.Drawing.Image> Objekts als Argument an einen <xref:System.Drawing.TextureBrush.%23ctor%2A> -Konstruktor. Die dritte Anweisung skaliert das Bild, und die vierte Anweisung füllt die Ellipse mit wiederholten Kopien des skalierten Bilds.  
  
 Im folgenden Code enthält die <xref:System.Drawing.TextureBrush.Transform%2A> -Eigenschaft die Transformation, die auf das Bild angewendet wird, bevor es gezeichnet wird. Angenommen, das ursprüngliche Bild hat eine Breite von 640 Pixeln und eine Höhe von 480 Pixel. Die Transformation verkleinert das Bild auf 75 × 75 durch Festlegen der horizontalen und vertikalen Skalierungs Werte.  
  
> [!NOTE]
> Im folgenden Beispiel ist die Bildgröße 75 × 75 und die Ellipse-Größe 150 × 250. Da das Bild kleiner als die Ellipse ist, die es füllt, wird die Ellipse mit dem Bild gekachelt. Das tiult bedeutet, dass das Bild horizontal und vertikal wiederholt wird, bis die Grenze der Form erreicht ist. Weitere Informationen zum tiult finden [Sie unter Gewusst wie: Kacheln Sie eine Form mit](how-to-tile-a-shape-with-an-image.md)einem Bild.  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das vorherige Beispiel wurde für die Verwendung mit Windows Forms entwickelt und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, was ein Parameter des- <xref:System.Windows.Forms.Control.Paint> Ereignis Handlers ist.  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden eines Pinsels zum Ausfüllen von Formen](using-a-brush-to-fill-shapes.md)
