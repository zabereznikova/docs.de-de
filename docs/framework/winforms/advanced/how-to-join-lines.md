---
title: 'Vorgehensweise: Verknüpfen von Linien'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
ms.openlocfilehash: a95ccddd89c85c5439c4d73f77a6ed67198dc7ba
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709862"
---
# <a name="how-to-join-lines"></a>Vorgehensweise: Verknüpfen von Linien
Ein Join für die Zeile ist die gemeinsamen Bereich, der zwei Zeilen gebildet wird, deren Enden erfüllen oder sich überlappen. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet drei: Linienverbindungsstile, Abschrägung und runden. Linienverbindungsstil ist eine Eigenschaft der <xref:System.Drawing.Pen> Klasse. Wenn Sie einen Linienstil für die Verknüpfung für angeben einer <xref:System.Drawing.Pen> -Objekt, dass für alle verbundenen Linien in einem Join-Format angewendet wird <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt mit diesem Stift gezeichnet.  
  
 Die folgende Abbildung zeigt die Ergebnisse des Beispiels Join abgeschrägte Zeile.  
  
 ![Stifte](./media/pens5.gif "pens5")  
  
## <a name="example"></a>Beispiel  
 Sie können die Linienart für den Join angeben, indem die <xref:System.Drawing.Pen.LineJoin%2A> Eigenschaft der <xref:System.Drawing.Pen> Klasse. Das Beispiel zeigt eine abgeschrägte linienverbindung zwischen einer horizontalen Linie und eine vertikale Linie. Im folgenden Code, den Wert <xref:System.Drawing.Drawing2D.LineJoin.Bevel> zugewiesen der <xref:System.Drawing.Pen.LineJoin%2A> Eigenschaft ist ein Mitglied der <xref:System.Drawing.Drawing2D.LineJoin> Enumeration. Die anderen Mitglieder des der <xref:System.Drawing.Drawing2D.LineJoin> Enumeration werden <xref:System.Drawing.Drawing2D.LineJoin.Miter> und <xref:System.Drawing.Drawing2D.LineJoin.Round>.  
  
 [!code-csharp[System.Drawing.UsingAPen#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch
- [Verwenden eines Stifts zum Zeichnen von Linien und Formen](using-a-pen-to-draw-lines-and-shapes.md)
