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
ms.openlocfilehash: df4aa7f3bf046ec871333f665ab77fa460c4095c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43802267"
---
# <a name="animation-tips-and-tricks"></a>Tipps und Tricks zu Animationen
Bei der Arbeit mit Animationen in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], gibt es eine Reihe von Tipps und Tricks, die die Animationen vornehmen können, bieten eine bessere Leistung, und speichern Sie die Frustration.  
  
<a name="generalissuessection"></a>   
## <a name="general-issues"></a>Allgemeine Probleme  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>Durch Animieren der Position einer Bildlaufleiste oder eines Schiebereglers wird das Element gesperrt  
 Wenn Sie animieren die Position einer Bildlaufleiste oder eines Schiebereglers mithilfe einer Animation, die eine <xref:System.Windows.Media.Animation.FillBehavior> von <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> (der Standardwert), der Benutzer werden nicht mehr die Bildlaufleiste oder den Schieberegler verschieben können. Das liegt daran, dass, obwohl die Animation beendet wurde, nach wie vor der Basiswert der Zieleigenschaft überschrieben wird. Um die Animation vom aktuellen Wert der Eigenschaft überschreiben zu beenden, entfernen, oder geben Sie ihm eine <xref:System.Windows.Media.Animation.FillBehavior> von <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Weitere Informationen und ein Beispiel finden Sie unter [Festlegen einer Eigenschaft nach Animation mit einem Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>Das Animieren der Ausgabe einer Animation hat keine Auswirkungen  
 Sie können kein Objekt animieren, das die Ausgabe einer anderen Animation ist. Angenommen, Sie verwenden eine <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> zum Animieren der <xref:System.Windows.Shapes.Shape.Fill%2A> von eine <xref:System.Windows.Shapes.Rectangle> aus eine <xref:System.Windows.Media.RadialGradientBrush> auf eine <xref:System.Windows.Media.SolidColorBrush>, Sie keine Eigenschaften animieren der <xref:System.Windows.Media.RadialGradientBrush> oder <xref:System.Windows.Media.SolidColorBrush>.  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>Das Ändern des Werts einer Eigenschaft ist nach dem Animieren nicht möglich  
 Möglicherweise kommt es vor, dass Sie den Wert einer einmal animierten Eigenschaft, auch nachdem die Animation beendet wurde, nicht verändern können. Das liegt daran, dass, obwohl die Animation beendet wurde, immer noch der Basiswert der Eigenschaft überschrieben wird. Um die Animation vom aktuellen Wert der Eigenschaft überschreiben zu beenden, entfernen, oder geben Sie ihm eine <xref:System.Windows.Media.Animation.FillBehavior> von <xref:System.Windows.Media.Animation.FillBehavior.Stop>. Weitere Informationen und ein Beispiel finden Sie unter [Festlegen einer Eigenschaft nach Animation mit einem Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### <a name="changing-a-timeline-has-no-effect"></a>Das Ändern einer Zeitachse hat keine Auswirkung  
 Obwohl die meisten <xref:System.Windows.Media.Animation.Timeline> -Eigenschaften animierbar sind und die Daten gebunden werden, ändern die Eigenschaftswerte einer aktiven <xref:System.Windows.Media.Animation.Timeline> scheint keine Auswirkung haben. Der Grund dafür ist, wenn eine <xref:System.Windows.Media.Animation.Timeline> ist begonnen, erstellt das Zeitsteuerungssystem eine Kopie der <xref:System.Windows.Media.Animation.Timeline> und verwendet sie zum Erstellen einer <xref:System.Windows.Media.Animation.Clock> Objekt. Eine Änderung des Original hat keine Auswirkung auf die Kopie des Systems.  
  
 Für eine <xref:System.Windows.Media.Animation.Timeline> um Änderungen widerzuspiegeln, seine Uhr muss erneut generiert und verwendet werden, die zuvor erstellte Uhr zu ersetzen. Uhren werden nicht automatisch neu generiert. Im Folgenden werden verschiedene Methoden beschrieben, wie Änderungen der Zeitachse übernommen werden können:  
  
-   Wenn die Zeitachse oder gehört zu einer <xref:System.Windows.Media.Animation.Storyboard>, haben, damit es die Änderungen durch das erneute Anwenden der Storyboards mithilfe einer <xref:System.Windows.Media.Animation.BeginStoryboard> oder <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode. Dies hat den Nebeneffekt, dass auch die Animation neu gestartet wird. Im Code können Sie die <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> Methode, um das Storyboard fahren fort, um zur vorherigen Position zurück.  
  
-   Wenn Sie eine Animation direkt an eine Eigenschaft mit dem <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> -Methode, rufen die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> -Methode erneut auf und übergeben sie die Animation, die geändert wurde.  
  
-   Wenn Sie direkt auf der Uhrebene arbeiten, erstellen Sie einen neuen Satz von Uhren, und verwenden sie diese, um den zuvor generierten Satz von Uhren zu ersetzen.  
  
 Weitere Informationen zu Zeitachsen und Uhren finden Sie unter [Animation und zeitliche Steuerung Systemübersicht](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>FillBehavior.Stop funktioniert nicht wie erwartet  
 Manchmal beim Festlegen der <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft <xref:System.Windows.Media.Animation.FillBehavior.Stop> scheint keine Auswirkung, z. B. wenn eine Animation "übergibt" in eine andere, da sie verfügt über eine <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> Festlegen der <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.  
  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Shapes.Rectangle> und <xref:System.Windows.Media.TranslateTransform>. Die <xref:System.Windows.Media.TranslateTransform> animiert wird zum Verschieben der <xref:System.Windows.Shapes.Rectangle> rund um die <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 In die Beispielen in diesem Abschnitt verwenden Sie die vorhergehenden Objekte, die um mehrere Fälle zu veranschaulichen, in denen die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft verhält sich nicht, wie Sie es erwarten.  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>FillBehavior="Stop" und HandoffBehavior mit mehreren Animationen  
 Manchmal es scheint, als ob eine Animation ignoriert die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft, wenn sie durch eine zweite Animation ersetzt wird. Im folgenden Beispiel, das zwei erstellt <xref:System.Windows.Media.Animation.Storyboard> -Objekte und verwendet diese zum Animieren derselben <xref:System.Windows.Media.TranslateTransform> im vorherigen Beispiel gezeigt.  
  
 Die erste <xref:System.Windows.Media.Animation.Storyboard>, `B1`, animiert die <xref:System.Windows.Media.TranslateTransform.X%2A> Eigenschaft der <xref:System.Windows.Media.TranslateTransform> von 0 auf 350, die das Rechteck um 350 Pixel nach rechts verschoben. Wenn die Animation das Ende ihrer Dauer erreicht und Wiedergabe beendet ist, die <xref:System.Windows.Media.TranslateTransform.X%2A> Eigenschaft wird auf den ursprünglichen Wert, der 0 zurückgesetzt. Das Rechteck wird daraufhin 350 Pixel nach rechts bewegt, und springt dann zurück an seine ursprüngliche Position.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 Die zweite <xref:System.Windows.Media.Animation.Storyboard>, `B2`, animiert ebenfalls die <xref:System.Windows.Media.TranslateTransform.X%2A> Eigenschaft desselben <xref:System.Windows.Media.TranslateTransform>. Da nur die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> -Eigenschaft der Animation in diesem <xref:System.Windows.Media.Animation.Storyboard> festgelegt ist, wird die Animation verwendet den aktuellen Wert der Eigenschaft, die sie animiert, als Startwert.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 Wenn Sie die zweite Schaltfläche, während das erste auf <xref:System.Windows.Media.Animation.Storyboard> ist wiedergeben, können Sie Folgendes erwarten:  
  
1.  Das erste Storyboard wird beendet und sendet Sie das Rechteck zurück an seine ursprüngliche Position, da die Animation hat eine <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> von <xref:System.Windows.Media.Animation.FillBehavior.Stop>.  
  
2.  Das zweite Storyboard wird wirksam und animiert von der aktuellen Position, 0, auf 500.  
  
 **Dies geschieht jedoch nicht.** Stattdessen springt das Rechteck nicht zurück; es verschiebt sich weiter nach rechts. Der Grund ist die zweite Animation, welche den aktuellen Wert der ersten Animation als ihren Startwert verwendet und von diesem Wert auf 500 animiert. Wenn die zweite Animation die erste ersetzt, weil die <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> <xref:System.Windows.Media.Animation.HandoffBehavior> verwendet wird, die <xref:System.Windows.Media.Animation.FillBehavior> der ersten Animation keine Rolle.  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior und das abgeschlossene Ereignis  
 Die nächsten Beispiele zeigen ein anderes Szenario, in dem die <xref:System.Windows.Media.Animation.FillBehavior.Stop> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> scheint keine Auswirkung haben. In diesem Fall im Beispiel wird mit einem Storyboard Animieren der <xref:System.Windows.Media.TranslateTransform.X%2A> Eigenschaft der <xref:System.Windows.Media.TranslateTransform> von 0 auf 350. Jedoch dieses Mal für das Beispiel registriert die <xref:System.Windows.Media.Animation.Timeline.Completed> Ereignis.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 Die <xref:System.Windows.Media.Animation.Timeline.Completed> Ereignishandler startet ein weiteres <xref:System.Windows.Media.Animation.Storyboard> , die die gleiche Eigenschaft vom aktuellen Wert auf 500 animiert.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 Im folgenden finden Sie das Markup, das zweite definiert <xref:System.Windows.Media.Animation.Storyboard> als Ressource.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 Beim Ausführen der <xref:System.Windows.Media.Animation.Storyboard>, Sie erwarten wahrscheinlich die <xref:System.Windows.Media.TranslateTransform.X%2A> Eigenschaft der <xref:System.Windows.Media.TranslateTransform> um von 0 auf 350 zu animieren, klicken Sie dann auf 0 zurückgesetzt, nachdem es abgeschlossen ist (da er besitzt eine <xref:System.Windows.Media.Animation.FillBehavior> Festlegen von <xref:System.Windows.Media.Animation.FillBehavior.Stop>), und dann von 0 auf 500 animiert. Stattdessen die <xref:System.Windows.Media.TranslateTransform> erstellt eine Animation von 0 auf 350 und dann auf 500.  
  
 Das liegt an der Reihenfolge, in der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] löst Ereignisse aus, und daran, dass Eigenschaftswerte zwischengespeichert werden und sind nicht neu berechnet, wenn die Eigenschaft ungültig ist. Die <xref:System.Windows.Media.Animation.Timeline.Completed> -Ereignis wird zuerst verarbeitet, da es durch die Zeitachse ausgelöst wurde (die erste <xref:System.Windows.Media.Animation.Storyboard>). Zu diesem Zeitpunkt die <xref:System.Windows.Media.TranslateTransform.X%2A> Eigenschaft gibt immer noch den animierten Wert zurück, da er noch nicht ungültig gemacht wurde. Die zweite <xref:System.Windows.Media.Animation.Storyboard> verwendet den zwischengespeicherten Wert als Startwert und beginnt mit der Animation.  
  
<a name="performancesection"></a>   
## <a name="performance"></a>Leistung  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>Animationen werden, auch nach Verlassen einer Seite fortgesetzt  
 Beim Navigieren aus einer <xref:System.Windows.Controls.Page> , die ausgeführte Animationen enthält, weiterhin diese Animationen bis zum Wiedergeben der <xref:System.Windows.Controls.Page> Garbage Collection durchgeführt wird. Abhängig vom Navigationssystem, das Sie verwenden, bleibt eine Seite, die Sie Verlassen möglicherweise für einen unbestimmten Zeitraum im Speicher , und es werden aufgrund von Animationen Ressourcen belegt. Dies ist am deutlichsten sichtbar, wenn eine Seite ständig ausgeführte(„Umgebungs“-) Animationen enthält.  
  
 Aus diesem Grund ist es eine gute Idee, verwenden Sie die <xref:System.Windows.FrameworkElement.Unloaded> Ereignis, um Animationen zu entfernen, wenn Sie von einer Seite Weg navigieren.  
  
 Es gibt verschiedene Möglichkeiten, eine Animation zu entfernen. Die folgenden Verfahren können verwendet werden, um Animationen zu entfernen, die zu gehören eine <xref:System.Windows.Media.Animation.Storyboard>.  
  
-   So entfernen Sie eine <xref:System.Windows.Media.Animation.Storyboard> Sie mit einem Ereignistrigger gestartet haben, finden Sie unter [Vorgehensweise: Entfernen eines Storyboards](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749412(v=vs.90)).  
  
-   Zum Verwenden von Code zum Entfernen einer <xref:System.Windows.Media.Animation.Storyboard>, finden Sie unter den <xref:System.Windows.Media.Animation.Storyboard.Remove%2A> Methode.  
  
 Die nächste Technik kann verwendet werden, unabhängig davon, wie die Animation gestartet wurde.  
  
-   Um Animationen aus einer bestimmten Eigenschaft zu entfernen, verwenden die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> Methode. Geben Sie die zu animierende Eigenschaft als ersten Parameter und `null` als das zweite. Dies entfernt alle Animationsuhren aus der Eigenschaft.  
  
 Weitere Informationen zu den verschiedenen Methoden zum Animieren von Eigenschaften finden Sie unter [Eigenschaft Techniken-Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>Das Verwenden von Compose HandoffBehavior belegt Systemressourcen  
 Beim Anwenden einer <xref:System.Windows.Media.Animation.Storyboard>, <xref:System.Windows.Media.Animation.AnimationTimeline>, oder <xref:System.Windows.Media.Animation.AnimationClock> auf eine Eigenschaft mit der <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior>, <xref:System.Windows.Media.Animation.Clock> Objekte, die diese Eigenschaft zuvor zugeordnet waren weiterhin Systemressourcen beanspruchen, nicht der Fall ist des Zeitsteuerungssystems Diese Uhren automatisch entfernt.  
  
 Um Leistungsprobleme zu vermeiden, wenn Sie eine große Anzahl von Uhren mithilfe anwenden <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>, sollten Sie zusammengesetzte Uhren aus der animierten Eigenschaft entfernen, nachdem sie ausgeführt. Es gibt mehrere Möglichkeiten, eine Uhr zu entfernen.  
  
-   Um alle Uhren aus einer Eigenschaft zu entfernen, verwenden die <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> oder <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> -Methode des animierten Objekts. Geben Sie die zu animierende Eigenschaft als ersten Parameter und `null` als das zweite. Dies entfernt alle Animationsuhren aus der Eigenschaft.  
  
-   Zum Entfernen einer bestimmten <xref:System.Windows.Media.Animation.AnimationClock> aus einer Liste von Uhren, mithilfe der <xref:System.Windows.Media.Animation.Clock.Controller%2A> Eigenschaft der <xref:System.Windows.Media.Animation.AnimationClock> zum Abrufen einer <xref:System.Windows.Media.Animation.ClockController>, rufen Sie dann die <xref:System.Windows.Media.Animation.ClockController.Remove%2A> -Methode der der <xref:System.Windows.Media.Animation.ClockController>. Dies erfolgt in der Regel in der <xref:System.Windows.Media.Animation.Clock.Completed> -Ereignishandler für eine Uhr. Beachten Sie, dass nur Stammuhren von gesteuert werden, können ein <xref:System.Windows.Media.Animation.ClockController>; die <xref:System.Windows.Media.Animation.Clock.Controller%2A> Eigenschaft einer untergeordneten Uhr gibt zurück, `null`. Beachten Sie auch, dass die <xref:System.Windows.Media.Animation.Clock.Completed> Ereignis wird nicht aufgerufen werden, wenn die effektive Dauer der Uhr endlos ist.  In diesem Fall müssen die Benutzer zum Ermitteln des Zeitpunkts aufrufen, <xref:System.Windows.Media.Animation.ClockController.Remove%2A>.  
  
 Dies betrifft hauptsächlich Animationen für Objekte, die eine lange Lebensdauer haben.  Wenn ein Objekt an den Garbage Collector übergeben wird, werden auch die Uhren getrennt und an den Garbage Collector übergeben.  
  
 Weitere Informationen zu uhrobjekten finden Sie unter [Animation und zeitliche Steuerung Systemübersicht](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
