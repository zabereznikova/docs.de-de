---
title: "Gewusst wie: Empfangen von Benachrichtigungen bei Status&#228;nderungen der Uhr | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Uhren, Benachrichtigung von Zustandsänderungen"
  - "Benachrichtigungen, Zustandsänderung der Uhr"
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Empfangen von Benachrichtigungen bei Status&#228;nderungen der Uhr
Das <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated>\-Ereignis einer Uhr tritt auf, wenn ihr <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> ungültig wird, beispielsweise, wenn die Uhr angehalten oder gestartet wird.  Sie können dieses Ereignis registrieren, indem Sie entweder direkt eine <xref:System.Windows.Media.Animation.Clock> verwenden, oder indem Sie die Registrierung mit einer <xref:System.Windows.Media.Animation.Timeline> vornehmen.  
  
 Im folgenden Beispiel werden ein <xref:System.Windows.Media.Animation.Storyboard>\-Objekt und zwei <xref:System.Windows.Media.Animation.DoubleAnimation>\-Objekte verwendet, um die Breite von zwei Rechtecken zu animieren.  Das <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>\-Ereignis wird verwendet, um Statusänderungen der Uhr zu überwachen.  
  
## Beispiel  
 [!code-xml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 Die folgende Abbildung zeigt die unterschiedlichen Zustände an, in die die Animationen übergehen, während die übergeordnete Zeitachse \(*Storyboard*\) fortschreitet.  
  
 ![Uhr&#45;Zustände für ein Drehbuch mit zwei Animationen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm\_3timelines")  
  
 In der folgenden Tabelle sind die Zeiten aufgeführt, zu denen das <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>\-Ereignis von *Animation1* ausgelöst wird:  
  
||||||||  
|-|-|-|-|-|-|-|  
|Zeit \(Sekunden\)|1|10|19|21|30|39|  
|Zustand|Aktiv|Aktiv|Beendet|Aktiv|Aktiv|Beendet|  
  
 In der folgenden Tabelle sind die Zeiten aufgeführt, zu denen das <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>\-Ereignis von *Animation2* ausgelöst wird:  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|Zeit \(Sekunden\)|1|9|11|19|21|29|31|39|  
|Zustand|Aktiv|Füllung|Aktiv|Beendet|Aktiv|Füllung|Aktiv|Beendet|  
  
 Beachten Sie, dass das <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>\-Ereignis von *Animation1* bei 10 Sekunden ausgelöst wird, obwohl der Status weiterhin <xref:System.Windows.Media.Animation.ClockState> ist.  Dies kommt daher, dass sich der Status bei 10 Sekunden geändert hat, wobei er sich jedoch von <xref:System.Windows.Media.Animation.ClockState> in <xref:System.Windows.Media.Animation.ClockState> und am selben Teilstrich wieder in <xref:System.Windows.Media.Animation.ClockState> geändert hat.