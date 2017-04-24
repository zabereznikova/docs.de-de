---
title: "&#220;bersicht &#252;ber Animationen | Microsoft Docs"
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
  - "Storyboards [WPF], Animationen"
  - "Animationen [WPF], Übersicht"
ms.assetid: bd9ce563-725d-4385-87c9-d7ee38cf79ea
caps.latest.revision: 73
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 73
---
# &#220;bersicht &#252;ber Animationen
<a name="introduction"></a>[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet einen leistungsfähigen Satz von Grafiken und Layout-Funktionen, die Ihnen ermöglichen, attraktive Benutzeroberflächen und ansprechende Dokumente erstellen. Animation kann eine ansprechende Benutzeroberfläche noch spektakuläre und nutzbar machen. Indem Sie einfach eine Hintergrundfarbe animieren oder Anwenden einer animierten <xref:System.Windows.Media.Transform>, Bildschirmübergänge erstellen oder hilfreiche visuelle Hinweise geben.  
  
 Diese Übersicht bietet eine Einführung in die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animations- und Zeitsteuerungssystem. Liegt der Schwerpunkt auf die Animation von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Objekten mithilfe von Storyboards.  

<a name="introducinganimations"></a>   
## <a name="introducing-animations"></a>Einführung in Animationen  
 Eine Animation entsteht, die erstellt wird, durch die rasche Abfolge einer Reihe von Bildern, jeweils ein wenig voneinander unterscheiden. Das Gehirn nimmt die Gruppe von Bildern als eine einzelne sich ändernde Szene wahr. Im Film wird diese Illusion mithilfe einer Kamera, die viele Fotos, oder Frames, pro Sekunde aufzeichnet erstellt. Bei der Wiedergabe der Frames in einem Projektor sieht das Publikum ein bewegtes Bild.  
  
 Animationen auf einem Computer entspricht. Beispielsweise kann ein Programm, das eine Zeichnung eines Rechtecks langsam angezeigt wird wie folgt arbeiten.  
  
-   Das Programm erstellt einen Zeitgeber.  
  
-   Das Programm überprüft den Zeitgeber in festgelegten Intervallen, um festzustellen, wie viel Zeit verstrichen ist.  
  
-   Jedes Mal, das Programm den Zeitgeber prüft, berechnet den aktuellen Wert der Deckkraft für das Rechteck basierend auf wie viel Zeit verstrichen ist.  
  
-   Das Programm wird dann das Rechteck mit dem neuen Wert aktualisiert, und zeichnet es neu.  
  
 Vor dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] mussten Entwickler zum Erstellen und verwalten ihre eigenen Systeme Timing oder spezielle benutzerdefinierte Bibliotheken verwenden.                  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]enthält ein effizientes Zeitsteuerungssystem, die mithilfe von verwaltetem Code verfügbar gemacht wird und [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und Multithreading tief in die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Framework.                  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Animation erleichtert es, Steuerelemente und andere Grafikobjekte zu animieren.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]gesamte Hintergrundarbeit das Verwalten eines Zeitsteuerungssystems und effizienten Neuzeichnen des Bildschirms. Es bietet Timing-Klassen, mit denen Sie den Schwerpunkt auf die Effekte, die Sie erstellen anstatt die Mechanik dieser Effekte erzielen, möchten.                  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Außerdem erleichtert es so erstellen Sie eigene Animationen Verfügbarmachen von Animation Basisklassen, die von denen die Klassen erben können, um benutzerdefinierte Animationen zu erzeugen. Diese benutzerdefinierten Animationen zu viele der Leistungsvorteile des standard-Animationsklassen erhalten.  
  
<a name="thewpftimingsystem"></a>   
## <a name="wpf-property-animation-system"></a>WPF-Eigenschaftssystem Animation  
 Wenn Sie verstehen, dass einige wichtige Konzepte zu den Zeitsteuerungssystem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animationen können einfacher zu verwenden sein. Am wichtigsten ist, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], animieren Sie Objekte, indem Sie Animationen auf ihre einzelnen Eigenschaften anwenden. Zum Beispiel um ein FrameworkElement zu vergrößern, animieren Sie dessen <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften. Um ein Objekt ausgeblendet, animieren Sie dessen <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft.  
  
 Für eine Eigenschaft Animation-Funktionen verfügen müssen sie die folgenden drei Anforderungen erfüllen:  
  
-   Es muss eine Abhängigkeitseigenschaft sein.  
  
-   Er muss zu einer Klasse, die von erbt gehören <xref:System.Windows.DependencyObject> und implementiert die <xref:System.Windows.Media.Animation.IAnimatable> Schnittstelle.  
  
