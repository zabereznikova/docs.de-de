---
title: 'Vorgehensweise: Ausfüllen offener Körper'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: addcf959e429974b9306353abb743bb2bb3114e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781433"
---
# <a name="how-to-fill-open-figures"></a>Vorgehensweise: Ausfüllen offener Körper
Sie können einen Pfad eingeben, durch Übergeben einer <xref:System.Drawing.Drawing2D.GraphicsPath> -Objekt an die <xref:System.Drawing.Graphics.FillPath%2A> Methode. Die <xref:System.Drawing.Graphics.FillPath%2A> Methode füllt den Pfad entsprechend der Füllmodus (alternative oder wicklungsreihenfolgen), die derzeit für den Pfad festgelegt. Wenn der Pfad offener Körper enthält, wird der Pfad gefüllt, als ob diese Zahlen geschlossen wurden. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Schließt eine Abbildung durch Zeichnen einer geraden Linie vom Endpunkt zum Ausgangspunkt erforderlich.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt einen Pfad an, der eine offene Form (einen Bogen) und eine geschlossene Form (eine Ellipse) verfügt. Die <xref:System.Drawing.Graphics.FillPath%2A> Methode füllt den Pfad entsprechend der Standardmodus für die Füllung, handelt es sich <xref:System.Drawing.Drawing2D.FillMode.Alternate>.  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispielcodes. Beachten Sie, dass der Pfad gefüllt wird (gemäß <xref:System.Drawing.Drawing2D.FillMode.Alternate>), als ob der geöffnete Figur mit einer geraden Linie vom Endpunkt zum Ausgangspunkt geschlossen wurden.  
  
 ![Diagramm die Ausgabe der FillPath-Methode zeigt](./media/how-to-fill-open-figures/fill-path-alternate-mode.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [Grafikpfade in GDI+](graphics-paths-in-gdi.md)
