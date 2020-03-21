---
title: Tipps und Tricks zu Animationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting [WPF], animation
- animations [WPF], FillBehavior property
- troubleshooting animation [WPF]
- animating objects [WPF], troubleshooting
- animation tips and tricks [WPF]
- tips and tricks [WPF], animation
- performance troubleshooting [WPF], animation
- animations [WPF], use of system resources
ms.assetid: e467796b-d5d4-45a6-a108-8c5d7ff69a0f
ms.openlocfilehash: 6b540448599c1e1083ed367a312ef60fceacd0d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187648"
---
# <a name="animation-tips-and-tricks"></a>Tipps und Tricks zu Animationen
Wenn Sie mit Animationen in WPF arbeiten, gibt es eine Reihe von Tipps und Tricks, die Ihre Animationen besser ausführen und Frustration ersparen können.  
  
<a name="generalissuessection"></a>
## <a name="general-issues"></a>Allgemeine Probleme  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>Durch Animieren der Position einer Bildlaufleiste oder eines Schiebereglers wird das Element gesperrt  
 Wenn Sie die Position eines Bildlaufleistens oder <xref:System.Windows.Media.Animation.FillBehavior> Schiebereglers mithilfe einer Animation mit einem von <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> (dem Standardwert) animieren, kann der Benutzer den Bildlaufbalken oder Schieberegler nicht mehr verschieben. Das liegt daran, dass, obwohl die Animation beendet wurde, nach wie vor der Basiswert der Zieleigenschaft überschrieben wird. Um zu verhindern, dass die Animation den aktuellen Wert der <xref:System.Windows.Media.Animation.FillBehavior> Eigenschaft <xref:System.Windows.Media.Animation.FillBehavior.Stop>überschreibt, entfernen Sie sie, oder geben Sie ihr eine von . Weitere Informationen und ein Beispiel finden Sie unter [Festlegen einer Eigenschaft nach dem Animieren mit einem Storyboard](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>Das Animieren der Ausgabe einer Animation hat keine Auswirkungen  
 Sie können kein Objekt animieren, das die Ausgabe einer anderen Animation ist. Wenn Sie z. <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> B. <xref:System.Windows.Shapes.Shape.Fill%2A> eine <xref:System.Windows.Shapes.Rectangle> verwenden, <xref:System.Windows.Media.RadialGradientBrush> um <xref:System.Windows.Media.SolidColorBrush>die von a zu animieren, können Sie keine Eigenschaften der <xref:System.Windows.Media.RadialGradientBrush> oder <xref:System.Windows.Media.SolidColorBrush>animieren.  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>Das Ändern des Werts einer Eigenschaft ist nach dem Animieren nicht möglich  
 Möglicherweise kommt es vor, dass Sie den Wert einer einmal animierten Eigenschaft, auch nachdem die Animation beendet wurde, nicht verändern können. Das liegt daran, dass, obwohl die Animation beendet wurde, immer noch der Basiswert der Eigenschaft überschrieben wird. Um zu verhindern, dass die Animation den aktuellen Wert der <xref:System.Windows.Media.Animation.FillBehavior> Eigenschaft <xref:System.Windows.Media.Animation.FillBehavior.Stop>überschreibt, entfernen Sie sie, oder geben Sie ihr eine von . Weitere Informationen und ein Beispiel finden Sie unter [Festlegen einer Eigenschaft nach dem Animieren mit einem Storyboard](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="changing-a-timeline-has-no-effect"></a>Das Ändern einer Zeitachse hat keine Auswirkung  
 Obwohl <xref:System.Windows.Media.Animation.Timeline> die meisten Eigenschaften animierbar sind und datengebunden sein <xref:System.Windows.Media.Animation.Timeline> können, scheint das Ändern der Eigenschaftswerte eines Aktiven keine Auswirkungen zu haben. Das liegt daran, <xref:System.Windows.Media.Animation.Timeline> dass das Timing-System, wenn <xref:System.Windows.Media.Animation.Timeline> ein gestartet wird, <xref:System.Windows.Media.Animation.Clock> eine Kopie des erstellt und es zum Erstellen eines Objekts verwendet. Eine Änderung des Original hat keine Auswirkung auf die Kopie des Systems.  
  
 Um <xref:System.Windows.Media.Animation.Timeline> Änderungen widerzuspiegeln, muss die Uhr regeneriert und verwendet werden, um die zuvor erstellte Uhr zu ersetzen. Uhren werden nicht automatisch neu generiert. Im Folgenden werden verschiedene Methoden beschrieben, wie Änderungen der Zeitachse übernommen werden können:  
  
- Wenn die Zeitachse eine <xref:System.Windows.Media.Animation.Storyboard>ist oder zu einem gehört, können Sie <xref:System.Windows.Media.Animation.BeginStoryboard> Änderungen <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> reflektieren, indem Sie ihr Storyboard mithilfe einer oder der Methode erneut anwenden. Dies hat den Nebeneffekt, dass auch die Animation neu gestartet wird. Im Code können Sie <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> die Methode verwenden, um das Storyboard wieder an seine vorherige Position zu bringen.  
  
- Wenn Sie eine Animation mithilfe der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode direkt <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> auf eine Eigenschaft angewendet haben, rufen Sie die Methode erneut auf, und übergeben Sie sie an die geänderte Animation.  
  
- Wenn Sie direkt auf der Uhrebene arbeiten, erstellen Sie einen neuen Satz von Uhren, und verwenden sie diese, um den zuvor generierten Satz von Uhren zu ersetzen.  
  
 Weitere Informationen zu Zeitachsen und Uhren finden Sie unter [Animation und Timing System Overview](animation-and-timing-system-overview.md).  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>FillBehavior.Stop funktioniert nicht wie erwartet  
 Es gibt Zeiten, <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> in <xref:System.Windows.Media.Animation.FillBehavior.Stop> denen die Einstellung der Eigenschaft auf "keine Wirkung" zu <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> haben <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>scheint, z. B. wenn eine Animation eine andere "abgibt", weil sie eine Einstellung von hat.  
  
 Im folgenden Beispiel <xref:System.Windows.Controls.Canvas>werden <xref:System.Windows.Shapes.Rectangle> a <xref:System.Windows.Media.TranslateTransform>, a und a erstellt. Die <xref:System.Windows.Media.TranslateTransform> wird animiert, um die <xref:System.Windows.Shapes.Rectangle> zu <xref:System.Windows.Controls.Canvas>bewegen.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 In den Beispielen in diesem Abschnitt werden <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> die vorherigen Objekte verwendet, um mehrere Fälle zu veranschaulichen, in denen sich die Eigenschaft nicht so verhält, wie Sie es vielleicht erwarten.  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>FillBehavior="Stop" und HandoffBehavior mit mehreren Animationen  
 Manchmal scheint es, als ob <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> eine Animation ihre Eigenschaft ignoriert, wenn sie durch eine zweite Animation ersetzt wird. Nehmen Sie das folgende <xref:System.Windows.Media.Animation.Storyboard> Beispiel, das zwei Objekte <xref:System.Windows.Media.TranslateTransform> erstellt und sie verwendet, um dasselbe zu animieren, das im vorherigen Beispiel gezeigt wurde.  
  
 Die <xref:System.Windows.Media.Animation.Storyboard>erste `B1`animiert <xref:System.Windows.Media.TranslateTransform.X%2A> die <xref:System.Windows.Media.TranslateTransform> Eigenschaft von 0 bis 350, wodurch das Rechteck 350 Pixel nach rechts verschoben wird. Wenn die Animation das Ende ihrer Dauer <xref:System.Windows.Media.TranslateTransform.X%2A> erreicht und die Wiedergabe beendet, wird die Eigenschaft auf ihren ursprünglichen Wert 0 zurückgesetzt. Das Rechteck wird daraufhin 350 Pixel nach rechts bewegt, und springt dann zurück an seine ursprüngliche Position.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 Die <xref:System.Windows.Media.Animation.Storyboard>zweite `B2`, animiert auch <xref:System.Windows.Media.TranslateTransform.X%2A> <xref:System.Windows.Media.TranslateTransform>die Eigenschaft derselben . Da nur <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> die Eigenschaft der <xref:System.Windows.Media.Animation.Storyboard> Animation in diesem Objekt festgelegt ist, verwendet die Animation den aktuellen Wert der Eigenschaft, die sie animiert, als Startwert.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 Wenn Sie auf die zweite <xref:System.Windows.Media.Animation.Storyboard> Schaltfläche klicken, während die erste wiedergabe, können Sie das folgende Verhalten erwarten:  
  
1. Das erste Storyboard endet und sendet das Rechteck zurück an <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.Stop>seine ursprüngliche Position, da die Animation eine von hat.  
  
2. Das zweite Storyboard wird wirksam und animiert von der aktuellen Position, 0, auf 500.  
  
 **Dies geschieht jedoch nicht.** Stattdessen springt das Rechteck nicht zurück; es verschiebt sich weiter nach rechts. Der Grund ist die zweite Animation, welche den aktuellen Wert der ersten Animation als ihren Startwert verwendet und von diesem Wert auf 500 animiert. Wenn die zweite Animation die <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> <xref:System.Windows.Media.Animation.HandoffBehavior> erste ersetzt, <xref:System.Windows.Media.Animation.FillBehavior> weil die verwendet wird, spielt die erste Animation keine Rolle.  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior und das abgeschlossene Ereignis  
 Die nächsten Beispiele zeigen ein <xref:System.Windows.Media.Animation.FillBehavior.Stop> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> anderes Szenario, in dem die keine Auswirkungen zu haben scheint. Auch hier wird im Beispiel ein <xref:System.Windows.Media.TranslateTransform.X%2A> Storyboard <xref:System.Windows.Media.TranslateTransform> verwendet, um die Eigenschaft von 0 bis 350 zu animieren. Dieses Mal wird jedoch das <xref:System.Windows.Media.Animation.Timeline.Completed> Beispiel für das Ereignis registriert.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 Der <xref:System.Windows.Media.Animation.Timeline.Completed> Ereignishandler <xref:System.Windows.Media.Animation.Storyboard> startet einen anderen, der dieselbe Eigenschaft von seinem aktuellen Wert auf 500 animiert.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 Im Folgenden finden Sie das Markup, das das zweite <xref:System.Windows.Media.Animation.Storyboard> Markals als Ressource definiert.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 Wenn Sie <xref:System.Windows.Media.Animation.Storyboard>die ausführen, <xref:System.Windows.Media.TranslateTransform.X%2A> können Sie <xref:System.Windows.Media.TranslateTransform> erwarten, dass die Eigenschaft des von 0 bis 350 animiert wird, und kehren dann nach Abschluss auf 0 zurück (da sie eine <xref:System.Windows.Media.Animation.FillBehavior> Einstellung von <xref:System.Windows.Media.Animation.FillBehavior.Stop>hat), und dann von 0 bis 500 animieren. Stattdessen werden <xref:System.Windows.Media.TranslateTransform> die Animationen von 0 bis 350 und dann auf 500 animiert.  
  
 Dies liegt an der Reihenfolge, in der WPF Ereignisse auslöst, und weil Eigenschaftswerte zwischengespeichert und nicht neu berechnet werden, es sei denn, die Eigenschaft wird ungültig. Das <xref:System.Windows.Media.Animation.Timeline.Completed> Ereignis wird zuerst verarbeitet, da es durch <xref:System.Windows.Media.Animation.Storyboard>die Stammzeitachse (die erste ) ausgelöst wurde. Zu diesem Zeitpunkt <xref:System.Windows.Media.TranslateTransform.X%2A> gibt die Eigenschaft immer noch ihren animierten Wert zurück, da sie noch nicht ungültig wurde. Der <xref:System.Windows.Media.Animation.Storyboard> zweite Wert verwendet den zwischengespeicherten Wert als Startwert und beginnt zu animieren.  
  
<a name="performancesection"></a>
## <a name="performance"></a>Leistung  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>Animationen werden, auch nach Verlassen einer Seite fortgesetzt  
 Wenn Sie von <xref:System.Windows.Controls.Page> einer, die ausgeführte Animationen enthält, <xref:System.Windows.Controls.Page> wegnavigieren, werden diese Animationen so lange fortgesetzt, bis der Garbage Collection ist. Abhängig vom Navigationssystem, das Sie verwenden, bleibt eine Seite, die Sie Verlassen möglicherweise für einen unbestimmten Zeitraum im Speicher , und es werden aufgrund von Animationen Ressourcen belegt. Dies ist am deutlichsten sichtbar, wenn eine Seite ständig ausgeführte(„Umgebungs“-) Animationen enthält.  
  
 Aus diesem Grund ist es eine gute <xref:System.Windows.FrameworkElement.Unloaded> Idee, das Ereignis zu verwenden, um Animationen zu entfernen, wenn Sie von einer Seite weg navigieren.  
  
 Es gibt verschiedene Möglichkeiten, eine Animation zu entfernen. Die folgenden Techniken können verwendet werden, <xref:System.Windows.Media.Animation.Storyboard>um Animationen zu entfernen, die zu einem gehören.  
  
- Informationen zum <xref:System.Windows.Media.Animation.Storyboard> Entfernen eines, das Sie mit einem Ereignistrigger gestartet haben, finden Sie unter [Gewusst wie: Entfernen eines Storyboards](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749412(v=vs.90)).  
  
- Informationen zum Entfernen <xref:System.Windows.Media.Animation.Storyboard>von Code <xref:System.Windows.Media.Animation.Storyboard.Remove%2A> finden Sie unter Die Methode.  
  
 Die nächste Technik kann verwendet werden, unabhängig davon, wie die Animation gestartet wurde.  
  
- Verwenden Sie die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> Methode, um Animationen aus einer bestimmten Eigenschaft zu entfernen. Geben Sie die Eigenschaft an, `null` die als erster Parameter und als zweiter animiert wird. Dies entfernt alle Animationsuhren aus der Eigenschaft.  
  
 Weitere Informationen zu den verschiedenen Möglichkeiten zum Animieren von Eigenschaften finden Sie unter [Übersicht über Eigenschaftenanimationstechniken](property-animation-techniques-overview.md).  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>Das Verwenden von Compose HandoffBehavior belegt Systemressourcen  
 Wenn Sie <xref:System.Windows.Media.Animation.Storyboard>eine <xref:System.Windows.Media.Animation.AnimationTimeline>, <xref:System.Windows.Media.Animation.AnimationClock> oder eine <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior>Eigenschaft <xref:System.Windows.Media.Animation.Clock> mit der anwenden, verbrauchen alle Objekte, die zuvor dieser Eigenschaft zugeordnet waren, weiterhin Systemressourcen. das Timing-System entfernt diese Uhren nicht automatisch.  
  
 Um Leistungsprobleme zu vermeiden, wenn Sie <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>eine große Anzahl von Uhren mit anwenden, sollten Sie die kompositionen Uhren aus der animierten Eigenschaft entfernen, nachdem sie abgeschlossen sind. Es gibt mehrere Möglichkeiten, eine Uhr zu entfernen.  
  
- Um alle Uhren aus einer Eigenschaft <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> zu entfernen, verwenden Sie die oder-Methode des animierten Objekts. Geben Sie die Eigenschaft an, `null` die als erster Parameter und als zweiter animiert wird. Dies entfernt alle Animationsuhren aus der Eigenschaft.  
  
- Um eine <xref:System.Windows.Media.Animation.AnimationClock> bestimmte aus einer Liste von <xref:System.Windows.Media.Animation.Clock.Controller%2A> Uhren <xref:System.Windows.Media.Animation.AnimationClock> zu entfernen, verwenden Sie die Eigenschaft des , um eine <xref:System.Windows.Media.Animation.ClockController>abzurufen, und rufen Sie dann die <xref:System.Windows.Media.Animation.ClockController.Remove%2A> Methode der <xref:System.Windows.Media.Animation.ClockController>auf. Dies geschieht in <xref:System.Windows.Media.Animation.Clock.Completed> der Regel im Ereignishandler für eine Uhr. Beachten Sie, dass nur Root-Uhren durch eine <xref:System.Windows.Media.Animation.ClockController>gesteuert werden können; die <xref:System.Windows.Media.Animation.Clock.Controller%2A> Eigenschaft einer untergeordneten `null`Uhr wird zurückgegeben. Beachten Sie <xref:System.Windows.Media.Animation.Clock.Completed> auch, dass das Ereignis nicht aufgerufen wird, wenn die effektive Dauer der Uhr für immer ist.  In diesem Fall muss der Benutzer bestimmen, wann er aufruft. <xref:System.Windows.Media.Animation.ClockController.Remove%2A>  
  
 Dies betrifft hauptsächlich Animationen für Objekte, die eine lange Lebensdauer haben.  Wenn ein Objekt an den Garbage Collector übergeben wird, werden auch die Uhren getrennt und an den Garbage Collector übergeben.  
  
 Weitere Informationen zu Uhrobjekten finden Sie unter [Animation und Timing System Overview](animation-and-timing-system-overview.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Animationen](animation-overview.md)
