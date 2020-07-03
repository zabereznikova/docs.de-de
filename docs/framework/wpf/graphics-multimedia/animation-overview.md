---
title: Übersicht über Animationen
description: Sorgen Sie für eine ansprechende Benutzeroberfläche mit dramatischen Bildschirm Übergängen oder lebhaften visuellen Hinweisen in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], animations
- animations [WPF], overview
ms.assetid: bd9ce563-725d-4385-87c9-d7ee38cf79ea
ms.openlocfilehash: d761be0c95fb8aa7eb39cb26b57979185226b8fb
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853860"
---
# <a name="animation-overview"></a>Übersicht über Animationen

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet eine Vielzahl leistungsstarker Grafik- und Layout-Funktionen, die Ihnen ermöglichen, attraktive Benutzeroberflächen und ansprechende Dokumente zu erstellen. Animation kann eine ansprechende Benutzeroberfläche noch spektakulärer und benutzerfreundlicher machen. Indem Sie einfach eine Hintergrundfarbe animieren oder einen animierten anwenden <xref:System.Windows.Media.Transform> , können Sie dramatische Bildschirm Übergänge erstellen oder hilfreiche visuelle Hinweise bereitstellen.

Diese Übersicht bietet eine Einführung in das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Animations-und Zeit Steuerungssystem. Der Schwerpunkt liegt auf der Animation von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Objekten mithilfe von Storyboards.

<a name="introducinganimations"></a>

## <a name="introducing-animations"></a>Einführung in Animationen

Mit einer Animation wird eine Illusion geschaffen, die durch die rasche Abfolge einer Reihe von Bildern erzeugt wird, wobei jedes Bild sich ein wenig vom vorherigen Bild unterscheidet. Die Abfolge von Bildern wird vom Gehirn als einzelne, sich ändernde Szene wahrgenommen. Im Film wird diese Illusion mithilfe einer Kamera, die viele Fotos, oder Frames, pro Sekunde aufzeichnet, erstellt. Bei der Wiedergabe der Frames in einem Projektor sieht das Publikum ein bewegtes Bild.

Animationen auf einem Computer ist ähnlich. Beispielsweise kann ein Programm, das die Zeichnung eines Rechtecks langsam ausblendet wie folgt arbeiten.

- Das Programm erstellt einen Timer.

- Das Programm überprüft den Timer in festgelegten Intervallen, um festzustellen, wie viel Zeit verstrichen ist.

- Jedes Mal wenn das Programm den Timer prüft, berechnet es den aktuellen Durchsichtigkeitswert für das Rechteck, basierend auf der verstrichenen Zeit.

- Das Programm übernimmt dann den neuen Wert für das Rechteck und zeichnet es neu.

Vor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mussten Microsoft Windows-Entwickler eigene Zeit Steuerungssysteme erstellen und verwalten oder spezielle benutzerdefinierte Bibliotheken verwenden. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]enthält ein effizientes Zeit Steuerungssystem, das über verwalteten Code verfügbar gemacht wird und [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] das tief in das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Framework integriert ist. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Animation ermöglicht es, Steuerelemente und andere Grafikobjekte ganz einfach zu animieren.

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erledigt die gesamte Hintergrundarbeit zum Verwalten eines Zeitsteuerungssystems und zum effizienten Neuzeichnen des Bildschirms. WPF bietet Zeitsteuerungsklassen, die Ihnen ermöglichen, sich auf die Effekte, die Sie erstellen möchten, zu konzentrieren, anstatt auf die technischen Details dieser Effekte. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ermöglicht es außerdem auf einfache Weise eigene Animationen zu erstellen, durch das Bereitstellen von Animationsbasisklassen, von denen Ihre Klassen erben können, um benutzerdefinierte Animationen zu erzeugen. Diese benutzerdefinierten Animationen profitieren von vielen Leistungsvorteilen der Standardanimationsklassen.

<a name="thewpftimingsystem"></a>

## <a name="wpf-property-animation-system"></a>Animationssystem für WPF-Eigenschaften

Wenn Sie ein paar wichtige Konzepte des Zeit Steuerungssystems verstanden haben, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Animationen einfacher zu verwenden sein. Am wichtigsten ist, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Sie in Objekte animieren, indem Sie Animationen auf die einzelnen Eigenschaften anwenden. Um z. b. ein FrameworkElement zu vergrößern, animieren Sie dessen <xref:System.Windows.FrameworkElement.Width%2A> -und- <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften. Damit ein Objekt aus der Ansicht ausgeblendet wird, animieren Sie seine- <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft.

Damit eine Eigenschaft animierbar ist, müssen die folgenden drei Anforderungen erfüllt sein:

- Es muss sich um eine Abhängigkeitseigenschaft handeln.

- Es muss einer Klasse angehören, die von erbt <xref:System.Windows.DependencyObject> und die- <xref:System.Windows.Media.Animation.IAnimatable> Schnittstelle implementiert.

