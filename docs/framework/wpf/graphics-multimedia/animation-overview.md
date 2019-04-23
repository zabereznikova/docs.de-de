---
title: Übersicht über Animationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], animations
- animations [WPF], overview
ms.assetid: bd9ce563-725d-4385-87c9-d7ee38cf79ea
ms.openlocfilehash: 530f6cb8fbe80df3ad374f8ad0e4836be82830a9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337733"
---
# <a name="animation-overview"></a>Übersicht über Animationen
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet eine leistungsstarke Reihe von Grafik- und Layout-Features, die Ihnen ermöglichen, attraktive Benutzeroberflächen und ansprechende Dokumente zu erstellen. Animation kann eine ansprechende Benutzeroberfläche noch spektakulärer und benutzerfreundlicher machen. Indem Sie einfach eine Hintergrundfarbe animieren oder Anwenden einer animierten <xref:System.Windows.Media.Transform>, können Sie eindrucksvolle Bildschirmübergänge erstellen oder hilfreiche visuelle Hinweise.  
  
 Diese Übersicht bietet eine Einführung in die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animations- und Zeitsteuerungssystem. Der Schwerpunkt liegt auf der Animation von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Objekte mithilfe von Storyboards.  

<a name="introducinganimations"></a>   
## <a name="introducing-animations"></a>Einführung in Animationen  
 Mit einer Animation wird eine Illusion geschaffen, die durch die rasche Abfolge einer Reihe von Bildern erzeugt wird, wobei jedes Bild sich ein wenig vom vorherigen Bild unterscheidet. Die Abfolge von Bildern wird vom Gehirn als einzelne, sich ändernde Szene wahrgenommen. Im Film wird diese Illusion mithilfe einer Kamera, die viele Fotos, oder Frames, pro Sekunde aufzeichnet, erstellt. Bei der Wiedergabe der Frames in einem Projektor sieht das Publikum ein bewegtes Bild.  
  
 Animationen auf einem Computer ist ähnlich. Beispielsweise kann ein Programm, das die Zeichnung eines Rechtecks langsam ausblendet wie folgt arbeiten.  
  
-   Das Programm erstellt einen Timer.  
  
-   Das Programm überprüft den Timer in festgelegten Intervallen, um festzustellen, wie viel Zeit verstrichen ist.  
  
-   Jedes Mal wenn das Programm den Timer prüft, berechnet es den aktuellen Durchsichtigkeitswert für das Rechteck, basierend auf der verstrichenen Zeit.  
  
-   Das Programm übernimmt dann den neuen Wert für das Rechteck und zeichnet es neu.  
  
 Vor dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] mussten Entwickler erstellen und verwalten ihre eigenen Zeitsteuerungssysteme oder spezielle benutzerdefinierte Bibliotheken verwenden. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält ein effizientes Zeitsteuerungssystem, die mithilfe von verwaltetem Code verfügbar gemacht wird und [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , die umfassend integriert ist, und die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Framework. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animation ermöglicht es, Steuerelemente und andere Grafikobjekte ganz einfach zu animieren.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erledigt die gesamte Hintergrundarbeit zum Verwalten eines Zeitsteuerungssystems und zum effizienten Neuzeichnen des Bildschirms. WPF bietet Zeitsteuerungsklassen, die Ihnen ermöglichen, sich auf die Effekte, die Sie erstellen möchten, zu konzentrieren, anstatt auf die technischen Details dieser Effekte. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ermöglicht es außerdem auf einfache Weise eigene Animationen zu erstellen, durch das Bereitstellen von Animationsbasisklassen, von denen Ihre Klassen erben können, um benutzerdefinierte Animationen zu erzeugen. Diese benutzerdefinierten Animationen profitieren von vielen Leistungsvorteilen der Standardanimationsklassen.  
  
<a name="thewpftimingsystem"></a>   
## <a name="wpf-property-animation-system"></a>Animationssystem für WPF-Eigenschaften  
 Wenn Sie wissen, dass einige wichtige Konzepte des Zeitsteuerungssystems [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animationen können einfacher zu verwenden sein. Am wichtigsten ist, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], Animieren von Objekten durch Anwenden von Animationen auf die einzelnen Eigenschaften. Zum Beispiel um ein FrameworkElement zu vergrößern, animieren Sie dessen <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften. Um ein Objekt auszublenden, animieren Sie dessen <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft.  
  
 Damit eine Eigenschaft animierbar ist, müssen die folgenden drei Anforderungen erfüllt sein:  
  
-   Es muss sich um eine Abhängigkeitseigenschaft handeln.  
  
-   Er muss zu einer Klasse, die von erbt gehören <xref:System.Windows.DependencyObject> und implementiert die <xref:System.Windows.Media.Animation.IAnimatable> Schnittstelle.  
  
-   Es muss ein kompatibler Animationstyp verfügbar sein. (Wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist nicht zur Verfügung stellt, können Sie Ihre eigenen erstellen. Finden Sie unter den [Übersicht über benutzerdefinierte Animationen](custom-animations-overview.md).)  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält viele Objekte mit <xref:System.Windows.Media.Animation.IAnimatable> Eigenschaften. Steuert, wie z. B. <xref:System.Windows.Controls.Button> und <xref:System.Windows.Controls.TabControl>, sowie <xref:System.Windows.Controls.Panel> und <xref:System.Windows.Shapes.Shape> Objekte erben von <xref:System.Windows.DependencyObject>. Die meisten Eigenschaften sind Abhängigkeitseigenschaften.  
  
 Animationen können fast überall verwendet werden, auch in Stil- und Steuerelementvorlagen. Animationen müssen nicht visuell sein; Sie können Objekte animieren, die nicht Teil der Benutzeroberfläche sind, wenn sie die Kriterien erfüllen, die in diesem Abschnitt beschrieben werden.  
  
<a name="storyboardwalkthrough"></a>   
## <a name="example-make-an-element-fade-in-and-out-of-view"></a>Beispiel: Ausblenden eines Elements und  
 Dieses Beispiel zeigt, wie Sie mit einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animation den Wert einer Abhängigkeitseigenschaft zu animieren. Verwendet eine <xref:System.Windows.Media.Animation.DoubleAnimation>, d.h. eine Art von Animation, die generiert <xref:System.Double> Werten animiert die <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft eine <xref:System.Windows.Shapes.Rectangle>. Daher die <xref:System.Windows.Shapes.Rectangle> ein-und ausgeblendet wird.  
  
 Der erste Teil des Beispiels erstellt eine <xref:System.Windows.Shapes.Rectangle> Element. Die folgenden Schritte zeigen, wie eine Animation erstellt, und wenden Sie diese in des Rechtecks des <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft.
  
 Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Shapes.Rectangle> Element in einem <xref:System.Windows.Controls.StackPanel> in XAML.  
  
 [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]  
  
 Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Shapes.Rectangle> Element in einem <xref:System.Windows.Controls.StackPanel> im Code.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]  
  
