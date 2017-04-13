---
title: "Tipps und Tricks zu Animationen | Microsoft Docs"
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
  - "Animieren von Objekten [WPF], Problembehandlung"
  - "Tipps und Tricks zu Animationen [WPF]"
  - "Animationen [WPF], FillBehavior-Eigenschaft"
  - "Animationen [WPF], Verwendung von Systemressourcen"
  - "Problembehandlung bei der Leistung [WPF], Animation"
  - "Tipps und Tricks [WPF], Animation"
  - "Problembehandlung [WPF], Animation"
  - "Problembehandlung bei der Animation [WPF]"
ms.assetid: e467796b-d5d4-45a6-a108-8c5d7ff69a0f
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Tipps und Tricks zu Animationen
Wenn Sie in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] mit Animationen arbeiten, stehen Ihnen eine Reihe von Tipps und Tricks zur Verfügung, mit denen Sie die Leistung Ihrer Animationen verbessern und Probleme vermeiden können.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="generalissuessection"></a>   
## Allgemeine Probleme  
  
### Durch Animieren der Position einer Schiebeleiste oder eines Schiebereglers wird das betroffene Element gesperrt  
 Wenn Sie die Position einer Schiebeleiste oder eines Schiebereglers animieren, bei der bzw. dem <xref:System.Windows.Media.Animation.FillBehavior> auf <xref:System.Windows.Media.Animation.FillBehavior> festgelegt ist \(Standardwert\), kann der Benutzer die Schiebeleiste oder den Schieberegler nicht mehr bewegen.  Das liegt daran, dass die Animation immer noch den Basiswert der Zieleigenschaft überschreibt, obwohl sie bereits beendet ist.  Um zu verhindern, dass die Animation den aktuellen Wert der Eigenschaft weiterhin überschreibt, entfernen Sie die Animation, oder Sie legen das <xref:System.Windows.Media.Animation.FillBehavior> auf <xref:System.Windows.Media.Animation.FillBehavior> fest.  Weitere Informationen und ein Beispiel finden Sie unter [Festlegen einer Eigenschaft nach einer Storyboard\-Animation](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### Das Animieren der Ausgabe einer Animation hat keine Auswirkungen  
 Sie können kein Objekt animieren, das die Ausgabe einer anderen Animation ist.  Wenn Sie beispielsweise mithilfe von <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> die <xref:System.Windows.Shapes.Shape.Fill%2A> für ein <xref:System.Windows.Shapes.Rectangle> von einem <xref:System.Windows.Media.RadialGradientBrush> bis zu einem <xref:System.Windows.Media.SolidColorBrush> animieren, können Sie keine Eigenschaften für den <xref:System.Windows.Media.RadialGradientBrush> oder den <xref:System.Windows.Media.SolidColorBrush> animieren.  
  
### Ändern des Werts einer Eigenschaft nach dem Animieren nicht möglich  
 Manchmal können Sie den Wert einer Eigenschaft nach dem Animieren nicht ändern, obwohl die Animation beendet ist.  Das liegt daran, dass die Animation immer noch den Basiswert der Eigenschaft überschreibt, obwohl sie bereits beendet ist.  Um zu verhindern, dass die Animation den aktuellen Wert der Eigenschaft weiterhin überschreibt, entfernen Sie die Animation, oder Sie legen das <xref:System.Windows.Media.Animation.FillBehavior> auf <xref:System.Windows.Media.Animation.FillBehavior> fest.  Weitere Informationen und ein Beispiel finden Sie unter [Festlegen einer Eigenschaft nach einer Storyboard\-Animation](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
### Das Ändern einer Zeitachse hat keine Auswirkungen  
 Obwohl die meisten <xref:System.Windows.Media.Animation.Timeline>\-Eigenschaften sich animieren und an Daten binden lassen, hat das Ändern der Eigenschaftswerte einer aktiven <xref:System.Windows.Media.Animation.Timeline> scheinbar keine Auswirkungen.  Das liegt daran, dass das Zeitsteuerungssystem nach Beginn der <xref:System.Windows.Media.Animation.Timeline> eine Kopie der <xref:System.Windows.Media.Animation.Timeline> erstellt und zum Erstellen eines <xref:System.Windows.Media.Animation.Clock>\-Objekts verwendet.  Eine Änderung des Originals hat keine Auswirkungen auf die Kopie des Systems.  
  
 Damit eine <xref:System.Windows.Media.Animation.Timeline> Änderungen widerspiegelt, muss ihr Uhrobjekt neu generiert und zum Ersetzen der zuvor erstellten Uhr verwendet werden.  Uhrobjekte werden nicht automatisch neu generiert.  Änderungen der Zeitachse können mit mehreren Verfahren übernommen werden:  
  
-   Wenn es sich bei der Zeitachse um ein <xref:System.Windows.Media.Animation.Storyboard> handelt oder wenn sie zu einem Storyboard gehört, kann sie Änderungen widerspiegeln, indem Sie das zugehörige Storyboard mithilfe von <xref:System.Windows.Media.Animation.BeginStoryboard> oder der <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>\-Methode erneut anwenden.  Als Nebeneffekt wird die Animation neu gestartet.  In Code können Sie die <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>\-Methode verwenden, um das Storyboard auf die vorherige Position zurückzusetzen.  
  
-   Wenn Sie eine Animation mithilfe der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>\-Methode direkt auf eine Eigenschaft angewendet haben, rufen Sie die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>\-Methode erneut auf, und übergeben Sie die geänderte Animation an die Methode.  
  
-   Wenn Sie direkt auf der Uhrebene arbeiten, erstellen Sie einen neuen Satz von Uhren, wenden Sie diesen an, und ersetzen Sie den zuvor generierten Satz von Uhren durch diesen Satz von Uhren.  
  
 Weitere Informationen zu Zeitachsen und Uhren finden Sie unter [Übersicht über das Animations\- und Zeitsteuerungssystem](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
### FillBehavior.Stop funktioniert nicht wie erwartet  
 Manchmal hat das Festlegen der <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>\-Eigenschaft auf <xref:System.Windows.Media.Animation.FillBehavior> scheinbar keine Auswirkungen, beispielsweise wenn eine Animation an eine andere "übergibt", weil das <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> auf <xref:System.Windows.Media.Animation.HandoffBehavior> festgelegt ist.  
  
 Im folgenden Beispiel werden ein <xref:System.Windows.Controls.Canvas>, ein <xref:System.Windows.Shapes.Rectangle> und eine <xref:System.Windows.Media.TranslateTransform> erstellt.  Die <xref:System.Windows.Media.TranslateTransform> wird animiert, um das <xref:System.Windows.Shapes.Rectangle> um den <xref:System.Windows.Controls.Canvas> zu verschieben.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 Die Beispiele in diesem Abschnitt verwenden die vorhergehenden Objekte, um mehrere Fälle zu veranschaulichen, in denen sich die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>\-Eigenschaft möglicherweise nicht wie erwartet verhält.  
  
#### FillBehavior\="Stop" und HandoffBehavior mit mehreren Animationen  
 Manchmal ignoriert eine Animation scheinbar ihre <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>\-Eigenschaft, wenn sie durch eine zweite Animation ersetzt wird.  Im folgenden Bespiel werden zwei <xref:System.Windows.Media.Animation.Storyboard>\-Objekte erstellt und zum Animieren derselben <xref:System.Windows.Media.TranslateTransform> verwendet, die im vorherigen Beispiel gezeigt wurde.  
  
 Das erste <xref:System.Windows.Media.Animation.Storyboard>, `B1`, animiert die <xref:System.Windows.Media.TranslateTransform.X%2A>\-Eigenschaft der <xref:System.Windows.Media.TranslateTransform> von 0 auf 350. Dadurch wird das Rechteck 350 Pixel nach rechts verschoben.  Wenn die Animation das Ende ihrer Dauer erreicht und die Wiedergabe beendet ist, wird die <xref:System.Windows.Media.TranslateTransform.X%2A>\-Eigenschaft auf den ursprünglichen Wert \(0\) zurückgesetzt.  Dementsprechend bewegt sich das Rechteck um 350 Pixel nach rechts und springt dann an seine ursprüngliche Position zurück.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 Das zweite <xref:System.Windows.Media.Animation.Storyboard>, `B2`, animiert ebenfalls die <xref:System.Windows.Media.TranslateTransform.X%2A>\-Eigenschaft derselben <xref:System.Windows.Media.TranslateTransform>.  Da nur die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>\-Eigenschaft der Animation in diesem <xref:System.Windows.Media.Animation.Storyboard> festgelegt ist, verwendet die Animation den aktuellen Wert der Eigenschaft, die sie animiert, als Startwert.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 Wenn Sie auf die zweite Schaltfläche klicken, während das erste <xref:System.Windows.Media.Animation.Storyboard> wiedergegeben wird, ist folgendes Verhalten möglich:  
  
1.  Das erste Storyboard wird beendet und sendet das Rechteck an seine ursprüngliche Position zurück, weil das <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> der Animation auf <xref:System.Windows.Media.Animation.FillBehavior> festgelegt ist.  
  
2.  Das zweite Storyboard wird aktiv und animiert von der aktuellen Position \(0\) auf 500.  
  
 **Das geschieht jedoch nicht.** Stattdessen springt das Rechteck nicht zurück. Es bewegt sich weiter nach rechts.  Das liegt daran, dass die zweite Animation den aktuellen Wert der ersten Animation als Startwert verwendet und von diesem Wert auf 500 animiert.  Wenn die zweite Animation die erste ersetzt, weil <xref:System.Windows.Media.Animation.HandoffBehavior> <xref:System.Windows.Media.Animation.HandoffBehavior> verwendet wird, spielt das <xref:System.Windows.Media.Animation.FillBehavior> der ersten Animation keine Rolle.  
  
#### FillBehavior und das abgeschlossene Ereignis  
 In den nächsten Beispielen wird ein anderes Szenario veranschaulicht, in dem <xref:System.Windows.Media.Animation.FillBehavior> als <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> keine Auswirkungen zu haben scheint.  Auch in diesem Beispiel wird ein Storyboard verwendet, um die <xref:System.Windows.Media.TranslateTransform.X%2A>\-Eigenschaft der <xref:System.Windows.Media.TranslateTransform> von 0 auf 350 zu animieren.  Das Beispiel wird jedoch für das <xref:System.Windows.Media.Animation.Timeline.Completed>\-Ereignis registriert.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 Der <xref:System.Windows.Media.Animation.Timeline.Completed>\-Ereignishandler startet ein weiteres <xref:System.Windows.Media.Animation.Storyboard>, das dieselbe Eigenschaft vom aktuellen Wert auf 500 animiert.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 Im Folgenden finden Sie das Markup, das das zweite <xref:System.Windows.Media.Animation.Storyboard> als Ressource definiert.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 Wenn Sie das <xref:System.Windows.Media.Animation.Storyboard> ausführen, wird erwartet, dass die <xref:System.Windows.Media.TranslateTransform.X%2A>\-Eigenschaft der <xref:System.Windows.Media.TranslateTransform> von 0 auf 350 animiert, nach Beendigung auf 0 zurückgesetzt wird \(weil das <xref:System.Windows.Media.Animation.FillBehavior> auf <xref:System.Windows.Media.Animation.FillBehavior> festgelegt ist\) und dann von 0 auf 500 animiert.  Stattdessen animiert die <xref:System.Windows.Media.TranslateTransform> von 0 auf 350 und dann auf 500.  
  
 Das liegt an der Reihenfolge, in der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Ereignisse auslöst, und daran, dass Eigenschaftswerte zwischengespeichert und nicht neu berechnet werden, sofern die Eigenschaft nicht ungültig gemacht wird.  Das <xref:System.Windows.Media.Animation.Timeline.Completed>\-Ereignis wird zuerst verarbeitet, da es von der Stammzeitachse \(vom ersten <xref:System.Windows.Media.Animation.Storyboard>\) ausgelöst wurde.  Zu diesem Zeitpunkt gibt die <xref:System.Windows.Media.TranslateTransform.X%2A>\-Eigenschaft immer noch den animierten Wert zurück, da er noch nicht ungültig gemacht wurde.  Das zweite <xref:System.Windows.Media.Animation.Storyboard> verwendet den zwischengespeicherten Wert als Startwert und beginnt mit der Animation.  
  
<a name="performancesection"></a>   
## Leistung  
  
### Animationen werden fortgesetzt, obwohl eine Seite verlassen wurde  
 Wenn Sie eine <xref:System.Windows.Controls.Page> verlassen, die ausgeführte Animationen enthält, werden diese Animationen wiedergegeben, bis die <xref:System.Windows.Controls.Page> an den Garbage Collector übergeben wird.  Je nach verwendetem Navigationssystem verbleibt eine Seite, die Sie verlassen, auf unbestimmte Zeit im Speicher und belegt wegen der Animationen Ressourcen.  Dies macht sich besonders bemerkbar, wenn eine Seite Animationen enthält, die ständig ausgeführt werden \("Ambient"\-Animationen\).  
  
 Deshalb empfiehlt es sich, Animationen mit dem <xref:System.Windows.FrameworkElement.Unloaded>\-Ereignis zu entfernen, wenn Sie eine Seite verlassen.  
  
 Animationen können auf unterschiedliche Weise entfernt werden.  Die folgenden Techniken können zum Entfernen von Animationen verwendet werden, die zu einem <xref:System.Windows.Media.Animation.Storyboard> gehören.  
  
-   Weitere Informationen zum Entfernen von einem <xref:System.Windows.Media.Animation.Storyboard>, das Sie mit einem Ereignistrigger gestartet haben, finden Sie unter [How to: Remove a Storyboard](http://msdn.microsoft.com/de-de/7fe39531-de2f-46a0-a69f-b783d04235ee).  
  
-   Weitere Informationen zum Entfernen von einem <xref:System.Windows.Media.Animation.Storyboard> mit Code finden Sie in der <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>\-Methode.  
  
 Die nächste Technik kann unabhängig davon verwendet werden, wie die Animation gestartet wurde.  
  
-   Um Animationen aus einer bestimmten Eigenschaft zu entfernen, verwenden Sie die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>\-Methode.  Geben Sie die zu animierende Eigenschaft als ersten Parameter und `null` als zweiten Parameter an.  Hierdurch werden alle Animationsuhren aus der Eigenschaft entfernt.  
  
 Weitere Informationen zu den verschiedenen Methoden zum Animieren von Eigenschaften finden Sie unter [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
### Das Verwenden von Compose HandoffBehavior belegt Systemressourcen  
 Wenn Sie ein <xref:System.Windows.Media.Animation.Storyboard>, eine <xref:System.Windows.Media.Animation.AnimationTimeline> oder eine <xref:System.Windows.Media.Animation.AnimationClock> mithilfe von <xref:System.Windows.Media.Animation.HandoffBehavior>\-<xref:System.Windows.Media.Animation.HandoffBehavior> auf eine Eigenschaft anwenden, beanspruchen <xref:System.Windows.Media.Animation.Clock>\-Objekte, die zuvor dieser Eigenschaft zugeordnet waren, weiterhin Systemressourcen. Diese Uhren werden nicht automatisch vom Zeitsteuerungssystem entfernt.  
  
 Um Leistungsprobleme zu vermeiden, wenn Sie mithilfe von <xref:System.Windows.Media.Animation.HandoffBehavior> eine große Anzahl von Uhren anwenden, sollten Sie zusammengesetzte Uhren aus der animierten Eigenschaft entfernen, nachdem sie ausgeführt wurden.  Es gibt mehrere Möglichkeiten, um eine Uhr zu entfernen.  
  
-   Um alle Uhren aus einer Eigenschaft zu entfernen, verwenden Sie die <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29>\-Methode oder die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>\-Methode des animierten Objekts.  Geben Sie die zu animierende Eigenschaft als ersten Parameter und `null` als zweiten Parameter an.  Hierdurch werden alle Animationsuhren aus der Eigenschaft entfernt.  
  
-   Zum Entfernen einer bestimmten <xref:System.Windows.Media.Animation.AnimationClock> aus einer Liste von Uhren verwenden Sie die <xref:System.Windows.Media.Animation.Clock.Controller%2A>\-Eigenschaft der <xref:System.Windows.Media.Animation.AnimationClock>, um einen <xref:System.Windows.Media.Animation.ClockController> abzurufen, und rufen Sie dann die <xref:System.Windows.Media.Animation.ClockController.Remove%2A>\-Methode des <xref:System.Windows.Media.Animation.ClockController> auf.  Dies erfolgt i. d. R. im <xref:System.Windows.Media.Animation.Clock.Completed>\-Ereignishandler für eine Uhr.  Beachten Sie, dass nur Stammuhren von einem <xref:System.Windows.Media.Animation.ClockController> gesteuert werden können. Die <xref:System.Windows.Media.Animation.Clock.Controller%2A>\-Eigenschaft einer untergeordneten Uhr gibt `null` zurück.  Beachten Sie außerdem, dass das <xref:System.Windows.Media.Animation.Clock.Completed>\-Ereignis nicht aufgerufen wird, wenn die effektive Dauer der Uhr endlos ist.  In diesem Fall muss der Benutzer bestimmen, wann <xref:System.Windows.Media.Animation.ClockController.Remove%2A> aufgerufen werden soll.  
  
 Dies betrifft hauptsächlich Animationen für Objekte mit einer langen Lebensdauer.  Wenn ein Objekt an den Garbage Collector übergeben wird, wird auch die Verbindung der Uhren des Objekts getrennt, und diese werden ebenfalls an den Garbage Collector übergeben.  
  
 Weitere Informationen über Uhrobjekte finden Sie unter [Übersicht über das Animations\- und Zeitsteuerungssystem](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)