- Es muss ein kompatibler Animationstyp verfügbar sein. (Wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kein solches bereitgestellt wird, können Sie eine eigene erstellen. Weitere Informationen finden Sie unter [Übersicht über benutzerdefinierte Animationen](custom-animations-overview.md).)

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]enthält viele-Objekte, die über <xref:System.Windows.Media.Animation.IAnimatable> Eigenschaften verfügen. Steuerelemente wie <xref:System.Windows.Controls.Button> und sowie- <xref:System.Windows.Controls.TabControl> <xref:System.Windows.Controls.Panel> und- <xref:System.Windows.Shapes.Shape> Objekte erben von <xref:System.Windows.DependencyObject> . Die meisten Eigenschaften sind Abhängigkeitseigenschaften.

Animationen können fast überall verwendet werden, auch in Stil- und Steuerelementvorlagen. Animationen müssen nicht visuell sein; Sie können Objekte animieren, die nicht Teil der Benutzeroberfläche sind, wenn sie die Kriterien erfüllen, die in diesem Abschnitt beschrieben werden.

<a name="storyboardwalkthrough"></a>

## <a name="example-make-an-element-fade-in-and-out-of-view"></a>Beispiel: Ein- und Ausblenden eines Elements

In diesem Beispiel wird gezeigt, wie eine Animation verwendet wird [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , um den Wert einer Abhängigkeits Eigenschaft zu animieren. Es wird ein verwendet <xref:System.Windows.Media.Animation.DoubleAnimation> , bei dem es sich um einen Typ von Animation handelt, der <xref:System.Double> Werte generiert, um die- <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft eines zu animieren <xref:System.Windows.Shapes.Rectangle> . Folglich werden die <xref:System.Windows.Shapes.Rectangle> in und aus der Ansicht ausgeblendet.

Im ersten Teil des Beispiels wird ein- <xref:System.Windows.Shapes.Rectangle> Element erstellt. In den folgenden Schritten wird gezeigt, wie eine Animation erstellt und auf die-Eigenschaft des Rechtecks angewendet wird <xref:System.Windows.UIElement.Opacity%2A> .

Das folgende Beispiel zeigt, wie ein- <xref:System.Windows.Shapes.Rectangle> Element in einem-Element <xref:System.Windows.Controls.StackPanel> in XAML erstellt wird.

[!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]

Das folgende Beispiel zeigt, wie ein- <xref:System.Windows.Shapes.Rectangle> Element in einem-Element <xref:System.Windows.Controls.StackPanel> in Code erstellt wird.

[!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
[!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]

<a name="opacity_animation_step1"></a>

### <a name="part-1-create-a-doubleanimation"></a>Teil 1: Erstellen einer DoubleAnimation

Eine Möglichkeit, ein Element ein-und auszublenden, besteht darin, seine- <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft zu animieren. Da die- <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft vom Typ ist <xref:System.Double> , benötigen Sie eine Animation, die doppelte Werte erzeugt. Eine <xref:System.Windows.Media.Animation.DoubleAnimation> ist eine solche Animation. Ein- <xref:System.Windows.Media.Animation.DoubleAnimation> Wert erstellt einen Übergang zwischen zwei Double-Werten. Legen Sie die zugehörige-Eigenschaft fest, um den Startwert anzugeben <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> . Zum Angeben des Endwerts legen Sie die zugehörige- <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Eigenschaft fest.

1. Durch einen Deckkraft Wert von wird `1.0` das Objekt vollständig nicht transparent, und durch einen Deckkraft Wert von `0.0` wird es vollständig unsichtbar. `1.0` `0.0` Legen Sie die <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> -Eigenschaft auf `1.0` und die-Eigenschaft auf fest <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> `0.0` , um den Animations Übergang von zu vorzunehmen. Im folgenden wird gezeigt, wie ein <xref:System.Windows.Media.Animation.DoubleAnimation> in XAML erstellt wird.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]

    Im folgenden wird gezeigt, wie Sie eine <xref:System.Windows.Media.Animation.DoubleAnimation> im Code erstellen.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]

2. Als nächstes müssen Sie ein angeben <xref:System.Windows.Media.Animation.Timeline.Duration%2A> . Der einer <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Animation gibt an, wie lange es dauert, bis von seinem Startwert zum Zielwert wechselt. Im folgenden wird gezeigt, wie <xref:System.Windows.Media.Animation.Timeline.Duration%2A> in XAML auf fünf Sekunden festgelegt wird.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]

    Im folgenden wird gezeigt, wie <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Sie den auf fünf Sekunden im Code festlegen.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]

