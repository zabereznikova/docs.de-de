---
title: 'Vorgehensweise: Ausfüllen einer Form mit einer Volltonfarbe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
ms.openlocfilehash: 576042d9d8e7a7f77d5375b7dfafafdc63b3e824
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601960"
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a>Vorgehensweise: Ausfüllen einer Form mit einer Volltonfarbe
Um eine Form mit einer Volltonfarbe zu füllen, erstellen Sie eine <xref:System.Drawing.SolidBrush> Objekt, und klicken Sie dann übergeben, die <xref:System.Drawing.SolidBrush> Objekt als Argument an eine der Füllmethoden der der <xref:System.Drawing.Graphics> Klasse. Das folgende Beispiel zeigt, wie Sie eine Ellipse mit der Farbe Rot zu füllen.  
  
## <a name="example"></a>Beispiel  
 In den folgenden Code der <xref:System.Drawing.SolidBrush.%23ctor%2A> Konstruktor akzeptiert ein <xref:System.Drawing.Color> Objekt als einziges Argument. Die Werte ein, die die <xref:System.Drawing.Color.FromArgb%2A> Methode darstellen, die alpha, roten, grünen und blauen-Komponenten der Farbe. Jeder dieser Werte muss im Bereich von 0 bis 255. Die ersten 255 gibt an, dass die Farbe vollständig deckend ist und das zweite 255 gibt an, dass die höchste Intensität der Rotanteil hat. Die zwei Nullen darauf hindeuten, dass die grünen und blauen Komponenten eine Intensität von 0.  
  
 Die vier Zahlen (0, 0, 100, 60), die an die <xref:System.Drawing.Graphics.FillEllipse%2A> Methode angeben, die Position und Größe des umschließenden Rechtecks für die Ellipse. Das Rechteck verfügt über einen oberen linken Ecke der (0, 0), einer Breite von 100 und einer Höhe von 60.  
  
 [!code-csharp[System.Drawing.UsingABrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch
- [Verwenden eines Pinsels zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