-   Es muss ein kompatibler Animationstyp verfügbar sein. (Wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nicht bereitstellen, können Sie Ihre eigenen erstellen. Finden Sie unter der [Übersicht über benutzerdefinierte Animationen](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md).)  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]enthält viele Objekte mit <xref:System.Windows.Media.Animation.IAnimatable> Eigenschaften. Steuerelemente, z. B. <xref:System.Windows.Controls.Button> und <xref:System.Windows.Controls.TabControl>, sowie <xref:System.Windows.Controls.Panel> und <xref:System.Windows.Shapes.Shape> Objekte erben von <xref:System.Windows.DependencyObject>. Die meisten Eigenschaften werden Abhängigkeitseigenschaften.  
  
 Animationen können fast überall, die Stile und Steuerelementvorlagen enthält. Animationen müssen nicht visual werden; Sie können Objekte animieren, die nicht Teil der Benutzeroberfläche sind, wenn sie die Kriterien erfüllen, die in diesem Abschnitt beschrieben werden.  
  
<a name="storyboardwalkthrough"></a>   
## <a name="example-make-an-element-fade-in-and-out-of-view"></a>Beispiel: Erstellen Sie und Anzeigen Ausblenden eines Elements  
 Dieses Beispiel zeigt, wie Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animation den Wert einer Abhängigkeitseigenschaft zu animieren. Verwendet eine <xref:System.Windows.Media.Animation.DoubleAnimation>, also eine Art von Animation, die generiert <xref:System.Double> Werte zu animieren der <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft eine <xref:System.Windows.Shapes.Rectangle>. Daher die <xref:System.Windows.Shapes.Rectangle> ein-und ausgeblendet.  
  
 Der erste Teil des Beispiels erstellt ein <xref:System.Windows.Shapes.Rectangle> Element. Die folgenden Schritte zeigen, wie eine Animation erstellt und auf des Rechtecks anwenden <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft.  
  
 Das folgende Beispiel zeigt, wie Sie erstellen ein <xref:System.Windows.Shapes.Rectangle> Element in einer <xref:System.Windows.Controls.StackPanel> in XAML.  
  
 [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]  
  
 Das folgende Beispiel zeigt, wie Sie erstellen ein <xref:System.Windows.Shapes.Rectangle> Element in einer <xref:System.Windows.Controls.StackPanel> im Code.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]  
  
<a name="opacity_animation_step1"></a>   
### <a name="part-1-create-a-doubleanimation"></a>Teil 1: Erstellen einer DoubleAnimation  
 Eine Möglichkeit, ein Element ein-und auszublenden, besteht darin, Animieren der <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft. Da die <xref:System.Windows.UIElement.Opacity%2A> -Eigenschaft ist vom Typ <xref:System.Double>, benötigen Sie eine Animation, die double-Werte erzeugt. Ein <xref:System.Windows.Media.Animation.DoubleAnimation> ist eine solche Animation. Ein <xref:System.Windows.Media.Animation.DoubleAnimation> erstellt einen Übergang zwischen zwei double-Werte. Wenn Startwert angeben möchten, legen Sie seine <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> Eigenschaft. Um den Endwert anzugeben, legen Sie seine <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft.  
  
1.  Durchlässigkeitswert `1.0` wird das Objekt transparent und Durchlässigkeitswert `0.0` ist es unsichtbar. To make the animation transition from                                  `1.0` to                                  `0.0` you set its                                  <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> property to                                  `1.0` and its                                  <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> property to                                  `0.0`. Das folgende Beispiel zeigt, wie Sie erstellen ein <xref:System.Windows.Media.Animation.DoubleAnimation> in XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]  
  
     Das folgende Beispiel zeigt, wie Sie erstellen ein <xref:System.Windows.Media.Animation.DoubleAnimation> im Code.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]  
  
2.  Als Nächstes geben Sie einen <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einer Animation gibt an, wie lange der Übergang vom Startwert zum Zielwert dauert. Das folgende Beispiel zeigt, wie Sie festlegen der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> auf fünf Sekunden in XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]  
  
     Das folgende Beispiel zeigt, wie Sie festlegen der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> auf fünf Sekunden im Code.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]  
  
3.  Der obige Code zeigt eine Animation, die von übergeht `1.0` zu `0.0`, wodurch das Zielelement aus transparent vollständig unsichtbar erreicht. Damit das Element Ausblenden nach wieder eingeblendet wird, setzen die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> -Eigenschaft der Animation, `true`. Um die Animation endlos wiederholt wird, legen Sie seine <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> -Eigenschaft <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. Das folgende Beispiel zeigt die Vorgehensweise bei der <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> und <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaften in XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]  
  
     Das folgende Beispiel zeigt die Vorgehensweise bei der <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> und <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaften im Code.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]  
  