<a name="opacity_animation_step1"></a>   
### <a name="part-1-create-a-doubleanimation"></a>Teil 1: Erstellen einer DoubleAnimation  
 Ist eine Möglichkeit, ein Element ein-und auszublenden, animieren seiner <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft. Da die <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft ist vom Typ <xref:System.Double>, benötigen Sie eine Animation, die double-Werte erzeugt. Ein <xref:System.Windows.Media.Animation.DoubleAnimation> ist eine solche Animation. Ein <xref:System.Windows.Media.Animation.DoubleAnimation> erstellt einen Übergang zwischen zwei double-Werten. Um den Startwert anzugeben, legen Sie dessen <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft. Um den Endwert anzugeben, legen Sie dessen <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft.  
  
1. Durchlässigkeitswert `1.0` wird das Objekt vollständig deckend und Durchlässigkeitswert `0.0` wird es vollständig unsichtbar. Der Animation Übergang von `1.0` zu `0.0` Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft `1.0` und die zugehörige <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft, um `0.0`. Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Media.Animation.DoubleAnimation> in XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]  
  
     Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Media.Animation.DoubleAnimation> im Code.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]  
  
2. Als Nächstes müssen Sie angeben einer <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einer Animation gibt an, wie lange es dauert, gehen vom Startwert zum Zielwert. Das folgende Beispiel zeigt, wie Sie festlegen der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> auf fünf Sekunden in XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]  
  
     Das folgende Beispiel zeigt, wie Sie festlegen der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> auf fünf Sekunden im Code.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]  
  
3. Der obige Code zeigt eine Animation, die von wechselt `1.0` zu `0.0`, wodurch das Zielelement von vollständig deckend zu vollständig unsichtbar übergeht. Das Element wieder eingeblendet, nachdem kann legen fest, um die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> -Eigenschaft der Animation zum `true`. Um die Animation endlos wiederholt wird, legen Sie dessen <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. Das folgende Beispiel zeigt, wie Sie festlegen der <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> und <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaften in XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]  
  
     Das folgende Beispiel zeigt, wie Sie festlegen der <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> und <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaften im Code.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]  
  
<a name="opacity_animation_step2"></a>   
### <a name="part-2-create-a-storyboard"></a>Teil 2: Erstellen Sie ein Storyboard  
 Zum Anwenden einer Animation auf ein Objekt, das Sie erstellen eine <xref:System.Windows.Media.Animation.Storyboard> und verwenden Sie die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> angefügten Eigenschaften zum Angeben des Objekts und die zu animierende Eigenschaft.  
  
