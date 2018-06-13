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
ms.openlocfilehash: 5fb9550ddce4ead900206c2ece2f976ab8b42c4b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558329"
---
# <a name="animation-overview"></a>Übersicht über Animationen
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet einen leistungsfähigen Satz an Grafiken und Layout-Funktionen, mit die Sie attraktive Benutzeroberflächen und ansprechende Dokumente erstellen können. Animation kann eine ansprechende Benutzeroberfläche noch spektakulärer und benutzerfreundlicher machen. Indem Sie einfach eine Hintergrundfarbe animieren oder Anwenden einer animierten <xref:System.Windows.Media.Transform>, können erhebliche Bildschirmübergänge erstellen oder hilfreiche visuelle Hinweise geben.  
  
 Diese Übersicht bietet eine Einführung in die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animations- und Zeitsteuerungssystems. Der Schwerpunkt liegt dabei auf die Animation des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Objekte mithilfe von Storyboards.  

<a name="introducinganimations"></a>   
## <a name="introducing-animations"></a>Einführung in Animationen  
 Mit einer Animation wird eine Illusion geschaffen, die durch die rasche Abfolge einer Reihe von Bildern erzeugt wird, wobei jedes Bild sich ein wenig vom vorherigen Bild unterscheidet. Die Abfolge von Bildern wird vom Gehirn als einzelne, sich ändernde Szene wahrgenommen. Im Film wird diese Illusion mithilfe einer Kamera, die viele Fotos, oder Frames, pro Sekunde aufzeichnet, erstellt. Bei der Wiedergabe der Frames in einem Projektor sieht das Publikum ein bewegtes Bild.  
  
 Animationen auf einem Computer ist ähnlich. Beispielsweise kann ein Programm, das die Zeichnung eines Rechtecks langsam ausblendet wie folgt arbeiten.  
  
-   Das Programm erstellt einen Timer.  
  
-   Das Programm überprüft den Timer in festgelegten Intervallen, um festzustellen, wie viel Zeit verstrichen ist.  
  
-   Jedes Mal wenn das Programm den Timer prüft, berechnet es den aktuellen Durchsichtigkeitswert für das Rechteck, basierend auf der verstrichenen Zeit.  
  
-   Das Programm übernimmt dann den neuen Wert für das Rechteck und zeichnet es neu.  
  
 Vor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] mussten Entwickler erstellen und verwalten ihre eigenen Timing Systeme oder spezielle benutzerdefinierte Bibliotheken verwenden. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält eine effiziente Zeitsteuerungssystems, die durch verwalteten Code verfügbar gemacht wird und [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] auch tief in integriert ist die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Framework. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animation ermöglicht es, Steuerelemente und andere Grafikobjekte ganz einfach zu animieren.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erledigt die gesamte Hintergrundarbeit zum Verwalten eines Zeitsteuerungssystems und zum effizienten Neuzeichnen des Bildschirms. WPF bietet Zeitsteuerungsklassen, die Ihnen ermöglichen, sich auf die Effekte, die Sie erstellen möchten, zu konzentrieren, anstatt auf die technischen Details dieser Effekte. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ermöglicht es außerdem auf einfache Weise eigene Animationen zu erstellen, durch das Bereitstellen von Animationsbasisklassen, von denen Ihre Klassen erben können, um benutzerdefinierte Animationen zu erzeugen. Diese benutzerdefinierten Animationen profitieren von vielen Leistungsvorteilen der Standardanimationsklassen.  
  
<a name="thewpftimingsystem"></a>   
## <a name="wpf-property-animation-system"></a>Animationssystem für WPF-Eigenschaften  
 Wenn Sie verstehen, dass einige wichtige Konzepte zu den Zeitsteuerungssystems [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animationen können einfacher verwendet werden. Am wichtigsten ist, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], Animieren von Objekten von Animationen auf ihre einzelnen Eigenschaften anwenden. Beispielsweise um eine FrameworkElement zu vergrößern, animieren Sie dessen <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften. Um ein Objekt aus der Ansicht ausgeblendet, animieren Sie dessen <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft.  
  
 Damit eine Eigenschaft animierbar ist, müssen die folgenden drei Anforderungen erfüllt sein:  
  
-   Es muss sich um eine Abhängigkeitseigenschaft handeln.  
  
-   Er muss auf eine Klasse, die von erben gehören <xref:System.Windows.DependencyObject> und implementiert die <xref:System.Windows.Media.Animation.IAnimatable> Schnittstelle.  
  
