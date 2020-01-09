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
ms.openlocfilehash: ef59631663e6cf1c98adfed77a2dbdb6ca124fa1
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636028"
---
# <a name="animation-tips-and-tricks"></a>Tipps und Tricks zu Animationen
Wenn Sie mit Animationen in WPF arbeiten, gibt es eine Reihe von Tipps und Tricks, mit denen Ihre Animationen besser funktionieren und Ihre Frustration verbessern können.  
  
<a name="generalissuessection"></a>   
## <a name="general-issues"></a>Allgemeine Probleme  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>Durch Animieren der Position einer Bildlaufleiste oder eines Schiebereglers wird das Element gesperrt  
 Wenn Sie die Position einer Bild Lauf Leiste oder eines Schiebereglers mithilfe einer Animation Animieren, die über eine <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> (Standardwert) verfügt, kann der Benutzer die Bild Lauf Leiste oder den Schieberegler nicht mehr verschieben. Das liegt daran, dass, obwohl die Animation beendet wurde, nach wie vor der Basiswert der Zieleigenschaft überschrieben wird. Um zu verhindern, dass die Animation den aktuellen Wert der Eigenschaft überschreibt, entfernen Sie Sie, oder versehen Sie Sie mit einem <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Weitere Informationen und ein Beispiel finden Sie unter [Festlegen einer Eigenschaft nach dem Animieren mit einem Storyboard](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>Das Animieren der Ausgabe einer Animation hat keine Auswirkungen  
 Sie können kein Objekt animieren, das die Ausgabe einer anderen Animation ist. Wenn Sie z. b. eine <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> zum Animieren der <xref:System.Windows.Shapes.Shape.Fill%2A> eines <xref:System.Windows.Shapes.Rectangle> von einem <xref:System.Windows.Media.RadialGradientBrush> zu einem <xref:System.Windows.Media.SolidColorBrush>verwenden, können Sie keine Eigenschaften des <xref:System.Windows.Media.RadialGradientBrush> oder <xref:System.Windows.Media.SolidColorBrush>animieren.  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>Das Ändern des Werts einer Eigenschaft ist nach dem Animieren nicht möglich  
 Möglicherweise kommt es vor, dass Sie den Wert einer einmal animierten Eigenschaft, auch nachdem die Animation beendet wurde, nicht verändern können. Das liegt daran, dass, obwohl die Animation beendet wurde, immer noch der Basiswert der Eigenschaft überschrieben wird. Um zu verhindern, dass die Animation den aktuellen Wert der Eigenschaft überschreibt, entfernen Sie Sie, oder versehen Sie Sie mit einem <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Weitere Informationen und ein Beispiel finden Sie unter [Festlegen einer Eigenschaft nach dem Animieren mit einem Storyboard](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="changing-a-timeline-has-no-effect"></a>Das Ändern einer Zeitachse hat keine Auswirkung  
 Obwohl die meisten <xref:System.Windows.Media.Animation.Timeline> Eigenschaften animabel sind und Daten gebunden werden können, hat das Ändern der Eigenschaftswerte einer aktiven <xref:System.Windows.Media.Animation.Timeline> anscheinend keine Auswirkung. Dies liegt daran, dass beim Beginn einer <xref:System.Windows.Media.Animation.Timeline> das Zeit Steuerungssystem eine Kopie der <xref:System.Windows.Media.Animation.Timeline> erstellt und zum Erstellen eines <xref:System.Windows.Media.Animation.Clock> Objekts verwendet. Eine Änderung des Original hat keine Auswirkung auf die Kopie des Systems.  
  
 Damit eine <xref:System.Windows.Media.Animation.Timeline> Änderungen widerspiegelt, muss die Uhr erneut generiert und verwendet werden, um die zuvor erstellte Uhr zu ersetzen. Uhren werden nicht automatisch neu generiert. Im Folgenden werden verschiedene Methoden beschrieben, wie Änderungen der Zeitachse übernommen werden können:  
  
- Wenn die Zeitachse zu einem <xref:System.Windows.Media.Animation.Storyboard>gehört oder zu einem gehört, können Sie die Änderungen wiedergeben, indem Sie das Storyboard mithilfe einer <xref:System.Windows.Media.Animation.BeginStoryboard> oder der <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode erneut anwenden. Dies hat den Nebeneffekt, dass auch die Animation neu gestartet wird. Im Code können Sie die <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>-Methode verwenden, um das Storyboard zurück zur vorherigen Position zu verschieben.  
  
- Wenn Sie mithilfe der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>-Methode eine Animation direkt auf eine Eigenschaft angewendet haben, müssen Sie die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>-Methode erneut aufzurufen und die Animation, die geändert wurde, übergeben.  
  
- Wenn Sie direkt auf der Uhrebene arbeiten, erstellen Sie einen neuen Satz von Uhren, und verwenden sie diese, um den zuvor generierten Satz von Uhren zu ersetzen.  
  
 Weitere Informationen zu Zeitachsen und Uhren finden Sie unter Übersicht über das [Animations-und Zeit Steuerungssystem](animation-and-timing-system-overview.md).  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>FillBehavior.Stop funktioniert nicht wie erwartet  
 Es gibt Zeiten, in denen die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>-Eigenschaft auf festgelegt wird, <xref:System.Windows.Media.Animation.FillBehavior.Stop> anscheinend keine Auswirkung hat, z. b., wenn eine Animation an eine andere "wird, da Sie über die <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> Einstellung <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>verfügt.  
  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Canvas>, eine <xref:System.Windows.Shapes.Rectangle> und eine <xref:System.Windows.Media.TranslateTransform>. Der <xref:System.Windows.Media.TranslateTransform> wird animiert, um die <xref:System.Windows.Shapes.Rectangle> um die <xref:System.Windows.Controls.Canvas>zu verschieben.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 In den Beispielen in diesem Abschnitt werden die vorangehenden Objekte verwendet, um verschiedene Fälle zu veranschaulichen, in denen sich die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>-Eigenschaft nicht wie erwartet verhält.  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>FillBehavior="Stop" und HandoffBehavior mit mehreren Animationen  
 Manchmal scheint es so, als ob eine Animation die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>-Eigenschaft ignoriert, wenn Sie durch eine zweite Animation ersetzt wird. Im folgenden Beispiel werden zwei <xref:System.Windows.Media.Animation.Storyboard> Objekte erstellt und verwendet, um denselben <xref:System.Windows.Media.TranslateTransform> zu animieren, wie im vorherigen Beispiel gezeigt.  
  
 Der erste <xref:System.Windows.Media.Animation.Storyboard>, `B1`, animiert die <xref:System.Windows.Media.TranslateTransform.X%2A>-Eigenschaft des <xref:System.Windows.Media.TranslateTransform> von 0 bis 350, wodurch das Rechteck 350 Pixel nach rechts verschoben wird. Wenn die Animation das Ende ihrer Dauer erreicht und die Wiedergabe beendet wird, wird die <xref:System.Windows.Media.TranslateTransform.X%2A>-Eigenschaft auf den ursprünglichen Wert 0 (null) zurückgesetzt. Das Rechteck wird daraufhin 350 Pixel nach rechts bewegt, und springt dann zurück an seine ursprüngliche Position.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 Der zweite <xref:System.Windows.Media.Animation.Storyboard>, `B2`, animiert auch die <xref:System.Windows.Media.TranslateTransform.X%2A>-Eigenschaft desselben <xref:System.Windows.Media.TranslateTransform>. Da nur die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-Eigenschaft der Animation in diesem <xref:System.Windows.Media.Animation.Storyboard> festgelegt wird, verwendet die Animation den aktuellen Wert der Eigenschaft, die Sie animiert, als Startwert.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 Wenn Sie auf die zweite Schaltfläche klicken, während die erste <xref:System.Windows.Media.Animation.Storyboard> abgespielt wird, können Sie das folgende Verhalten erwarten:  
  
1. Das erste Storyboard wird beendet und sendet das Rechteck zurück an seine ursprüngliche Position, da die Animation über eine <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.Stop>verfügt.  
  
2. Das zweite Storyboard wird wirksam und animiert von der aktuellen Position, 0, auf 500.  
  
 **Dies geschieht jedoch nicht.** Stattdessen springt das Rechteck nicht zurück; es verschiebt sich weiter nach rechts. Der Grund ist die zweite Animation, welche den aktuellen Wert der ersten Animation als ihren Startwert verwendet und von diesem Wert auf 500 animiert. Wenn die zweite Animation den ersten ersetzt, da die <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace><xref:System.Windows.Media.Animation.HandoffBehavior> verwendet wird, spielt der <xref:System.Windows.Media.Animation.FillBehavior> der ersten Animation keine Rolle.  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior und das abgeschlossene Ereignis  
 In den folgenden Beispielen wird ein anderes Szenario veranschaulicht, in dem die <xref:System.Windows.Media.Animation.FillBehavior.Stop><xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> anscheinend keine Auswirkung haben. Auch in diesem Beispiel wird ein Storyboard verwendet, um die <xref:System.Windows.Media.TranslateTransform.X%2A>-Eigenschaft des <xref:System.Windows.Media.TranslateTransform> zwischen 0 und 350 zu animieren. Diesmal wird das Beispiel jedoch für das <xref:System.Windows.Media.Animation.Timeline.Completed>-Ereignis registriert.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 Der <xref:System.Windows.Media.Animation.Timeline.Completed>-Ereignishandler startet einen weiteren <xref:System.Windows.Media.Animation.Storyboard>, der die gleiche Eigenschaft von seinem aktuellen Wert auf 500 animiert.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 Im folgenden finden Sie das Markup, das die zweite <xref:System.Windows.Media.Animation.Storyboard> als Ressource definiert.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 Wenn Sie die <xref:System.Windows.Media.Animation.Storyboard>ausführen, erwarten Sie möglicherweise, dass die <xref:System.Windows.Media.TranslateTransform.X%2A>-Eigenschaft des <xref:System.Windows.Media.TranslateTransform> zwischen 0 und 350 animiert und dann nach Abschluss des Vorgangs auf 0 zurückgesetzt wird (da Sie über die <xref:System.Windows.Media.Animation.FillBehavior> Einstellung <xref:System.Windows.Media.Animation.FillBehavior.Stop>verfügt) und dann zwischen 0 und 500 animieren. Stattdessen wird der <xref:System.Windows.Media.TranslateTransform> von 0 bis 350 und dann bis 500 animiert.  
  
 Dies liegt an der Reihenfolge, in der WPF Ereignisse auslöst, und weil Eigenschaftswerte zwischengespeichert werden und nicht neu berechnet werden, es sei denn, die Eigenschaft ist ungültig. Das <xref:System.Windows.Media.Animation.Timeline.Completed> Ereignis wird zuerst verarbeitet, da es durch die Stamm Zeitachse ausgelöst wurde (die erste <xref:System.Windows.Media.Animation.Storyboard>). Die <xref:System.Windows.Media.TranslateTransform.X%2A>-Eigenschaft gibt zu diesem Zeitpunkt weiterhin den animierten Wert zurück, da Sie noch nicht ungültig gemacht wurde. Der zweite <xref:System.Windows.Media.Animation.Storyboard> verwendet den zwischengespeicherten Wert als Startwert und beginnt mit der Animation.  
  
<a name="performancesection"></a>   
## <a name="performance"></a>Leistung  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>Animationen werden, auch nach Verlassen einer Seite fortgesetzt  
 Wenn Sie von einer <xref:System.Windows.Controls.Page> navigieren, die laufende Animationen enthält, werden diese Animationen so lange wiedergegeben, bis die <xref:System.Windows.Controls.Page> in die Garbage Collection aufgenommen werden. Abhängig vom Navigationssystem, das Sie verwenden, bleibt eine Seite, die Sie Verlassen möglicherweise für einen unbestimmten Zeitraum im Speicher , und es werden aufgrund von Animationen Ressourcen belegt. Dies ist am deutlichsten sichtbar, wenn eine Seite ständig ausgeführte(„Umgebungs“-) Animationen enthält.  
  
 Aus diesem Grund empfiehlt es sich, das <xref:System.Windows.FrameworkElement.Unloaded>-Ereignis zum Entfernen von Animationen zu verwenden, wenn Sie von einer Seite weg navigieren.  
  
 Es gibt verschiedene Möglichkeiten, eine Animation zu entfernen. Die folgenden Verfahren können zum Entfernen von Animationen verwendet werden, die zu einem <xref:System.Windows.Media.Animation.Storyboard>gehören.  
  
- Informationen zum Entfernen einer <xref:System.Windows.Media.Animation.Storyboard>, die Sie mit einem Ereignis Auslösung gestartet haben, finden Sie unter Gewusst [wie: Entfernen eines Storyboards](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749412(v=vs.90)).  
  
- Informationen zum Verwenden von Code zum Entfernen eines <xref:System.Windows.Media.Animation.Storyboard>finden Sie unter der <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>-Methode.  
  
 Die nächste Technik kann verwendet werden, unabhängig davon, wie die Animation gestartet wurde.  
  
- Um Animationen aus einer bestimmten Eigenschaft zu entfernen, verwenden Sie die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>-Methode. Geben Sie die zu animierende Eigenschaft als ersten Parameter an, und `null` als Sekunde. Dies entfernt alle Animationsuhren aus der Eigenschaft.  
  
 Weitere Informationen zu den verschiedenen Möglichkeiten zum Animieren von Eigenschaften finden Sie unter [Übersicht über die Animation](property-animation-techniques-overview.md)von Eigenschaften.  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>Das Verwenden von Compose HandoffBehavior belegt Systemressourcen  
 Wenn Sie mithilfe der <xref:System.Windows.Media.Animation.HandoffBehavior.Compose><xref:System.Windows.Media.Animation.HandoffBehavior>eine <xref:System.Windows.Media.Animation.Storyboard>, <xref:System.Windows.Media.Animation.AnimationTimeline>oder <xref:System.Windows.Media.Animation.AnimationClock> auf eine Eigenschaft anwenden, verbrauchen alle <xref:System.Windows.Media.Animation.Clock> Objekte, die dieser Eigenschaft zugeordnet sind, weiterhin Systemressourcen. Diese Uhren werden vom Zeit Steuerungssystem nicht automatisch entfernt.  
  
 Um Leistungsprobleme zu vermeiden, wenn Sie eine große Anzahl von Uhren mithilfe von <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>anwenden, sollten Sie das Verfassen von Uhren aus der animierten Eigenschaft entfernen, nachdem Sie fertiggestellt wurden. Es gibt mehrere Möglichkeiten, eine Uhr zu entfernen.  
  
- Um alle Uhren aus einer Eigenschaft zu entfernen, verwenden Sie die <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29>-oder <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>-Methode des animierten Objekts. Geben Sie die zu animierende Eigenschaft als ersten Parameter an, und `null` als Sekunde. Dies entfernt alle Animationsuhren aus der Eigenschaft.  
  
- Um eine bestimmte <xref:System.Windows.Media.Animation.AnimationClock> aus einer Liste von Uhren zu entfernen, verwenden Sie die <xref:System.Windows.Media.Animation.Clock.Controller%2A>-Eigenschaft des <xref:System.Windows.Media.Animation.AnimationClock>, um eine <xref:System.Windows.Media.Animation.ClockController>abzurufen, und rufen Sie dann die <xref:System.Windows.Media.Animation.ClockController.Remove%2A>-Methode des <xref:System.Windows.Media.Animation.ClockController>auf. Dies erfolgt in der Regel im <xref:System.Windows.Media.Animation.Clock.Completed> Ereignishandler für eine Uhr. Beachten Sie, dass nur Stamm Uhren von einem <xref:System.Windows.Media.Animation.ClockController>gesteuert werden können. die <xref:System.Windows.Media.Animation.Clock.Controller%2A>-Eigenschaft einer untergeordneten Uhr gibt `null`zurück. Beachten Sie auch, dass das <xref:System.Windows.Media.Animation.Clock.Completed>-Ereignis nicht aufgerufen wird, wenn die effektive Dauer der Uhr ewig ist.  In diesem Fall muss der Benutzer bestimmen, wann <xref:System.Windows.Media.Animation.ClockController.Remove%2A>aufgerufen werden soll.  
  
 Dies betrifft hauptsächlich Animationen für Objekte, die eine lange Lebensdauer haben.  Wenn ein Objekt an den Garbage Collector übergeben wird, werden auch die Uhren getrennt und an den Garbage Collector übergeben.  
  
 Weitere Informationen zu Clock-Objekten finden Sie unter Übersicht über das [Animations-und Zeit Steuerungssystem](animation-and-timing-system-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](animation-overview.md)
