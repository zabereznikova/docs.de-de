---
title: 'Gewusst wie: Ausfüllen einer Form mit einer Bildstruktur'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: c1eb090bebcced125193c1db16087b6165d27ff3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523289"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a>Gewusst wie: Ausfüllen einer Form mit einer Bildstruktur
Sie können mit einer Textur eine geschlossene Form ausfüllen, mithilfe der <xref:System.Drawing.Image> Klasse und die <xref:System.Drawing.TextureBrush> Klasse.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel füllt eine Ellipse mit einem Bild. Der Code erstellt ein <xref:System.Drawing.Image> -Objekt und übergibt dann die Adresse des, <xref:System.Drawing.Image> Objekt als Argument an einen <xref:System.Drawing.TextureBrush.%23ctor%2A> Konstruktor. Die dritte Anweisung wird das Bild skaliert, und die vierte Anweisung füllt die Ellipse mit Kopien der skalierten Bildes gekachelt.  
  
 Im folgenden Code wird die <xref:System.Drawing.TextureBrush.Transform%2A> Eigenschaft enthält die Transformation, die auf das Abbild angewendet wird, bevor es gezeichnet wird. Wird davon ausgegangen Sie, dass das ursprüngliche Bild einer Breite von 640 Pixel und eine Höhe von 480 Pixel verfügt. Die Transformation verkleinert das Bild auf 75 × 75, durch die horizontale und vertikale Skalierung Werte festlegen.  
  
> [!NOTE]
>  Im folgenden Beispiel die Bildgröße beträgt 75 × 75, und die Ellipse-Größe beträgt 150 × 250. Da das Bild kleiner als die Ellipse, die es ausfüllt ist, wird der Ellipse, die mit dem Image angeordnet. Kacheln bedeutet, dass das Bild horizontal und vertikal bis die Begrenzung der Form wiederholt wird, wurde erreicht. Weitere Informationen zu Kacheln finden Sie unter [wie: Kacheln einer Form mit einem Bild](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden eines Pinsels zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
