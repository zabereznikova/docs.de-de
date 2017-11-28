---
title: 'Gewusst wie: Anwenden von Animationen auf Text'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0298462db5897e955bf0a2551cca7fc81bb27d89
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-apply-animations-to-text"></a>Gewusst wie: Anwenden von Animationen auf Text
Animationen können die Anzeige und die Darstellung von Text in Ihrer Anwendung ändern. In den folgenden Beispielen verschiedene Arten von Animationen verwenden, um zu beeinflussen, die Anzeige von Text in einem <xref:System.Windows.Controls.TextBlock> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> um die Breite des Textblocks animieren. Der Breitenwert ändert sich innerhalb von 10 Sekunden von der Breite des Textblocks auf 0. Anschließend werden die Breitenwerte umgekehrt und es wird fortgefahren. Dieser Animationstyp erstellt einen Wipe-Effekt.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> die Durchlässigkeit des Textblocks animiert. Der Deckkraftwert wird über einen Zeitraum von 5 Sekunden von 1,0 auf 0 geändert. Anschließend werden die Deckkraftwerte umgekehrt und es wird fortgefahren.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 Das folgende Diagramm zeigt die Auswirkung des der <xref:System.Windows.Controls.TextBlock> Steuerelement Änderung der Durchlässigkeit aus `1.00` auf `0.00` während des definierten von 5 Sekunden-Intervalls die <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  
  
 ![Ändern der Deckkraft von 1,00 in 0,00 Text](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")  
Änderung der Deckkraft des Textes von 1,00 in 0,00  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.ColorAnimation> die Vordergrundfarbe des Textblocks animiert. Der Wert für die Vordergrundfarbe ändert sich im Verlauf von 5 Sekunden von einer Farbe in eine zweite Farbe. Anschließend werden die Farbwerte umgekehrt und es wird fortgefahren.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> Textblocks drehen. Der Textblock führt eine vollständige Drehung über einen Zeitraum von 20 Sekunden aus, und anschließend wird die Drehung wiederholt.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