1. Erstellen der <xref:System.Windows.Media.Animation.Storyboard> und fügen Sie die Animation als untergeordnetes Element hinzu. Das folgende Beispiel zeigt, wie Sie erstellen die <xref:System.Windows.Media.Animation.Storyboard> in XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]    
  
     Zum Erstellen der <xref:System.Windows.Media.Animation.Storyboard> im Code deklariert eine <xref:System.Windows.Media.Animation.Storyboard> Variablen auf Klassenebene.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]  
  
     Initialisieren Sie dann die <xref:System.Windows.Media.Animation.Storyboard> und fügen Sie die Animation als untergeordnetes Element hinzu.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]  
  
2. Die <xref:System.Windows.Media.Animation.Storyboard> wissen, wo die Animation angewendet wurde. Verwenden der <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> angefügte Eigenschaft, um die zu animierende Objekt anzugeben. Das folgende Beispiel zeigt, wie Sie den Zielnamen der Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimation> zu `MyRectangle` in XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]  
  
     Das folgende Beispiel zeigt, wie Sie den Zielnamen der Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimation> zu `MyRectangle` im Code.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]  
  
3. Verwenden der <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> angefügten Eigenschaft, um die zu animierende Eigenschaft anzugeben. Das folgende Beispiel zeigt, wie die Animation konfiguriert ist Ziel der <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft der <xref:System.Windows.Shapes.Rectangle> in XAML.
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]  
  
     Das folgende Beispiel zeigt, wie die Animation konfiguriert ist Ziel der <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft der <xref:System.Windows.Shapes.Rectangle> im Code.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]  
  
 Weitere Informationen zu <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> Syntax und weitere Beispiele finden Sie unter den [Übersicht über Storyboards](storyboards-overview.md).  
  
<a name="opacity_animation_step3"></a>   
### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>Teil 3 (XAML): Ordnen Sie das Storyboard mit einem Trigger  
 Die einfachste Möglichkeit zum Anwenden und Starten einer <xref:System.Windows.Media.Animation.Storyboard> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist die Verwendung ein Ereignistriggers. In diesem Abschnitt wird gezeigt, wie zum Zuordnen der <xref:System.Windows.Media.Animation.Storyboard> mit einem Trigger in XAML.  
  
1. Erstellen Sie eine <xref:System.Windows.Media.Animation.BeginStoryboard> Objekt aus, und ordnen Sie ihm das Storyboard zu. Ein <xref:System.Windows.Media.Animation.BeginStoryboard> ist eine Art von <xref:System.Windows.TriggerAction> , die angewendet wird, und startet eine <xref:System.Windows.Media.Animation.Storyboard>.  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]  
  
2. Erstellen einer <xref:System.Windows.EventTrigger> und Hinzufügen der <xref:System.Windows.Media.Animation.BeginStoryboard> auf seine <xref:System.Windows.EventTrigger.Actions%2A> Auflistung. Legen Sie die <xref:System.Windows.EventTrigger.RoutedEvent%2A> Eigenschaft der <xref:System.Windows.EventTrigger> auf das Routingereignis, das Sie starten möchten die <xref:System.Windows.Media.Animation.Storyboard>. (Weitere Informationen zu Routingereignissen finden Sie unter den [Übersicht über Routingereignisse](../advanced/routed-events-overview.md).)  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]  
  
3. Hinzufügen der <xref:System.Windows.EventTrigger> auf die <xref:System.Windows.FrameworkElement.Triggers%2A> -Auflistung des Rechtecks.  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]  
  
<a name="opacity_animation_step3code"></a>   
### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>Teil 3 (Code): Ordnen Sie das Storyboard mit einem Ereignishandler  
 Die einfachste Möglichkeit zum Anwenden und Starten einer <xref:System.Windows.Media.Animation.Storyboard> im Code ist die Verwendung ein ereignishandlers. In diesem Abschnitt wird gezeigt, wie zum Zuordnen der <xref:System.Windows.Media.Animation.Storyboard> mit einem Ereignishandler im Code.  
  
1. Registrieren Sie sich für die <xref:System.Windows.FrameworkElement.Loaded> -Ereignis des Rechtecks.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]  
  
2. Deklarieren Sie den Ereignishandler. Verwenden Sie im Ereignishandler, der <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode, um das Storyboard anzuwenden.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_105](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_105)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_105](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_105)]  
  
### <a name="complete-example"></a>Vollständiges Beispiel  
 Der folgende Code zeigt ein Rechteck erstellt wird, das in XAML ein-und ausgeblendet wird.  
  
 [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml#rectangleopacityfadeexamplexaml)]  
  
 Der folgende Code zeigt, wie ein Rechteck erstellt wird, das im Code ein- und ausgeblendet wird.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode)]  
  
