---
title: 'Gewusst wie: Anwenden von Animationen auf Text'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: ed2f3beb904f724ac93e2c4033aa6b2eb3fa1290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174627"
---
# <a name="how-to-apply-animations-to-text"></a>Gewusst wie: Anwenden von Animationen auf Text
Animationen können die Anzeige und die Darstellung von Text in Ihrer Anwendung ändern. In den folgenden Beispielen werden verschiedene Arten von <xref:System.Windows.Controls.TextBlock> Animationen verwendet, um die Anzeige von Text in einem Steuerelement zu beeinflussen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.DoubleAnimation> wird eine verwendet, um die Breite des Textblocks zu animieren. Der Breitenwert ändert sich innerhalb von 10 Sekunden von der Breite des Textblocks auf 0. Anschließend werden die Breitenwerte umgekehrt und es wird fortgefahren. Dieser Animationstyp erstellt einen Wipe-Effekt.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.DoubleAnimation> wird ein verwendet, um die Deckkraft des Textblocks zu animieren. Der Deckkraftwert wird über einen Zeitraum von 5 Sekunden von 1,0 auf 0 geändert. Anschließend werden die Deckkraftwerte umgekehrt und es wird fortgefahren.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 Das folgende Diagramm zeigt <xref:System.Windows.Controls.TextBlock> den Effekt, dass `1.00` `0.00` das Steuerelement seine Deckkraft <xref:System.Windows.Media.Animation.Timeline.Duration%2A>von zu während des 5-Sekunden-Intervalls ändert, das durch die definiert wird.  
  
 ![Textänderung der Deckkraft von 1,00 bis 0,00.](./media/how-to-apply-animations-to-text/faded-text-opacity-change.png)  

 Im folgenden Beispiel <xref:System.Windows.Media.Animation.ColorAnimation> wird eine verwendet, um die Vordergrundfarbe des Textblocks zu animieren. Der Wert für die Vordergrundfarbe ändert sich im Verlauf von 5 Sekunden von einer Farbe in eine zweite Farbe. Anschließend werden die Farbwerte umgekehrt und es wird fortgefahren.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.DoubleAnimation> wird ein zum Drehen des Textblocks verwendet. Der Textblock führt eine vollständige Drehung über einen Zeitraum von 20 Sekunden aus, und anschließend wird die Drehung wiederholt.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Animationen](../graphics-multimedia/animation-overview.md)
