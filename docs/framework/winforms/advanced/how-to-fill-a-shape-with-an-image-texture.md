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
ms.openlocfilehash: bf1e09548ff9bc4eb650048eb21a9c300f3f6405
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601778"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a>Vorgehensweise: Ausfüllen einer Form mit einer Bildstruktur
Sie können eine geschlossene Form mit einer Textur eingeben, mit der <xref:System.Drawing.Image> Klasse und die <xref:System.Drawing.TextureBrush> Klasse.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Ellipse mit einem Bild. Der Code erstellt ein <xref:System.Drawing.Image> Objekt und übergibt dann die Adresse, die <xref:System.Drawing.Image> Objekt als Argument an eine <xref:System.Drawing.TextureBrush.%23ctor%2A> Konstruktor. Die dritte Anweisung wird das Bild skaliert, und die vierte Anweisung füllt, das die Ellipse mit wiederholte Kopien, von skalierten Bild.  
  
 In den folgenden Code der <xref:System.Drawing.TextureBrush.Transform%2A> Eigenschaft enthält die Transformation, die auf das Bild angewendet wird, bevor es gezeichnet wird. Wird davon ausgegangen Sie, dass das Originalbild einer Breite von 640 Pixeln und eine Höhe von 480 Pixel verfügt. Die Transformation wird der Abbildung auf 75 × 75 durch Festlegen der Werte für horizontale und vertikale Skalierung reduziert.  
  
> [!NOTE]
>  Im folgenden Beispiel die Bildgröße beträgt 75 × 75 und die Ellipse beträgt 150 × 250. Da das Image kleiner als die Ellipse, die es voll ist ist, wird die Ellipse mit dem Image gekachelt. Kacheln bedeutet, dass das Bild horizontal und vertikal bis zum Rand der Form wiederholt wird, wurde erreicht. Weitere Informationen zu Kacheln finden Sie unter [Vorgehensweise: Kacheln einer Form mit einem Bild](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch
- [Verwenden eines Pinsels zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