-   Es muss ein kompatibler Animationstyp verfügbar sein. (Wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nicht bereitstellen, können Ihre eigenen erstellen. Finden Sie unter der [Übersicht über benutzerdefinierte Animationen](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md).)  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält viele Objekte mit <xref:System.Windows.Media.Animation.IAnimatable> Eigenschaften. Steuert, wie z. B. <xref:System.Windows.Controls.Button> und <xref:System.Windows.Controls.TabControl>, sowie <xref:System.Windows.Controls.Panel> und <xref:System.Windows.Shapes.Shape> Objekte erben von <xref:System.Windows.DependencyObject>. Die meisten Eigenschaften sind Abhängigkeitseigenschaften.  
  
 Animationen können fast überall verwendet werden, auch in Stil- und Steuerelementvorlagen. Animationen müssen nicht visuell sein; Sie können Objekte animieren, die nicht Teil der Benutzeroberfläche sind, wenn sie die Kriterien erfüllen, die in diesem Abschnitt beschrieben werden.  
  
<a name="storyboardwalkthrough"></a>   
## <a name="example-make-an-element-fade-in-and-out-of-view"></a>Beispiel: Ein- und Ausblenden eines Elements  
 Dieses Beispiel zeigt, wie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animation animiert den Wert einer Abhängigkeitseigenschaft. Er verwendet ein <xref:System.Windows.Media.Animation.DoubleAnimation>, d. h. einen Typ der Animation an, die generiert <xref:System.Double> Werte, die zu animierende der <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft eine <xref:System.Windows.Shapes.Rectangle>. Daher die <xref:System.Windows.Shapes.Rectangle> ein-und ausgeblendet.  
  
 Der erste Teil des Beispiels erstellt ein <xref:System.Windows.Shapes.Rectangle> Element. Die folgenden Schritte zeigen, wie eine Animation erstellen, und wenden Sie es in des Rechtecks <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft.
  
 Im folgenden wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Shapes.Rectangle> Element in einem <xref:System.Windows.Controls.StackPanel> in XAML.  
  
 [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]  
  
 Im folgenden wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Shapes.Rectangle> Element in einem <xref:System.Windows.Controls.StackPanel> im Code.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]  
  
<a name="opacity_animation_step1"></a>   
### <a name="part-1-create-a-doubleanimation"></a>Teil 1: Erstellen einer DoubleAnimation  
 Eine Möglichkeit, ein Element ein-und gestalten zum Animieren wird seine <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft. Da die <xref:System.Windows.UIElement.Opacity%2A> -Eigenschaft ist vom Typ <xref:System.Double>, benötigen Sie eine Animation, double-Werte erzeugt. Ein <xref:System.Windows.Media.Animation.DoubleAnimation> ist eine solche Animation. Ein <xref:System.Windows.Media.Animation.DoubleAnimation> erstellt einen Übergang zwischen zwei double-Werte. Um ihren Startwert anzugeben, legen Sie dessen <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft. Wenn Endwert angeben möchten, legen Sie dessen <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft.  
  
1.  Ein Wert für die Deckkraft des `1.0` wird das Objekt vollständig deckend und einen Wert für die Deckkraft des `0.0` wird es vollständig unsichtbar. Für die Animationsübergang aus `1.0` auf `0.0` Festlegen seiner <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft, um `1.0` und seine <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft `0.0`. Im folgenden wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Media.Animation.DoubleAnimation> in XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]  
  
     Im folgenden wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Media.Animation.DoubleAnimation> im Code.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]  
  
2.  Als Nächstes geben Sie einen <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einer Animation gibt an, wie lange es dauert, um von ihren Startwert zum Zielwert zu wechseln. Im folgenden veranschaulicht das Festlegen der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> auf fünf Sekunden in XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]  
  
     Im folgenden veranschaulicht das Festlegen der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> auf fünf Sekunden im Code.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]  
  
3.  Der obige Code zeigt eine Animation, der Übergang von `1.0` zu `0.0`, die bewirkt, dass des Zielelements werden von vollständig deckend abgeblendet, um vollständig unsichtbar. Möchten das Element wieder in der Ansicht ausgeblendet werden soll, nachdem es verschwindet, Festlegen der <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> -Eigenschaft der Animation auf `true`. Um die Animation endlos wiederholt wird, legen Sie dessen <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. Im folgenden veranschaulicht das Festlegen der <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> und <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaften in XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]  
  
     Im folgenden veranschaulicht das Festlegen der <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> und <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaften im Code.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]  
  
<a name="opacity_animation_step2"></a>   
### <a name="part-2-create-a-storyboard"></a>Teil 2: Erstellen eines Storyboards  
 Um eine Animation auf ein Objekt anzuwenden, erstellen Sie eine <xref:System.Windows.Media.Animation.Storyboard> und Verwenden der <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> angefügte Eigenschaften zum Angeben des Objekts und die zu animierende Eigenschaft.  
  
