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
ms.openlocfilehash: f0f55c948d10c61ebab57f47e3461531ccf5f610
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559715"
---
# <a name="animation-overview"></a>Übersicht über Animationen

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet einen leistungsstarken Satz an Grafiken und Layoutfeatures, die es Ihnen ermöglichen, attraktive Benutzeroberflächen und ansprechende Dokumente zu erstellen. Animation kann eine ansprechende Benutzeroberfläche noch spektakulärer und benutzerfreundlicher machen. Indem Sie einfach eine Hintergrundfarbe animieren oder einen animierten <xref:System.Windows.Media.Transform>anwenden, können Sie dramatische Bildschirm Übergänge erstellen oder hilfreiche visuelle Hinweise bereitstellen.

Diese Übersicht bietet eine Einführung in das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animations-und Zeit Steuerungssystem. Der Schwerpunkt liegt auf der Animation von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Objekten mithilfe von Storyboards.

<a name="introducinganimations"></a>

## <a name="introducing-animations"></a>Einführung in Animationen

Mit einer Animation wird eine Illusion geschaffen, die durch die rasche Abfolge einer Reihe von Bildern erzeugt wird, wobei jedes Bild sich ein wenig vom vorherigen Bild unterscheidet. Die Abfolge von Bildern wird vom Gehirn als einzelne, sich ändernde Szene wahrgenommen. Im Film wird diese Illusion mithilfe einer Kamera, die viele Fotos, oder Frames, pro Sekunde aufzeichnet, erstellt. Bei der Wiedergabe der Frames in einem Projektor sieht das Publikum ein bewegtes Bild.

Animationen auf einem Computer ist ähnlich. Beispielsweise kann ein Programm, das die Zeichnung eines Rechtecks langsam ausblendet wie folgt arbeiten.

- Das Programm erstellt einen Timer.

- Das Programm überprüft den Timer in festgelegten Intervallen, um festzustellen, wie viel Zeit verstrichen ist.

- Jedes Mal wenn das Programm den Timer prüft, berechnet es den aktuellen Durchsichtigkeitswert für das Rechteck, basierend auf der verstrichenen Zeit.

- Das Programm übernimmt dann den neuen Wert für das Rechteck und zeichnet es neu.

Vor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]mussten Microsoft Windows-Entwickler eigene Zeit Steuerungssysteme erstellen und verwalten oder spezielle benutzerdefinierte Bibliotheken verwenden. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält ein effizientes Zeit Steuerungssystem, das über verwalteten Code verfügbar gemacht wird und [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], das tief in das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Framework integriert ist. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animation ermöglicht es, Steuerelemente und andere Grafikobjekte ganz einfach zu animieren.

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erledigt die gesamte Hintergrundarbeit zum Verwalten eines Zeitsteuerungssystems und zum effizienten Neuzeichnen des Bildschirms. WPF bietet Zeitsteuerungsklassen, die Ihnen ermöglichen, sich auf die Effekte, die Sie erstellen möchten, zu konzentrieren, anstatt auf die technischen Details dieser Effekte. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ermöglicht es außerdem auf einfache Weise eigene Animationen zu erstellen, durch das Bereitstellen von Animationsbasisklassen, von denen Ihre Klassen erben können, um benutzerdefinierte Animationen zu erzeugen. Diese benutzerdefinierten Animationen profitieren von vielen Leistungsvorteilen der Standardanimationsklassen.

<a name="thewpftimingsystem"></a>

## <a name="wpf-property-animation-system"></a>Animationssystem für WPF-Eigenschaften

Wenn Sie ein paar wichtige Konzepte des Zeit Steuerungssystems verstanden haben, können [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animationen leichter zu verwenden sein. Am wichtigsten ist, dass Sie in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Objekte animieren, indem Sie Animationen auf die einzelnen Eigenschaften anwenden. Um z. b. ein FrameworkElement zu vergrößern, animieren Sie dessen <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften. Damit ein Objekt aus der Ansicht ausgeblendet wird, animieren Sie dessen <xref:System.Windows.UIElement.Opacity%2A>-Eigenschaft.

Damit eine Eigenschaft animierbar ist, müssen die folgenden drei Anforderungen erfüllt sein:

- Es muss sich um eine Abhängigkeitseigenschaft handeln.

- Es muss einer Klasse angehören, die von <xref:System.Windows.DependencyObject> erbt und die <xref:System.Windows.Media.Animation.IAnimatable>-Schnittstelle implementiert.

- Es muss ein kompatibler Animationstyp verfügbar sein. (Wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] keinen bereitstellt, können Sie eine eigene erstellen. Weitere Informationen finden Sie unter [Übersicht über benutzerdefinierte Animationen](custom-animations-overview.md).)

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält viele Objekte, die über <xref:System.Windows.Media.Animation.IAnimatable> Eigenschaften verfügen. Steuerelemente wie <xref:System.Windows.Controls.Button> und <xref:System.Windows.Controls.TabControl>sowie <xref:System.Windows.Controls.Panel> und <xref:System.Windows.Shapes.Shape> Objekte erben von <xref:System.Windows.DependencyObject>. Die meisten Eigenschaften sind Abhängigkeitseigenschaften.

