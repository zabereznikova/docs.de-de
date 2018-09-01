---
title: Übersicht über die Verfahren zur Animation von Eigenschaften
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- animation [WPF], properties [WPF], methods for
- properties [WPF], methods for animating
ms.assetid: 74f61413-f8c0-4e75-bf04-951886426c8b
ms.openlocfilehash: 438b59aa4aa4213960e0bc3d479a2b949f6d374e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43395961"
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
|Storyboard-Animation|Pro Instanz, <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, <xref:System.Windows.DataTemplate>|Ja|Ja|  
|Lokale Animation|Pro Instanz|Nein|Nein|  
|Uhranimation|Pro Instanz|Nein|Ja|  
|Pro-Frame-Animation|Pro Instanz|Nein|Nicht zutreffend|  
  
<a name="storyboard_animations"></a>   
## <a name="storyboard-animations"></a>Storyboard-Animationen  
 Verwenden einer <xref:System.Windows.Media.Animation.Storyboard> soll beim Definieren und Anwenden von Animationen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]interaktiv steuern von Animationen, nach der sie beginnen, erstellen eine komplexe Struktur von Animationen oder Animieren in einem <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate> oder <xref:System.Windows.DataTemplate>. Für ein Objekt in einem animiert werden eine <xref:System.Windows.Media.Animation.Storyboard>, muss ein <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>, oder es muss werden verwendet, um eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>. Weitere Einzelheiten finden Sie unter [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 Ein <xref:System.Windows.Media.Animation.Storyboard> ist ein spezieller Typ des Containers <xref:System.Windows.Media.Animation.Timeline> , die Zielinformationen für die darin enthaltenen Animationen bereitstellt. Animieren mit einem <xref:System.Windows.Media.Animation.Storyboard>, Sie die folgenden drei Schritte ausführen.  
  
1.  Deklarieren Sie eine <xref:System.Windows.Media.Animation.Storyboard> und eine oder mehrere Animationen.  
  
2.  Verwenden der <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> angefügte Eigenschaften an das Zielobjekt und Eigenschaft der einzelnen Animationen.  
  
3.  (Nur Code) Definieren einer <xref:System.Windows.NameScope> für eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>. Registrieren Sie die Namen der Objekte, die mit dem Animieren <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>.  
  
4.  Beginnen der <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Ab einem <xref:System.Windows.Media.Animation.Storyboard> Animationen auf die Eigenschaften, die sie animieren angewendet, und startet sie. Es gibt zwei Möglichkeiten, um zu beginnen eine <xref:System.Windows.Media.Animation.Storyboard>: können Sie die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode bereitgestellt wird, durch die <xref:System.Windows.Media.Animation.Storyboard> -Klasse, oder Sie können eine <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion. Die einzige Möglichkeit zur Animation in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist die Verwendung einer <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion. Ein <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion kann verwendet werden, eine <xref:System.Windows.EventTrigger>, Eigenschaft <xref:System.Windows.Trigger>, oder ein <xref:System.Windows.DataTrigger>.  
  
 Die folgende Tabelle zeigt die unterschiedlichen Stellen, in dem jede <xref:System.Windows.Media.Animation.Storyboard> beginnen Technik wird unterstützt: pro Instanz, Stil, Steuerelementvorlage und Datenvorlage.  
  
|Storyboard wird gestartet mit...|Pro Instanz|Stil|Steuerelementvorlage|Datenvorlage|Beispiel|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> und ein <xref:System.Windows.EventTrigger>|Ja|Ja|Ja|Ja|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> und eine Eigenschaft <xref:System.Windows.Trigger>|Nein|Ja|Ja|Ja|[Auslösen einer Animation, wenn sich eine Eigenschaft ändert](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> und ein <xref:System.Windows.DataTrigger>|Nein|Ja|Ja|Ja|[Vorgehensweise: Auslösen einer Animation bei Änderung eines Eigenschaftswerts](https://msdn.microsoft.com/library/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode|Ja|Nein|Nein|Nein|[Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 Weitere Informationen zu <xref:System.Windows.Media.Animation.Storyboard> Objekten finden Sie die [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
## <a name="local-animations"></a>Lokale Animationen  
 Lokale Animationen bieten eine bequeme Möglichkeit, eine Abhängigkeitseigenschaft eines animieren <xref:System.Windows.Media.Animation.Animatable> Objekt. Verwenden Sie lokale Animationen, wenn Sie eine einzelne Animation auf eine Eigenschaft anwenden möchten und Sie die Animation nach dem Start nicht interaktiv steuern müssen. Im Gegensatz zu einem <xref:System.Windows.Media.Animation.Storyboard> Animation, die eine lokale Animation kann eine Animieren eines Objekts, die zugeordnet wird keine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>. Müssen Sie auch nicht definieren eine <xref:System.Windows.NameScope> für diese Art von Animation.  
  
 Lokale Animationen können nur in Code verwendet und können nicht in Stilen, Steuerelementvorlagen oder Datenvorlagen definiert werden. Eine lokale Animation kann nicht interaktiv gesteuert werden, nachdem sie gestartet wurde.  
  
 Zum Animieren mithilfe einer lokalen Animation führen Sie folgende Schritte aus.  
  
1.  Erstellen Sie eine <xref:System.Windows.Media.Animation.AnimationTimeline> Objekt.  
  
2.  Verwenden der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode des Objekts, das zu animierende zum Anwenden der <xref:System.Windows.Media.Animation.AnimationTimeline> der Eigenschaft, die Sie angeben.  
  
 Das folgende Beispiel zeigt, wie Sie die Breite und Hintergrundfarbe Farbe Animieren einer <xref:System.Windows.Controls.Button>.  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## <a name="clock-animations"></a>Uhranimationen  
 Verwendung <xref:System.Windows.Media.MediaPlayer.Clock%2A> Objekte ohne animiert werden soll eine <xref:System.Windows.Media.Animation.Storyboard> und komplexe zeitsteuerungsbäume erstellen oder Animationen nach ihrem start interaktiv steuern möchten. Können Sie uhrobjekten eine Abhängigkeitseigenschaft eines animieren <xref:System.Windows.Media.Animation.Animatable> Objekt.  
  
 Sie können keine <xref:System.Windows.Media.Animation.Clock> Objekte direkt zum Animieren in Stilen, steuern, Vorlagen oder Datenvorlagen. (Das Animations- und Zeitsteuerungssystem verwendet <xref:System.Windows.Media.Animation.Clock> Objekte animieren in Stilen, Steuerelementvorlagen, und Datenvorlagen, aber sie müssen diese erstellen <xref:System.Windows.Media.Animation.Clock> Objekte für Sie aus einer <xref:System.Windows.Media.Animation.Storyboard>. Weitere Informationen über die Beziehung zwischen <xref:System.Windows.Media.Animation.Storyboard> Objekte und <xref:System.Windows.Media.Animation.Clock> Objekten finden Sie die [Animation und zeitliche Steuerung Systemübersicht](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).)  
  
 Anwenden eine einzelnen <xref:System.Windows.Media.Animation.Clock> auf eine Eigenschaft, führen Sie die folgenden Schritte aus.  
  
1.  Erstellen Sie eine <xref:System.Windows.Media.Animation.AnimationTimeline> Objekt.  
  
2.  Verwenden der <xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A> Methode der <xref:System.Windows.Media.Animation.AnimationTimeline> zum Erstellen einer <xref:System.Windows.Media.Animation.AnimationClock>.  
  
3.  Verwenden der <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> Methode des Objekts, das zu animierende zum Anwenden der <xref:System.Windows.Media.Animation.AnimationClock> der Eigenschaft, die Sie angeben.  
  
 Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Media.Animation.AnimationClock> und auf zwei ähnliche Eigenschaften angewendet.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Um eine Zeitsteuerungsstruktur zu erstellen und zum Animieren von Eigenschaften zu verwenden, führen Sie die folgenden Schritte aus.  
  
1.  Verwendung <xref:System.Windows.Media.Animation.ParallelTimeline> und <xref:System.Windows.Media.Animation.AnimationTimeline> Objekte zum Erstellen einer zeitsteuerungsstruktur.  
  
2.  Verwenden der <xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A> des Stamms <xref:System.Windows.Media.Animation.ParallelTimeline> zum Erstellen einer <xref:System.Windows.Media.Animation.ClockGroup>.  
  
3.  Durchlaufen der <xref:System.Windows.Media.Animation.ClockGroup.Children%2A> von der <xref:System.Windows.Media.Animation.ClockGroup> und Anwenden von untergeordneten <xref:System.Windows.Media.Animation.Clock> Objekte. Für jede <xref:System.Windows.Media.Animation.AnimationClock> untergeordneten, verwenden die <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> Methode des Objekts, das Sie animieren, die zum anwenden möchten die <xref:System.Windows.Media.Animation.AnimationClock> der Eigenschaft, die Sie angeben  
  
 Weitere Informationen zu Uhrobjekten finden Sie unter [Übersicht über das Animations- und Zeitsteuerungssystem](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## <a name="per-frame-animation-bypass-the-animation-and-timing-system"></a>Pro-Frame-Animation: Umgehen Sie das Animations- und Zeitsteuerungssystem  
 Verwenden Sie diesen Ansatz, wenn Sie das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animationssystem vollständig umgehen müssen. Ein Szenario für diesen Ansatz sind Animationen in der Physik. Hier setzt jeder Schritt der Animation voraus, dass Objekte basierend auf dem letzten Satz von Objektinteraktionen neu berechnet werden müssen.  
  
 Pro-Frame-Animationen können nicht innerhalb der Stile, Steuerelementvorlagen oder Datenvorlagen definiert werden.  
  
 Um einen Frame für Frame zu animieren, registrieren Sie sich für die <xref:System.Windows.Media.CompositionTarget.Rendering> -Ereignis des Objekts, das die Objekte enthält, Sie animieren möchten. Diese Ereignishandlermethode wird einmal pro Frame aufgerufen. Immer wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die beibehaltenen Renderingdaten in der visuellen Struktur für die Kompositionsstruktur marshallt, wird die Ereignishandlermethode aufgerufen.  
  
 Führen Sie im Ereignishandler alle für den Animationseffekt erforderlichen Berechnungen durch, und legen Sie die Eigenschaften der Objekte fest, die Sie mit diesen Werten animieren möchten.  
  
 Um die Präsentationszeit für den aktuellen Frame, erhalten die <xref:System.EventArgs> zugeordnete Ereignis umgewandelt werden kann <xref:System.Windows.Media.RenderingEventArgs>, bieten eine <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> -Eigenschaft, die Sie verwenden können, um den aktuellen Frame abzurufen des rendering-Zeit.  
  
 Weitere Informationen finden Sie unter den <xref:System.Windows.Media.CompositionTarget.Rendering> Seite.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Übersicht über das Animations- und Zeitsteuerungssystem](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