<a name="animationtypes"></a>   
## <a name="animation-types"></a>Animationstypen  
 Da Animationen Eigenschaftswerte generieren, gibt es verschiedene Animationstypen für unterschiedliche Eigenschaftentypen. Zum Animieren einer Eigenschaft, die akzeptiert eine <xref:System.Double>, z. B. die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft eines Elements, verwenden Sie eine Animation, die erzeugt <xref:System.Double> Werte. Zum Animieren einer Eigenschaft, die akzeptiert eine <xref:System.Windows.Point>, verwenden Sie eine Animation, die erzeugt <xref:System.Windows.Point> Werte und So weiter. Aufgrund der Anzahl der verschiedenen Eigenschaftentypen, es gibt mehrere Animationsklassen in die <xref:System.Windows.Media.Animation> Namespace. Glücklicherweise folgen sie einer strengen Benennungskonvention, die es erleichtert, sie voneinander zu unterscheiden:  
  
-   \<*Typ*> Animation  
  
     Bekannt als „From/To/By“ oder „basic“ Animation, laufen die Animationen zwischen einem Start- und Ziel-Wert ab oder durch Hinzufügen eines Offsetwerts zum Startwert.  
  
    -   Legen Sie die From-Eigenschaft der Animation fest, um einen Startwert anzugeben.  
  
    -   Legen Sie die To-Eigenschaft der Animation fest, um einen Endwert anzugeben.  
  
    -   Legen Sie die By-Eigenschaft der Animation fest, um einen Offsetwert anzugeben.  
  
     Die Beispiele in dieser Übersicht verwenden diese Animationen, da sie am einfachsten zu verwenden sind. From/To/By-Animationen werden in der Übersicht über die to--Animationen ausführlich beschrieben.  
  
-   \<*Type*>AnimationUsingKeyFrames  
  
     Keyframe-Animationen sind leistungsstärker als From-/To-/By-Animationen, da Sie eine beliebige Anzahl an Zielwerten angeben und sogar die Interpolationsmethode steuern können. Einige Typen können nur mit Keyframe-Animationen animiert werden. Keyframe-Animationen ausführlich beschrieben werden die [Übersicht über Keyframe Animationen](key-frame-animations-overview.md).  
  
-   \<*Type*>AnimationUsingPath  
  
     Pfadanimationen ermöglichen Ihnen einen geometrischen Pfad zu verwenden, um animierte Werte zu erzeugen.  
  
-   \<*Type*>AnimationBase  
  
     Abstrakte Klasse, die animiert, wenn Sie sie implementieren eine \< *Typ*> Wert. Diese Klasse dient als Basisklasse für \< *Typ*> Animation und \< *Typ*> AnimationUsingKeyFrames-Klassen. Sie müssen nur dann direkt mit diesen Klassen arbeiten, wenn Sie eigene benutzerdefinierte Animationen erstellen möchten. Verwenden Sie andernfalls eine \< *Typ*>-Animation oder KeyFrame\<*Typ*> Animation.  
  
 In den meisten Fällen sollten Sie verwenden die \< *Typ*> Animation-Klassen, z. B. <xref:System.Windows.Media.Animation.DoubleAnimation> und <xref:System.Windows.Media.Animation.ColorAnimation>.  
  
 Die folgende Tabelle zeigt mehrere allgemeine Animationstypen und einige Eigenschaften, mit denen sie verwendet werden.  
  
|Eigenschaftentyp|Zugehörige Basisanimation (From/To/By)|Zugehörige Keyframe-Animation|Zugehörige Pfadanimation|Beispiel für die Verwendung|  
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Keiner|Animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> von einem <xref:System.Windows.Media.SolidColorBrush> oder <xref:System.Windows.Media.GradientStop>.|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|Animieren der <xref:System.Windows.FrameworkElement.Width%2A> von einer <xref:System.Windows.Controls.DockPanel> oder <xref:System.Windows.FrameworkElement.Height%2A> von eine <xref:System.Windows.Controls.Button>.|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|Animieren der <xref:System.Windows.Media.EllipseGeometry.Center%2A> position eine <xref:System.Windows.Media.EllipseGeometry>.|  
|<xref:System.String>|Keiner|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Keiner|Animieren der <xref:System.Windows.Controls.TextBlock.Text%2A> von einer <xref:System.Windows.Controls.TextBlock> oder <xref:System.Windows.Controls.ContentControl.Content%2A> von eine <xref:System.Windows.Controls.Button>.|  
  