Animationen können fast überall verwendet werden, auch in Stil- und Steuerelementvorlagen. Animationen müssen nicht visuell sein; Sie können Objekte animieren, die nicht Teil der Benutzeroberfläche sind, wenn sie die Kriterien erfüllen, die in diesem Abschnitt beschrieben werden.

<a name="storyboardwalkthrough"></a>

## <a name="example-make-an-element-fade-in-and-out-of-view"></a>Beispiel: Ein- und Ausblenden eines Elements

In diesem Beispiel wird gezeigt, wie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animation verwendet wird, um den Wert einer Abhängigkeits Eigenschaft zu animieren. Dabei wird eine <xref:System.Windows.Media.Animation.DoubleAnimation>verwendet, bei der es sich um eine Art von Animation handelt, die <xref:System.Double> Werte generiert, um die <xref:System.Windows.UIElement.Opacity%2A>-Eigenschaft einer <xref:System.Windows.Shapes.Rectangle>zu animieren. Folglich werden die <xref:System.Windows.Shapes.Rectangle> in der Ansicht ausgeblendet.

Im ersten Teil des Beispiels wird ein <xref:System.Windows.Shapes.Rectangle>-Element erstellt. In den folgenden Schritten wird gezeigt, wie eine Animation erstellt und auf die <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft des Rechtecks angewendet wird.

Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Shapes.Rectangle>-Element in einer <xref:System.Windows.Controls.StackPanel> in XAML erstellt wird.

[!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]

Im folgenden wird gezeigt, wie ein <xref:System.Windows.Shapes.Rectangle>-Element in einer <xref:System.Windows.Controls.StackPanel> im Code erstellt wird.

[!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
[!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]

<a name="opacity_animation_step1"></a>

### <a name="part-1-create-a-doubleanimation"></a>Teil 1: Erstellen einer DoubleAnimation

Eine Möglichkeit, ein Element ein-und auszublenden, besteht darin, die <xref:System.Windows.UIElement.Opacity%2A>-Eigenschaft zu animieren. Da die <xref:System.Windows.UIElement.Opacity%2A>-Eigenschaft vom Typ <xref:System.Double>ist, benötigen Sie eine Animation, die doppelte Werte erzeugt. Eine <xref:System.Windows.Media.Animation.DoubleAnimation> ist eine solche Animation. Ein <xref:System.Windows.Media.Animation.DoubleAnimation> der einen Übergang zwischen zwei doppelten Werten erstellt. Legen Sie die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>-Eigenschaft fest, um den Startwert anzugeben. Legen Sie die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-Eigenschaft fest, um den Endwert anzugeben.

1. Bei einem Deckkraft Wert von `1.0` wird das Objekt vollständig nicht transparent, und ein Deckkraft Wert von `0.0` macht ihn vollständig unsichtbar. Damit der Animations Übergang von `1.0` zu `0.0` wird, legen Sie dessen Eigenschaft <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> auf `1.0` und die <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-Eigenschaft auf `0.0`fest. Im folgenden wird gezeigt, wie ein <xref:System.Windows.Media.Animation.DoubleAnimation> in XAML erstellt wird.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]

    Im folgenden wird gezeigt, wie Sie eine <xref:System.Windows.Media.Animation.DoubleAnimation> im Code erstellen.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]

2. Als nächstes müssen Sie einen <xref:System.Windows.Media.Animation.Timeline.Duration%2A>angeben. Der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> einer Animation gibt an, wie lange es dauert, bis der Startwert in seinen Zielwert wechselt. Im folgenden wird gezeigt, wie die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> auf fünf Sekunden in XAML festgelegt wird.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]

    Im folgenden wird gezeigt, wie die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> auf fünf Sekunden im Code festgelegt wird.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]

3. Der vorherige Code hat eine Animation gezeigt, die von `1.0` zu `0.0`übergeht, was bewirkt, dass das Ziel Element von vollständig undurchsichtigem in vollständig unsichtbar wird. Legen Sie die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>-Eigenschaft der Animation auf `true`fest, damit das Element nach dem verschwinden wieder ausgeblendet wird. Legen Sie die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>-Eigenschaft auf <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>fest, damit die Animation unbegrenzt wiederholt wird. Das folgende Beispiel zeigt, wie Sie die Eigenschaften <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> und <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> in XAML festlegen.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]

    Im folgenden wird gezeigt, wie Sie die Eigenschaften <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> und <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> im Code festlegen.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]

<a name="opacity_animation_step2"></a>

### <a name="part-2-create-a-storyboard"></a>Teil 2: Erstellen eines Storyboards

Wenn Sie eine Animation auf ein Objekt anwenden möchten, erstellen Sie eine <xref:System.Windows.Media.Animation.Storyboard> und verwenden die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> angefügten Eigenschaften, um das zu animierende Objekt und die Eigenschaft anzugeben.

