---
title: 'Vorgehensweise: Festlegen der Kachelgröße für ein TileBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tilepropertys
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: 2b603345e00ae3067c4be860b6aad1cf7b9883c5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354452"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>Vorgehensweise: Festlegen der Kachelgröße für ein TileBrush
Dieses Beispiel veranschaulicht das Festlegen die Flächengröße für ein <xref:System.Windows.Media.TileBrush>. Standardmäßig eine <xref:System.Windows.Media.TileBrush> erzeugt eine einzelne Kachel, die den Bereich vollständig ausfüllt, die Sie zeichnen werden. Sie können dieses Verhalten überschreiben, indem Sie die Einstellung der <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaften.  
  
 Die <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft gibt die Flächengröße für ein <xref:System.Windows.Media.TileBrush>. Standardmäßig wird der Wert des der <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft ist relativ zur Größe des gezeichneten Bereichs. Vornehmen der <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft geben Sie eine absolute Flächengröße, legen Sie die <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaft <xref:System.Windows.Media.BrushMappingMode.Absolute>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.ImageBrush>, einen Typ von <xref:System.Windows.Media.TileBrush>, um ein Rechteck mit Flächen gezeichnet werden soll. In diesem Beispiel werden die Seiten der einzelnen Flächen auf 50 x 50 Prozent der Seiten des Ausgabebereichs (des Rechtecks) festgelegt. Als Ergebnis wird das Rechteck mit vier Projektionen des Bilds gezeichnet.  
  
 In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.
  
 ![Beispiel für die Anordnung mit einem Bildpinsel](./media/0.png "0")  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 Im nächsten Beispiel wird erstellt eine <xref:System.Windows.Media.ImageBrush>, legt diese fest seine <xref:System.Windows.Media.TileBrush.Viewport%2A> zu `0,0,25,25` und die zugehörige <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> zu <xref:System.Windows.Media.BrushMappingMode.Absolute>, und verwendet, um ein weiteres Rechteck gezeichnet. Als Ergebnis erzeugt der Pinsel Flächen mit einer Breite und Höhe von 25 Pixeln.  
  
 In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Flächen mit einem Viewport von 0,0,0.25,0.25](./media/25x25viewport.png "25x25viewport")  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 Die vorangehenden Beispiele sind Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel zu ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).  
  
 Obwohl dieses Beispiel verwendet die <xref:System.Windows.Media.ImageBrush> -Klasse, die <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaften verhalten sich identisch, für die anderen <xref:System.Windows.Media.TileBrush> Objekte, d. h. für <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush>. Weitere Informationen zu <xref:System.Windows.Media.ImageBrush> und die andere <xref:System.Windows.Media.TileBrush> Objekten finden Sie [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.TileBrush>
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
- [Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush](how-to-create-different-tile-patterns-with-a-tilebrush.md)
