---
title: Skalieren von Farben mithilfe von Transformationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
ms.openlocfilehash: ff6172d571a7ca449ab21d1f7a7f9a699bf40f8e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737974"
---
# <a name="using-transformations-to-scale-colors"></a>Skalieren von Farben mithilfe von Transformationen
Die Skalierungstransformation multipliziert mindestens eine der vier Farbkomponenten durch eine Zahl. Die Farbe Matrix Einträge, die Skalierung darstellen, werden in der folgenden Tabelle angegeben.  
  
|Komponente skaliert werden|Matrixeintrag|  
|----------------------------|------------------|  
|Rot|[0][0]|  
|Grün|[1][1]|  
|Blau|[2][2]|  
|Alpha|[3][3]|  
  
## <a name="scaling-one-color"></a>Skalieren einer Farbe  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei ColorBars2.bmp. Klicken Sie dann skaliert der Code die blaue Komponente der einzelnen Pixel in der Abbildung, um den Faktor 2. Das ursprüngliche Bild wird zusammen mit den transformierten Bild gezeichnet.  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und die skalierten Bild auf der rechten Seite an.  
  
 ![Skalieren von Farben](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")  
  
 Die folgende Tabelle enthält die Farbe Vektoren für die vier Balken, vor und nach der blauen Skalierung. Beachten Sie, dass die blaue Komponente in der vierten Farbleiste aus 0.8 auf 0.6 ist ein Fehler aufgetreten. Der Grund dafür ist [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] behält nur der Bruchteil des Ergebnisses. Beispielsweise (: (2)(0.8) = 1.6, und der Bruchteil von 1.6 ist 0.6. Nur die Nachkommastellen beibehalten wird sichergestellt, dass das Ergebnis immer im Intervall [0, 1].  
  
|Ursprünglich|Skaliert|  
|--------------|------------|  
|(0.4, 0.4, 0.4, 1)|(0.4, 0.4, 0.8, 1)|  
|(0.4, 0.2, 0.2, 1)|(0.4, 0.2, 0.4, 1)|  
|(0.2, 0.4, 0.2, 1)|(0.2, 0.4, 0.4, 1)|  
|(0.4, 0.4, 0.8, 1)|(0.4, 0.4, 0.6, 1)|  
  
## <a name="scaling-multiple-colors"></a>Skalieren von mehreren Farben  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei ColorBars2.bmp. Dann wird der Code die Rot-, Grün- und blauen-Komponenten der einzelnen Pixel in der Abbildung skaliert. Die roten Komponenten werden so skaliert, um 25 Prozent, die grüne Komponenten werden 35 Prozent herunterskaliert und die blaue Komponenten werden so skaliert, um 50 Prozent.  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und die skalierten Bild auf der rechten Seite an.  
  
 ![Skalieren von Farben](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")  
  
 Die folgende Tabelle enthält die Farbe Vektoren für die vier Balken, vor und nach die roten, grünen und blauen Skalierung.  
  
|Ursprünglich|Skaliert|  
|--------------|------------|  
|(0.6, 0.6, 0.6, 1)|(0.45, 0.39, 0.3, 1)|  
|(0, 1, 1, 1)|(0, 0.65, 0.5, 1)|  
|(1, 1, 0, 1)|(0.75, 0.65, 0, 1)|  
|(1, 0, 1, 1)|(0.75, 0, 0.5, 1)|  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [Neufärben von Bildern](../../../../docs/framework/winforms/advanced/recoloring-images.md)