<a name="opacity_animation_step2"></a>   
### <a name="part-2-create-a-storyboard"></a>Teil 2: Erstellen Sie ein Storyboard  
 Um eine Animation auf ein Objekt anzuwenden, erstellen Sie eine <xref:System.Windows.Media.Animation.Storyboard> und die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> Eigenschaften zum Angeben des Objekts und die zu animierende Eigenschaft angefügt.  
  
1.  Erstellen der <xref:System.Windows.Media.Animation.Storyboard> und fügen Sie die Animation als untergeordnetes Element hinzu. Das folgende Beispiel zeigt, wie Sie erstellen die <xref:System.Windows.Media.Animation.Storyboard> in XAML.  
  
     <!-- TODO: review snippet reference [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]  -->  
  
     Erstellen der <xref:System.Windows.Media.Animation.Storyboard> im Code deklariert eine <xref:System.Windows.Media.Animation.Storyboard> Variablen auf Klassenebene.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]  
  
     Anschließend initialisieren die <xref:System.Windows.Media.Animation.Storyboard> und fügen Sie die Animation als untergeordnetes Element hinzu.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]  
  
2.  Die <xref:System.Windows.Media.Animation.Storyboard> wissen, wo die Animation angewendet wurde. Verwenden der <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=fullName> angefügte Eigenschaft, um das zu animierende Objekt angeben. Das folgende Beispiel zeigt, wie Sie den Zielnamen der Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimation> auf `MyRectangle` in XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]  
  
     Das folgende Beispiel zeigt, wie Sie den Zielnamen der Festlegen der <xref:System.Windows.Media.Animation.DoubleAnimation> auf `MyRectangle` im Code.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]  
  
3.  Verwenden der <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> angefügte Eigenschaft, um die zu animierende Eigenschaft angeben. Das folgende Beispiel zeigt, wie die Animation konfiguriert ist Ziel der <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft der <xref:System.Windows.Shapes.Rectangle> in XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]  
  
     Das folgende Beispiel zeigt, wie die Animation konfiguriert ist Ziel der <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft der <xref:System.Windows.Shapes.Rectangle> im Code.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]  
  
 Weitere Informationen zu <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> Syntax und zusätzliche Beispiele finden Sie in der [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
<a name="opacity_animation_step3"></a>   
### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>Teil 3 (XAML): Zuordnen des Storyboards zu einem Trigger  
 Die einfachste Möglichkeit, anwenden und Starten einer <xref:System.Windows.Media.Animation.Storyboard> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist die Verwendung ein Ereignistriggers.                          Dieser Abschnitt beschreibt das Zuordnen der <xref:System.Windows.Media.Animation.Storyboard> mit einem Trigger in XAML.  
  
1.  Erstellen einer <xref:System.Windows.Media.Animation.BeginStoryboard> Objekt, und ordnen Sie ihm das Storyboard zu. Ein <xref:System.Windows.Media.Animation.BeginStoryboard> ist ein <xref:System.Windows.TriggerAction> , die angewendet wird, und startet einen <xref:System.Windows.Media.Animation.Storyboard>.  
  
     [!code-xml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]  
  
2.  Erstellen einer <xref:System.Windows.EventTrigger> und Hinzufügen der <xref:System.Windows.Media.Animation.BeginStoryboard> , seine <xref:System.Windows.EventTrigger.Actions%2A> Auflistung. Legen Sie die <xref:System.Windows.EventTrigger.RoutedEvent%2A> Eigenschaft der <xref:System.Windows.EventTrigger> zu den Ereignissen, die Sie starten möchten die <xref:System.Windows.Media.Animation.Storyboard>. (Weitere Informationen zu Routingereignissen finden Sie unter der [Ereignisübersicht weitergeleitet](../../../../docs/framework/wpf/advanced/routed-events-overview.md).)  
  
     [!code-xml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]  
  
3.  Hinzufügen der <xref:System.Windows.EventTrigger> an der <xref:System.Windows.FrameworkElement.Triggers%2A> -Auflistung des Rechtecks.  
  
     [!code-xml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]  
  
<a name="opacity_animation_step3code"></a>   
### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>Teil 3 (Code): Zuordnen des Storyboards zu einem Ereignishandler  
 Die einfachste Möglichkeit, anwenden und Starten einer <xref:System.Windows.Media.Animation.Storyboard> im Code wird einen Ereignishandler verwenden. Dieser Abschnitt beschreibt das Zuordnen der <xref:System.Windows.Media.Animation.Storyboard> mit einem Ereignishandler im Code.  
  
1.  Registrieren Sie sich für die <xref:System.Windows.FrameworkElement.Loaded> -Ereignis des Rechtecks.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]  
  
