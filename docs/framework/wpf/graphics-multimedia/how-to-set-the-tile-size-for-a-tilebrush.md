---
title: 'Vorgehensweise: Festlegen der Kachelgröße für einen TileBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: 80b5dfc668464df829db593668bea8a9a4ec09e4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839695"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>Vorgehensweise: Festlegen der Kachelgröße für einen TileBrush

Dieses Beispiel veranschaulicht das Festlegen die Flächengröße für ein <xref:System.Windows.Media.TileBrush>. Standardmäßig eine <xref:System.Windows.Media.TileBrush> erzeugt eine einzelne Kachel, die den Bereich vollständig ausfüllt, die Sie zeichnen werden. Sie können dieses Verhalten überschreiben, indem Sie die Einstellung der <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaften.

Die <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft gibt die Flächengröße für ein <xref:System.Windows.Media.TileBrush>. Standardmäßig wird der Wert des der <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft ist relativ zur Größe des gezeichneten Bereichs. Vornehmen der <xref:System.Windows.Media.TileBrush.Viewport%2A> Eigenschaft geben Sie eine absolute Flächengröße, legen Sie die <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaft <xref:System.Windows.Media.BrushMappingMode.Absolute>.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein <xref:System.Windows.Media.ImageBrush>, einen Typ von <xref:System.Windows.Media.TileBrush>, um ein Rechteck mit Flächen gezeichnet werden soll. Im Beispiel wird jede Kachel auf 50 x 50 Prozent des Ausgabebereichs (das Rechteck). Als Ergebnis wird das Rechteck mit vier Projektionen des Bilds gezeichnet.

Die folgende Abbildung zeigt die Ausgabe, die das Beispiel erzeugt:

![Ein Rechteck mit vier Kirschen Anordnung mit einem Bildpinsel veranschaulicht.](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

Im nächsten Beispiel wird erstellt eine <xref:System.Windows.Media.ImageBrush>, legt diese fest seine <xref:System.Windows.Media.TileBrush.Viewport%2A> zu `0,0,25,25` und die zugehörige <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> zu <xref:System.Windows.Media.BrushMappingMode.Absolute>, und verwendet, um ein weiteres Rechteck gezeichnet. Als Ergebnis erzeugt der Pinsel Flächen mit einer Breite und Höhe von 25 Pixeln.

Die folgende Abbildung zeigt die Ausgabe, die das Beispiel erzeugt:

![Ein Rechteck mit zugeht Kirschen einen gekachelten TileBrush mit einem Viewport veranschaulicht.](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

Die vorangehenden Beispiele sind Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel zu ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).

Obwohl dieses Beispiel verwendet die <xref:System.Windows.Media.ImageBrush> -Klasse, die <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> Eigenschaften verhalten sich identisch, für die anderen <xref:System.Windows.Media.TileBrush> Objekte, d. h. für <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush>. Weitere Informationen zu <xref:System.Windows.Media.ImageBrush> und die andere <xref:System.Windows.Media.TileBrush> Objekten finden Sie [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.TileBrush>
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
- [Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush](how-to-create-different-tile-patterns-with-a-tilebrush.md)
