---
title: 'Gewusst wie: Erstellen von Figuren aus Linien, Kurven und Formen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: 222245fa4b3b593e0a38752a8cb991a12e469698
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a>Gewusst wie: Erstellen von Figuren aus Linien, Kurven und Formen
Um eine Figur zu erstellen, erstellen Sie eine <xref:System.Drawing.Drawing2D.GraphicsPath>, und rufen Sie Methoden, wie z. B. <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> und <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, um den Pfad Primitive hinzuzufügen.  
  
## <a name="example"></a>Beispiel  
 Die folgenden Codebeispiele erstellen Pfade, die Formen aufweisen:  
  
-   Im erste Beispiel erstellt einen Pfad mit einer einzelnen Abbildung. Die Abbildung besteht aus einem einzelnen Bogen. Der Bogen hat bei einem mittelpunktswinkel von –180 Grad, also in der Standardeinstellung Koordinatensystem gegen den Uhrzeigersinn.  
  
-   Im zweite Beispiel wird einen Pfad, der zwei Zahlen wurde erstellt. Die erste Abbildung ist einen Bogen, gefolgt von einer Zeile. Die zweite Abbildung ist eine Zeile, gefolgt von einer Kurve, gefolgt von einer Zeile. In der ersten Abbildung bleibt geöffnet, und die zweite Abbildung geschlossen wird.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 In den vorherigen Beispielen sind für die Verwendung mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [Erstellen und Zeichnen von Pfaden](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)  
 [Verwenden eines Stifts zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