3. Der vorherige Code zeigte eine Animation, die von `1.0` zu übergeht `0.0` , wodurch das Ziel Element von vollständig undurchsichtigem in vollständig unsichtbar wird. Legen Sie die- <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft der Animation auf fest, damit das Element nach dem verschwinden wieder in die Ansicht zurückgesetzt wird `true` . Legen Sie die-Eigenschaft auf fest, damit die Animation unbegrenzt wiederholt wird <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> . Im folgenden wird gezeigt, wie die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaften und in XAML festgelegt werden.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]

    Im folgenden wird gezeigt, wie Sie die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> -Eigenschaft und die-Eigenschaft <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> im Code festlegen.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]

<a name="opacity_animation_step2"></a>

### <a name="part-2-create-a-storyboard"></a>Teil 2: Erstellen eines Storyboards

Wenn Sie eine Animation auf ein Objekt anwenden möchten, erstellen Sie eine <xref:System.Windows.Media.Animation.Storyboard> und verwenden die <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> angefügten Eigenschaften und, um das zu animierende Objekt und die Eigenschaft anzugeben.

1. Erstellen Sie den, <xref:System.Windows.Media.Animation.Storyboard> und fügen Sie die Animation als untergeordnetes Element hinzu. Im folgenden wird gezeigt, wie Sie <xref:System.Windows.Media.Animation.Storyboard> in XAML erstellen.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]

    Um den <xref:System.Windows.Media.Animation.Storyboard> im Code zu erstellen, deklarieren Sie eine <xref:System.Windows.Media.Animation.Storyboard> Variable auf Klassenebene.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]

    Initialisieren Sie dann das, <xref:System.Windows.Media.Animation.Storyboard> und fügen Sie die Animation als untergeordnetes Element hinzu.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]

2. Der <xref:System.Windows.Media.Animation.Storyboard> muss wissen, wo die Animation angewendet werden soll. Mit der <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> angefügten-Eigenschaft geben Sie das zu animierende Objekt an. Im folgenden wird gezeigt, wie der Zielname von <xref:System.Windows.Media.Animation.DoubleAnimation> `MyRectangle` in XAML auf festgelegt wird.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]

    Im folgenden Beispiel wird gezeigt, wie der Zielname von <xref:System.Windows.Media.Animation.DoubleAnimation> im Code auf festgelegt wird `MyRectangle` .

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]

3. Verwenden <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> Sie die angefügte-Eigenschaft zum Angeben der zu animierende Eigenschaft. Im folgenden Beispiel wird gezeigt, wie die Animation so konfiguriert wird, dass Sie auf die- <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft von <xref:System.Windows.Shapes.Rectangle> in XAML ausgerichtet ist.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]

    Im folgenden wird gezeigt, wie die Animation so konfiguriert wird, dass Sie auf die- <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft von <xref:System.Windows.Shapes.Rectangle> im Code ausgerichtet ist.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]

Weitere Informationen zur <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> Syntax und weitere Beispiele finden Sie in der [Übersicht über Storyboards](storyboards-overview.md).

<a name="opacity_animation_step3"></a>

### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>Teil 3 (XAML): Zuordnen des Storyboards zu einem Trigger

Die einfachste Möglichkeit, ein in anzuwenden und zu starten, <xref:System.Windows.Media.Animation.Storyboard> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist die Verwendung eines Ereignis Auslösers. In diesem Abschnitt wird gezeigt, wie Sie den <xref:System.Windows.Media.Animation.Storyboard> mit einem--in XAML-Code verknüpfen.

1. Erstellen <xref:System.Windows.Media.Animation.BeginStoryboard> Sie ein-Objekt, und ordnen Sie es dem Storyboard zu. Ein <xref:System.Windows.Media.Animation.BeginStoryboard> ist ein Typ von <xref:System.Windows.TriggerAction> , der angewendet wird und eine startet <xref:System.Windows.Media.Animation.Storyboard> .

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]

2. Erstellen <xref:System.Windows.EventTrigger> Sie ein, und fügen Sie der Auflistung hinzu <xref:System.Windows.Media.Animation.BeginStoryboard> <xref:System.Windows.EventTrigger.Actions%2A> . Legen Sie die- <xref:System.Windows.EventTrigger.RoutedEvent%2A> Eigenschaft von <xref:System.Windows.EventTrigger> auf das-Routing Ereignis fest, das Sie starten möchten <xref:System.Windows.Media.Animation.Storyboard> . (Weitere Informationen zu Routing Ereignissen finden Sie unter Übersicht über Routing [Ereignisse](../advanced/routed-events-overview.md).)

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]

3. Fügen Sie der-Auflistung <xref:System.Windows.EventTrigger> <xref:System.Windows.FrameworkElement.Triggers%2A> des Rechtecks hinzu.

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]

<a name="opacity_animation_step3code"></a>

### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>Teil 3 (Code): Zuordnen des Storyboards zu einem Ereignishandler

Die einfachste Möglichkeit, ein im Code anzuwenden und zu starten <xref:System.Windows.Media.Animation.Storyboard> , ist die Verwendung eines Ereignis Handlers. In diesem Abschnitt wird gezeigt, wie der <xref:System.Windows.Media.Animation.Storyboard> einem Ereignishandler im Code zugeordnet wird.

