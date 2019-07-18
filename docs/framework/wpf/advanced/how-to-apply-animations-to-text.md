---
title: 'Vorgehensweise: Anwenden von Animationen auf Text'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: 38aa432fecc5b5e10d8eb90be9c1c596728ed613
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776890"
---
# <a name="how-to-apply-animations-to-text"></a>Vorgehensweise: Anwenden von Animationen auf Text
Animationen können die Anzeige und die Darstellung von Text in Ihrer Anwendung ändern. Die folgenden Beispiele verwenden die verschiedene Arten von Animationen die Anzeige von Text in beeinflusst eine <xref:System.Windows.Controls.TextBlock> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> die Breite des Textblocks animiert. Der Breitenwert ändert sich innerhalb von 10 Sekunden von der Breite des Textblocks auf 0. Anschließend werden die Breitenwerte umgekehrt und es wird fortgefahren. Dieser Animationstyp erstellt einen Wipe-Effekt.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> die Deckkraft des Textblocks animiert. Der Deckkraftwert wird über einen Zeitraum von 5 Sekunden von 1,0 auf 0 geändert. Anschließend werden die Deckkraftwerte umgekehrt und es wird fortgefahren.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 Das folgende Diagramm zeigt die Auswirkung des der <xref:System.Windows.Controls.TextBlock> Steuerelement Änderung der Durchlässigkeit von `1.00` zu `0.00` während des 5-Sekunden-Intervalls von definiert die <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  
  
 ![Der Text sich ändernder Deckkraft von 1,00 in 0,00.](./media/how-to-apply-animations-to-text/faded-text-opacity-change.png)  
   
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.ColorAnimation> die Vordergrundfarbe des Textblocks animiert. Der Wert für die Vordergrundfarbe ändert sich im Verlauf von 5 Sekunden von einer Farbe in eine zweite Farbe. Anschließend werden die Farbwerte umgekehrt und es wird fortgefahren.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> den Textblock gedreht. Der Textblock führt eine vollständige Drehung über einen Zeitraum von 20 Sekunden aus, und anschließend wird die Drehung wiederholt.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](../graphics-multimedia/animation-overview.md)
