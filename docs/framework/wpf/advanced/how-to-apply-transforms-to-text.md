---
title: 'Vorgehensweise: Anwenden von Transformationen auf Text'
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
ms.openlocfilehash: 7737a2e01ddfe2a639426bbced643d8f78961207
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740543"
---
# <a name="how-to-apply-transforms-to-text"></a>Vorgehensweise: Anwenden von Transformationen auf Text
Transformationen können die Anzeige von Text in Ihrer Anwendung ändern. Die folgenden Beispiele verwenden verschiedene Arten von Renderingtransformationen die Anzeige von Text in beeinflusst eine <xref:System.Windows.Controls.TextBlock> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt um einen bestimmten Punkt in der zweidimensionalen X-Y-Ebene gedrehten Text.  
  
 ![Gedrehter Text mithilfe einer RotateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext01.jpg "TransformedText01")  
Beispiel für um 90 Grad gedrehten Text  
  
 Im folgenden Codebeispiel wird eine <xref:System.Windows.Media.RotateTransform> um Text zu drehen. Ein <xref:System.Windows.Media.RotateTransform.Angle%2A> -Wert von 90 Dreht das Element um 90 Grad im Uhrzeigersinn.  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 Das folgende Beispiel zeigt die zweite Textzeile, die um 150 % entlang der X-Achse skaliert ist, und die dritte Textzeile, die um 150 % entlang der Y-Achse skaliert ist.  
  
 ![Skalierter Text mithilfe einer ScaleTransform skalierter](../../../../docs/framework/wpf/advanced/media/transformedtext02.jpg "TransformedText02")  
Beispiel für skalierten Text  
  
 Im folgenden Codebeispiel wird eine <xref:System.Windows.Media.ScaleTransform> zum Skalieren von Text aus der ursprünglichen Größe.  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  Das Skalieren von Text ist nicht identisch mit der Erhöhung des Schriftgrads des Texts. Schriftgrade werden unabhängig voneinander berechnet, um die beste Lösung in unterschiedlichen Größen bereitzustellen. Skalierter Text behält andererseits die Proportionen der ursprünglichen Textgröße bei.  
  
 Das folgende Beispiel zeigt einen entlang der X-Achse geneigten Text.  
  
 ![Geneigter Text mithilfe einer SkewTransform](../../../../docs/framework/wpf/advanced/media/transformedtext03.jpg "TransformedText03")  
Beispiel für verzerrten Text  
  
 Im folgenden Codebeispiel wird eine <xref:System.Windows.Media.SkewTransform> um Text zu neigen. Eine Neigung ist eine Transformation, die den Koordinatenraum auf ungleichmäßige Art ausdehnt. In diesem Beispiel werden die zwei Textzeichenfolgen um -30 Grad und 30 Grad entlang der X-Koordinate geneigt.  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 Das folgende Beispiel zeigt Text, der entlang der X- und Y-Achse übersetzt oder verschoben wurde.  
  
 ![Textversatz mithilfe einer TranslateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext04.jpg "TransformedText04")  
Beispiel für übersetzten Text  
  
 Im folgenden Codebeispiel wird eine <xref:System.Windows.Media.TranslateTransform> um Text zu versetzen. In diesem Beispiel erstellt eine geringfügig versetzte Kopie des Textes hinter dem primären Text einen Schatteneffekt.  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  Die <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> bietet einen umfangreichen Satz von Funktionen für das Bereitstellen von Schatteneffekten. Weitere Informationen finden Sie unter [Erstellen von Text mit einem Schatten](../../../../docs/framework/wpf/advanced/how-to-create-text-with-a-shadow.md).  
  
## <a name="see-also"></a>Siehe auch
- [Anwenden von Animationen auf Text](../../../../docs/framework/wpf/advanced/how-to-apply-animations-to-text.md)
