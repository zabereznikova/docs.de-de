---
title: 'Gewusst wie: Festlegen der Flächengröße für ein TileBrush-Objekt'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: af7bab59a292549b29dad9b6a7417f22b1b84e48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186833"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>Gewusst wie: Festlegen der Flächengröße für ein TileBrush-Objekt

In diesem Beispiel wird gezeigt, <xref:System.Windows.Media.TileBrush>wie die Kachelgröße für eine festgelegt wird. Standardmäßig erzeugt <xref:System.Windows.Media.TileBrush> a eine einzelne Kachel, die den Bereich, den Sie malen, vollständig ausfüllt. Sie können dieses Verhalten überschreiben, indem Sie die <xref:System.Windows.Media.TileBrush.Viewport%2A> und-Eigenschaften <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> festlegen.

Die <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft gibt die Kachelgröße für eine <xref:System.Windows.Media.TileBrush>an. Standardmäßig ist der Wert <xref:System.Windows.Media.TileBrush.Viewport%2A> der Eigenschaft relativ zur Größe des zu malenden Bereichs. Damit die <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft eine absolute Kachelgröße <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> angibt, legen Sie die Eigenschaft auf fest. <xref:System.Windows.Media.BrushMappingMode.Absolute>

## <a name="example"></a>Beispiel

Im folgenden Beispiel <xref:System.Windows.Media.ImageBrush>wird ein <xref:System.Windows.Media.TileBrush>, ein Typ von verwendet, um ein Rechteck mit Kacheln zu zeichnen. Im Beispiel wird jede Kachel auf 50 Prozent um 50 Prozent der Ausgabefläche (rechteckig) festgelegt. Als Ergebnis wird das Rechteck mit vier Projektionen des Bilds gezeichnet.

Die folgende Abbildung zeigt die Ausgabe, die das Beispiel erzeugt:

![Ein Rechteck mit vier Kirschen, die Fliesen mit einem Bildpinsel demonstrieren.](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

Im nächsten Beispiel <xref:System.Windows.Media.ImageBrush>wird <xref:System.Windows.Media.TileBrush.Viewport%2A> eine `0,0,25,25` , <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> <xref:System.Windows.Media.BrushMappingMode.Absolute>auf und auf festgelegt und verwendet, um ein weiteres Rechteck zu malen. Als Ergebnis erzeugt der Pinsel Flächen mit einer Breite und Höhe von 25 Pixeln.

Die folgende Abbildung zeigt die Ausgabe, die das Beispiel erzeugt:

![Ein Rechteck mit 48 Kirschen, die einen gefliesten TileBrush mit einem Viewport demonstrieren.](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

Die vorangehenden Beispiele sind Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [ImageBrush-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).

Obwohl in diesem <xref:System.Windows.Media.ImageBrush> Beispiel <xref:System.Windows.Media.TileBrush.Viewport%2A> die <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Klasse verwendet wird, <xref:System.Windows.Media.TileBrush> verhalten sich die <xref:System.Windows.Media.DrawingBrush> und-Eigenschaften für die anderen Objekte, d. h. für und, <xref:System.Windows.Media.VisualBrush>identisch. Weitere Informationen <xref:System.Windows.Media.ImageBrush> zu und <xref:System.Windows.Media.TileBrush> zu den anderen Objekten finden Sie unter [Malen mit Bildern, Zeichnungen und Visuals](painting-with-images-drawings-and-visuals.md).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.TileBrush>
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
- [Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush](how-to-create-different-tile-patterns-with-a-tilebrush.md)