1. Registrieren Sie sich für das- <xref:System.Windows.FrameworkElement.Loaded> Ereignis des Rechtecks.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]

2. Deklarieren Sie den Ereignishandler. Verwenden Sie im-Ereignishandler die- <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode, um das Storyboard anzuwenden.

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

Da Animationen Eigenschaftswerte generieren, gibt es verschiedene Animationstypen für unterschiedliche Eigenschaftentypen. Verwenden Sie zum Animieren einer Eigenschaft, die einen annimmt <xref:System.Double> , wie z. b. die- <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft eines Elements, eine Animation, die <xref:System.Double> Werte erzeugt. Verwenden Sie zum Animieren einer Eigenschaft, die einen annimmt, <xref:System.Windows.Point> eine Animation, die <xref:System.Windows.Point> Werte erzeugt, usw. Aufgrund der Anzahl unterschiedlicher Eigenschafts Typen gibt es mehrere Animations Klassen im- <xref:System.Windows.Media.Animation> Namespace. Glücklicherweise folgen sie einer strengen Benennungskonvention, die es erleichtert, sie voneinander zu unterscheiden:

- \<*Type*>Animation

  Bekannt als „From/To/By“ oder „basic“ Animation, laufen die Animationen zwischen einem Start- und Ziel-Wert ab oder durch Hinzufügen eines Offsetwerts zum Startwert.

  - Legen Sie die From-Eigenschaft der Animation fest, um einen Startwert anzugeben.

  - Legen Sie die To-Eigenschaft der Animation fest, um einen Endwert anzugeben.

  - Legen Sie die By-Eigenschaft der Animation fest, um einen Offsetwert anzugeben.

  Die Beispiele in dieser Übersicht verwenden diese Animationen, da sie am einfachsten zu verwenden sind. From/to/by-Animationen werden in der Übersicht über from/to/by-Animationen ausführlich beschrieben.

- \<*Type*>AnimationUsingKeyFrames

  Keyframe-Animationen sind leistungsstärker als From-/To-/By-Animationen, da Sie eine beliebige Anzahl an Zielwerten angeben und sogar die Interpolationsmethode steuern können. Einige Typen können nur mit Keyframe-Animationen animiert werden. Keyframe-Animationen werden in der [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)ausführlich beschrieben.

- \<*Type*>Animationusingpath

  Pfadanimationen ermöglichen Ihnen einen geometrischen Pfad zu verwenden, um animierte Werte zu erzeugen.

- \<*Type*>AnimationBase

  Eine abstrakte Klasse, die bei der Implementierung einen-Wert animiert \<*Type*> . Diese Klasse dient als Basisklasse für die \<*Type*> Klassen Animation und \<*Type*> AnimationUsingKeyFrames. Sie müssen nur dann direkt mit diesen Klassen arbeiten, wenn Sie eigene benutzerdefinierte Animationen erstellen möchten. Verwenden Sie andernfalls eine \<*Type*> Animation oder Keyframe- \<*Type*> Animation.

In den meisten Fällen möchten Sie die \<*Type*> Animations Klassen verwenden, wie z. b <xref:System.Windows.Media.Animation.DoubleAnimation> <xref:System.Windows.Media.Animation.ColorAnimation> . und.

Die folgende Tabelle zeigt mehrere allgemeine Animationstypen und einige Eigenschaften, mit denen sie verwendet werden.

|Eigenschaftstyp|Zugehörige Basisanimation (From/To/By)|Zugehörige Keyframe-Animation|Zugehörige Pfadanimation|Verwendungsbeispiel|
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Keine|Animieren <xref:System.Windows.Media.SolidColorBrush.Color%2A> von einem <xref:System.Windows.Media.SolidColorBrush> oder einem <xref:System.Windows.Media.GradientStop> .|
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|Animieren eines-oder eines-oder eines- <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Controls.Button> .|
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|Animieren der <xref:System.Windows.Media.EllipseGeometry.Center%2A> Position eines <xref:System.Windows.Media.EllipseGeometry> .|
|<xref:System.String>|Keine|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Keine|Animieren eines-oder eines-oder eines- <xref:System.Windows.Controls.TextBlock.Text%2A> <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.ContentControl.Content%2A> <xref:System.Windows.Controls.Button> .|

<a name="animationsaretimelines"></a>

### <a name="animations-are-timelines"></a>Animationen sind Timeline-Klassen

Alle Animations Typen erben von der- <xref:System.Windows.Media.Animation.Timeline> Klasse. Daher sind alle Animationen spezialisierte Typen von Zeitachsen. Eine <xref:System.Windows.Media.Animation.Timeline> definiert einen Zeitabschnitt. Sie können das *Zeit Steuerungs Verhalten* einer Zeitachse angeben <xref:System.Windows.Media.Animation.Timeline.Duration%2A> , wie oft Sie wiederholt wird und sogar wie schnell die Zeit für die Zeitspanne ist.