2.  Deklarieren Sie den Ereignishandler. Verwenden Sie im Ereignishandler, der <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode, um das Storyboard anzuwenden.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_105)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_105)]  
  
### <a name="complete-example"></a>Vollständiges Beispiel  
 Der folgende Code zeigt ein Rechteck zu erstellen, die in XAML ein-und ausgeblendet wird.  
  
 [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml#rectangleopacityfadeexamplexaml)]  
  
 Der folgende Code zeigt ein Rechteck zu erstellen, die im Code ein-und ausgeblendet wird.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode)]  
  
<a name="animationtypes"></a>   
## <a name="animation-types"></a>Animationstypen  
 Da Animationen Eigenschaftswerte generieren, gibt es verschiedene Animationstypen für verschiedene Eigenschaftentypen. Eine Eigenschaft animieren, akzeptiert ein <xref:System.Double>, wie z. B. die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft eines Elements, verwenden Sie eine Animation, erzeugt <xref:System.Double> Werte. Eine Eigenschaft animieren, akzeptiert ein <xref:System.Windows.Point>, verwenden Sie eine Animation, erzeugt <xref:System.Windows.Point> Werte usw.. Aufgrund der Anzahl der verschiedenen Eigenschaftentypen, es gibt mehrere Animationsklassen in der <xref:System.Windows.Media.Animation> Namespace. Glücklicherweise folgen sie eine strenge Benennungskonvention, die es erleichtert, sie zu unterscheiden:  
  
-   \<                         *Typ*> Animation  
  
     Bekannt als "From/To/By" oder "basic" Animation, animieren diese zwischen einem Start- und Ziel-Wert oder durch Hinzufügen eines Offsetwerts zum Startwert.  
  
    -   Um einen Startwert anzugeben, legen Sie die From-Eigenschaft der Animation.  
  
    -   Um einen Endwert angeben möchten, legen Sie die To-Eigenschaft der Animation.  
  
    -   Um einen Offsetwert angeben, legen Sie die Eigenschaft der Animation.  
  
     In den Beispielen in dieser Übersicht verwenden diese Animationen, da sie am einfachsten zu verwenden sind. From/To/By-Animationen werden in der Übersicht über Animationen From/To/By ausführlich beschrieben.  
  