1. Erstellen Sie die <xref:System.Windows.Media.Animation.Storyboard>, und fügen Sie die Animation als untergeordnetes Element hinzu. Im folgenden wird gezeigt, wie die <xref:System.Windows.Media.Animation.Storyboard> in XAML erstellt wird.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]

    Um die <xref:System.Windows.Media.Animation.Storyboard> im Code zu erstellen, deklarieren Sie eine <xref:System.Windows.Media.Animation.Storyboard> Variable auf Klassenebene.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]

    Initialisieren Sie dann die <xref:System.Windows.Media.Animation.Storyboard>, und fügen Sie die Animation als untergeordnetes Element hinzu.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]

2. Der <xref:System.Windows.Media.Animation.Storyboard> muss wissen, wo die Animation angewendet werden soll. Verwenden Sie die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> angefügte-Eigenschaft, um das zu animierende Objekt anzugeben. Im folgenden wird gezeigt, wie Sie den Zielnamen der <xref:System.Windows.Media.Animation.DoubleAnimation> auf `MyRectangle` in XAML festlegen.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]

    Im folgenden wird gezeigt, wie der Zielname der <xref:System.Windows.Media.Animation.DoubleAnimation> auf `MyRectangle` im Code festgelegt wird.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]

3. Verwenden Sie die <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> angefügte-Eigenschaft, um die zu animierende Eigenschaft anzugeben. Im folgenden wird gezeigt, wie die Animation so konfiguriert wird, dass Sie die <xref:System.Windows.UIElement.Opacity%2A>-Eigenschaft des <xref:System.Windows.Shapes.Rectangle> in XAML als Ziel hat.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]

    Im folgenden Beispiel wird gezeigt, wie die Animation so konfiguriert wird, dass Sie die <xref:System.Windows.UIElement.Opacity%2A>-Eigenschaft der <xref:System.Windows.Shapes.Rectangle> im Code als Ziel hat.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]

Weitere Informationen zur <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> Syntax und weitere Beispiele finden Sie in der [Übersicht über Storyboards](storyboards-overview.md).

<a name="opacity_animation_step3"></a>

### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>Teil 3 (XAML): Zuordnen des Storyboards zu einem Trigger

Die einfachste Möglichkeit, eine <xref:System.Windows.Media.Animation.Storyboard> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] anzuwenden und zu starten, ist die Verwendung eines Ereignis Auslösers. In diesem Abschnitt wird gezeigt, wie Sie die <xref:System.Windows.Media.Animation.Storyboard> einem-in XAML-Code zuordnen.

1. Erstellen Sie ein <xref:System.Windows.Media.Animation.BeginStoryboard> Objekt, und ordnen Sie es dem Storyboard zu. Ein <xref:System.Windows.Media.Animation.BeginStoryboard> ist ein <xref:System.Windows.TriggerAction>, der einen <xref:System.Windows.Media.Animation.Storyboard>anwendet und startet.

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]

2. Erstellen Sie eine <xref:System.Windows.EventTrigger>, und fügen Sie die <xref:System.Windows.Media.Animation.BeginStoryboard> der <xref:System.Windows.EventTrigger.Actions%2A> Auflistung hinzu. Legen Sie die <xref:System.Windows.EventTrigger.RoutedEvent%2A>-Eigenschaft des <xref:System.Windows.EventTrigger> auf das-Routing Ereignis fest, für das der <xref:System.Windows.Media.Animation.Storyboard>gestartet werden soll. (Weitere Informationen zu Routing Ereignissen finden Sie unter Übersicht über Routing [Ereignisse](../advanced/routed-events-overview.md).)

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]

3. Fügen Sie die <xref:System.Windows.EventTrigger> der <xref:System.Windows.FrameworkElement.Triggers%2A>-Auflistung des Rechtecks hinzu.

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]

<a name="opacity_animation_step3code"></a>

### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>Teil 3 (Code): Zuordnen des Storyboards zu einem Ereignishandler

Die einfachste Möglichkeit, eine <xref:System.Windows.Media.Animation.Storyboard> im Code anzuwenden und zu starten, ist die Verwendung eines Ereignis Handlers. In diesem Abschnitt wird gezeigt, wie Sie die <xref:System.Windows.Media.Animation.Storyboard> einem Ereignishandler im Code zuordnen.

1. Registrieren Sie sich für das <xref:System.Windows.FrameworkElement.Loaded>-Ereignis des Rechtecks.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]

2. Deklarieren Sie den Ereignishandler. Verwenden Sie im-Ereignishandler die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode, um das Storyboard anzuwenden.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_105](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_105)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_105](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_105)]

### <a name="complete-example"></a>Vollständiges Beispiel

Das folgende Beispiel zeigt, wie ein Rechteck erstellt wird, das in XAML ein-und ausgeblendet wird.

[!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml#rectangleopacityfadeexamplexaml)]

Der folgende Code zeigt, wie ein Rechteck erstellt wird, das im Code ein- und ausgeblendet wird.

[!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode)]
[!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode)]