1.  Erstellen der <xref:System.Windows.Media.Animation.Storyboard> und fügen Sie die Animation als untergeordnetes Element hinzu. Im folgenden wird gezeigt, wie zum Erstellen der <xref:System.Windows.Media.Animation.Storyboard> in XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]    
  
     Zum Erstellen der <xref:System.Windows.Media.Animation.Storyboard> in Code deklariert eine <xref:System.Windows.Media.Animation.Storyboard> Variablen auf Klassenebene.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]  
  
     Initialisieren Sie dann die <xref:System.Windows.Media.Animation.Storyboard> und fügen Sie die Animation als untergeordnetes Element hinzu.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]  
  
2.  Die <xref:System.Windows.Media.Animation.Storyboard> wissen, wo die Animation angewendet wurde. Verwenden der <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> -Eigenschaft, um anzugeben, das zu animierende Objekt. Im folgenden wird gezeigt, wie den Zielnamen der Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimation> auf `MyRectangle` in XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]  
  
     Im folgenden wird gezeigt, wie den Zielnamen der Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimation> auf `MyRectangle` im Code.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]  
  
3.  Verwenden der <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> -Eigenschaft, um anzugeben, die zu animierende Eigenschaft. Das folgende Beispiel zeigt, wie die Animation konfiguriert ist Ziel der <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft von der <xref:System.Windows.Shapes.Rectangle> in XAML.
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]  
  
     Das folgende Beispiel zeigt, wie die Animation konfiguriert ist Ziel der <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft von der <xref:System.Windows.Shapes.Rectangle> im Code.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]  
  
 Weitere Informationen zu <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> Syntax und weitere Beispiele finden Sie unter der [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
<a name="opacity_animation_step3"></a>   
### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>Teil 3 (XAML): Zuordnen des Storyboards zu einem Trigger  
 Die einfachste Möglichkeit zum Anwenden und Starten einer <xref:System.Windows.Media.Animation.Storyboard> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] einen Ereignisauslöser verwendet wird. In diesem Abschnitt wird gezeigt, wie zum Zuordnen der <xref:System.Windows.Media.Animation.Storyboard> mit einem Trigger in XAML.  
  
1.  Erstellen einer <xref:System.Windows.Media.Animation.BeginStoryboard> -Objekt und das Storyboard zuordnen. Ein <xref:System.Windows.Media.Animation.BeginStoryboard> ist eine Art von <xref:System.Windows.TriggerAction> , die angewendet wird, und startet eine <xref:System.Windows.Media.Animation.Storyboard>.  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]  
  
2.  Erstellen einer <xref:System.Windows.EventTrigger> und Hinzufügen der <xref:System.Windows.Media.Animation.BeginStoryboard> auf seine <xref:System.Windows.EventTrigger.Actions%2A> Auflistung. Festlegen der <xref:System.Windows.EventTrigger.RoutedEvent%2A> Eigenschaft von der <xref:System.Windows.EventTrigger> auf das Routingereignis, die Sie starten möchten die <xref:System.Windows.Media.Animation.Storyboard>. (Weitere Informationen zu Routingereignissen finden Sie unter der [Ereignisübersicht weitergeleitet](../../../../docs/framework/wpf/advanced/routed-events-overview.md).)  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]  
  
3.  Hinzufügen der <xref:System.Windows.EventTrigger> auf die <xref:System.Windows.FrameworkElement.Triggers%2A> Auflistung des Rechtecks.  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]  
  
<a name="opacity_animation_step3code"></a>   
### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>Teil 3 (Code): Zuordnen des Storyboards zu einem Ereignishandler  
 Die einfachste Möglichkeit zum Anwenden und Starten einer <xref:System.Windows.Media.Animation.Storyboard> Code befindet, um einen Ereignishandler zu verwenden. In diesem Abschnitt wird gezeigt, wie zum Zuordnen der <xref:System.Windows.Media.Animation.Storyboard> mit einem Ereignishandler im Code.  
  
1.  Registrieren Sie sich für die <xref:System.Windows.FrameworkElement.Loaded> Ereignis des Rechtecks.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]  
  
2.  Deklarieren Sie den Ereignishandler. Verwenden Sie im Ereignishandler, die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode, um das Storyboard anzuwenden.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_105)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_105)]  
  
### <a name="complete-example"></a>Vollständiges Beispiel  
 Im folgenden wird gezeigt, wie ein Rechteck erstellt, die in XAML ein-und ausgeblendet wird.  
  
 [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml#rectangleopacityfadeexamplexaml)]  
  
 Der folgende Code zeigt, wie ein Rechteck erstellt wird, das im Code ein- und ausgeblendet wird.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode)]  
  
