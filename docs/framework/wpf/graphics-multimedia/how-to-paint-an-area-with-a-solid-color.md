---
title: 'Vorgehensweise: Zeichnen eines Bereichs mit einer Volltonfarbe'
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: c85ba72c858d155f29875bb944824db1c44ffaab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086844"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>Vorgehensweise: Zeichnen eines Bereichs mit einer Volltonfarbe
Um einen Bereich mit einer Volltonfarbe zu zeichnen, können Sie einen vordefinierten Systempinsel, z. B. <xref:System.Windows.Media.Brushes.Red%2A> oder <xref:System.Windows.Media.Brushes.Blue%2A>, oder Sie können ein neues erstellen <xref:System.Windows.Media.SolidColorBrush> und eine Beschreibung für die <xref:System.Windows.Media.SolidColorBrush.Color%2A> mit alpha, Rot, Grün und Blau-Werte. In XAML können Sie einen Bereich mit einer Volltonfarbe auch mit der Hexadezimalschreibweise zeichnen.  
  
 Im folgenden Beispiel wird jede der folgenden Methoden zum Zeichnen einer <xref:System.Windows.Shapes.Rectangle> Blau.  
  
## <a name="example"></a>Beispiel  
 **Verwenden eines vordefinierten Pinsels**  
  
 Im folgenden Beispiel wird der vordefinierten Pinsel <xref:System.Windows.Media.Brushes.Blue%2A> zu blaues ein Rechteck zu zeichnen.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Mithilfe der hexadezimalen Schreibweise**  
  
 Im nächsten Beispiel wird die Hexadezimalschreibweise mit acht Ziffern verwendet.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Verwenden über den ARGB-Werte**  
  
 Im nächste Beispiel erstellt eine <xref:System.Windows.Media.SolidColorBrush> und beschreibt die <xref:System.Windows.Media.SolidColorBrush.Color%2A> mithilfe der ARGB-Werte für die Farbe Blau.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Andere Methoden zur Farbdefinition, finden Sie unter den <xref:System.Windows.Media.Color> Struktur.  
  
 **Verwandte Themen**  
  
 Weitere Informationen zu <xref:System.Windows.Media.SolidColorBrush> und weitere Beispiele finden Sie unter den [Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md) Übersicht.  
  
 Dieses Codebeispiel ist Teil eines umfangreicheren Beispiels für die <xref:System.Windows.Media.SolidColorBrush> Klasse. Das vollständige Beispiel finden Sie unter der [Beispiel für Pinsel](https://go.microsoft.com/fwlink/?LinkID=159973).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Brushes>
