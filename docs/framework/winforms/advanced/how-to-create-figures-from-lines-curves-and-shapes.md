---
title: 'Vorgehensweise: Erstellen von Figuren aus Linien, Kurven und Formen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: eeaf478375e08734b20d83b6f3c8030732495013
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224909"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a>Vorgehensweise: Erstellen von Figuren aus Linien, Kurven und Formen
Erstellen Sie zum Erstellen einer Figur eine <xref:System.Drawing.Drawing2D.GraphicsPath>, und rufen Sie anschließend die Methoden, wie z. B. <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> und <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, um primitive Typen in den Pfad hinzuzufügen.  
  
## <a name="example"></a>Beispiel  
 Die folgenden Codebeispiele erstellen Pfade, die Zahlen haben:  
  
-   Im erste Beispiel erstellt einen Pfad, der eine einzelne Figur enthält. In der Abbildung besteht aus einem einzelnen Bogen. Der Bogen hat bei einem mittelpunktswinkel von –180 Grad gegen den Uhrzeigersinn in das Standardkoordinatensystem ist.  
  
-   Im zweite Beispiel wird einen Pfad, der zwei Abbildungen wurde erstellt. Die erste Figur ist einen Bogen, gefolgt von einer Zeile. Die zweite Abbildung ist eine Zeile, gefolgt von einer Kurve, gefolgt von einer Zeile. Die erste Figur bleibt geöffnet, und die zweite Abbildung geschlossen ist.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 In den vorherigen Beispielen sind für die Verwendung mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [Erstellen und Zeichnen von Pfaden](constructing-and-drawing-paths.md)
- [Verwenden eines Stifts zum Zeichnen von Linien und Formen](using-a-pen-to-draw-lines-and-shapes.md)
