---
title: 'Gewusst wie: Erstellen eines linearen Farbverlaufs'
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
ms.openlocfilehash: 9eeedf1ef92bdf6e5e2724eeca5060765b0778f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522459"
---
# <a name="how-to-create-a-linear-gradient"></a>Gewusst wie: Erstellen eines linearen Farbverlaufs
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet horizontale, vertikale und diagonale lineare Farbverläufe. Standardmäßig ändert sich die Farbe in einem linearen Farbverlauf einheitlich. Allerdings können Sie einen linearen Farbverlauf anpassen, sodass sich die Farbe auf nicht einheitliche Weise ändert.  
  
 Im folgenden Beispiel wird eine Zeile und einer Ellipse, die ein Rechteck mit einem horizontalen linearen Farbverlaufspinsel.  
  
 Die <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> Konstruktor empfängt vier Argumente: zwei Punkten und mit zwei Farben aus. Der erste Punkt (0, 10) bezieht sich auf der ersten Farbe (Rot), und der zweite Punkt (200, 10) der zweiten Farbe (Blau) zugeordnet ist. Erwartungsgemäß, der Linie von (0, 10), (200, 10) ändert sich allmählich von Rot und Blau.  
  
 Die Werte 10 in den Punkten (50, 10) und (200, 10) sind nicht wichtig. Wichtig ist, dass die beiden Punkte derselben zweite Koordinate haben – die verbindenden Zeile ist horizontal. Ellipse und des Rechtecks ändert auch allmählich von Rot in Blau, da die horizontale Koordinate von 0 bis 200 wird.  
  
 Die folgende Abbildung zeigt die Zeile, das die Ellipse und das Rechteck. Beachten Sie, dass der Farbverlauf wird wiederholt als die horizontale Koordinate 200 hinausgeht.  
  
 ![Linearer Farbverlauf](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")  
  
### <a name="to-use-horizontal-linear-gradients"></a>Verwenden Sie horizontale lineare Farbverläufe  
  
-   Übergeben Sie die nicht transparenten Rot und Blau als die dritte und vierte Argument.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 Im vorherigen Beispiel Ändern der Farbkomponenten linear beim Wechseln von einer horizontale Koordinate von 0 bis zu einer horizontalen Koordinate 200. Beispielsweise wird ein Punkt, dessen erste Koordinate in der Mitte zwischen 0 und 200 ist, eine blaue Komponente aufweisen, in der Mitte zwischen 0 und 255 ist.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] können Sie, wie eine Farbe aus einer Kante eines Farbverlaufs zum anderen anzupassen. Angenommen Sie, Sie möchten einen Pinsel mit Farbverlauf erstellen, der sich in Rot entsprechend der folgenden Tabelle aus Schwarz ändert.  
  
|Horizontale Koordinate|RGB-Komponenten|  
|---------------------------|--------------------|  
|0|(0, 0, 0)|  
|40|(128, 0, 0)|  
|300|(255, 0, 0)|  
  
 Beachten Sie, dass Rotanteils zur Hälfte Intensität ist, wird die horizontale Koordinate nur 20 Prozent der Möglichkeit von 0 bis 200.  
  
 Im folgenden Beispiel wird die <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> Eigenschaft von einem <xref:System.Drawing.Drawing2D.LinearGradientBrush> Objekt, das drei relative Intensitäten mit drei relativen Positionen zu verknüpfen. Wie in der obigen Tabelle ist eine relative Intensität von 0,5 eine relative Position von 0,2 zugeordnet. Der Code füllt eine Ellipse und ein Rechteck mit dem Farbverlaufspinsel.  
  
 Die folgende Abbildung zeigt das resultierende Ellipse und das Rechteck.  
  
 ![Linearer Farbverlauf](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")  
  
### <a name="to-customize-linear-gradients"></a>Lineare Farbverläufe anpassen  
  
-   Übergeben Sie die deckend Schwarz und Rot als die dritte und vierte Argument.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 Die Farbverläufe in den vorherigen Beispielen wurden horizontale; d. h. ändert sich die Farbe graduell ab, wie Sie auf einer horizontalen Linie verschieben. Sie können auch die vertikale und diagonale Farbverläufe definieren.  
  
 Das folgende Beispiel übergibt die Punkte (0, 0) und (200, 100), um eine <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> Konstruktor. Die Farbe Blau zugeordnet ist (0, 0), und die Farbe Grün zugeordnet ist (200, 100). Eine Linie (mit Stiftbreite 10) und einer Ellipse, die sind mit der linearen Farbverlaufspinsel gefüllt.  
  
 Die folgende Abbildung zeigt die Zeile und die Ellipse. Beachten Sie, dass die Farbe in der Ellipse wechselt allmählich entlang einer Linie wird parallel zu der Position übergeben (0, 0) und (200, 100).  
  
 ![Linearer Farbverlauf](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")  
  
### <a name="to-create-diagonal-linear-gradients"></a>So erstellen diagonaler, linearer Farbverläufe  
  
-   Übergeben Sie die nicht transparenten Blau und Grün als die dritte und vierte Argument.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