<a name="animationtypes"></a>

## <a name="animation-types"></a>Animationstypen

Da Animationen Eigenschaftswerte generieren, gibt es verschiedene Animationstypen für unterschiedliche Eigenschaftentypen. Verwenden Sie zum Animieren einer Eigenschaft, die eine <xref:System.Double>annimmt, wie z. b. die <xref:System.Windows.FrameworkElement.Width%2A>-Eigenschaft eines Elements, eine Animation, die <xref:System.Double> Werte erzeugt. Verwenden Sie zum Animieren einer Eigenschaft, die einen <xref:System.Windows.Point>annimmt, eine Animation, die <xref:System.Windows.Point> Werte erzeugt, usw. Aufgrund der Anzahl unterschiedlicher Eigenschafts Typen gibt es mehrere Animations Klassen im <xref:System.Windows.Media.Animation>-Namespace. Glücklicherweise folgen sie einer strengen Benennungskonvention, die es erleichtert, sie voneinander zu unterscheiden:

- \<*Type*>Animation

  Bekannt als „From/To/By“ oder „basic“ Animation, laufen die Animationen zwischen einem Start- und Ziel-Wert ab oder durch Hinzufügen eines Offsetwerts zum Startwert.

  - Legen Sie die From-Eigenschaft der Animation fest, um einen Startwert anzugeben.

  - Legen Sie die To-Eigenschaft der Animation fest, um einen Endwert anzugeben.

  - Legen Sie die By-Eigenschaft der Animation fest, um einen Offsetwert anzugeben.

  Die Beispiele in dieser Übersicht verwenden diese Animationen, da sie am einfachsten zu verwenden sind. From/to/by-Animationen werden in der Übersicht über from/to/by-Animationen ausführlich beschrieben.

- \<*Type*>AnimationUsingKeyFrames

  Keyframe-Animationen sind leistungsstärker als From-/To-/By-Animationen, da Sie eine beliebige Anzahl an Zielwerten angeben und sogar die Interpolationsmethode steuern können. Einige Typen können nur mit Keyframe-Animationen animiert werden. Keyframe-Animationen werden in der [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)ausführlich beschrieben.

- \<*Type*>AnimationUsingPath

  Pfadanimationen ermöglichen Ihnen einen geometrischen Pfad zu verwenden, um animierte Werte zu erzeugen.

- \<*Type*>AnimationBase

  Abstrakte Klasse, die einen \<*Typ*>-Wert animiert, wenn Sie implementiert wird. Diese Klasse dient als Basisklasse für \<*Typ*>-Animation und \<*Typ*>AnimationUsingKeyFrames-Klassen. Sie müssen nur dann direkt mit diesen Klassen arbeiten, wenn Sie eigene benutzerdefinierte Animationen erstellen möchten. Verwenden Sie andernfalls eine \<*Typ*>-Animation oder KeyFrame\<*Typ*>-Animation.

In den meisten Fällen empfiehlt es sich, den \<- *Typ*> Animations Klassen wie <xref:System.Windows.Media.Animation.DoubleAnimation> und <xref:System.Windows.Media.Animation.ColorAnimation>zu verwenden.

Die folgende Tabelle zeigt mehrere allgemeine Animationstypen und einige Eigenschaften, mit denen sie verwendet werden.

|Eigenschaftentyp|Zugehörige Basisanimation (From/To/By)|Zugehörige Keyframe-Animation|Zugehörige Pfadanimation|Beispiel für die Verwendung|
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Keine|Animieren des <xref:System.Windows.Media.SolidColorBrush.Color%2A> einer <xref:System.Windows.Media.SolidColorBrush> oder eines <xref:System.Windows.Media.GradientStop>.|
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|Animieren Sie den <xref:System.Windows.FrameworkElement.Width%2A> einer <xref:System.Windows.Controls.DockPanel> oder die <xref:System.Windows.FrameworkElement.Height%2A> einer <xref:System.Windows.Controls.Button>.|
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|Animieren der <xref:System.Windows.Media.EllipseGeometry.Center%2A> Position eines <xref:System.Windows.Media.EllipseGeometry>.|
|<xref:System.String>|Keine|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Keine|Animieren Sie den <xref:System.Windows.Controls.TextBlock.Text%2A> einer <xref:System.Windows.Controls.TextBlock> oder die <xref:System.Windows.Controls.ContentControl.Content%2A> einer <xref:System.Windows.Controls.Button>.|

<a name="animationsaretimelines"></a>

### <a name="animations-are-timelines"></a>Animationen sind Timeline-Klassen

Alle Animations Typen erben von der <xref:System.Windows.Media.Animation.Timeline>-Klasse. Daher sind alle Animationen spezialisierte Typen von Zeitachsen. Ein <xref:System.Windows.Media.Animation.Timeline> der einen Zeitabschnitt definiert. Sie können das *Zeit Steuerungs Verhalten* einer Zeitachse angeben: die <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, die Häufigkeit, mit der es wiederholt wird, und sogar die Geschwindigkeit der Zeit.

