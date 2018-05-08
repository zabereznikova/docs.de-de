---
title: 'Gewusst wie: Zeichnen eines Bereichs mit einer Volltonfarbe'
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: 7e8e3fa5a379f02c3bb126c17bbe37fc0f3d57cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>Gewusst wie: Zeichnen eines Bereichs mit einer Volltonfarbe
Um einen Bereich mit einer Volltonfarbe zu zeichnen, können Sie einen vordefinierten Systempinsel, z. B. <xref:System.Windows.Media.Brushes.Red%2A> oder <xref:System.Windows.Media.Brushes.Blue%2A>, oder erstellen Sie ein neues <xref:System.Windows.Media.SolidColorBrush> und eine Beschreibung für die <xref:System.Windows.Media.SolidColorBrush.Color%2A> mit alpha, Rot-, Grün- und Blau-Werte. In XAML können Sie einen Bereich mit einer Volltonfarbe auch mit der Hexadezimalschreibweise zeichnen.  
  
 Im folgenden Beispiel wird jede dieser Techniken zum Zeichnen einer <xref:System.Windows.Shapes.Rectangle> Blau.  
  
## <a name="example"></a>Beispiel  
 **Verwenden eines vordefinierten Pinsels**  
  
 Im folgenden Beispiel wird den vordefinierten Pinsel <xref:System.Windows.Media.Brushes.Blue%2A> ein Rechteck blauen gezeichnet.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Hexadezimalnotation**  
  
 Im nächsten Beispiel wird die Hexadezimalschreibweise mit acht Ziffern verwendet.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Verwenden der ARGB-Werte**  
  
 Im nächste Beispiel erstellt eine <xref:System.Windows.Media.SolidColorBrush> und beschreibt dessen <xref:System.Windows.Media.SolidColorBrush.Color%2A> mithilfe der ARGB-Werte für die Farbe Blau.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Andere Möglichkeiten zur Beschreibung der Farbe, finden Sie unter der <xref:System.Windows.Media.Color> Struktur.  
  
 **Verwandte Themen**  
  
 Weitere Informationen zu <xref:System.Windows.Media.SolidColorBrush> und weitere Beispiele finden Sie unter der [Zeichnen mit Volltonfarben und Farbverläufen (Übersicht)](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) (Übersicht).  
  
 Dieses Codebeispiel ist Teil eines umfangreicheren Beispiels für die <xref:System.Windows.Media.SolidColorBrush> Klasse. Das vollständige Beispiel finden Sie unter der [Beispiel für Pinsel](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Brushes>