<a name="animationtypes"></a>   
## <a name="animation-types"></a>Animationstypen  
 Da Animationen Eigenschaftswerte generieren, gibt es verschiedene Animationstypen für unterschiedliche Eigenschaftentypen. Eine Eigenschaft animieren, akzeptiert eine <xref:System.Double>, wie z. B. die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft eines Elements, verwenden Sie eine Animation, erzeugt <xref:System.Double> Werte. Eine Eigenschaft animieren, akzeptiert eine <xref:System.Windows.Point>, verwenden Sie eine Animation, erzeugt <xref:System.Windows.Point> Werte und So weiter. Dank der zahlreichen verschiedenen Eigenschaftentypen, es gibt mehrere Animationsklassen in der <xref:System.Windows.Media.Animation> Namespace. Glücklicherweise folgen sie einer strengen Benennungskonvention, die es erleichtert, sie voneinander zu unterscheiden:  
  
-   \<*Typ*> Animation  
  
     Bekannt als „From/To/By“ oder „basic“ Animation, laufen die Animationen zwischen einem Start- und Ziel-Wert ab oder durch Hinzufügen eines Offsetwerts zum Startwert.  
  
    -   Legen Sie die From-Eigenschaft der Animation fest, um einen Startwert anzugeben.  
  
    -   Legen Sie die To-Eigenschaft der Animation fest, um einen Endwert anzugeben.  
  
    -   Legen Sie die By-Eigenschaft der Animation fest, um einen Offsetwert anzugeben.  
  
     Die Beispiele in dieser Übersicht verwenden diese Animationen, da sie am einfachsten zu verwenden sind. Von/zu/von Animationen werden in der Übersicht über die From/To/By Animationen im Detail beschrieben.  
  
