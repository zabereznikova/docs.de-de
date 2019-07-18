---
title: 'Vorgehensweise: Zeichnen eines Bilds mit einer ImageDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
ms.openlocfilehash: f9459185bf81160b45222e7d6821e0f945ada381
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947594"
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a>Vorgehensweise: Zeichnen eines Bilds mit einer ImageDrawing
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.ImageDrawing> Zeichnen eines Bildes. Ein <xref:System.Windows.Media.ImageDrawing> ermöglicht, die Sie anzeigen, eine <xref:System.Windows.Media.ImageSource> mit einem <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, oder <xref:System.Windows.Media.Visual>. Um ein Bild zu zeichnen, erstellen Sie eine <xref:System.Windows.Media.ImageDrawing> und legen Sie dessen <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> und <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> Eigenschaften. Die <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> Eigenschaft gibt an, das Bild zu zeichnen, und die <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> Eigenschaft gibt an, die Position und Größe der einzelnen Bilder.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine zusammengesetzte Zeichnung mit vier <xref:System.Windows.Media.ImageDrawing> Objekte. Dieses Beispiel erzeugt die folgende Abbildung:  
  
 ![Mehrere DrawingImage-Objekte](./media/graphicsmm-imagedrawingexample.jpg "Graphicsmm_ImageDrawingExample")  
Vier ImageDrawing-Objekte  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 Ein Beispiel für eine einfache Möglichkeit zum Anzeigen eines Bilds ohne <xref:System.Windows.Media.ImageDrawing>, finden Sie unter [verwenden Sie das Image-Element](../controls/how-to-use-the-image-element.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Freezable.Freeze%2A>
- <xref:System.Windows.Controls.Image>
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
- [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md)
- [PresentationOptions:Freeze-Attribut](../advanced/presentationoptions-freeze-attribute.md)
