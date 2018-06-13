---
title: 'Gewusst wie: Ausfüllen einer Form mit einer Volltonfarbe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
ms.openlocfilehash: 7f719417a6a1226d7dc4d600518711ba31920a6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521322"
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a>Gewusst wie: Ausfüllen einer Form mit einer Volltonfarbe
Um eine Form mit einer Volltonfarbe auszufüllen, erstellen Sie eine <xref:System.Drawing.SolidBrush> Objekts, und übergeben Sie, die <xref:System.Drawing.SolidBrush> Objekt als Argument an eine der Füllmethoden der der <xref:System.Drawing.Graphics> Klasse. Im folgende Beispiel wird gezeigt, wie eine Ellipse, die mit der Farbe Rot ausgefüllt wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code wird die <xref:System.Drawing.SolidBrush.%23ctor%2A> Konstruktor akzeptiert ein <xref:System.Drawing.Color> Objekt als einziges Argument. Die Werte von verwendet die <xref:System.Drawing.Color.FromArgb%2A> Methode darstellen, die alpha, Rot-, Grün- und blauen-Komponenten der Farbe. Jeder dieser Werte muss im Bereich von 0 bis 255. Die ersten 255 gibt an, dass die Farbe vollständig deckend ist, und das zweite 255 gibt an, dass die rote Komponente mit voller Intensität. Die zwei Nullen anzugeben, dass die Komponenten grünen und blauen eine Intensität von 0 haben.  
  
 Die vier Ziffern (0, 0, 100, 60) übergeben, um die <xref:System.Drawing.Graphics.FillEllipse%2A> Methode geben Sie die Position und Größe des umschließenden Rechtecks für die Ellipse. Das Rechteck verfügt über einen oberen linken Ecke des (0, 0), einer Breite von 100 und einer Höhe von 60.  
  
 [!code-csharp[System.Drawing.UsingABrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden eines Pinsels zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
