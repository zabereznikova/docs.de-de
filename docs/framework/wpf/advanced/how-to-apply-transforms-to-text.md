---
title: 'Gewusst wie: Anwenden von Transformationen auf Text'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], rotated text
- typography [WPF], scaled text
- skewed text [WPF]
- typography [WPF], translated text
- typography [WPF], shadowed text
- rotated text [WPF]
- translated text [WPF]
- shadowed text [WPF]
- transforms in text [WPF]
- typography [WPF], transforms
- scaled text [WPF]
- typography [WPF], skewed text
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
ms.openlocfilehash: 867f39e3df8493014d8601530e91310c3bbbeeb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141613"
---
# <a name="how-to-apply-transforms-to-text"></a>Gewusst wie: Anwenden von Transformationen auf Text
Transformationen können die Anzeige von Text in Ihrer Anwendung ändern. In den folgenden Beispielen werden verschiedene Arten von Rendering-Transformationen verwendet, um die Anzeige von Text in einem <xref:System.Windows.Controls.TextBlock> Steuerelement zu beeinflussen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt um einen bestimmten Punkt in der zweidimensionalen X-Y-Ebene gedrehten Text.  
  
 ![Gedrehter Text mithilfe einer RotateTransform](./media/how-to-apply-transforms-to-text/text-rotated-ninety-degrees.jpg)  
  
 Im folgenden Codebeispiel <xref:System.Windows.Media.RotateTransform> wird ein zum Drehen von Text verwendet. Bei <xref:System.Windows.Media.RotateTransform.Angle%2A> einem Wert von 90 wird das Element um 90 Grad im Uhrzeigersinn gedreht.  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 Das folgende Beispiel zeigt die zweite Textzeile, die um 150 % entlang der X-Achse skaliert ist, und die dritte Textzeile, die um 150 % entlang der Y-Achse skaliert ist.  
  
 ![Skalierter Text mithilfe einer ScaleTransform](./media/how-to-apply-transforms-to-text/scaled-text-scaletransform.jpg)
  
 Im folgenden Codebeispiel <xref:System.Windows.Media.ScaleTransform> wird ein verwendet, um Text von seiner ursprünglichen Größe zu skalieren.  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
> Das Skalieren von Text ist nicht identisch mit der Erhöhung des Schriftgrads des Texts. Schriftgrade werden unabhängig voneinander berechnet, um die beste Lösung in unterschiedlichen Größen bereitzustellen. Skalierter Text behält andererseits die Proportionen der ursprünglichen Textgröße bei.  
  
 Das folgende Beispiel zeigt einen entlang der X-Achse geneigten Text.  
  
 ![Geneigter Text mithilfe einer SkewTransform](./media/how-to-apply-transforms-to-text/skewed-transformed-text.jpg)

 Im folgenden Codebeispiel <xref:System.Windows.Media.SkewTransform> wird ein zum Verzerren von Text verwendet. Eine Neigung ist eine Transformation, die den Koordinatenraum auf ungleichmäßige Art ausdehnt. In diesem Beispiel werden die zwei Textzeichenfolgen um -30 Grad und 30 Grad entlang der X-Koordinate geneigt.  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 Das folgende Beispiel zeigt Text, der entlang der X- und Y-Achse übersetzt oder verschoben wurde.  
  
 ![Textversatz mithilfe einer TranslateTransform](./media/how-to-apply-transforms-to-text/transformed-text-x-y-axis.jpg)
  
 Im folgenden Codebeispiel <xref:System.Windows.Media.TranslateTransform> wird ein zum Versetzen von Text verwendet. In diesem Beispiel erstellt eine geringfügig versetzte Kopie des Textes hinter dem primären Text einen Schatteneffekt.  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
> Der <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> bietet eine Vielzahl von Funktionen für die Bereitstellung von Schatteneffekten. Weitere Informationen finden Sie unter [Erstellen von Text mit einem Schatten](how-to-create-text-with-a-shadow.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Anwenden von Animationen auf Text](how-to-apply-animations-to-text.md)