Da eine Animation eine ist <xref:System.Windows.Media.Animation.Timeline> , stellt Sie auch einen Zeitabschnitt dar. Eine Animation berechnet auch Ausgabewerte, während Sie das angegebene Zeitsegment (oder) durchläuft <xref:System.Windows.Media.Animation.Timeline.Duration%2A> . Während die Animation durchlaufen oder „abgespielt“ wird, wird die ihr zugeordnete Eigenschaft aktualisiert.

Drei häufig verwendete Zeit Steuerungseigenschaften sind <xref:System.Windows.Media.Animation.Timeline.Duration%2A> , <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> und <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> .

#### <a name="the-duration-property"></a>Duration-Eigenschaft

Wie bereits erwähnt, stellt eine Zeitachse einen Zeitabschnitt dar. Die Länge dieses Segments wird durch die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> der Zeitachse bestimmt, die normalerweise mithilfe eines-Werts angegeben wird <xref:System.Windows.Duration.TimeSpan%2A> . Wenn eine Zeitachse das Ende ihrer Dauer erreicht, hat sie eine Iteration abgeschlossen.

Eine Animation verwendet die- <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft, um Ihren aktuellen Wert zu bestimmen. Wenn Sie keinen <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Wert für eine Animation angeben, wird 1 Sekunde verwendet. Dies ist die Standardeinstellung.

Die folgende Syntax zeigt eine vereinfachte Version der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Attribut Syntax für die- <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft.

*Stunden* `:` *Minuten* `:` *Sekunden*

In der folgenden Tabelle werden mehrere <xref:System.Windows.Duration> Einstellungen und deren resultierende Werte angezeigt.

|Einstellung|Ergebniswert|
|-------------|---------------------|
|0:0:5.5|5.5 Sekunden.|
|0:30:5.5|30 Minuten und 5,5 Sekunden.|
|1:30:5.5|1 Stunde, 30 Minuten und 5,5 Sekunden.|

Eine Möglichkeit, ein <xref:System.Windows.Duration> im Code anzugeben, ist die Verwendung der- <xref:System.TimeSpan.FromSeconds%2A> Methode, um eine zu erstellen <xref:System.TimeSpan> , und anschließend eine neue- <xref:System.Windows.Duration> Struktur mit dieser zu deklarieren <xref:System.TimeSpan> .

