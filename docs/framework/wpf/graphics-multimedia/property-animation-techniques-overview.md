---
title: "Übersicht über die Verfahren zur Animation von Eigenschaften"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- animation [WPF], properties [WPF], methods for
- properties [WPF], methods for animating
ms.assetid: 74f61413-f8c0-4e75-bf04-951886426c8b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8ba7c580963214cdfede605f086b6b6c7ecb5657
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="property-animation-techniques-overview"></a>Übersicht über die Verfahren zur Animation von Eigenschaften
Dieses Thema beschreibt die unterschiedlichen Ansätze zum Animieren von Eigenschaften: Storyboards, lokale Animationen, Uhren und Pro-Frame-Animationen.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Als Voraussetzung für dieses Thema sollten Sie mit den grundlegenden Animationsfunktionen unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) vertraut sein.  
  
<a name="summary"></a>   
## <a name="different-ways-to-animate"></a>Verschiedene Methoden zum Animieren  
 Da viele unterschiedliche Szenarien zum Animieren von Eigenschaften vorhanden sind, bietet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mehrere Ansätze zum Animieren von Eigenschaften.  
  
 Für jeden der Ansätze gibt die folgende Tabelle an, ob er pro Instanz, in Stilen, in Steuerelementvorlagen oder in Datenvorlagen verwendet werden kann, ob er in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwendet werden kann und ob er Ihnen ermöglicht, die Animation interaktiv steuern kann.  „Pro Instanz“ bezieht sich auf das Verfahren, eine Animation oder ein Storyboard direkt auf Instanzen eines Objekts und nicht in einem Stil, einer Steuerelementvorlage oder einer Datenvorlage anzuwenden.  
  
|Animationsmethode|Szenarien|Unterstützt XAML|Interaktiv steuerbar|  
|-------------------------|---------------|-------------------|--------------------------------|  
|Storyboard-Animation|Pro Instanz <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>,<xref:System.Windows.DataTemplate>|Ja|Ja|  
|Lokale Animation|Pro Instanz|Nein|Nein|  
|Uhranimation|Pro Instanz|Nein|Ja|  
|Pro-Frame-Animation|Pro Instanz|Nein|Nicht zutreffend|  
  
