---
title: Bereiche in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
ms.openlocfilehash: 33d4f4ecca7b9d777fa4eab5b6d031de10f03ccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956781"
---
# <a name="regions-in-gdi"></a>Bereiche in GDI+
Ein Bereich ist ein Teil der Anzeigebereich des ein Ausgabegerät. Regionen können es sich um einfache (ein einzelnes Rechteck) oder komplexe (eine Kombination von Polygonen und geschlossene Kurven) sein. Die folgende Abbildung zeigt zwei Regionen: eine von einem Rechteck erstellt und die andere erstellt aus einem Pfad.  
  
 ![Regions](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")  
  
## <a name="using-regions"></a>Verwenden von Bereichen  
 Regionen werden häufig für das Clipping verwendet und den Treffertest durchführen. Clipping wird beschränkt Zeichnen in einer bestimmten Region des Anzeigebereichs, normalerweise der Teil, der aktualisiert werden muss. Treffertests umfasst das Überprüfen, um festzustellen, ob der Cursor befindet sich in einer bestimmten Region des Bildschirms, wenn eine Maustaste gedrückt wird.  
  
 Sie können eine Region aus einem Rechteck oder einen Pfad erstellen. Sie können auch komplexe Regionen erstellen, durch die Kombination der vorhandener Regions. Die <xref:System.Drawing.Region> Klasse stellt die folgenden Methoden zum Kombinieren von Bereichen: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, und <xref:System.Drawing.Region.Complement%2A>.  
  
 Die Schnittmenge von zwei Regionen ist die Menge aller Punkte, die in beiden Regionen gehören. Die Union ist die Menge aller Punkte, die zu den anderen oder beide Regionen gehören. Das Komplement eines Bereichs ist die Menge aller Punkte, die nicht in der Region sind. Die folgende Abbildung zeigt die Schnittmenge und die Union der beiden Regionen in der vorherigen Abbildung dargestellt.  
  
 ![Regions](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")  
  
 Die <xref:System.Drawing.Region.Xor%2A> -Methode angewendet wird, auf ein Paar von Regionen, generiert einen Bereich, der alle Punkte enthält, die zu einer Region oder die andere aber nicht beide gehören. Die <xref:System.Drawing.Region.Exclude%2A> -Methode angewendet wird, auf ein Paar von Regionen, generiert einen Bereich, der alle Punkte in der ersten Region enthält, die nicht in der zweiten Region sind. Die folgende Abbildung zeigt die Bereiche, die aus der Anwendung führen die <xref:System.Drawing.Region.Xor%2A> und <xref:System.Drawing.Region.Exclude%2A> Methoden, um die beiden Bereiche am Anfang dieses Themas.  
  
 ![Regions](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")  
  
 Um eine Region zu füllen, müssen Sie eine <xref:System.Drawing.Graphics> Objekt eine <xref:System.Drawing.Brush> Objekt und ein <xref:System.Drawing.Region> Objekt. Die <xref:System.Drawing.Graphics> -Objekt ermöglicht die <xref:System.Drawing.Graphics.FillRegion%2A> -Methode, und die <xref:System.Drawing.Brush> -Objekt speichert Attribute für die Füllung, z. B. Farbe oder einem Muster. Das folgende Beispiel füllt einen Bereich mit einer Volltonfarbe aus.  
  
 [!code-csharp[LinesCurvesAndShapes#61](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [Linien, Kurven und Formen](lines-curves-and-shapes.md)
- [Verwenden von Bereichen](using-regions.md)