Weitere Informationen zu <xref:System.Windows.Duration> -Werten und der kompletten [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Syntax finden Sie in der- <xref:System.Windows.Duration> Struktur.

#### <a name="autoreverse"></a>AutoReverse

Die- <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft gibt an, ob eine Zeitachse rückwärts abgespielt wird, nachdem Sie das Ende der erreicht hat <xref:System.Windows.Media.Animation.Timeline.Duration%2A> . Wenn Sie diese Animations Eigenschaft auf festlegen `true` , kehrt eine Animation wieder her, nachdem Sie das Ende der erreicht <xref:System.Windows.Media.Animation.Timeline.Duration%2A> hat, wobei der Endwert wieder auf den Startwert zurückgesetzt wird. Standardmäßig ist diese Eigenschaft `false` .

#### <a name="repeatbehavior"></a>RepeatBehavior

Die- <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft gibt an, wie oft eine Zeitachse abgespielt wird. Standardmäßig haben Zeitachsen eine Iterations Anzahl von `1.0` , was bedeutet, dass Sie einmalig wiedergegeben werden und nicht wiederholt werden.

Weitere Informationen zu diesen Eigenschaften und anderen Eigenschaften finden Sie unter [Übersicht über Zeit Steuerungs Verhalten](timing-behaviors-overview.md).

<a name="applyanimationstoproperty"></a>

## <a name="applying-an-animation-to-a-property"></a>Anwenden einer Animation auf eine Eigenschaft

Die vorhergehenden Abschnitte beschreiben die verschiedenen Arten von Animationen und ihre Zeitsteuerungseigenschaften. In diesem Abschnitt wird gezeigt, wie Sie die Animation auf die zu animierende Eigenschaft anwenden. <xref:System.Windows.Media.Animation.Storyboard>-Objekte bieten eine Möglichkeit, Animationen auf Eigenschaften anzuwenden. Ein <xref:System.Windows.Media.Animation.Storyboard> ist eine *Container Zeitachse* , die Ziel Informationen für die darin enthaltenen Animationen bereitstellt.

### <a name="targeting-objects-and-properties"></a>Zielobjekte und -Eigenschaften

Die <xref:System.Windows.Media.Animation.Storyboard> -Klasse stellt <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> die <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> angefügten Eigenschaften und bereit. Durch Festlegen dieser Eigenschaften wird der Animation mitgeteilt, was animiert werden soll. Bevor eine Animation jedoch auf ein Objekt angewendet werden kann, muss dem Objekt in der Regel ein Name gegeben werden.

Das Zuweisen eines Namens zu einem unter <xref:System.Windows.FrameworkElement> scheidet sich vom Zuweisen eines Namens zu einem- <xref:System.Windows.Freezable> Objekt. Die meisten Steuerelemente und Bereiche sind Frameworkelemente; hingegen sind die meisten rein grafischen Objekte, z.B. Pinsel, Transformationen und Geometrien Freezable-Objekte. Wenn Sie nicht sicher sind, ob ein Typ ein <xref:System.Windows.FrameworkElement> oder ein ist <xref:System.Windows.Freezable> , lesen Sie den Abschnitt **Vererbungs Hierarchie** in der zugehörigen Referenz Dokumentation.

- <xref:System.Windows.FrameworkElement>Wenn Sie ein Animations Ziel erstellen möchten, geben Sie ihm einen Namen, indem Sie die zugehörige- <xref:System.Windows.FrameworkElement.Name%2A> Eigenschaft festlegen. Im Code müssen Sie auch die- <xref:System.Windows.FrameworkElement.RegisterName%2A> Methode verwenden, um den Elementnamen mit der Seite zu registrieren, zu der er gehört.

- Um ein- <xref:System.Windows.Freezable> Objekt zu einem Animations Ziel in zu machen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , verwenden Sie die [x:Name-Direktive](../../../desktop-wpf/xaml-services/xname-directive.md) , um ihm einen Namen zuzuweisen. Im Code verwenden Sie einfach die- <xref:System.Windows.FrameworkElement.RegisterName%2A> Methode, um das Objekt mit der Seite zu registrieren, zu der es gehört.

In den folgenden Abschnitten wird ein Beispiel für das Benennen eines Elements in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -und-Code bereitgestellt. Ausführlichere Informationen zum Benennen und zum Ziel finden Sie in der [Übersicht über Storyboards](storyboards-overview.md).

### <a name="applying-and-starting-storyboards"></a>Anwenden und Starten von Storyboards

Um ein Storyboard in zu starten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , verknüpfen Sie es mit einem <xref:System.Windows.EventTrigger> . Ein <xref:System.Windows.EventTrigger> ist ein Objekt, das beschreibt, welche Aktionen ausgeführt werden sollen, wenn ein bestimmtes Ereignis auftritt. Eine dieser Aktionen kann eine Aktion sein <xref:System.Windows.Media.Animation.BeginStoryboard> , die Sie verwenden, um das Storyboard zu starten. Ereignistrigger ähneln in ihrem Konzept Ereignishandlern, da sie angeben können, wie Ihre Anwendung auf ein bestimmtes Ereignis reagieren soll. Im Gegensatz zu Ereignis Handlern können Ereignis Trigger vollständig in beschrieben werden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . es ist kein anderer Code erforderlich.

<xref:System.Windows.Media.Animation.Storyboard>Wenn Sie ein im Code starten möchten, können Sie ein <xref:System.Windows.EventTrigger> oder die- <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode der-Klasse verwenden <xref:System.Windows.Media.Animation.Storyboard> .

<a name="controllingstoryboards"></a>

## <a name="interactively-control-a-storyboard"></a>Interaktives Steuern eines Storyboards

Im vorherigen Beispiel wurde gezeigt, wie ein gestartet wird, <xref:System.Windows.Media.Animation.Storyboard> Wenn ein Ereignis auftritt. Sie können eine auch nach dem <xref:System.Windows.Media.Animation.Storyboard> Start interaktiv steuern: Sie können Sie anhalten, fortsetzen, anhalten, in den Füllzeitraum verschieben, suchen und entfernen <xref:System.Windows.Media.Animation.Storyboard> . Weitere Informationen und ein Beispiel, das zeigt, wie eine interaktiv gesteuert <xref:System.Windows.Media.Animation.Storyboard> werden kann, finden Sie in der [Übersicht über Storyboards](storyboards-overview.md).

<a name="fillbehaviorsection"></a>

## <a name="what-happens-after-an-animation-ends"></a>Was geschieht nach dem Ende einer Animation?

Die- <xref:System.Windows.Media.Animation.FillBehavior> Eigenschaft gibt an, wie sich eine Zeitachse beim Ende verhält. Standardmäßig beginnt eine Zeitachse, <xref:System.Windows.Media.Animation.ClockState.Filling> Wenn Sie endet. Eine Animation, die <xref:System.Windows.Media.Animation.ClockState.Filling> den endgültigen Ausgabewert enthält.

Der <xref:System.Windows.Media.Animation.DoubleAnimation> im vorherigen Beispiel endet nicht, da seine- <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft auf festgelegt ist <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> . Im folgenden Beispiel wird ein Rechteck mithilfe einer ähnlichen Animation animiert. Im Gegensatz zum vorherigen Beispiel <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> verbleiben die-Eigenschaft und die-Eigenschaft <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> dieser Animation ihren Standardwerten. Aus diesem Grund wechselt die Animation innerhalb von fünf Sekunden von 1 auf 0 und hält dann an.

[!code-xaml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]

[!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
[!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]

Da deren <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Standardwert nicht geändert wurde, d <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> . h., die Animation enthält den endgültigen Wert 0, wenn Sie endet. Daher bleibt der <xref:System.Windows.UIElement.Opacity%2A> des Rechtecks nach Ende der Animation bei 0. Wenn Sie den <xref:System.Windows.UIElement.Opacity%2A> des Rechtecks auf einen anderen Wert festlegen, scheint der Code keine Auswirkung zu haben, da die Animation weiterhin die <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft beeinträchtigt.

Eine Möglichkeit, eine animierte Eigenschaft im Code wieder zu steuern, besteht darin, die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> -Methode zu verwenden und NULL für den- <xref:System.Windows.Media.Animation.AnimationTimeline> Parameter anzugeben. Weitere Informationen und ein Beispiel finden Sie unter [Festlegen einer Eigenschaft nach dem Animieren mit einem Storyboard](how-to-set-a-property-after-animating-it-with-a-storyboard.md).

Beachten Sie Folgendes: Obwohl das Festlegen eines Eigenschafts Werts <xref:System.Windows.Media.Animation.ClockState.Active> mit einer-oder- <xref:System.Windows.Media.Animation.ClockState.Filling> Animation keine Auswirkung hat, ändert sich der-Eigenschafts Wert. Weitere Informationen finden Sie unter [Übersicht über das Animations-und Zeit Steuerungssystem](animation-and-timing-system-overview.md).

<a name="databindingAndAnimatingAnimationsSection"></a>

## <a name="data-binding-and-animating-animations"></a>Datenbindung und Animieren von Animationen

Die meisten Animations Eigenschaften können Daten gebunden oder animiert sein. Beispielsweise können Sie die- <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft eines animieren <xref:System.Windows.Media.Animation.DoubleAnimation> . Aufgrund der Funktionsweise des Zeitsteuerungssystems verhalten sich datengebundene oder animierte Animationen jedoch nicht wie andere datengebundene oder animierte Objekte. Um ihr Verhalten zu verstehen, sollten sie wissen, was es bedeutet, eine Animation auf eine Eigenschaft anzuwenden.

Informationen zum Animieren eines Rechtecks finden Sie im Beispiel im vorherigen Abschnitt <xref:System.Windows.UIElement.Opacity%2A> . Wenn das Rechteck im vorherigen Beispiel geladen wurde, wendet der zugehörige Ereignis--Auslösung den an <xref:System.Windows.Media.Animation.Storyboard> . Das Zeit Steuerungssystem erstellt eine Kopie von <xref:System.Windows.Media.Animation.Storyboard> und der zugehörigen Animation. Diese Kopien sind fixiert (schreibgeschützt), und <xref:System.Windows.Media.Animation.Clock> Objekte werden daraus erstellt. Das eigentliche Animieren der Zieleigenschaften erfolgt durch diese Uhren.

Das Zeit Steuerungssystem erstellt eine Uhr für die <xref:System.Windows.Media.Animation.DoubleAnimation> und wendet Sie auf das Objekt und die Eigenschaft an, die vom <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> und der angegeben werden <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> <xref:System.Windows.Media.Animation.DoubleAnimation> . In diesem Fall wendet das Zeit Steuerungssystem die Uhr auf die- <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft des Objekts mit dem Namen "myrechteck" an.

Obwohl eine Uhr auch für den erstellt wird <xref:System.Windows.Media.Animation.Storyboard> , wird die Uhr nicht auf Eigenschaften angewendet. Der Zweck besteht darin, die untergeordnete Uhr zu steuern, die Uhr, die für die erstellt wird <xref:System.Windows.Media.Animation.DoubleAnimation> .

Damit eine Animation Änderungen der Datenbindung und der Animation widerspiegelt, muss die Uhr erneut generiert werden. Uhren werden nicht automatisch neu generiert. Um eine Animation widerzuspiegeln, wenden Sie das Storyboard erneut an, indem Sie <xref:System.Windows.Media.Animation.BeginStoryboard> die-Methode oder die- <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode verwenden. Wenn Sie eine dieser beiden Methoden anwenden, startet die Animation neu. Im Code können Sie die- <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> Methode verwenden, um das Storyboard zurück zur vorherigen Position zu verschieben.

Ein Beispiel für eine Daten gebundene Animation finden Sie unter Beispiel für eine [KeySpline-Animation](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/KeySplineAnimations). Weitere Informationen zur Funktionsweise des Animations-und Zeit Steuerungssystems finden Sie unter Übersicht über das [Animations-und Zeit Steuerungssystem](animation-and-timing-system-overview.md).

<a name="otherWaysToAnimateSection"></a>

## <a name="other-ways-to-animate"></a>Andere Möglichkeiten für Animationen

Die Beispiele in dieser Übersicht zeigen, wie Animationen mithilfe von Storyboards erstellt werden. Im Code können Sie Animationen auf verschiedenste Weise erstellen. Weitere Informationen finden Sie in der [Übersicht über die Eigenschaften Animationstechniken](property-animation-techniques-overview.md).

<a name="animation_samples"></a>

## <a name="animation-samples"></a>Beispiele für Animationen

In den folgenden Beispielen sehen Sie, wie Sie Animationen zu Ihren Anwendungen Hinzufügen können.

- [Beispiel für From-, To- und By-Animationszielwerte](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)

  Veranschaulicht verschiedene From, To, By-Einstellungen.

- [Beispiel zum Verhalten der Animationszeitsteuerung](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)

  Zeigt die verschiedenen Möglichkeiten, wie Sie das Zeitsteuerungsverhalten einer Animation steuern können. Dieses Beispiel zeigt auch, wie Sie die Datenbindung für den Zielwert einer Animation durchführen.

<a name="related_topics"></a>

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[Übersicht über das Animations- und Zeitsteuerungssystem](animation-and-timing-system-overview.md)|Beschreibt, wie das Zeit Steuerungssystem die <xref:System.Windows.Media.Animation.Timeline> -Klasse und die- <xref:System.Windows.Media.Animation.Clock> Klasse verwendet, die das Erstellen von Animationen ermöglichen.|
|[Tipps und Tricks zu Animationen](animation-tips-and-tricks.md)|Hier sind hilfreiche Tipps zum Beheben von Problemen mit Animationfen, z.B. Leistungsprobleme aufgelistet.|
|[Übersicht über benutzerdefinierte Animationen](custom-animations-overview.md)|Beschreibt, wie das Animationssystem mit Keyframes, Animationsklassen oder Pro-Frame-Rückrufen erweitert werden kann.|
|[Übersicht über From/To/By-Animationen](from-to-by-animations-overview.md)|Beschreibt, wie Sie eine Animation erstellen, die zwischen zwei Werten wechselt.|
|[Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)|Beschreibt das Erstellen einer Animation mit mehreren Zielwerten, einschließlich der Möglichkeit, die Interpolationsmethode zu steuern.|
|[Beschleunigungsfunktionen](easing-functions.md)|Erklärt, wie mathematische Formeln auf die Animationen angewendet werden, um ein realistisches Verhalten, z.B. Sprungeffekte zu erreichen.|
|[Übersicht über Pfadanimationen](path-animations-overview.md)|Beschreibt das Verschieben oder Drehen eines Objekts entlang eines komplexen Pfads.|
|[Übersicht über die Verfahren zur Animation von Eigenschaften](property-animation-techniques-overview.md)|Beschreibt Eigenschaftenanimationen mithilfe von Storyboards, lokalen Animationen, Uhren und Pro-Frame-Animationen.|
|[Übersicht über Storyboards](storyboards-overview.md)|Beschreibt, wie Storyboards mit mehreren Zeitachsen zum Erstellen komplexer Animationen verwendet werden.|
|[Übersicht über Zeitsteuerungsverhalten](timing-behaviors-overview.md)|Beschreibt die <xref:System.Windows.Media.Animation.Timeline> Typen und Eigenschaften, die in Animationen verwendet werden.|
|[Übersicht über Zeitsteuerungsereignisse](timing-events-overview.md)|Beschreibt die Ereignisse <xref:System.Windows.Media.Animation.Timeline> , die für das-Objekt und das- <xref:System.Windows.Media.Animation.Clock> Objekt zum Ausführen von Code an Punkten in der Zeitachse verfügbar sind, z. b. Begin, Pause, Resume, Skip oder Break|
|[Artikel zu Vorgehensweisen](animation-and-timing-how-to-topics.md)|Enthält Codebeispiele für die Verwendung von Animationen und Zeitachsen in der Anwendung.|
|[Gewusst-wie-Themen zu Uhren](clocks-how-to-topics.md)|Enthält Codebeispiele für die Verwendung des- <xref:System.Windows.Media.Animation.Clock> Objekts in der Anwendung.|
|[Themen zur Vorgehensweise mit Keyframes](key-frame-animation-how-to-topics.md)|Enthält Codebeispiele für die Verwendung von Keyframe-Animationen in Ihrer Anwendung.|
|[Gewusst-wie-Themen zur Pfadanimation](path-animation-how-to-topics.md)|Enthält Codebeispiele für die Verwendung von Pfadanimationen in Ihrer Anwendung.|

<a name="reference"></a>

## <a name="reference"></a>Verweis

- <xref:System.Windows.Media.Animation.Timeline>

- <xref:System.Windows.Media.Animation.Storyboard>

- <xref:System.Windows.Media.Animation.BeginStoryboard>

- <xref:System.Windows.Media.Animation.Clock>
