---
title: 'Vorgehensweise: Erstellen eines linearen Farbverlaufs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: b836659821b54698b675d48acd4e46466001d654
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937895"
---
# <a name="how-to-create-a-linear-gradient"></a>Vorgehensweise: Erstellen eines linearen Farbverlaufs
GDI + enthält horizontale, vertikale und diagonale lineare Farbverläufen. Standardmäßig ändert sich die Farbe in einem linearen Farbverlauf einheitlich. Allerdings können Sie einen linearen Farbverlauf anpassen, um die Farbe auf nicht einheitliche Weise zu ändern.  

> [!NOTE]
> In die Beispielen in diesem Artikel werden die Methoden, die von eines Steuerelements aufgerufen werden <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.  

Im folgenden Beispiel wird eine Zeile, einer Ellipse und ein Rechteck mit einem horizontalen linearen Farbverlaufspinsel.  
  
Die <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> Konstruktor empfängt vier Argumente: zwei Punkte und zwei Farben aus. Der erste Punkt (0, 10) bezieht sich auf die erste Farbe (Rot), und der zweite Punkt ("200", "10") bezieht sich auf die zweite Farbe (Blau). Erwartungsgemäß, die Linie gezeichnet werden (0, 10), ("200", "10") ändert sich allmählich von Rot zu Blau.  
  
 Die Werte 10 in die Punkte ("0", "10") und (200, 10) sind nicht wichtig. Wichtig ist, dass die beiden Punkte derselben zweite Koordinate haben – verbindenden Linie ist horizontal. Die Ellipse und des Rechtecks ändert sich auch allmählich von Rot zu Blau im Laufe der der horizontalen Koordinate von 0 bis 200.  
  
 Die folgende Abbildung zeigt die Zeile, das die Ellipse und das Rechteck. Beachten Sie, dass der Farbverlauf wird wiederholt, wie die horizontale Koordinate 200 überschreitet.  
  
 ![Linearer Farbverlauf](./media/cslineargradient1.png "cslineargradient1")  
  
### <a name="to-use-horizontal-linear-gradients"></a>Verwenden Sie horizontale lineare Farbverläufe  
  
- Übergeben Sie das nicht transparente Rot und Blau als die dritte und vierte Argument.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 Im vorherigen Beispiel Ändern der Farbkomponenten linear wie die Umstellung von einer horizontalen Koordinate 0 auf eine horizontale Koordinate von 200. Beispielsweise müssen ein Punkt, dessen erste Koordinate in der Mitte zwischen 0 und 200 wird, eine blaue Komponente, die in der Mitte zwischen 0 und 255 ist.  
  
 GDI + können Sie, wie eine Farbe aus einer Kante eines Farbverlaufs in den anderen anzupassen. Nehmen wir an, dass einen Pinsel mit Farbverlauf zu erstellen, der von Schwarz ändert sich in Rot gemäß der folgenden Tabelle werden soll.  
  
|Horizontale Koordinate|RGB-Komponenten|  
|---------------------------|--------------------|  
|0|(0, 0, 0)|  
|40|(128, 0, 0)|  
|200|(255, 0, 0)|  
  
 Beachten Sie, dass der Rotanteil auf halbe Intensität ist, wenn die horizontale Koordinate nur 20 Prozent der die Möglichkeit von 0 bis 200 ist.  
  
 Im folgenden Beispiel wird die <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType> Eigenschaft, drei relativen Positionen drei relative Intensitäten zugeordnet werden soll. Wie in der obigen Tabelle wird die relative Intensität von 0,5 eine relative Position von 0,2 zugeordnet. Der Code füllt einer Ellipse und ein Rechteck mit dem Pinsel mit Farbverlauf.  
  
 Die folgende Abbildung zeigt das resultierende Ellipse und das Rechteck.  
  
 ![Linearer Farbverlauf](./media/cslineargradient2.png "cslineargradient2")  

### <a name="to-customize-linear-gradients"></a>Lineare Farbverläufe anpassen  
  
- Übergeben Sie die deckend Schwarz und Rot als die dritte und vierte Argument.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 Die Farbverläufe in den vorherigen Beispielen wurden horizontale; d. h. ändert die Farbe allmählich während des Verschiebens auf einer horizontalen Linie im. Sie können auch die vertikale und diagonale Farbverläufe definieren.  
  
 Das folgende Beispiel übergibt die Punkte ("0", "0") und (200, 100), um eine <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> Konstruktor. Die Farbe Blau zugeordnet ist (0, 0), und die Farbe Grün zugeordnet ist (200, 100). Eine Zeile (mit Stiftbreite 10) und eine Ellipse sind mit Pinsels mit linearem Farbverlauf gefüllt.  
  
 Die folgende Abbildung zeigt die Zeile und der Ellipse. Beachten Sie, dass die Farbe in der Ellipse ändert sich allmählich entlang einer auf die Linie wird parallel zu der Zeile durchläuft (0, 0) und (200, 100).  
  
 ![Linearer Farbverlauf](./media/cslineargradient3.png "cslineargradient3")  
  
### <a name="to-create-diagonal-linear-gradients"></a>Zum Erstellen der diagonaler linearer Farbverläufen  
  
- Übergeben Sie das nicht transparente Blau und Grün als die dritte und vierte Argument.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen](using-a-gradient-brush-to-fill-shapes.md)
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