<a name="animationsaretimelines"></a>   
### <a name="animations-are-timelines"></a>Animationen sind Timeline-Klassen  
 Alle Animationstypen erben von der <xref:System.Windows.Media.Animation.Timeline> Klasse; daher werden alle Animationen spezialisierte Typen von Zeitachsen. Ein <xref:System.Windows.Media.Animation.Timeline> definiert einen Zeitabschnitt. Sie können angeben, die *Zeitsteuerungsverhalten* einer Zeitachse: die <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, wie oft sie wiederholt werden und sogar wie schnell die Zeit.  
  
 Da eine Animation ist eine <xref:System.Windows.Media.Animation.Timeline>, es stellt auch einen Zeitabschnitt dar. Eine Animation auch Ausgabewerte berechnet, während ihr die angegebenen Zeitabschnitt durchlaufen (oder <xref:System.Windows.Media.Animation.Timeline.Duration%2A>). Während die Animation durchlaufen oder „abgespielt“ wird, wird die ihr zugeordnete Eigenschaft aktualisiert.  
  
 Drei häufig verwendete Zeitsteuerungseigenschaften sind <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, und <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>.  
  
#### <a name="the-duration-property"></a>Die Duration-Eigenschaft  
 Wie bereits erwähnt, stellt eine Zeitachse einen Zeitabschnitt dar. Die Länge dieses Abschnitts richtet sich nach der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Zeitachse, die in der Regel mithilfe des Parameters eine <xref:System.Windows.Duration.TimeSpan%2A> Wert. Wenn eine Zeitachse das Ende ihrer Dauer erreicht, hat sie eine Iteration abgeschlossen.  
  
 Eine Animation verwendet die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft, um den aktuellen Wert zu bestimmen. Wenn Sie keinen angeben einer <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Wert für eine Animation, Sekunde, die Standardeinstellung verwendet.  
  
 Die folgende Syntax zeigt eine vereinfachte Version der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Attributsyntax für die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft.  
  
*Stunden* `:` *Minuten* `:` *Sekunden*
  
 Die folgende Tabelle zeigt verschiedene <xref:System.Windows.Duration> Einstellungen und die zugehörigen Werte.  
  