Da eine Animation eine <xref:System.Windows.Media.Animation.Timeline>ist, stellt Sie auch einen Zeitabschnitt dar. Eine Animation berechnet auch Ausgabewerte, während Sie das angegebene Zeitsegment (oder <xref:System.Windows.Media.Animation.Timeline.Duration%2A>) durchläuft. Während die Animation durchlaufen oder „abgespielt“ wird, wird die ihr zugeordnete Eigenschaft aktualisiert.

Drei häufig verwendete Zeit Steuerungseigenschaften sind <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>und <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>.

#### <a name="the-duration-property"></a>Duration-Eigenschaft

Wie bereits erwähnt, stellt eine Zeitachse einen Zeitabschnitt dar. Die Länge dieses Segments wird durch den <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Zeitachse bestimmt, der in der Regel mit einem <xref:System.Windows.Duration.TimeSpan%2A> Wert angegeben wird. Wenn eine Zeitachse das Ende ihrer Dauer erreicht, hat sie eine Iteration abgeschlossen.

Eine Animation verwendet die <xref:System.Windows.Media.Animation.Timeline.Duration%2A>-Eigenschaft, um Ihren aktuellen Wert zu bestimmen. Wenn Sie für eine Animation keinen <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Wert angeben, wird eine Sekunde verwendet. Dies ist die Standardeinstellung.

Die folgende Syntax zeigt eine vereinfachte Version der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Attribut Syntax für die <xref:System.Windows.Media.Animation.Timeline.Duration%2A>-Eigenschaft.

*Stunden* `:` *Minuten* `:` *Sekunden*

In der folgenden Tabelle werden mehrere <xref:System.Windows.Duration> Einstellungen und deren resultierende Werte angezeigt.

|-Einstellung|Ergebniswert|
|-------------|---------------------|
|0:0:5.5|5.5 Sekunden.|
|0:30:5.5|30 Minuten und 5,5 Sekunden.|
|1:30:5.5|1 Stunde, 30 Minuten und 5,5 Sekunden.|

Eine Möglichkeit, eine <xref:System.Windows.Duration> im Code anzugeben, besteht darin, die <xref:System.TimeSpan.FromSeconds%2A>-Methode zu verwenden, um eine <xref:System.TimeSpan>zu erstellen, und dann eine neue <xref:System.Windows.Duration> Struktur mithilfe dieses <xref:System.TimeSpan>zu deklarieren.

Weitere Informationen über <xref:System.Windows.Duration> Werte und die gesamte [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Syntax finden Sie in der <xref:System.Windows.Duration>-Struktur.

#### <a name="autoreverse"></a>AutoReverse

Die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>-Eigenschaft gibt an, ob eine Zeitachse rückwärts abgespielt wird, nachdem Sie das Ende der <xref:System.Windows.Media.Animation.Timeline.Duration%2A>erreicht hat. Wenn Sie diese Animations Eigenschaft auf `true`festlegen, kehrt eine Animation wieder her, nachdem Sie das Ende der <xref:System.Windows.Media.Animation.Timeline.Duration%2A>erreicht hat, wobei der Endwert wieder auf den Startwert zurückgesetzt wird. Standardmäßig ist diese Eigenschaft `false`.

#### <a name="repeatbehavior"></a>RepeatBehavior

Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>-Eigenschaft gibt an, wie oft eine Zeitachse abgespielt wird. Standardmäßig haben Zeitachsen eine Iterations Anzahl von `1.0`. Dies bedeutet, dass Sie einmal abgespielt werden und nicht wiederholt werden.

Weitere Informationen zu diesen Eigenschaften und anderen Eigenschaften finden Sie unter [Übersicht über Zeit Steuerungs Verhalten](timing-behaviors-overview.md).

<a name="applyanimationstoproperty"></a>

## <a name="applying-an-animation-to-a-property"></a>Anwenden einer Animation auf eine Eigenschaft

Die vorhergehenden Abschnitte beschreiben die verschiedenen Arten von Animationen und ihre Zeitsteuerungseigenschaften. In diesem Abschnitt wird gezeigt, wie Sie die Animation auf die zu animierende Eigenschaft anwenden. <xref:System.Windows.Media.Animation.Storyboard>-Objekte bieten eine Möglichkeit, Animationen auf Eigenschaften anzuwenden. Eine <xref:System.Windows.Media.Animation.Storyboard> ist eine *Container Zeitachse* , die Ziel Informationen für die darin enthaltenen Animationen bereitstellt.

### <a name="targeting-objects-and-properties"></a>Zielobjekte und -Eigenschaften

Die <xref:System.Windows.Media.Animation.Storyboard>-Klasse stellt die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und die <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> angefügten Eigenschaften bereit. Durch Festlegen dieser Eigenschaften wird der Animation mitgeteilt, was animiert werden soll. Bevor eine Animation jedoch auf ein Objekt angewendet werden kann, muss dem Objekt in der Regel ein Name gegeben werden.

Das Zuweisen eines Namens zu einem <xref:System.Windows.FrameworkElement> unterscheidet sich vom Zuweisen eines Namens zu einem <xref:System.Windows.Freezable> Objekt. Die meisten Steuerelemente und Bereiche sind Frameworkelemente; hingegen sind die meisten rein grafischen Objekte, z.B. Pinsel, Transformationen und Geometrien Freezable-Objekte. Wenn Sie nicht sicher sind, ob ein Typ ein <xref:System.Windows.FrameworkElement> oder ein <xref:System.Windows.Freezable>ist, lesen Sie den Abschnitt **Vererbungs Hierarchie** in der zugehörigen Referenz Dokumentation.

- Wenn Sie einen <xref:System.Windows.FrameworkElement> einem Animations Ziel erstellen möchten, geben Sie ihm einen Namen, indem Sie dessen <xref:System.Windows.FrameworkElement.Name%2A>-Eigenschaft festlegen. Im Code müssen Sie auch die <xref:System.Windows.FrameworkElement.RegisterName%2A>-Methode verwenden, um den Elementnamen mit der Seite zu registrieren, zu der er gehört.

- Wenn Sie ein <xref:System.Windows.Freezable> Objekt in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]als Animations Ziel festlegen möchten, verwenden Sie die [x:Name-Direktive](../../../desktop-wpf/xaml-services/xname-directive.md) , um ihm einen Namen zuzuweisen. Im Code verwenden Sie einfach die <xref:System.Windows.FrameworkElement.RegisterName%2A>-Methode, um das Objekt bei der Seite zu registrieren, zu der es gehört.

