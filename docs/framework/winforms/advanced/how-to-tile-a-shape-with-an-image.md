---
title: 'Gewusst wie: Kacheln einer Form mit einem Bild'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
ms.openlocfilehash: 0905f29b0f74c72979e252cf94e677d1c7e0525d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523122"
---
# <a name="how-to-tile-a-shape-with-an-image"></a>Gewusst wie: Kacheln einer Form mit einem Bild
Wie Kacheln eine Etage abdecken nebeneinander platziert werden können, können rechteckige Bilder zum Füllen (Kachel) eine Form vom Typ nebeneinander platziert werden. Um das Innere einer Form gekachelt, verwenden Sie einen Strukturpinsel. Bei der Erstellung einer <xref:System.Drawing.TextureBrush> Objekt eines der Argumente, die Sie an den Konstruktor übergeben, wird ein <xref:System.Drawing.Image> Objekt. Wenn Sie die Strukturpinsel verwenden, um das Innere einer Form zu zeichnen, wird die Form mit wiederholten Kopien dieses Bild gefüllt.  
  
 Der Wrap-Mode-Eigenschaft von der <xref:System.Drawing.TextureBrush> Objekt bestimmt, wie das Bild ausgerichtet ist, da es in einem rechteckigen Raster wiederholt wird. Können Sie alles, was die Kacheln im Raster sind die gleiche Ausrichtung vornehmen können, oder Sie das Image von einer Rasterseite Position zur nächsten kippen. Die kippen kann horizontal, vertikal oder beides. Die folgenden Beispiele zeigen die Kacheln mit verschiedenen Typen von spiegeln.  
  
### <a name="to-tile-an-image"></a>Um ein Bild Kachel  
  
-   In diesem Beispiel verwendet Abbildung 75 × 75, um ein Rechteck 200 x 200 Kachel.  
  
 ![Kachel 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")  
  
-   Die folgende Abbildung zeigt, wie das Rechteck mit dem Bild gekachelt wird. Beachten Sie, dass alle Kacheln dieselbe Ausrichtung haben. Es gibt keine ein umlegen.  
  
 ![Kachel 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a>Um ein Bild Kacheln horizontal gekippt.  
  
-   Dieses Beispiel verwendet das gleiche 75 × 75 Bild zum Ausfüllen eines Rechtecks 200 x 200. Der Wrap-Modus festgelegt ist, das Bild horizontal gekippt. Die folgende Abbildung zeigt, wie das Rechteck mit dem Bild gekachelt wird. Beachten Sie, wie Sie eine Kachel zur nächsten in einer bestimmten Zeile verschieben, wird das Bild horizontal gekippt.  
  
 ![Kachel 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a>Um ein Bild Kacheln vertikal kippen  
  
-   Dieses Beispiel verwendet das gleiche 75 × 75 Bild zum Ausfüllen eines Rechtecks 200 x 200. Der Wrap-Modus festgelegt ist, das Bild vertikal gekippt.  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a>Um ein Bild Kacheln horizontal und vertikal kippen  
  
-   In diesem Beispiel verwendet dasselbe 75 × 75 Bild, um ein Rechteck 200 x 200 Kachel. Der Umbruchmodus wird festgelegt, um das Bild horizontal und vertikal gekippt. Die folgende Abbildung zeigt, wie das Rechteck mit dem Bild gekachelt wird. Beachten Sie, wie Sie eine Kachel zur nächsten in einer bestimmten Zeile verschieben, wird das Bild horizontal gekippt, und wie Sie eine Kachel zur nächsten in einer bestimmten Spalte verschieben, wird das Bild vertikal gekippt.  
  
 ![Kachel 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden eines Pinsels zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