-   \<*Typ*> AnimationUsingKeyFrames  
  
     Keyframe-Animationen sind leistungsstärker als From-/To-/By-Animationen, da Sie eine beliebige Anzahl an Zielwerten angeben und sogar die Interpolationsmethode steuern können. Einige Typen können nur mit Keyframe-Animationen animiert werden. Keyframe-Animationen werden ausführlich beschrieben unter der [Keyframe-Animationen Übersicht](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
-   \<*Typ*> AnimationUsingPath  
  
     Pfadanimationen ermöglichen Ihnen einen geometrischen Pfad zu verwenden, um animierte Werte zu erzeugen.  
  
-   \<*Typ*> AnimationBase  
  
     Abstrakte Klasse, die eine, wenn Sie sie implementieren Animation eine \< *Typ*> Wert. Diese Klasse dient als Basisklasse für \< *Typ*> Animation und \< *Typ*> AnimationUsingKeyFrames-Klassen. Sie müssen nur dann direkt mit diesen Klassen arbeiten, wenn Sie eigene benutzerdefinierte Animationen erstellen möchten. Verwenden Sie andernfalls eine \< *Typ*> Animation oder KeyFrame\<*Typ*> Animation.  
  
 In den meisten Fällen besteht Ihr Ziel zum Verwenden der \< *Typ*> Animation-Klassen, z. B. <xref:System.Windows.Media.Animation.DoubleAnimation> und <xref:System.Windows.Media.Animation.ColorAnimation>.  
  
 Die folgende Tabelle zeigt mehrere allgemeine Animationstypen und einige Eigenschaften, mit denen sie verwendet werden.  
  
|Eigenschaftentyp|Zugehörige Basisanimation (From/To/By)|Zugehörige Keyframe-Animation|Zugehörige Pfadanimation|Beispiel für die Verwendung|  
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Keiner|Animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> von einem <xref:System.Windows.Media.SolidColorBrush> oder ein <xref:System.Windows.Media.GradientStop>.|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|Animieren der <xref:System.Windows.FrameworkElement.Width%2A> von einer <xref:System.Windows.Controls.DockPanel> oder die <xref:System.Windows.FrameworkElement.Height%2A> des eine <xref:System.Windows.Controls.Button>.|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|Animieren der <xref:System.Windows.Media.EllipseGeometry.Center%2A> position ein <xref:System.Windows.Media.EllipseGeometry>.|  
|<xref:System.String>|Keiner|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Keiner|Animieren der <xref:System.Windows.Controls.TextBlock.Text%2A> von einer <xref:System.Windows.Controls.TextBlock> oder die <xref:System.Windows.Controls.ContentControl.Content%2A> des eine <xref:System.Windows.Controls.Button>.|  
  
<a name="animationsaretimelines"></a>   
### <a name="animations-are-timelines"></a>Animationen sind Timeline-Klassen  
 Alle Animationstypen erben von der <xref:System.Windows.Media.Animation.Timeline> -Klasse; daher werden alle Animationen spezialisierte Typen von Zeitplänen. Ein <xref:System.Windows.Media.Animation.Timeline> definiert einen Zeitabschnitt. Sie können angeben, der *Zeitsteuerungsverhalten* einer Zeitachse: seine <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, wie oft sie wiederholt und sogar wie schnell die Zeit dafür wechselt.  
  
 Da eine Animation ist eine <xref:System.Windows.Media.Animation.Timeline>, er stellt auch einen Zeitabschnitt. Berechnet eine Animation auch Ausgabewerte, währenddessen aber seine angegebenen Zeitabschnitt (oder <xref:System.Windows.Media.Animation.Timeline.Duration%2A>). Während die Animation durchlaufen oder „abgespielt“ wird, wird die ihr zugeordnete Eigenschaft aktualisiert.  
  
 Drei häufig verwendete Zeitsteuerungseigenschaften sind <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, und <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>.  
  
#### <a name="the-duration-property"></a>Die Duration-Eigenschaft  
 Wie bereits erwähnt, stellt eine Zeitachse einen Zeitabschnitt dar. Die Länge des Abschnitts richtet sich nach der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Zeitachse, die in der Regel mithilfe des Parameters eine <xref:System.Windows.Duration.TimeSpan%2A> Wert. Wenn eine Zeitachse das Ende ihrer Dauer erreicht, hat sie eine Iteration abgeschlossen.  
  
 Eine Animation verwendet seine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> -Eigenschaft können Sie den aktuellen Wert zu bestimmen. Wenn Sie keinen angeben einer <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Wert für eine Animation 1 Sekunde, die Standardeinstellung verwendet.  
  
 Die folgende Syntax zeigt eine vereinfachte Version der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Attributsyntax für die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft.  
  
*Stunden* `:` *Minuten* `:` *Sekunden*
  
 Die folgende Tabelle zeigt verschiedene <xref:System.Windows.Duration> Einstellungen und zugehörigen Werte.  
  
|Einstellung|Ergebniswert|  
|-------------|---------------------|  
|0:0:5.5|5.5 Sekunden.|  
|0:30:5.5|30 Minuten und 5,5 Sekunden.|  
|1:30:5.5|1 Stunde, 30 Minuten und 5,5 Sekunden.|  
  
 Eine Möglichkeit zum Angeben einer <xref:System.Windows.Duration> im Code ist die Verwendung der <xref:System.TimeSpan.FromSeconds%2A> Methode zum Erstellen einer <xref:System.TimeSpan>, deklarieren Sie ein neues <xref:System.Windows.Duration> Struktur verwenden, die <xref:System.TimeSpan>.  
  
 Weitere Informationen zu <xref:System.Windows.Duration> Werte und die vollständige [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Syntax finden Sie unter der <xref:System.Windows.Duration> Struktur.  
  
#### <a name="autoreverse"></a>AutoReverse  
 Die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft gibt an, ob eine Zeitachse rückwärts durchlaufen wird, nach das Ende erreichen seiner <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Wenn Sie diese Animationseigenschaft, um festgelegt `true`, eine Animation kehrt nach des Endes des erreichen seine <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, während der Wiedergabe aus den Endwert wieder auf den ersten Wert. Standardmäßig ist diese Eigenschaft `false`.  
  
#### <a name="repeatbehavior"></a>RepeatBehavior  
 Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft gibt an, wie oft eine Zeitachse wiedergegeben wird. Wird standardmäßig von Zeitachsen ist eine Iteration `1.0`, d. h. sie eine Zeit und nicht wiederholen.  
  
 Weitere Informationen zu diesen und anderen Eigenschaften finden Sie unter der [Timing Behaviors Overview](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md).  
  
<a name="applyanimationstoproperty"></a>   
## <a name="applying-an-animation-to-a-property"></a>Anwenden einer Animation auf eine Eigenschaft  
 Die vorhergehenden Abschnitte beschreiben die verschiedenen Arten von Animationen und ihre Zeitsteuerungseigenschaften. In diesem Abschnitt wird gezeigt, wie Sie die Animation auf die zu animierende Eigenschaft anwenden. <xref:System.Windows.Media.Animation.Storyboard> Objekte bieten eine Möglichkeit, Animationen auf Eigenschaften anwenden. Ein <xref:System.Windows.Media.Animation.Storyboard> ist ein *Containerzeitachse* Zielinformationen für die darin enthaltenen Animationen bereitstellt.  
  
### <a name="targeting-objects-and-properties"></a>Zielobjekte und -Eigenschaften  
 Die <xref:System.Windows.Media.Animation.Storyboard> -Klasse stellt die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> angefügte Eigenschaften. Durch Festlegen dieser Eigenschaften wird der Animation mitgeteilt, was animiert werden soll. Bevor eine Animation jedoch auf ein Objekt angewendet werden kann, muss dem Objekt in der Regel ein Name gegeben werden.  
  
 Zuweisen eines Namens zu einer <xref:System.Windows.FrameworkElement> unterscheidet sich von der ein Name zugewiesen ein <xref:System.Windows.Freezable> Objekt. Die meisten Steuerelemente und Bereiche sind Frameworkelemente; hingegen sind die meisten rein grafischen Objekte, z.B. Pinsel, Transformationen und Geometrien Freezable-Objekte. Wenn Sie nicht sicher sind, ob ein Typ ist ein <xref:System.Windows.FrameworkElement> oder ein <xref:System.Windows.Freezable>, finden Sie unter der **Vererbungshierarchie** Abschnitt der Referenzdokumentation.  
  
-   Vornehmen einer <xref:System.Windows.FrameworkElement> ein Animationsziel aus der, Sie benennen Sie es durch Festlegen seiner <xref:System.Windows.FrameworkElement.Name%2A> Eigenschaft. Im Code müssen Sie auch verwenden die <xref:System.Windows.FrameworkElement.RegisterName%2A> Methode, um den Elementnamen mit der Seite registrieren, zu dem er gehört.  
  
-   Vornehmen einer <xref:System.Windows.Freezable> -Objekt in ein Animationsziel aus der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden Sie die [X: Name-Direktive](../../../../docs/framework/xaml-services/x-name-directive.md) einen Namen zuweisen. Im Code verwenden Sie einfach die <xref:System.Windows.FrameworkElement.RegisterName%2A> Methode, um das Objekt mit der Seite zu registrieren, zu dem er gehört.  
  
 Die folgenden Abschnitte, geben Sie ein Beispiel für das Benennen eines Elements in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und Code. Ausführlichere Informationen zum Benennen und Zielgruppenadressierung finden Sie unter der [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
### <a name="applying-and-starting-storyboards"></a>Anwenden und Starten von Storyboards  
 So starten Sie ein Storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], ordnen Sie es mit einer <xref:System.Windows.EventTrigger>. Ein <xref:System.Windows.EventTrigger> ist ein Objekt, das beschreibt, welche Aktionen beim Auftreten eines bestimmten Ereignisses ergreifen soll. Eine dieser Aktionen kann eine <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion, die Sie verwenden, um das Storyboard zu starten. Ereignistrigger ähneln in ihrem Konzept Ereignishandlern, da sie angeben können, wie Ihre Anwendung auf ein bestimmtes Ereignis reagieren soll. Im Gegensatz zu den Ereignishandlern, Ereignistriggern kann vollständig in der beschriebenen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; es ist kein weiterer Code erforderlich.  
  
 Starten einer <xref:System.Windows.Media.Animation.Storyboard> im Code können Sie ein <xref:System.Windows.EventTrigger> , oder verwenden Sie die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode der <xref:System.Windows.Media.Animation.Storyboard> Klasse.  
  
<a name="controllingstoryboards"></a>   
## <a name="interactively-control-a-storyboard"></a>Interaktives Steuern eines Storyboards  
 Im vorherige Beispiel wurde gezeigt, wie das Starten einer <xref:System.Windows.Media.Animation.Storyboard> bei Auftreten eines Ereignisses. Sie können auch interaktiv steuern eine <xref:System.Windows.Media.Animation.Storyboard> nach dem Start: Sie können anhalten, fortsetzen, beenden, auf den Füllzeitraum zu gelangen, suchen und Entfernen der <xref:System.Windows.Media.Animation.Storyboard>. Weitere Informationen und ein Beispiel, das zeigt, wie Sie interaktiv steuern eine <xref:System.Windows.Media.Animation.Storyboard>, finden Sie unter der [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
<a name="fillbehaviorsection"></a>   
## <a name="what-happens-after-an-animation-ends"></a>Was geschieht nach dem Ende einer Animation?  
 Die <xref:System.Windows.Media.Animation.FillBehavior> Eigenschaft gibt an, wie eine Zeitachse verhält, wenn diese endet. Standardmäßig beginnt eine Zeitachse <xref:System.Windows.Media.Animation.ClockState.Filling> wenn er beendet. Eine Animation, <xref:System.Windows.Media.Animation.ClockState.Filling> enthält die endgültige Ausgabe-Wert.  
  
 Die <xref:System.Windows.Media.Animation.DoubleAnimation> im vorherigen Beispiel wird nicht beendet, da seine <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> -Eigenschaftensatz auf <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. Im folgenden Beispiel wird ein Rechteck mithilfe einer ähnlichen Animation animiert. Im Gegensatz zum vorherigen Beispiel der <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> und <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> befinden sich die Eigenschaften dieser Animation die Standardwerte bei. Aus diesem Grund wechselt die Animation innerhalb von fünf Sekunden von 1 auf 0 und hält dann an.  
  
 [!code-xaml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]  
  
 [!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
 [!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]  
  
 Da die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> wurde nicht geändert werden, der Standardwert, also <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, behält die Animation Endwert, 0, wenn diese endet. Aus diesem Grund die <xref:System.Windows.UIElement.Opacity%2A> endet, der das Rechteck bleibt bei 0 nach der Animation. Wenn Sie festlegen, die <xref:System.Windows.UIElement.Opacity%2A> des Rechtecks in einen anderen Wert Code keine Auswirkung hat wird angezeigt, da die Animation immer noch beeinträchtigt die <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft.  
  
 Eine Möglichkeit, die Kontrolle über eine animierte Eigenschaft im Code ist die Verwendung der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode, und geben Sie null für den <xref:System.Windows.Media.Animation.AnimationTimeline> Parameter. Weitere Informationen und ein Beispiel finden Sie unter [legen Sie eine Eigenschaft nach dem Animieren sie mit einem Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
 Beachten Sie Folgendes: Obwohl einem Eigenschaftswert festlegen, die hat eine <xref:System.Windows.Media.Animation.ClockState.Active> oder <xref:System.Windows.Media.Animation.ClockState.Filling> Animation angezeigt wird, keine Auswirkung hat, der Eigenschaftswert ändert. Weitere Informationen finden Sie unter der [Animationen und zeitlichen Steuerung Systemübersicht](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
<a name="databindingAndAnimatingAnimationsSection"></a>   
## <a name="data-binding-and-animating-animations"></a>Datenbindung und Animieren von Animationen  
 Die meisten Animationseigenschaften können Daten gebunden oder animiert werden; Sie können z. B. Animieren der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft von einem <xref:System.Windows.Media.Animation.DoubleAnimation>. Aufgrund der Funktionsweise des Zeitsteuerungssystems verhalten sich datengebundene oder animierte Animationen jedoch nicht wie andere datengebundene oder animierte Objekte. Um ihr Verhalten zu verstehen, sollten sie wissen, was es bedeutet, eine Animation auf eine Eigenschaft anzuwenden.  
  
 Finden Sie im Beispiel im vorherigen Abschnitt wurde gezeigt, wie dem animiert werden soll, die die <xref:System.Windows.UIElement.Opacity%2A> eines Rechtecks. Wenn das Rechteck im vorherigen Beispiel geladen wird, gilt die Ereignisauslöser der <xref:System.Windows.Media.Animation.Storyboard>. Die Zeitsteuerungssystems erstellt eine Kopie der <xref:System.Windows.Media.Animation.Storyboard> und die Animation. Diese Kopien werden gesperrt (schreibgeschützt) und <xref:System.Windows.Media.Animation.Clock> Objekte daraus erstellt werden. Das eigentliche Animieren der Zieleigenschaften erfolgt durch diese Uhren.  
  
 Die Zeitsteuerungssystems erstellt eine Uhr für die <xref:System.Windows.Media.Animation.DoubleAnimation> und wendet sie auf das Objekt und die Eigenschaft, die von angegeben wird die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> von der <xref:System.Windows.Media.Animation.DoubleAnimation>. In diesem Fall gilt die Zeitsteuerungssystems Uhr der <xref:System.Windows.UIElement.Opacity%2A> -Eigenschaft des Objekts mit dem Namen "MyRectangle."  
  
 Obwohl auch für eine Uhr erstellt wird die <xref:System.Windows.Media.Animation.Storyboard>, die Uhr ist nicht auf alle Eigenschaften angewendet. Dieses dient zum zugehörigen untergeordneten Uhr, die Uhr zu steuern, die für erstellt wird die <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 Damit eine Animation Änderungen der Datenbindung und der Animation widerspiegelt, muss die Uhr erneut generiert werden. Uhren werden nicht automatisch neu generiert. Um eine Animation, Änderungen vorzunehmen, wenden Sie erneut an das Storyboard mit einem <xref:System.Windows.Media.Animation.BeginStoryboard> oder <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode. Wenn Sie eine dieser beiden Methoden anwenden, startet die Animation neu. Im Code können Sie die <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> Methode, um im Storyboard zur vorherigen Position zurück.  
  
 Ein Beispiel einer Animation gebunden ist, finden Sie unter [Key Spline Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160011). Weitere Informationen zur Funktionsweise der Animation und zeitlichen finden Sie unter [Animationen und zeitlichen Steuerung Systemübersicht](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
<a name="otherWaysToAnimateSection"></a>   
## <a name="other-ways-to-animate"></a>Andere Möglichkeiten für Animationen  
 Die Beispiele in dieser Übersicht zeigen, wie Animationen mithilfe von Storyboards erstellt werden. Im Code können Sie Animationen auf verschiedenste Weise erstellen. Weitere Informationen finden Sie unter der [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_samples"></a>   
## <a name="animation-samples"></a>Beispiele für Animationen  
 In den folgenden Beispielen sehen Sie, wie Sie Animationen zu Ihren Anwendungen Hinzufügen können.  
  
-   [From, To, and By Animation Target Values Sample (Beispiel für From-, To- und By-Animationszielwerte)](http://go.microsoft.com/fwlink/?LinkID=159988)  
  
     Veranschaulicht verschiedene From, To, By-Einstellungen.  
  
-   [Beispiel zum Verhalten der Animationszeitsteuerung](http://go.microsoft.com/fwlink/?LinkID=159970)  
  
     Zeigt die verschiedenen Möglichkeiten, wie Sie das Zeitsteuerungsverhalten einer Animation steuern können. Dieses Beispiel zeigt auch, wie Sie die Datenbindung für den Zielwert einer Animation durchführen.  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Übersicht über das Animations- und Zeitsteuerungssystem](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)|Beschreibt, wie die Zeitsteuerungssystems verwendet die <xref:System.Windows.Media.Animation.Timeline> und <xref:System.Windows.Media.Animation.Clock> Klassen, die Sie Animationen erstellen können.|  
|[Tipps und Tricks zu Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)|Hier sind hilfreiche Tipps zum Beheben von Problemen mit Animationfen, z.B. Leistungsprobleme aufgelistet.|  
|[Übersicht über benutzerdefinierte Animationen](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)|Beschreibt, wie das Animationssystem mit Keyframes, Animationsklassen oder Pro-Frame-Rückrufen erweitert werden kann.|  
|Übersicht über From/To/By-Animationen|Beschreibt, wie Sie eine Animation erstellen, die zwischen zwei Werten wechselt.|  
|[Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)|Beschreibt das Erstellen einer Animation mit mehreren Zielwerten, einschließlich der Möglichkeit, die Interpolationsmethode zu steuern.|  
|[Beschleunigungsfunktionen](../../../../docs/framework/wpf/graphics-multimedia/easing-functions.md)|Erklärt, wie mathematische Formeln auf die Animationen angewendet werden, um ein realistisches Verhalten, z.B. Sprungeffekte zu erreichen.|  
|[Übersicht über Pfadanimationen](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)|Beschreibt das Verschieben oder Drehen eines Objekts entlang eines komplexen Pfads.|  
|[Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)|Beschreibt Eigenschaftenanimationen mithilfe von Storyboards, lokalen Animationen, Uhren und Pro-Frame-Animationen.|  
|[Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)|Beschreibt, wie Storyboards mit mehreren Zeitachsen zum Erstellen komplexer Animationen verwendet werden.|  
|[Übersicht über Zeitsteuerungsverhalten](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)|Beschreibt die <xref:System.Windows.Media.Animation.Timeline> Typen und Eigenschaften für Animationen.|  
|[Übersicht über Zeitsteuerungsereignisse](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)|Beschreibt die Ereignisse, die auf die <xref:System.Windows.Media.Animation.Timeline> und <xref:System.Windows.Media.Animation.Clock> Objekte zum Ausführen des Codes an Punkten in der Zeitachse, z. B. starten, anhalten, fortsetzen, überspringen oder beenden.|  
|[Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)|Enthält Codebeispiele für die Verwendung von Animationen und Zeitachsen in der Anwendung.|  
|[Clocks How-to Topics (Themen zur Vorgehensweise zu Uhren)](../../../../docs/framework/wpf/graphics-multimedia/clocks-how-to-topics.md)|Enthält Codebeispiele für die Verwendung der <xref:System.Windows.Media.Animation.Clock> Objekten in der Anwendung.|  
|[Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)|Enthält Codebeispiele für die Verwendung von Keyframe-Animationen in Ihrer Anwendung.|  
|[Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)|Enthält Codebeispiele für die Verwendung von Pfadanimationen in Ihrer Anwendung.|  
  
<a name="reference"></a>   
## <a name="reference"></a>Referenz  
 <xref:System.Windows.Media.Animation.Timeline>  
  
 <xref:System.Windows.Media.Animation.Storyboard>  
  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
  
 <xref:System.Windows.Media.Animation.Clock>
