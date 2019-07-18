---
title: 'Vorgehensweise: Verwenden einer Zeichnung als Bildquelle'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: d4b91a6495e1c54400d5fbfe43b6311d908565a7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769356"
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a>Vorgehensweise: Verwenden einer Zeichnung als Bildquelle
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.Drawing> als die <xref:System.Windows.Controls.Image.Source%2A> für eine <xref:System.Windows.Controls.Image> Steuerelement. Zum Anzeigen einer <xref:System.Windows.Media.Drawing> mit eine <xref:System.Windows.Controls.Image> steuern, verwenden Sie eine <xref:System.Windows.Media.DrawingImage> als die <xref:System.Windows.Controls.Image> des Steuerelements <xref:System.Windows.Controls.Image.Source%2A> und legen Sie die <xref:System.Windows.Media.DrawingImage> des Objekts <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> Eigenschaft, um die Zeichnung, die Sie anzeigen möchten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingImage> und <xref:System.Windows.Controls.Image> -Steuerelement zum Anzeigen einer <xref:System.Windows.Media.GeometryDrawing>. Dieses Beispiel erzeugt die folgende Ausgabe:  
  
 ![Eine GeometryDrawing von zwei Ellipsen](./media/graphicsmm-geodraw.jpg "Graphicsmm_geodraw")  
Ein DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Freezable.Freeze%2A>
- [Zeichnen eines Bilds mit ImageDrawing](how-to-draw-an-image-using-imagedrawing.md)
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
- [Übersicht über Freezable-Objekte](../advanced/freezable-objects-overview.md)
- [PresentationOptions:Freeze-Attribut](../advanced/presentationoptions-freeze-attribute.md)