<a name="storyboard_animations"></a>   
## <a name="storyboard-animations"></a>Storyboard-Animationen  
 Verwenden einer <xref:System.Windows.Media.Animation.Storyboard> soll beim Definieren und Anwenden von Animationen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]interaktiv Animationen steuern, nachdem er beginnen, erstellen eine komplexe Struktur von Animationen oder in animieren eine <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate> oder <xref:System.Windows.DataTemplate>. Für ein Objekt nach animiert werden soll eine <xref:System.Windows.Media.Animation.Storyboard>, muss er eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>, oder es muss verwendet werden, Festlegen einer <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>. Weitere Einzelheiten finden Sie unter [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 Ein <xref:System.Windows.Media.Animation.Storyboard> ist ein besonderer Typ des Containers <xref:System.Windows.Media.Animation.Timeline> Zielinformationen für die darin enthaltenen Animationen bereitstellt. Animieren Sie mit einem <xref:System.Windows.Media.Animation.Storyboard>, Sie die folgenden drei Schritte ausführen.  
  
1.  Deklarieren Sie eine <xref:System.Windows.Media.Animation.Storyboard> und eine oder mehrere Animationen.  
  
2.  Verwenden der <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> angefügte Eigenschaften zur Angabe des Zielobjekts und die Eigenschaft für jede Animation.  
  
3.  (Nur Code) Definieren einer <xref:System.Windows.NameScope> für eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>. Registrieren Sie die Namen der Objekte, die mit dem Animieren <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>.  
  
4.  Beginnen der <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Beginnt eine <xref:System.Windows.Media.Animation.Storyboard> Animationen angewendet, um die Eigenschaften, die sie dem animiert werden soll, und starten. Es gibt zwei Möglichkeiten, um zu beginnen ein <xref:System.Windows.Media.Animation.Storyboard>: können Sie die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode bereitgestellt wird, indem Sie die <xref:System.Windows.Media.Animation.Storyboard> -Klasse, oder Sie können eine <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion. Die einzige Möglichkeit zum Animieren [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist die Verwendung einer <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion. Ein <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion kann verwendet werden, eine <xref:System.Windows.EventTrigger>, Eigenschaft <xref:System.Windows.Trigger>, oder ein <xref:System.Windows.DataTrigger>.  
  
 Die folgende Tabelle zeigt die verschiedenen Positionen, in dem jede <xref:System.Windows.Media.Animation.Storyboard> beginnen Technik wird unterstützt: pro Instanz, Stil, Steuerelementvorlage und Datenvorlage.  
  
|Storyboard wird gestartet mit...|Pro Instanz|Stil|Steuerelementvorlage|Datenvorlage|Beispiel|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>und ein<xref:System.Windows.EventTrigger>|Ja|Ja|Ja|Ja|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>und einer Eigenschaft<xref:System.Windows.Trigger>|Nein|Ja|Ja|Ja|[Auslösen einer Animation, wenn sich eine Eigenschaft ändert](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>und ein<xref:System.Windows.DataTrigger>|Nein|Ja|Ja|Ja|[Vorgehensweise: Auslösen einer Animation bei Änderung eines Eigenschaftswerts](http://msdn.microsoft.com/library/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode|Ja|Nein|Nein|Nein|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 Weitere Informationen zu <xref:System.Windows.Media.Animation.Storyboard> anzuzeigen, die [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
## <a name="local-animations"></a>Lokale Animationen  
 Lokale Animationen bieten eine einfache Möglichkeit, eine Abhängigkeitseigenschaft eines beliebigen animieren <xref:System.Windows.Media.Animation.Animatable> Objekt. Verwenden Sie lokale Animationen, wenn Sie eine einzelne Animation auf eine Eigenschaft anwenden möchten und Sie die Animation nach dem Start nicht interaktiv steuern müssen. Im Gegensatz zu einer <xref:System.Windows.Media.Animation.Storyboard> Animation, eine lokale Animation kann ein Objekt, das zugeordnet ist nicht Animieren einer <xref:System.Windows.FrameworkElement> oder ein <xref:System.Windows.FrameworkContentElement>. Müssen Sie auch nicht definieren eine <xref:System.Windows.NameScope> für diesen Typ der Animation.  
  
 Lokale Animationen können nur in Code verwendet und können nicht in Stilen, Steuerelementvorlagen oder Datenvorlagen definiert werden. Eine lokale Animation kann nicht interaktiv gesteuert werden, nachdem sie gestartet wurde.  
  
 Zum Animieren mithilfe einer lokalen Animation führen Sie folgende Schritte aus.  
  
1.  Erstellen Sie ein <xref:System.Windows.Media.Animation.AnimationTimeline> Objekt.  
  
2.  Verwenden der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> -Methode des Objekts, die zu animierende zum Anwenden der <xref:System.Windows.Media.Animation.AnimationTimeline> der Eigenschaft, die Sie angeben.  
  
 Das folgende Beispiel zeigt, wie Sie die Breite und Hintergrund Farbe Animieren einer <xref:System.Windows.Controls.Button>.  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## <a name="clock-animations"></a>Uhranimationen  
 Verwendung <xref:System.Windows.Media.MediaPlayer.Clock%2A> Objekte, wenn Sie ohne animieren möchten eine <xref:System.Windows.Media.Animation.Storyboard> und komplexe Zeitstrukturen erstellen oder Animationen nach dem start interaktiv steuern möchten. Können Sie Objekte Uhr um zu animierende Abhängigkeitseigenschaft eines beliebigen <xref:System.Windows.Media.Animation.Animatable> Objekt.  
  
 Sie können keine <xref:System.Windows.Media.Animation.Clock> Objekte direkt zu animierende in Formaten, kontrollieren, Vorlagen oder Datenvorlagen. (Der Animation und zeitlichen Steuerung verwendet <xref:System.Windows.Media.Animation.Clock> Objekte zu animierende im Stile, Vorlagen, und Datenvorlagen, aber sie müssen die erstellen <xref:System.Windows.Media.Animation.Clock> Objekte für Sie von einem <xref:System.Windows.Media.Animation.Storyboard>. Weitere Informationen über die Beziehung zwischen <xref:System.Windows.Media.Animation.Storyboard> Objekte und <xref:System.Windows.Media.Animation.Clock> anzuzeigen, die [Animationen und zeitlichen Steuerung Systemübersicht](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).)  
  
 Anwenden eine einzelnen <xref:System.Windows.Media.Animation.Clock> einer Eigenschaft, die folgenden Schritte ausführen.  
  
1.  Erstellen Sie ein <xref:System.Windows.Media.Animation.AnimationTimeline> Objekt.  
  
2.  Verwenden der <xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A> Methode der <xref:System.Windows.Media.Animation.AnimationTimeline> zum Erstellen einer <xref:System.Windows.Media.Animation.AnimationClock>.  
  
3.  Verwenden der <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> -Methode des Objekts, die zu animierende zum Anwenden der <xref:System.Windows.Media.Animation.AnimationClock> der Eigenschaft, die Sie angeben.  
  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Media.Animation.AnimationClock> und auf zwei ähnliche Eigenschaften angewendet.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Um eine Zeitsteuerungsstruktur zu erstellen und zum Animieren von Eigenschaften zu verwenden, führen Sie die folgenden Schritte aus.  
  
1.  Verwendung <xref:System.Windows.Media.Animation.ParallelTimeline> und <xref:System.Windows.Media.Animation.AnimationTimeline> -Objekten, die Zeitstruktur zu erstellen.  
  
2.  Verwenden der <xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A> des Stamms <xref:System.Windows.Media.Animation.ParallelTimeline> zum Erstellen einer <xref:System.Windows.Media.Animation.ClockGroup>.  
  
3.  Durchlaufen der <xref:System.Windows.Media.Animation.ClockGroup.Children%2A> von der <xref:System.Windows.Media.Animation.ClockGroup> und Anwenden von untergeordneten <xref:System.Windows.Media.Animation.Clock> Objekte. Für jede <xref:System.Windows.Media.Animation.AnimationClock> untergeordneten, verwenden die <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> -Methode des Objekts, die zu animierende zum Anwenden der <xref:System.Windows.Media.Animation.AnimationClock> der Eigenschaft, die Sie angeben  
  
 Weitere Informationen zu Uhrobjekten finden Sie unter [Übersicht über das Animations- und Zeitsteuerungssystem](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## <a name="per-frame-animation-bypass-the-animation-and-timing-system"></a>Pro-Frame-Animation: Umgehen Sie das Animations- und Zeitsteuerungssystem  
 Verwenden Sie diesen Ansatz, wenn Sie das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationssystem vollständig umgehen müssen. Ein Szenario für diesen Ansatz sind Animationen in der Physik. Hier setzt jeder Schritt der Animation voraus, dass Objekte basierend auf dem letzten Satz von Objektinteraktionen neu berechnet werden müssen.  
  
 Pro-Frame-Animationen können nicht innerhalb der Stile, Steuerelementvorlagen oder Datenvorlagen definiert werden.  
  
 Um einen Frame nach dem anderen animieren, registrieren Sie sich für die <xref:System.Windows.Media.CompositionTarget.Rendering> -Ereignis für das Objekt, das die Objekte enthält animiert werden soll. Diese Ereignishandlermethode wird einmal pro Frame aufgerufen. Immer wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die beibehaltenen Renderingdaten in der visuellen Struktur für die Kompositionsstruktur marshallt, wird die Ereignishandlermethode aufgerufen.  
  
 Führen Sie im Ereignishandler alle für den Animationseffekt erforderlichen Berechnungen durch, und legen Sie die Eigenschaften der Objekte fest, die Sie mit diesen Werten animieren möchten.  
  
 Zum Abrufen der Präsentationszeit für den aktuellen Frame der <xref:System.EventArgs> zugeordnete Ereignis umgewandelt werden kann, als <xref:System.Windows.Media.RenderingEventArgs>, bieten eine <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> -Eigenschaft, die Sie verwenden können, um den aktuellen Frame erhalten die rendering-Zeit.  
  
 Weitere Informationen finden Sie unter der <xref:System.Windows.Media.CompositionTarget.Rendering> Seite.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Übersicht über das Animations- und Zeitsteuerungssystem](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
