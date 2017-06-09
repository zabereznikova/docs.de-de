---
title: "Gewusst wie: Anwenden von Animationen auf Text | Microsoft Docs"
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
  - "Animation, Text"
  - "Typografie, Animationen"
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Anwenden von Animationen auf Text
Animationen können die Anzeige und die Darstellung von Text in der Anwendung ändern.  In den folgenden Beispielen wird mit verschiedenen Arten von Animationen die Darstellung von Text in einem <xref:System.Windows.Controls.TextBlock>\-Steuerelement beeinflusst.  
  
## Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> verwendet, um die Breite des Textblocks zu animieren.  Der Wert für die Breite ändert sich im Verlauf von 10 Sekunden von der Breite des Textblocks in 0. Anschließend werden die Werte für die Breite umgekehrt, und der Vorgang wird fortgesetzt.  Dieser Typ von Animation erstellt einen Wischeffekt.  
  
 [!code-xml[TextAnimationSample#TextAnimationSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> verwendet, um die Durchlässigkeit des Textblocks zu animieren.  Der Wert für die Durchlässigkeit ändert sich im Verlauf von 5 Sekunden von 1,0 in 0. Anschließend werden die Werte für die Durchlässigkeit umgekehrt, und der Vorgang wird fortgesetzt.  
  
 [!code-xml[TextAnimationSample#TextAnimationSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 Das folgende Diagramm zeigt, wie sich die Änderung der Durchlässigkeit des <xref:System.Windows.Controls.TextBlock>\-Steuerelements von `1.00` in `0.00` innerhalb des von <xref:System.Windows.Media.Animation.Timeline.Duration%2A> definierten 5\-Sekunden\-Intervalls auswirkt.  
  
 ![Text mit sich von 1,00 in 0,00 ändernder Deckkraft](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")  
Änderung der Textdurchlässigkeit  von 1,00 in 0,00  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.ColorAnimation> verwendet, um die Vordergrundfarbe des Textblocks zu animieren.  Der Wert für die Vordergrundfarbe ändert sich im Verlauf von 5 Sekunden von einer Farbe in eine zweite Farbe. Anschließend werden die Werte für die Farbe umgekehrt, und der Vorgang wird fortgesetzt.  
  
 [!code-xml[TextAnimationSample#TextAnimationSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> verwendet, um den Textblock zu drehen.  Der Textblock führt im Verlauf von 20 Sekunden eine ganze Drehung aus. Anschließend wird die Drehung wiederholt.  
  
 [!code-xml[TextAnimationSample#TextAnimationSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)