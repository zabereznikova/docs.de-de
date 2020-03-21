---
title: 'Gewusst wie: Zeichnen eines Bereichs mit einer Volltonfarbe'
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: be28a0af04c4e43cdf745a5429468aee99e34c40
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849521"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>Gewusst wie: Zeichnen eines Bereichs mit einer Volltonfarbe
Um einen Bereich mit einer Volltonfarbe zu malen, <xref:System.Windows.Media.Brushes.Red%2A> <xref:System.Windows.Media.Brushes.Blue%2A>können Sie einen vordefinierten Systempinsel verwenden, z. B. oder , oder Sie können einen neuen <xref:System.Windows.Media.SolidColorBrush> erstellen und seine <xref:System.Windows.Media.SolidColorBrush.Color%2A> mit Alpha-, Rot-, Grün- und Blauwerten beschreiben. In XAML können Sie einen Bereich mit einer Volltonfarbe auch mit der Hexadezimalschreibweise zeichnen.  
  
 In den folgenden Beispielen wird <xref:System.Windows.Shapes.Rectangle> jede dieser Techniken verwendet, um ein Blau zu malen.  
  
## <a name="example"></a>Beispiel  
 **Verwenden eines vordefinierten Pinsels**  
  
 Im folgenden Beispiel wird der <xref:System.Windows.Media.Brushes.Blue%2A> vordefinierte Pinsel verwendet, um ein Rechteck blau zu malen.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Hexadezimalnotation**  
  
 Im nächsten Beispiel wird die Hexadezimalschreibweise mit acht Ziffern verwendet.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Verwenden der ARGB-Werte**  
  
 Im nächsten Beispiel <xref:System.Windows.Media.SolidColorBrush> wird <xref:System.Windows.Media.SolidColorBrush.Color%2A> eine erstellt und die Verwendung der ARGB-Werte für die Farbe Blau beschrieben.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Weitere Möglichkeiten, Farbe zu <xref:System.Windows.Media.Color> beschreiben, finden Sie in der Struktur.  
  
 **Ähnliche Themen**  
  
 Weitere Informationen <xref:System.Windows.Media.SolidColorBrush> zu und weitere Beispiele finden Sie in der [Übersicht "Gemälde mit Volltonfarben und Farbverläufen".](painting-with-solid-colors-and-gradients-overview.md)  
  
 Dieses Codebeispiel ist Teil eines größeren <xref:System.Windows.Media.SolidColorBrush> Beispiels, das für die Klasse bereitgestellt wurde. Das vollständige Beispiel finden Sie unter der [Beispiel für Pinsel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Brushes>