In den folgenden Abschnitten wird ein Beispiel für das Benennen eines Elements in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und Code bereitgestellt. Ausführlichere Informationen zum Benennen und zum Ziel finden Sie in der [Übersicht über Storyboards](storyboards-overview.md).

### <a name="applying-and-starting-storyboards"></a>Anwenden und Starten von Storyboards

Um ein Storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]zu starten, verknüpfen Sie es mit einem <xref:System.Windows.EventTrigger>. Ein <xref:System.Windows.EventTrigger> ist ein Objekt, das beschreibt, welche Aktionen ausgeführt werden sollen, wenn ein bestimmtes Ereignis eintritt. Eine dieser Aktionen kann eine <xref:System.Windows.Media.Animation.BeginStoryboard> Aktion sein, die Sie verwenden, um das Storyboard zu starten. Ereignistrigger ähneln in ihrem Konzept Ereignishandlern, da sie angeben können, wie Ihre Anwendung auf ein bestimmtes Ereignis reagieren soll. Im Gegensatz zu Ereignis Handlern können Ereignis Trigger vollständig in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]beschrieben werden. Es ist kein weiterer Code erforderlich.

Um eine <xref:System.Windows.Media.Animation.Storyboard> im Code zu starten, können Sie eine <xref:System.Windows.EventTrigger> verwenden oder die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode der <xref:System.Windows.Media.Animation.Storyboard>-Klasse verwenden.

<a name="controllingstoryboards"></a>

## <a name="interactively-control-a-storyboard"></a>Interaktives Steuern eines Storyboards

Im vorherigen Beispiel wurde gezeigt, wie ein <xref:System.Windows.Media.Animation.Storyboard> gestartet wird, wenn ein Ereignis auftritt. Sie können eine <xref:System.Windows.Media.Animation.Storyboard> auch interaktiv steuern, nachdem Sie gestartet wurde: Sie können die <xref:System.Windows.Media.Animation.Storyboard>anhalten, fortsetzen, anhalten, Sie in den Füllzeitraum verschieben, suchen und entfernen. Weitere Informationen und ein Beispiel, das zeigt, wie eine <xref:System.Windows.Media.Animation.Storyboard>interaktiv gesteuert werden kann, finden Sie in der [Übersicht über Storyboards](storyboards-overview.md).

<a name="fillbehaviorsection"></a>

## <a name="what-happens-after-an-animation-ends"></a>Was geschieht nach dem Ende einer Animation?

Die <xref:System.Windows.Media.Animation.FillBehavior>-Eigenschaft gibt an, wie sich eine Zeitachse beim Ende verhält. Standardmäßig beginnt eine Zeitachse <xref:System.Windows.Media.Animation.ClockState.Filling>, wenn Sie endet. Eine Animation, die <xref:System.Windows.Media.Animation.ClockState.Filling> ist, enthält ihren endgültigen Ausgabewert.

Die <xref:System.Windows.Media.Animation.DoubleAnimation> im vorherigen Beispiel endet nicht, da die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>-Eigenschaft auf <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>festgelegt ist. Im folgenden Beispiel wird ein Rechteck mithilfe einer ähnlichen Animation animiert. Im Gegensatz zum vorherigen Beispiel werden die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>-und <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaften dieser Animation mit ihren Standardwerten belassen. Aus diesem Grund wechselt die Animation innerhalb von fünf Sekunden von 1 auf 0 und hält dann an.