|Einstellung|Ergebniswert|  
|-------------|---------------------|  
|0:0:5.5|5.5 Sekunden.|  
|0:30:5.5|30 Minuten und 5,5 Sekunden.|  
|1:30:5.5|1 Stunde, 30 Minuten und 5,5 Sekunden.|  
  
 Eine Möglichkeit zum Angeben einer <xref:System.Windows.Duration> im Code ist die Verwendung der <xref:System.TimeSpan.FromSeconds%2A> Methode zum Erstellen einer <xref:System.TimeSpan>, deklariert dann eine neue <xref:System.Windows.Duration> Struktur verwenden, die <xref:System.TimeSpan>.  
  
 Weitere Informationen zu <xref:System.Windows.Duration> Werte und die vollständige [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Syntax finden Sie unter den <xref:System.Windows.Duration> Struktur.  
  
#### <a name="autoreverse"></a>AutoReverse  
 Die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft gibt an, ob eine Zeitachse rückwärts durchlaufen wird, nachdem das Ende erreicht seiner <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Wenn Sie diese Animationseigenschaft auf `true`, eine Animation kehrt nach des Endes von erreichen der <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, während der Wiedergabe vom Endwert zurück zum Startwert. Diese Eigenschaft ist standardmäßig `false`.  
  
#### <a name="repeatbehavior"></a>RepeatBehavior  
 Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft gibt an, wie oft eine Zeitachse durchlaufen wird. In der Standardeinstellung haben Zeitachsen einen Iterationszähler von `1.0`, d. h. sie eine Zeit und überhaupt nicht wiederholen.  
  
 Weitere Informationen zu diesen und anderen Eigenschaften finden Sie unter den [Übersicht über Zeitsteuerungsverhalten](timing-behaviors-overview.md).  
  
<a name="applyanimationstoproperty"></a>   
## <a name="applying-an-animation-to-a-property"></a>Anwenden einer Animation auf eine Eigenschaft  
 Die vorhergehenden Abschnitte beschreiben die verschiedenen Arten von Animationen und ihre Zeitsteuerungseigenschaften. In diesem Abschnitt wird gezeigt, wie Sie die Animation auf die zu animierende Eigenschaft anwenden. <xref:System.Windows.Media.Animation.Storyboard> Objekte stellen eine Möglichkeit zum Anwenden von Animationen auf Eigenschaften. Ein <xref:System.Windows.Media.Animation.Storyboard> ist eine *Containerzeitachse* , die Zielinformationen für die darin enthaltenen Animationen bereitstellt.  
  
### <a name="targeting-objects-and-properties"></a>Zielobjekte und -Eigenschaften  
 Die <xref:System.Windows.Media.Animation.Storyboard> -Klasse stellt die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> angefügten Eigenschaften. Durch Festlegen dieser Eigenschaften wird der Animation mitgeteilt, was animiert werden soll. Bevor eine Animation jedoch auf ein Objekt angewendet werden kann, muss dem Objekt in der Regel ein Name gegeben werden.  
  
 Zuweisen eines Namens zu einer <xref:System.Windows.FrameworkElement> unterscheidet sich vom Zuweisen eines Namens zu einer <xref:System.Windows.Freezable> Objekt. Die meisten Steuerelemente und Bereiche sind Frameworkelemente; hingegen sind die meisten rein grafischen Objekte, z.B. Pinsel, Transformationen und Geometrien Freezable-Objekte. Wenn Sie nicht sicher sind, gibt an, ob ein Typ ist ein <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.Freezable>, finden Sie in der **Vererbungshierarchie** Abschnitt der jeweiligen Referenzdokumentation.  
  
-   Vornehmen einer <xref:System.Windows.FrameworkElement> ein Animationsziel Sie benennen Sie sie durch Festlegen seiner <xref:System.Windows.FrameworkElement.Name%2A> Eigenschaft. Sie müssen auch verwenden, im Code die <xref:System.Windows.FrameworkElement.RegisterName%2A> Methode, um den Elementnamen mit der Seite registrieren, zu dem er gehört.  
  
-   Vornehmen einer <xref:System.Windows.Freezable> -Objekt ein Animationsziel in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie verwenden die [X: Name Directive](../../xaml-services/x-name-directive.md) um ihm einen Namen zuzuweisen. Im Code verwenden Sie einfach die <xref:System.Windows.FrameworkElement.RegisterName%2A> Methode, um das Objekt mit der Seite zu registrieren, zu dem er gehört.  
  
 Geben Sie ein Beispiel für das Benennen eines Elements in die folgenden Abschnitten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und Code. Ausführlichere Informationen zum Benennen und adressieren, finden Sie unter den [Übersicht über Storyboards](storyboards-overview.md).  
  
### <a name="applying-and-starting-storyboards"></a>Anwenden und Starten von Storyboards  
 Zum Starten eines Storyboards [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], ordnen sie einer <xref:System.Windows.EventTrigger>. Ein <xref:System.Windows.EventTrigger> ist ein Objekt, das beschreibt, welche Aktionen auf, wenn ein bestimmtes Ereignis auftritt. Eine dieser Aktionen sein kann eine <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion, die Sie verwenden, um das Storyboard zu starten. Ereignistrigger ähneln in ihrem Konzept Ereignishandlern, da sie angeben können, wie Ihre Anwendung auf ein bestimmtes Ereignis reagieren soll. Im Gegensatz zum Ereignishandler, können Ereignistrigger vollständig beschrieben werden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; es ist kein weiterer Code erforderlich.  
  
 Starten einer <xref:System.Windows.Media.Animation.Storyboard> im Code können Sie eine <xref:System.Windows.EventTrigger> oder verwenden Sie die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> -Methode der der <xref:System.Windows.Media.Animation.Storyboard> Klasse.  
  
<a name="controllingstoryboards"></a>   
## <a name="interactively-control-a-storyboard"></a>Interaktives Steuern eines Storyboards  
 Im vorherige Beispiel wurde gezeigt, wie zu einem <xref:System.Windows.Media.Animation.Storyboard> bei Auftreten eines Ereignisses. Sie können auch interaktiv steuern eine <xref:System.Windows.Media.Animation.Storyboard> nach dem Start: Sie können anhalten, fortsetzen, beenden, können Sie es auf seines Füllbereichs, suchen und Entfernen der <xref:System.Windows.Media.Animation.Storyboard>. Weitere Informationen und ein Beispiel, das zeigt, wie Sie interaktiv steuern eine <xref:System.Windows.Media.Animation.Storyboard>, finden Sie unter den [Übersicht über Storyboards](storyboards-overview.md).  
  
<a name="fillbehaviorsection"></a>   
## <a name="what-happens-after-an-animation-ends"></a>Was geschieht nach dem Ende einer Animation?  
 Die <xref:System.Windows.Media.Animation.FillBehavior> Eigenschaft gibt an, wie eine Zeitachse verhält, wenn sie endet. Standardmäßig eine Zeitachse gestartet wird, <xref:System.Windows.Media.Animation.ClockState.Filling> endet. Eine Animation, die <xref:System.Windows.Media.Animation.ClockState.Filling> behält ihren endgültigen Ausgabewert.  
  
 Die <xref:System.Windows.Media.Animation.DoubleAnimation> im vorherigen Beispiel wird nicht beendet, da die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> -Eigenschaftensatz auf <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. Im folgenden Beispiel wird ein Rechteck mithilfe einer ähnlichen Animation animiert. Im Gegensatz zum vorherigen Beispiel ist die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> und <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> -Eigenschaften dieser Animation bleiben die Standardwerte bei. Aus diesem Grund wechselt die Animation innerhalb von fünf Sekunden von 1 auf 0 und hält dann an.  
  
 [!code-xaml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]  
  
 [!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
 [!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]  
  
 Da die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> wurde nicht geändert werden, von seinem Standardwert, d.h. <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, behält die Animation Endwert 0 bei, wenn sie endet. Aus diesem Grund die <xref:System.Windows.UIElement.Opacity%2A> der Rechteck bleibt bei 0, nachdem die Animation endet. Setzen Sie die <xref:System.Windows.UIElement.Opacity%2A> des Rechtecks auf einen anderen Wert Code keine Auswirkung, haben wird angezeigt, da die Animation immer noch beeinträchtigt die <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft.  
  
 Eine Möglichkeit, die Kontrolle über eine animierte Eigenschaft im Code ist die Verwendung der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode, und geben Sie null für den <xref:System.Windows.Media.Animation.AnimationTimeline> Parameter. Weitere Informationen und ein Beispiel finden Sie unter [Festlegen einer Eigenschaft nach Animation mit einem Storyboard](how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
 Beachten Sie, dass, obwohl das Festlegen eines Eigenschaftswerts, der hat eine <xref:System.Windows.Media.Animation.ClockState.Active> oder <xref:System.Windows.Media.Animation.ClockState.Filling> Animation scheinbar keine Auswirkung, die den Wert der Eigenschaft ändert. Weitere Informationen finden Sie unter den [Animation und zeitliche Steuerung Systemübersicht](animation-and-timing-system-overview.md).  
  
<a name="databindingAndAnimatingAnimationsSection"></a>   
## <a name="data-binding-and-animating-animations"></a>Datenbindung und Animieren von Animationen  
 Die meisten Animationseigenschaften können an Daten gebunden oder animiert sein; Sie können z. B. Animieren der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.DoubleAnimation>. Aufgrund der Funktionsweise des Zeitsteuerungssystems verhalten sich datengebundene oder animierte Animationen jedoch nicht wie andere datengebundene oder animierte Objekte. Um ihr Verhalten zu verstehen, sollten sie wissen, was es bedeutet, eine Animation auf eine Eigenschaft anzuwenden.  
  
 Finden Sie im Beispiel im vorherigen Abschnitt wurde gezeigt, wie Sie animieren, die die <xref:System.Windows.UIElement.Opacity%2A> eines Rechtecks. Wenn das Rechteck im vorherigen Beispiel geladen wird, wendet der Ereignistrigger das <xref:System.Windows.Media.Animation.Storyboard>. Das Zeitsteuerungssystem erstellt eine Kopie der <xref:System.Windows.Media.Animation.Storyboard> und seiner Animation. Diese Kopien werden gesperrt (schreibgeschützt) und <xref:System.Windows.Media.Animation.Clock> Objekte daraus erstellt werden. Das eigentliche Animieren der Zieleigenschaften erfolgt durch diese Uhren.  
  
 Das Zeitsteuerungssystem erstellt eine Uhr für die <xref:System.Windows.Media.Animation.DoubleAnimation> und wendet sie auf das Objekt und Eigenschaft, die angegeben wird die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> von der <xref:System.Windows.Media.Animation.DoubleAnimation>. In diesem Fall gilt das Zeitsteuerungssystem die Uhr um die <xref:System.Windows.UIElement.Opacity%2A> -Eigenschaft des Objekts mit dem Namen "MyRectangle" angewendet.  
  
 Obwohl für ebenfalls eine Uhr erstellt wird der <xref:System.Windows.Media.Animation.Storyboard>, die Uhr nicht auf alle Eigenschaften, die angewendet wird. Der Zweck besteht seine untergeordneten Uhr zu steuern, die für erstellt wird die <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 Damit eine Animation Änderungen der Datenbindung und der Animation widerspiegelt, muss die Uhr erneut generiert werden. Uhren werden nicht automatisch neu generiert. Um eine Animation Änderungen vornehmen möchten, wenden Sie erneut an das Storyboard mit einem <xref:System.Windows.Media.Animation.BeginStoryboard> oder <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode. Wenn Sie eine dieser beiden Methoden anwenden, startet die Animation neu. Im Code können Sie die <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> Methode, um im Storyboard zur vorherigen Position zurück.  
  
 Ein Beispiel für eine datengebundene Animation finden Sie unter [Key Spline Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160011). Weitere Informationen zur Funktionsweise des Animations- und Zeitsteuerungssystem finden Sie unter [Animation und zeitliche Steuerung Systemübersicht](animation-and-timing-system-overview.md).  
  
<a name="otherWaysToAnimateSection"></a>   
## <a name="other-ways-to-animate"></a>Andere Möglichkeiten für Animationen  
 Die Beispiele in dieser Übersicht zeigen, wie Animationen mithilfe von Storyboards erstellt werden. Im Code können Sie Animationen auf verschiedenste Weise erstellen. Weitere Informationen finden Sie unter den [Eigenschaft Techniken-Übersicht über Animationen](property-animation-techniques-overview.md).  
  
<a name="animation_samples"></a>   
## <a name="animation-samples"></a>Beispiele für Animationen  
 In den folgenden Beispielen sehen Sie, wie Sie Animationen zu Ihren Anwendungen Hinzufügen können.  
  
-   [From, To, and By Animation Target Values Sample (Beispiel für From-, To- und By-Animationszielwerte)](https://go.microsoft.com/fwlink/?LinkID=159988)  
  
     Veranschaulicht verschiedene From, To, By-Einstellungen.  
  
-   [Beispiel zum Verhalten der Animationszeitsteuerung](https://go.microsoft.com/fwlink/?LinkID=159970)  
  
     Zeigt die verschiedenen Möglichkeiten, wie Sie das Zeitsteuerungsverhalten einer Animation steuern können. Dieses Beispiel zeigt auch, wie Sie die Datenbindung für den Zielwert einer Animation durchführen.  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Übersicht über das Animations- und Zeitsteuerungssystem](animation-and-timing-system-overview.md)|Beschreibt, wie das Zeitsteuerungssystem verwendet die <xref:System.Windows.Media.Animation.Timeline> und <xref:System.Windows.Media.Animation.Clock> Klassen, die Ihnen beim Erstellen von Animationen ermöglichen.|  
|[Tipps und Tricks zu Animationen](animation-tips-and-tricks.md)|Hier sind hilfreiche Tipps zum Beheben von Problemen mit Animationfen, z.B. Leistungsprobleme aufgelistet.|  
|[Übersicht über benutzerdefinierte Animationen](custom-animations-overview.md)|Beschreibt, wie das Animationssystem mit Keyframes, Animationsklassen oder Pro-Frame-Rückrufen erweitert werden kann.|  
|Übersicht über From/To/By-Animationen|Beschreibt, wie Sie eine Animation erstellen, die zwischen zwei Werten wechselt.|  
|[Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)|Beschreibt das Erstellen einer Animation mit mehreren Zielwerten, einschließlich der Möglichkeit, die Interpolationsmethode zu steuern.|  
|[Beschleunigungsfunktionen](easing-functions.md)|Erklärt, wie mathematische Formeln auf die Animationen angewendet werden, um ein realistisches Verhalten, z.B. Sprungeffekte zu erreichen.|  
|[Übersicht über Pfadanimationen](path-animations-overview.md)|Beschreibt das Verschieben oder Drehen eines Objekts entlang eines komplexen Pfads.|  
|[Übersicht über die Verfahren zur Animation von Eigenschaften](property-animation-techniques-overview.md)|Beschreibt Eigenschaftenanimationen mithilfe von Storyboards, lokalen Animationen, Uhren und Pro-Frame-Animationen.|  
|[Übersicht über Storyboards](storyboards-overview.md)|Beschreibt, wie Storyboards mit mehreren Zeitachsen zum Erstellen komplexer Animationen verwendet werden.|  
|[Übersicht über Zeitsteuerungsverhalten](timing-behaviors-overview.md)|Beschreibt die <xref:System.Windows.Media.Animation.Timeline> Typen und Eigenschaften, die in Animationen verwendeten.|  
|[Übersicht über Zeitsteuerungsereignisse](timing-events-overview.md)|Beschreibt die Ereignisse, die auf die <xref:System.Windows.Media.Animation.Timeline> und <xref:System.Windows.Media.Animation.Clock> -Objekten zum Ausführen des Codes an Punkten auf der Zeitachse, z. B. starten, anhalten, fortsetzen, überspringen oder beenden.|  
|[Themen zu Vorgehensweisen](animation-and-timing-how-to-topics.md)|Enthält Codebeispiele für die Verwendung von Animationen und Zeitachsen in der Anwendung.|  
|[Clocks How-to Topics (Themen zur Vorgehensweise zu Uhren)](clocks-how-to-topics.md)|Enthält Codebeispiele für die Verwendung der <xref:System.Windows.Media.Animation.Clock> Objekt in der Anwendung.|  
|[Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](key-frame-animation-how-to-topics.md)|Enthält Codebeispiele für die Verwendung von Keyframe-Animationen in Ihrer Anwendung.|  
|[Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)](path-animation-how-to-topics.md)|Enthält Codebeispiele für die Verwendung von Pfadanimationen in Ihrer Anwendung.|  
  
<a name="reference"></a>   
## <a name="reference"></a>Referenz  
 <xref:System.Windows.Media.Animation.Timeline>  
  
 <xref:System.Windows.Media.Animation.Storyboard>  
  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
  
 <xref:System.Windows.Media.Animation.Clock>