-   \<                         *Typ*> AnimationUsingKeyFrames-Klasse  
  
     Keyframe-Animationen sind leistungsstärker als From/To/By-Animationen, da Sie eine beliebige Anzahl an Zielwerten angeben und sogar die Interpolationsmethode steuern können. Einige Typen können nur mit Keyframe-Animationen animiert werden. Keyframe-Animationen ausführlich beschrieben werden die [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
-   \<                         *Typ*> AnimationUsingPath  
  
     Pfadanimationen können Sie mithilfe eines geometrischen Pfads animierten Werte zu erstellen.  
  
-   \<                         *Typ*> AnimationBase  
  
     Abstrakte Klasse, die animiert, wenn Sie sie implementieren eine <> \</> *Typ*> Wert. Diese Klasse dient als Basisklasse für <> \</> *Typ*> Animation und <> \</> *Typ*> AnimationUsingKeyFrames-Klassen. Sie müssen direkt mit diesen Klassen nur, wenn Sie eigene benutzerdefinierten Animationen erstellen möchten. Verwenden Sie andernfalls eine <> \</> *Typ*> Animation oder KeyFrame<>*Typ*> Animation.  
  
 In den meisten Fällen sollten Sie mithilfe der <> \</> *Typ*> Animation-Klassen, z. B. <xref:System.Windows.Media.Animation.DoubleAnimation> und <xref:System.Windows.Media.Animation.ColorAnimation>.  
  
 Die folgende Tabelle zeigt mehrere allgemeine Animationstypen und einige Eigenschaften, mit denen sie verwendet werden.  
  
|Eigenschaftentyp|Zugehörige Basic (From/To/By) animation|Zugehörige Keyframe-animation|Zugehörige Pfadanimation|Beispiel für die Verwendung|  
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Keine|Animate the                                  <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a                                  <xref:System.Windows.Media.SolidColorBrush> or a                                  <xref:System.Windows.Media.GradientStop>.|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|Animate the                                  <xref:System.Windows.FrameworkElement.Width%2A> of a                                  <xref:System.Windows.Controls.DockPanel> or the                                  <xref:System.Windows.FrameworkElement.Height%2A> of a                                  <xref:System.Windows.Controls.Button>.|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|Animieren der <xref:System.Windows.Media.EllipseGeometry.Center%2A> position ein <xref:System.Windows.Media.EllipseGeometry>.|  
|<xref:System.String>|Keine|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Keine|Animate the                                  <xref:System.Windows.Controls.TextBlock.Text%2A> of a                                  <xref:System.Windows.Controls.TextBlock> or the                                  <xref:System.Windows.Controls.ContentControl.Content%2A> of a                                  <xref:System.Windows.Controls.Button>.|  
  
<a name="animationsaretimelines"></a>   
### <a name="animations-are-timelines"></a>Animationen sind Timeline-Klassen  
 Alle Animationstypen erben von der <xref:System.Windows.Media.Animation.Timeline> -Klasse; daher sind alle Animationen spezialisierte Typen von Zeitplänen. Ein <xref:System.Windows.Media.Animation.Timeline> definiert einen Zeitabschnitt. Sie können angeben, die *Zeitverhalten* einer Zeitachse: seine <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, wie oft es wiederholt wird und sogar wie schnell die Zeit für das Objekt abläuft.  
  
 Da eine Animation eine <xref:System.Windows.Media.Animation.Timeline>, auch einen Zeitabschnitt dar. Berechnet eine Animation auch Ausgabewerte, während ihr Zeitabschnitt Mal durchlaufen (oder <xref:System.Windows.Media.Animation.Timeline.Duration%2A>). Wie die Ausführung der Animation erfolgt, oder "Wiedergabe" wird die Eigenschaft, der zugeordneten aktualisiert.  
  
 Drei häufig verwendete Zeitsteuerungseigenschaften sind <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, und <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>.  
  
#### <a name="the-duration-property"></a>Die Duration-Eigenschaft  
 Wie bereits erwähnt stellt eine Zeitachse einen Zeitabschnitt dar. Die Länge dieses Abschnitts wird anhand der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Zeitachse, die normalerweise mit ist eine <xref:System.Windows.Duration.TimeSpan%2A> Wert. Wenn eine Zeitachse das Ende ihrer Dauer erreicht, hat es eine Iteration abgeschlossen.  
  
 Eine Animation verwendet die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> -Eigenschaft können Sie den aktuellen Wert zu bestimmen. Wenn Sie keinen angeben einer <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Wert für eine Animation Sekunde, was der Standardeinstellung verwendet.  
  
 Die folgende Syntax zeigt eine vereinfachte Version der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Attributsyntax für die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft.  
  
||  
|-|  
|*hours* `:` *minutes* `:` *seconds*|  
  
 Die folgende Tabelle zeigt verschiedene <xref:System.Windows.Duration> Einstellungen und die zugehörigen Werte.  
  
|Einstellung|Ergebniswert|  
|-------------|---------------------|  
|0:0:5.5|Exchange&5;.5 Sekunden.|  
|0:30:5.5|30 Minuten und 5,5 Sekunden.|  
|1:30:5.5|1 Stunde, 30 Minuten und 5,5 Sekunden.|  
  
 Eine Möglichkeit zum Angeben einer <xref:System.Windows.Duration> im Code ist die Verwendung der <xref:System.TimeSpan.FromSeconds%2A> Methode zum Erstellen einer <xref:System.TimeSpan>, deklarieren Sie eine neue <xref:System.Windows.Duration> Struktur verwenden, die <xref:System.TimeSpan>.  
  
 Weitere Informationen zu <xref:System.Windows.Duration> Werte und die vollständige [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Syntax finden Sie unter der <xref:System.Windows.Duration> Struktur.  
  
#### <a name="autoreverse"></a>AutoReverse  
 Die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> -Eigenschaft gibt an, ob eine Zeitachse rückwärts durchlaufen wird, nach des Endes des erreichen seine <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Wenn Sie diese Animationseigenschaft auf `true`, eine Animation kehrt nach des Endes des erreichen seine <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, während der Wiedergabe vom Endwert zum Startwert zurück. Diese Eigenschaft ist standardmäßig `false`.  
  
#### <a name="repeatbehavior"></a>RepeatBehavior  
 Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft gibt an, wie oft eine Zeitachse durchlaufen wird. In der Standardeinstellung von Zeitachsen ist eine Iteration `1.0`, d. h. sie eine Zeit, und nicht wiederholt.  
  
 Weitere Informationen zu diesen und anderen Eigenschaften finden Sie unter der [Übersicht über Zeitsteuerungsverhalten](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md).  
  
<a name="applyanimationstoproperty"></a>   
## <a name="applying-an-animation-to-a-property"></a>Anwenden einer Animation zu einer Eigenschaft  
 In den vorherigen Abschnitten werden die verschiedenen Arten von Animationen und ihre Zeitsteuerungseigenschaften beschrieben. In diesem Abschnitt wird gezeigt, wie die Animation auf die Eigenschaft angewendet, die Sie animieren möchten.                  <xref:System.Windows.Media.Animation.Storyboard> Objekte bieten eine Möglichkeit, Animationen auf Eigenschaften anzuwenden. Ein <xref:System.Windows.Media.Animation.Storyboard> ist ein *Containerzeitachse* , Zielinformationen für die darin enthaltenen Animationen bereitstellt.  
  
### <a name="targeting-objects-and-properties"></a>Zielobjekte und-Eigenschaften  
 Die <xref:System.Windows.Media.Animation.Storyboard> -Klasse stellt die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> angefügte Eigenschaften. Durch Festlegen dieser Eigenschaften für eine Animation, weisen Sie die Animation zu animieren. Allerdings vor eine Animation ein Objekt angewendet werden kann, muss das Objekt in der Regel ein Name zugewiesen werden.  
  
 Ein Name zugewiesen ein <xref:System.Windows.FrameworkElement> unterscheidet sich ein Name zugewiesen ein <xref:System.Windows.Freezable> Objekt. Die meisten Steuerelemente und Bereiche sind Framework-Elemente. Allerdings sind die meisten rein grafische Objekte, z. B. Pinsel, Transformationen und Geometrien freezable-Objekte. Wenn Sie nicht sicher sind, ob ein Typ ist ein <xref:System.Windows.FrameworkElement> oder eine <xref:System.Windows.Freezable>, finden Sie in der **Vererbungshierarchie** Abschnitt der Dokumentation.  
  
-   Vornehmen einer <xref:System.Windows.FrameworkElement> ein Animationsziel, Sie geben sie einen Namen durch Festlegen seiner <xref:System.Windows.FrameworkElement.Name%2A> Eigenschaft. Im Code müssen Sie außerdem verwenden die <xref:System.Windows.FrameworkElement.RegisterName%2A> Methode, um den Elementnamen mit der Seite registrieren, zu der er gehört.  
  
-   Zu einer <xref:System.Windows.Freezable> -Objekt ein Animationsziel in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden Sie die [X: Name-Direktive](../../../../docs/framework/xaml-services/x-name-directive.md) es sich um einen Namen zuzuweisen. Im Code verwenden Sie einfach die <xref:System.Windows.FrameworkElement.RegisterName%2A> Methode, um das Objekt mit der Seite zu registrieren, zu der er gehört.  
  
 Die folgenden Abschnitte enthalten ein Beispiel Benennen eines Elements in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und Code. Ausführlichere Informationen zum Benennen und abzielen, finden Sie unter der [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
### <a name="applying-and-starting-storyboards"></a>Anwenden und Starten von Storyboards  
 So starten Sie ein Storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], ordnen Sie es ein <xref:System.Windows.EventTrigger>. Ein <xref:System.Windows.EventTrigger> ist ein Objekt, das beschreibt, welche Aktionen durchgeführt werden, wenn ein bestimmtes Ereignis auftritt. Eine solche Aktion kann eine <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion, die Sie verwenden, um das Storyboard zu starten. Ereignistrigger ähneln Konzept Ereignishandler da können Sie angeben, wie Ihre Anwendung auf ein bestimmtes Ereignis reagiert. Im Gegensatz zum Ereignishandler Ereignistrigger kann vollständig beschrieben [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; es ist kein weiterer Code erforderlich.  
  
 Starten einer <xref:System.Windows.Media.Animation.Storyboard> im Code können Sie ein <xref:System.Windows.EventTrigger> oder verwenden Sie die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode der <xref:System.Windows.Media.Animation.Storyboard> Klasse.  
  
<a name="controllingstoryboards"></a>   
## <a name="interactively-control-a-storyboard"></a>Interaktives Steuern eines Storyboards  
 Das vorherige Beispiel zeigte Starten einer <xref:System.Windows.Media.Animation.Storyboard> bei Auftreten eines Ereignisses. Sie können auch interaktiv steuern einer <xref:System.Windows.Media.Animation.Storyboard> nach dem Start: Sie können anhalten, fortsetzen, beenden, werden sie zur seines, suchen und Entfernen der <xref:System.Windows.Media.Animation.Storyboard>. Weitere Informationen und ein Beispiel, das zeigt, wie Sie interaktiv steuern einer <xref:System.Windows.Media.Animation.Storyboard>, finden Sie unter der [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
<a name="fillbehaviorsection"></a>   
## <a name="what-happens-after-an-animation-ends"></a>Was geschieht nach dem Ende einer Animation?  
 Die <xref:System.Windows.Media.Animation.FillBehavior> -Eigenschaft gibt das Verhalten am Ende der Zeitachse. Standardmäßig beginnt eine Zeitachse <xref:System.Windows.Media.Animation.ClockState> endet. Eine Animation, <xref:System.Windows.Media.Animation.ClockState> enthält den endgültige Ausgabe-Wert.  
  
 Die <xref:System.Windows.Media.Animation.DoubleAnimation> im vorherigen Beispiel wird nicht beendet, da die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> -Eigenschaft wird festgelegt, um <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. Im folgende Beispiel wird ein Rechteck mithilfe einer ähnlichen Animation animiert. Im Gegensatz zum vorherigen Beispiel ist die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> und <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaften dieser Animation sind Links, die Standardwerte. Aus diesem Grund wird die Animation wechselt von 1 auf 0 innerhalb von fünf Sekunden und hält dann an.  
  
 [!code-xml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]  
  
 [!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
 [!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]  
  
 Da die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> wurde nicht von den Standardwert <xref:System.Windows.Media.Animation.FillBehavior>, behält die Animation Endwert, 0, wenn er beendet wird. Aus diesem Grund die <xref:System.Windows.UIElement.Opacity%2A> der Rechteck bleibt bei 0, nachdem die Animation beendet. Wenn Sie festlegen, die <xref:System.Windows.UIElement.Opacity%2A> des Rechtecks auf einen anderen Wert Code keine Auswirkung hat wird angezeigt, da die Animation immer noch beeinträchtigt wird die <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft.  
  
 Eine Möglichkeit, die Kontrolle über eine animierte Eigenschaft im Code ist die Verwendung der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode und geben Sie null für den <xref:System.Windows.Media.Animation.AnimationTimeline> Parameter. Weitere Informationen und ein Beispiel finden Sie unter [legen Sie eine Eigenschaft nach animieren sie ein Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
 Beachten Sie, dass zwar über einem Eigenschaftswert festlegen, der eine <xref:System.Windows.Media.Animation.ClockState> oder <xref:System.Windows.Media.Animation.ClockState> Animation angezeigt wird, keine Auswirkung hat, den Wert der Eigenschaft ändert. Weitere Informationen finden Sie unter der [Animation and Timing System Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
<a name="databindingAndAnimatingAnimationsSection"></a>   
## <a name="data-binding-and-animating-animations"></a>Bindung und Animieren von Animationen  
 Die meisten Animationseigenschaften können Daten gebunden oder animiert werden; Sie können z. B. Animieren der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft ein <xref:System.Windows.Media.Animation.DoubleAnimation>. Jedoch aufgrund der Funktionsweise des Zeitsteuerungssystems Daten datengebundene oder animierte Animationen nicht wie andere Verhalten gebunden wurde oder animierte Objekte. Um ihr Verhalten zu verstehen, sollten sie wissen, was es bedeutet, eine Animation auf eine Eigenschaft anzuwenden.  
  
 Finden Sie im Beispiel im vorherigen Abschnitt wurde gezeigt, wie Sie animieren, die die <xref:System.Windows.UIElement.Opacity%2A> eines Rechtecks. Ereignistrigger angewendet wird, wenn das Rechteck im vorherigen Beispiel geladen wird, die <xref:System.Windows.Media.Animation.Storyboard>. Das Zeitsteuerungssystem erstellt eine Kopie der <xref:System.Windows.Media.Animation.Storyboard> und die Animation. Diese Kopien werden gesperrt (schreibgeschützt) und <xref:System.Windows.Media.Animation.Clock> Objekte daraus erstellt werden. Das eigentliche Animieren der Zieleigenschaften erfolgt durch diese Uhren.  
  
 Das Zeitsteuerungssystem erstellt eine Uhr für die <xref:System.Windows.Media.Animation.DoubleAnimation> und wendet sie auf das Objekt und die Eigenschaft, die durch angegeben ist die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> von der <xref:System.Windows.Media.Animation.DoubleAnimation>. In diesem Fall gilt das Zeitsteuerungssystem Uhr der <xref:System.Windows.UIElement.Opacity%2A> -Eigenschaft des Objekts mit dem Namen "MyRectangle" angewendet.  
  
 Zwar ebenfalls eine Uhr für erstellt die <xref:System.Windows.Media.Animation.Storyboard>, die Uhr auf Eigenschaften angewendet wird. Sein Zweck besteht darin, seine untergeordneten Uhr, die Uhr zu steuern, die für erstellt wird die <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 Für eine Animation Daten Bindung oder Animation widerzuspiegeln muss die Uhr erneut generiert werden. Uhren werden nicht automatisch neu generiert. Damit eine Animation aktualisiert wird, wenden Sie erneut an das Storyboard mit einer <xref:System.Windows.Media.Animation.BeginStoryboard> oder <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode. Wenn Sie eine dieser Methoden verwenden, startet die Animation neu. Im Code können Sie die <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> Methode, um im Storyboard zur vorherigen Position zurück.  
  
 Ein Beispiel für eine datengebundene Animation finden Sie unter [Key Spline Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160011).                  Weitere Informationen zur Funktionsweise des Animations- und Zeitsteuerungssystem finden Sie unter [Animation and Timing System Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
<a name="otherWaysToAnimateSection"></a>   
## <a name="other-ways-to-animate"></a>Andere Methoden zum Animieren von  
 In den Beispielen in dieser Übersicht wird die Animation von mit Storyboards. Wenn Sie Code verwenden, können Sie auf verschiedene Weise animieren. Weitere Informationen finden Sie unter der [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_samples"></a>   
## <a name="animation-samples"></a>Beispiele für Animationen  
 In den folgenden Beispielen können Sie beim Hinzufügen von Animationen zu einer Anwendung starten.  
  
-   [Aus, To und By Animation Target Values Sample](http://go.microsoft.com/fwlink/?LinkID=159988)  
  
     Veranschaulicht verschiedene From/To/By-Einstellungen.  
  
-   [Animation Timing Behavior Sample](http://go.microsoft.com/fwlink/?LinkID=159970)  
  
     Zeigt die verschiedenen Methoden, die Sie der Zeitsteuerungsverhalten einer Animation steuern können. Dieses Beispiel auch zeigt wie an Daten binden, den Zielwert einer Animation.  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Das Animations- und Zeitsteuerungssystem Systemübersicht](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)|Beschreibt, wie das Zeitsteuerungssystem verwendet die <xref:System.Windows.Media.Animation.Timeline> und <xref:System.Windows.Media.Animation.Clock> Klassen, die Sie beim Erstellen von Animationen ermöglichen.|  
|[Animation-Tipps und Tricks](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)|Listen Sie hilfreiche Tipps zum Beheben von Problemen mit Animationen, z. B. die Leistung.|  
|[Übersicht über benutzerdefinierte Animationen](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)|Beschreibt, wie das Animationssystem mit Keyframes, Animationsklassen oder pro-Frame-Rückrufe zu erweitern.|  
|Übersicht über From/To/By-Animationen|Beschreibt, wie Sie eine Animation erstellen, die zwischen zwei Werten wechselt.|  
|[Übersicht über Keyframe Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)|Beschreibt das Erstellen einer Animation mit mehreren Zielwerten, einschließlich der Möglichkeit, die Interpolationsmethode steuern.|  
|[Beschleunigungsfunktionen](../../../../docs/framework/wpf/graphics-multimedia/easing-functions.md)|Erklärt, wie mathematische Formeln für die Animationen, um realistische Verhalten, z. B. Zurückweisen anwenden.|  
|[Übersicht über Pfadanimationen](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)|Beschreibt das Verschieben oder Drehen eines Objekts entlang eines Pfads komplexer.|  
|[Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)|Beschreibt Eigenschaftenanimationen mit Storyboards, lokalen Animationen, Uhren und pro-Frame-Animationen.|  
|[Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)|Beschreibt, wie Storyboards mit mehreren Zeitachsen zum Erstellen komplexer Animationen.|  
|[Übersicht über Zeitsteuerungsverhalten](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)|Beschreibt die <xref:System.Windows.Media.Animation.Timeline> Typen und Eigenschaften für Animationen.|  
|[Übersicht über Zeitsteuerungsereignisse](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)|Beschreibt die Ereignisse, die auf die <xref:System.Windows.Media.Animation.Timeline> und <xref:System.Windows.Media.Animation.Clock> -Objekte zum Ausführen des Codes an Punkten auf der Zeitachse, z. B. starten, anhalten, fortsetzen, überspringen oder beenden.|  
|[Gewusst-wie-Themen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)|Enthält Codebeispiele für die Verwendung von Animationen und Zeitachsen in der Anwendung.|  
|[Uhren Gewusst-wie-Themen](../../../../docs/framework/wpf/graphics-multimedia/clocks-how-to-topics.md)|Enthält Codebeispiele für die Verwendung der <xref:System.Windows.Media.Animation.Clock> Objekt in der Anwendung.|  
|[Themen zur Keyframe-](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)|Enthält Codebeispiele für die Verwendung von Keyframe-Animationen in Ihrer Anwendung.|  
|[Pfad-Themen zur Pfadanimation](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)|Enthält Codebeispiele für die Verwendung von Pfadanimationen in der Anwendung.|  
  
<a name="reference"></a>   
## <a name="reference"></a>Verweis  
 <xref:System.Windows.Media.Animation.Timeline>  
  
 <xref:System.Windows.Media.Animation.Storyboard>  
  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
  
 <xref:System.Windows.Media.Animation.Clock>