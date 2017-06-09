---
title: "Gewusst wie: Anwenden von Transformationen auf Text | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Gedrehter Text"
  - "Skalierter Text"
  - "Schattierter Text"
  - "Verzerrter Text"
  - "Texttransformationen"
  - "Übersetzter Text"
  - "Typografie, Gedrehter Text"
  - "Typografie, Skalierter Text"
  - "Typografie, Schattierter Text"
  - "Typografie, Verzerrter Text"
  - "Typografie, Transformationen"
  - "Typografie, Übersetzter Text"
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Anwenden von Transformationen auf Text
Transformationen können die Darstellung von Text in der Anwendung ändern.  In den folgenden Beispielen wird mit verschiedenen Arten von Renderingtransformationen die Darstellung von Text in einem <xref:System.Windows.Controls.TextBlock>\-Steuerelement beeinflusst.  
  
## Beispiel  
 Im folgenden Beispiel wird Text gezeigt, der um einen bestimmten Punkt in der zweidimensionalen x\-y\-Ebene gedreht ist.  
  
 ![Gedrehter Text mithilfe einer RotateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext01.png "TransformedText01")  
Beispiel für einen um 90 Grad gedrehten Text  
  
 Im folgenden Codebeispiel wird Text mithilfe von <xref:System.Windows.Media.RotateTransform> gedreht.  Durch einen <xref:System.Windows.Media.RotateTransform.Angle%2A>\-Wert von 90 wird das Element um 90 Grad im Uhrzeigersinn gedreht.  
  
 [!code-xml[TextTransformSample#TextTransformSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 Im folgenden Beispiel wird die zweite Textzeile entlang der x\-Achse und die dritte Textzeile entlang der y\-Achse um je 150 % skaliert.  
  
 ![Skalierter Text mithilfe einer ScaleTransform](../../../../docs/framework/wpf/advanced/media/transformedtext02.png "TransformedText02")  
Beispiel für skalierten Text  
  
 Im folgenden Codebeispiel wird mithilfe von <xref:System.Windows.Media.ScaleTransform> Text ausgehend von seiner ursprünglichen Größe skaliert.  
  
 [!code-xml[TextTransformSample#TextTransformSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  Das Skalieren von Text ist etwas anderes als das Vergrößern des Schriftgrads von Text.  Schriftgrade werden unabhängig voneinander berechnet, um bei unterschiedlichen Größen die beste Auflösung zu ermöglichen.  Skalierter Text hingegen behält die Proportionen der ursprünglichen Größe des Texts bei.  
  
 Im folgenden Beispiel wird ein entlang der x\-Achse verzerrter Text dargestellt.  
  
 ![Geneigter Text mithilfe einer SkewTransform](../../../../docs/framework/wpf/advanced/media/transformedtext03.png "TransformedText03")  
Beispiel für verzerrten Text  
  
 Im folgenden Codebeispiel wird Text mithilfe von <xref:System.Windows.Media.SkewTransform> verzerrt.  Eine Verzerrung \(auch als Scherung bekannt\), ist eine Transformation, die den Koordinatenraum auf ungleichmäßige Art ausdehnt.  In diesem Beispiel werden die zwei Textzeichenfolgen um \-30° und 30° entlang der x\-Koordinate verzerrt.  
  
 [!code-xml[TextTransformSample#TextTransformSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 Im folgenden Beispiel wird Text dargestellt, der entlang der x\- und y\-Achse übersetzt bzw. verschoben ist.  
  
 ![Textversatz mithilfe einer TranslateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext04.png "TransformedText04")  
Beispiel für übersetzten Text  
  
 Im folgenden Codebeispiel wird ein <xref:System.Windows.Media.TranslateTransform> verwendet, um Text zu versetzen.  In diesem Beispiel wird ein Schatteneffekt erzielt, indem die Kopie des Textes hinter dem primären Text geringfügig versetzt wird.  
  
 [!code-xml[TextTransformSample#TextTransformSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  Der <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> verfügt über einen umfangreichen Satz an Features zum Bereitstellen von Schatteneffekten.  Weitere Informationen finden Sie unter [Erstellen von Text mit einem Schatten](../../../../docs/framework/wpf/advanced/how-to-create-text-with-a-shadow.md).  
  
## Siehe auch  
 [Anwenden von Animationen auf Text](../../../../docs/framework/wpf/advanced/how-to-apply-animations-to-text.md)