[!code-xaml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]

[!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
[!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]

Da der zugehörige <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> nicht von seinem Standardwert geändert wurde (<xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>), behält die Animation den endgültigen Wert 0, wenn Sie endet. Daher bleibt die <xref:System.Windows.UIElement.Opacity%2A> des Rechtecks nach Ende der Animation bei 0. Wenn Sie die <xref:System.Windows.UIElement.Opacity%2A> des Rechtecks auf einen anderen Wert festlegen, scheint der Code keine Auswirkung zu haben, da die Animation weiterhin die <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft beeinflusst.

Eine Möglichkeit, eine animierte Eigenschaft im Code wieder zu steuern, besteht darin, die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>-Methode zu verwenden und NULL für den <xref:System.Windows.Media.Animation.AnimationTimeline>-Parameter anzugeben. Weitere Informationen und ein Beispiel finden Sie unter [Festlegen einer Eigenschaft nach dem Animieren mit einem Storyboard](how-to-set-a-property-after-animating-it-with-a-storyboard.md).

Beachten Sie Folgendes: Obwohl das Festlegen eines Eigenschafts Werts, der über eine <xref:System.Windows.Media.Animation.ClockState.Active>-oder <xref:System.Windows.Media.Animation.ClockState.Filling> Animation verfügt, keine Auswirkung hat, ändert sich der Eigenschafts Wert. Weitere Informationen finden Sie unter [Übersicht über das Animations-und Zeit Steuerungssystem](animation-and-timing-system-overview.md).

<a name="databindingAndAnimatingAnimationsSection"></a>

## <a name="data-binding-and-animating-animations"></a>Datenbindung und Animieren von Animationen

Die meisten Animations Eigenschaften können Daten gebunden oder animiert sein. Beispielsweise können Sie die <xref:System.Windows.Media.Animation.Timeline.Duration%2A>-Eigenschaft einer <xref:System.Windows.Media.Animation.DoubleAnimation>animieren. Aufgrund der Funktionsweise des Zeitsteuerungssystems verhalten sich datengebundene oder animierte Animationen jedoch nicht wie andere datengebundene oder animierte Objekte. Um ihr Verhalten zu verstehen, sollten sie wissen, was es bedeutet, eine Animation auf eine Eigenschaft anzuwenden.

Lesen Sie das Beispiel im vorherigen Abschnitt, in dem gezeigt wurde, wie die <xref:System.Windows.UIElement.Opacity%2A> eines Rechtecks animiert werden. Wenn das Rechteck im vorherigen Beispiel geladen wurde, wendet der Ereignis--Auslösung den <xref:System.Windows.Media.Animation.Storyboard>an. Das Zeit Steuerungssystem erstellt eine Kopie der <xref:System.Windows.Media.Animation.Storyboard> und der zugehörigen Animation. Diese Kopien sind fixiert (schreibgeschützt) und <xref:System.Windows.Media.Animation.Clock> Objekte erstellt werden. Das eigentliche Animieren der Zieleigenschaften erfolgt durch diese Uhren.

Das Zeit Steuerungssystem erstellt eine Uhr für die <xref:System.Windows.Media.Animation.DoubleAnimation> und wendet Sie auf das Objekt und die Eigenschaft an, die durch die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> der <xref:System.Windows.Media.Animation.DoubleAnimation>angegeben werden. In diesem Fall wendet das Zeit Steuerungssystem die Uhr auf die <xref:System.Windows.UIElement.Opacity%2A>-Eigenschaft des Objekts mit dem Namen "myrechteck" an.

Obwohl eine Uhr auch für die <xref:System.Windows.Media.Animation.Storyboard>erstellt wird, wird die Uhr nicht auf Eigenschaften angewendet. Der Zweck besteht darin, die untergeordnete Uhr zu steuern, die Uhr, die für die <xref:System.Windows.Media.Animation.DoubleAnimation>erstellt wird.

Damit eine Animation Änderungen der Datenbindung und der Animation widerspiegelt, muss die Uhr erneut generiert werden. Uhren werden nicht automatisch neu generiert. Um eine Animation widerzuspiegeln, wenden Sie das Storyboard erneut an, indem Sie eine <xref:System.Windows.Media.Animation.BeginStoryboard> oder die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>-Methode verwenden. Wenn Sie eine dieser beiden Methoden anwenden, startet die Animation neu. Im Code können Sie die <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>-Methode verwenden, um das Storyboard zurück zur vorherigen Position zu verschieben.

Ein Beispiel für eine Daten gebundene Animation finden Sie unter Beispiel für eine [KeySpline-Animation](https://go.microsoft.com/fwlink/?LinkID=160011). Weitere Informationen zur Funktionsweise des Animations-und Zeit Steuerungssystems finden Sie unter Übersicht über das [Animations-und Zeit Steuerungssystem](animation-and-timing-system-overview.md).

<a name="otherWaysToAnimateSection"></a>

## <a name="other-ways-to-animate"></a>Andere Möglichkeiten für Animationen

Die Beispiele in dieser Übersicht zeigen, wie Animationen mithilfe von Storyboards erstellt werden. Im Code können Sie Animationen auf verschiedenste Weise erstellen. Weitere Informationen finden Sie in der [Übersicht über die Eigenschaften Animationstechniken](property-animation-techniques-overview.md).

<a name="animation_samples"></a>

## <a name="animation-samples"></a>Beispiele für Animationen

In den folgenden Beispielen sehen Sie, wie Sie Animationen zu Ihren Anwendungen Hinzufügen können.

- [Beispiel für From-, To- und By-Animationszielwerte](https://go.microsoft.com/fwlink/?LinkID=159988)

  Veranschaulicht verschiedene From, To, By-Einstellungen.

- [Beispiel zum Verhalten der Animationszeitsteuerung](https://go.microsoft.com/fwlink/?LinkID=159970)

  Zeigt die verschiedenen Möglichkeiten, wie Sie das Zeitsteuerungsverhalten einer Animation steuern können. Dieses Beispiel zeigt auch, wie Sie die Datenbindung für den Zielwert einer Animation durchführen.

<a name="related_topics"></a>

## <a name="related-topics"></a>Verwandte Themen

|Title|Beschreibung|
|-----------|-----------------|
|[Übersicht über das Animations- und Zeitsteuerungssystem](animation-and-timing-system-overview.md)|Beschreibt, wie das Zeit Steuerungssystem die Klassen <xref:System.Windows.Media.Animation.Timeline> und <xref:System.Windows.Media.Animation.Clock> verwendet, mit denen Sie Animationen erstellen können.|
|[Tipps und Tricks zu Animationen](animation-tips-and-tricks.md)|Hier sind hilfreiche Tipps zum Beheben von Problemen mit Animationfen, z.B. Leistungsprobleme aufgelistet.|
|[Übersicht über benutzerdefinierte Animationen](custom-animations-overview.md)|Beschreibt, wie das Animationssystem mit Keyframes, Animationsklassen oder Pro-Frame-Rückrufen erweitert werden kann.|
|[Übersicht über From/To/By-Animationen](from-to-by-animations-overview.md)|Beschreibt, wie Sie eine Animation erstellen, die zwischen zwei Werten wechselt.|
|[Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)|Beschreibt das Erstellen einer Animation mit mehreren Zielwerten, einschließlich der Möglichkeit, die Interpolationsmethode zu steuern.|
|[Beschleunigungsfunktionen](easing-functions.md)|Erklärt, wie mathematische Formeln auf die Animationen angewendet werden, um ein realistisches Verhalten, z.B. Sprungeffekte zu erreichen.|
|[Übersicht über Pfadanimationen](path-animations-overview.md)|Beschreibt das Verschieben oder Drehen eines Objekts entlang eines komplexen Pfads.|
|[Übersicht über die Verfahren zur Animation von Eigenschaften](property-animation-techniques-overview.md)|Beschreibt Eigenschaftenanimationen mithilfe von Storyboards, lokalen Animationen, Uhren und Pro-Frame-Animationen.|
|[Übersicht über Storyboards](storyboards-overview.md)|Beschreibt, wie Storyboards mit mehreren Zeitachsen zum Erstellen komplexer Animationen verwendet werden.|
|[Übersicht über Zeitsteuerungsverhalten](timing-behaviors-overview.md)|Beschreibt die <xref:System.Windows.Media.Animation.Timeline> Typen und Eigenschaften, die in Animationen verwendet werden.|
|[Übersicht über Zeitsteuerungsereignisse](timing-events-overview.md)|Beschreibt die Ereignisse, die auf dem <xref:System.Windows.Media.Animation.Timeline> und <xref:System.Windows.Media.Animation.Clock> Objekten zum Ausführen von Code an Punkten in der Zeitachse verfügbar sind, wie z. b. Begin, Pause, Resume, Skip oder Break.|
|[Gewusst wie-Themen](animation-and-timing-how-to-topics.md)|Enthält Codebeispiele für die Verwendung von Animationen und Zeitachsen in der Anwendung.|
|[Clocks How-to Topics (Themen zur Vorgehensweise zu Uhren)](clocks-how-to-topics.md)|Enthält Codebeispiele für die Verwendung des <xref:System.Windows.Media.Animation.Clock>-Objekts in der Anwendung.|
|[Gewusst-wie-Themen zu Keyframes](key-frame-animation-how-to-topics.md)|Enthält Codebeispiele für die Verwendung von Keyframe-Animationen in Ihrer Anwendung.|
|[Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)](path-animation-how-to-topics.md)|Enthält Codebeispiele für die Verwendung von Pfadanimationen in Ihrer Anwendung.|

<a name="reference"></a>

## <a name="reference"></a>Referenz

- <xref:System.Windows.Media.Animation.Timeline>

- <xref:System.Windows.Media.Animation.Storyboard>

- <xref:System.Windows.Media.Animation.BeginStoryboard>

- <xref:System.Windows.Media.Animation.Clock>
