---
title: Erstellen einer Vorlage in WPF - .NET Desktop
description: Erfahren Sie, wie Sie eine Steuerelementvorlage in Windows Presentation Foundation und .NET Core erstellen und darauf verweisen.
author: thraka
ms.author: adegeo
ms.date: 11/15/2019
no-loc:
- <Window>
- <ControlTemplate>
- <Ellipse>
- <ContentPresenter>
- <Trigger>
- <Setter>
- <PropertyTrigger>
- <Grid>
- <VisualStateManager.VisualStateGroups>
- <VisualStateGroup>
- <VisualState>
- <Storyboard>
- SizeToContent
- MinWidth
- TargetType
- Title
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.openlocfilehash: c901864d387b8de976bbfa9a9b3c14a7d5a0b4d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "81432539"
---
# <a name="create-a-template-for-a-control"></a>Erstellen einer Vorlage für ein Steuerelement

Mit Windows Presentation Foundation (WPF) können Sie die visuelle Struktur und das Verhalten eines vorhandenen Steuerelements mit Einer eigenen wiederverwendbaren Vorlage anpassen. Vorlagen können global auf Ihre Anwendung, Fenster und Seiten oder direkt auf Steuerelemente angewendet werden. Die meisten Szenarien, in denen Sie ein neues Steuerelement erstellen müssen, können stattdessen durch das Erstellen einer neuen Vorlage für ein vorhandenes Steuerelement abgedeckt werden.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

In diesem Artikel werden Sie das <xref:System.Windows.Controls.ControlTemplate> Erstellen <xref:System.Windows.Controls.Button> eines neuen Steuerelements untersuchen.

## <a name="when-to-create-a-controltemplate"></a>Wann sie eine ControlTemplate erstellen

Steuerelemente verfügen über <xref:System.Windows.Controls.Border.Background%2A>viele <xref:System.Windows.Controls.Control.Foreground%2A>Eigenschaften, z. B. , und <xref:System.Windows.Controls.Control.FontFamily%2A>. Diese Eigenschaften steuern verschiedene Aspekte der Darstellung des Steuerelements, aber die Änderungen, die Sie durch Festlegen dieser Eigenschaften vornehmen können, sind begrenzt. Sie können die <xref:System.Windows.Controls.Control.Foreground%2A> Eigenschaft z. <xref:System.Windows.Controls.Control.FontStyle%2A> B. auf blau <xref:System.Windows.Controls.CheckBox>und auf Kursiv für eine festlegen. Wenn Sie die Darstellung des Steuerelements über das Festlegen der anderen Eigenschaften <xref:System.Windows.Controls.ControlTemplate>des Steuerelements hinaus anpassen möchten, erstellen Sie eine .

In den meisten Benutzeroberflächen hat eine Schaltfläche die gleiche allgemeine Darstellung: ein Rechteck mit etwas Text. Wenn Sie eine abgerundete Schaltfläche erstellen möchten, können Sie ein neues Steuerelement erstellen, das von der Schaltfläche erbt oder die Funktionalität der Schaltfläche neu erstellt. Darüber hinaus würde das neue Benutzersteuerelement die kreisförmige Visualisierung bereitstellen.

Sie können das Erstellen neuer Steuerelemente vermeiden, indem Sie das visuelle Layout eines vorhandenen Steuerelements anpassen. Mit einer abgerundeten Schaltfläche <xref:System.Windows.Controls.ControlTemplate> erstellen Sie eine mit dem gewünschten visuellen Layout.

Wenn Sie hingegen ein Steuerelement mit neuen Funktionen, unterschiedlichen Eigenschaften und neuen <xref:System.Windows.Controls.UserControl>Einstellungen benötigen, erstellen Sie eine neue .

## <a name="prerequisites"></a>Voraussetzungen

Erstellen Sie eine neue WPF-Anwendung, und legen Sie in *MainWindow.xaml* (oder einem anderen Fenster Ihrer Wahl) die folgenden Eigenschaften im ** \<Window>-Element** fest:

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

Legen Sie den Inhalt des ** \<Window>-Elements** auf das folgende XAML fest:

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

Am Ende sollte die *Datei MainWindow.xaml* wie folgt aussehen:

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

Wenn Sie die Anwendung ausführen, sieht sie wie folgt aus:

![WPF-Fenster mit zwei unformatierten Schaltflächen](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a>Erstellen einer ControlTemplate

Die häufigste Möglichkeit zum <xref:System.Windows.Controls.ControlTemplate> Deklarieren einer `Resources` ist als Ressource im Abschnitt in einer XAML-Datei. Da Vorlagen Ressourcen sind, befolgen sie dieselben Bereichsregeln, die für alle Ressourcen gelten. Einfach ausgedrückt, wo Sie eine Vorlage deklarieren wirkt, wo die Vorlage angewendet werden kann. Wenn Sie beispielsweise die Vorlage im Stammelement Der XAML-Datei der Anwendungsdefinition deklarieren, kann die Vorlage überall in der Anwendung verwendet werden. Wenn Sie die Vorlage in einem Fenster definieren, können nur die Steuerelemente in diesem Fenster die Vorlage verwenden.

Fügen Sie zunächst `Window.Resources` ein Element zu Ihrer *MainWindow.xaml-Datei* hinzu:

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

Erstellen Sie eine neue ** \<ControlTemplate->** mit den folgenden Eigenschaftensatz:

|     |     |
| --- | --- |
| **x:Key**         | `roundbutton` |
| **TargetType**    | `Button` |

Diese Steuerelementvorlage ist einfach:

- ein Stammelement für das Steuerelement, ein<xref:System.Windows.Controls.Grid>
- a, <xref:System.Windows.Shapes.Ellipse> um das abgerundete Erscheinungsbild der Schaltfläche zu zeichnen
- a <xref:System.Windows.Controls.ContentPresenter> zum Anzeigen des benutzerdefinierten Schaltflächeninhalts

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a>TemplateBinding

Wenn Sie einen <xref:System.Windows.Controls.ControlTemplate>neuen erstellen, können Sie die öffentlichen Eigenschaften weiterhin verwenden, um die Darstellung des Steuerelements zu ändern. Die [TemplateBinding-Markuperweiterung](../../framework/wpf/advanced/templatebinding-markup-extension.md) bindet eine Eigenschaft eines <xref:System.Windows.Controls.ControlTemplate> Elements, das sich im Element befindet, an eine öffentliche Eigenschaft, die durch das Steuerelement definiert wird. Wenn Sie eine [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md)verwenden, aktivieren Sie Eigenschaften für das Steuerelement, um als Parameter für die Vorlage zu fungieren. D.h., beim Festlegen einer Steuerelementeigenschaft wird dieser Wert an das Element mit [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) übergeben.

### <a name="ellipse"></a>Ellipse

Beachten **:::no-loc text="Fill":::** Sie, **:::no-loc text="Stroke":::** dass die und die Eigenschaften des ** \<Ellipse->-Elements** an die Eigenschaften des Steuerelements <xref:System.Windows.Controls.Control.Foreground> und <xref:System.Windows.Controls.Control.Background> der Eigenschaften gebunden sind.

### <a name="contentpresenter"></a>ContentPresenter

Ein [ \<ContentPresenter->-Element](xref:System.Windows.Controls.ContentPresenter) wird ebenfalls zur Vorlage hinzugefügt. Da diese Vorlage für eine Schaltfläche entworfen wurde, sollten <xref:System.Windows.Controls.ContentControl>Sie berücksichtigen, dass die Schaltfläche von erbt. Die Schaltfläche zeigt den Inhalt des Elements an. Sie können alles innerhalb der Schaltfläche festlegen, z. B. Nur-Text oder sogar ein anderes Steuerelement. Beide der folgenden Schaltflächen sind gültig:

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

In beiden vorherigen Beispielen werden der Text und das Kontrollkästchen als [Button.Content-Eigenschaft](xref:System.Windows.Controls.ContentControl.Content) festgelegt. Was auch immer als Inhalt festgelegt wird, kann über einen ** \<ContentPresenter>** dargestellt werden, was die Vorlage tut.

Wenn <xref:System.Windows.Controls.ControlTemplate> der auf <xref:System.Windows.Controls.ContentControl> einen Typ angewendet `Button`wird, z. B. ein , <xref:System.Windows.Controls.ContentPresenter> wird in der Elementstruktur gesucht. Wenn `ContentPresenter` der gefunden wird, bindet die Vorlage <xref:System.Windows.Controls.ContentControl.Content> automatisch `ContentPresenter`die Eigenschaft des Steuerelements an die .

## <a name="use-the-template"></a>Verwenden der Vorlage

Suchen Sie die Schaltflächen, die am Anfang dieses Artikels deklariert wurden.

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

Legen Sie die <xref:System.Windows.Controls.Control.Template> Eigenschaft der `roundbutton` zweiten Schaltfläche auf die Ressource fest:

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

Wenn Sie das Projekt ausführen und sich das Ergebnis ansehen, sehen Sie, dass die Schaltfläche einen abgerundeten Hintergrund hat.

![WPF-Fenster mit einer ovalen Vorlagetaste](media/create-apply-template/styled-button.png)

Sie haben vielleicht bemerkt, dass die Schaltfläche kein Kreis ist, sondern verzerrt ist. Aufgrund der Funktionsweise des ** \<Ellipse->-Elements** wird es immer erweitert, um den verfügbaren Platz zu füllen. Machen Sie den Kreis gleichmäßig, **:::no-loc text="width":::** **:::no-loc text="height":::** indem Sie die Schaltfläche und die Eigenschaften auf denselben Wert ändern:

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![WPF-Fenster mit einer Vorlagen-Rundschaltfläche](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a>Hinzufügen eines Triggers

Auch wenn eine Schaltfläche mit einer angewendeten Vorlage anders aussieht, verhält sie sich genauso wie jede andere Schaltfläche. Wenn Sie die Taste <xref:System.Windows.Controls.Primitives.ButtonBase.Click> drücken, wird das Ereignis ausgelöst. Sie haben jedoch möglicherweise bemerkt, dass sich die Visuellen der Schaltfläche nicht ändern, wenn Sie die Maus über die Schaltfläche bewegen. Diese visuellen Interaktionen werden alle durch die Vorlage definiert.

Mit den dynamischen Ereignis- und Eigenschaftssystemen, die WPF bereitstellt, können Sie eine bestimmte Eigenschaft für einen Wert ansehen und die Vorlage dann entsprechend umgestalten. In diesem Beispiel sehen Sie sich <xref:System.Windows.UIElement.IsMouseOver> die Eigenschaft der Schaltfläche an. Wenn die Maus über dem Steuerelement ist, stilisieren Sie die ** \<Ellipse->** mit einer neuen Farbe. Dieser Triggertyp wird als *PropertyTrigger*bezeichnet.

Damit dies funktioniert, müssen Sie dem ** \<Ellipse->** einen Namen hinzufügen, auf den Sie verweisen können. Geben Sie ihm den Namen **backgroundElement**.

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

Fügen Sie als <xref:System.Windows.Trigger> Nächstes der [ControlTemplate.Triggers-Auflistung](xref:System.Windows.Controls.ControlTemplate.Triggers) eine neue hinzu. Der Trigger beobachtet `IsMouseOver` das Ereignis `true`für den Wert .

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

Fügen Sie als Nächstes eine ** \<Setter->** zum ** \<Trigger->** hinzu, die die **Fill-Eigenschaft** der ** \<Ellipse->** in eine neue Farbe ändert.

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

Führen Sie das Projekt aus. Beachten Sie, dass sich beim Bewegen der Maus über die Schaltfläche die Farbe der ** \<Ellipse->** ändert.

![Maus bewegt sich über die WPF-Taste, um die Füllfarbe zu ändern](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a>Verwenden eines VisualState

Visuelle Zustände werden durch ein Steuerelement definiert und ausgelöst. Wenn die Maus beispielsweise über das Steuerelement bewegt `CommonStates.MouseOver` wird, wird der Zustand ausgelöst. Sie können Eigenschaftenänderungen basierend auf dem aktuellen Status des Steuerelements animieren. Im vorherigen Abschnitt wurde `IsMouseOver` ein `true` ** \<PropertyTrigger->** verwendet, um `AliceBlue` den Vordergrund der Schaltfläche in den Zeitpunkt zu ändern, zu dem die Eigenschaft war. Erstellen Sie stattdessen einen visuellen Zustand, der die Änderung dieser Farbe animiert und einen reibungslosen Übergang bietet. Weitere Informationen zu *VisualStates*finden Sie [unter Stile und Vorlagen in WPF](../fundamentals/styles-templates-overview.md#visual-states).

Um ** \<propertyTrigger>** in einen animierten visuellen Zustand zu konvertieren, entfernen Sie zuerst das ** \<ControlTemplate.Triggers>-Element** aus Ihrer Vorlage.

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

Fügen Sie anschließend im ** \<Stammverzeichnis "Grid>"** der Steuerelementvorlage das ** \<VisualStateManager.VisualStateGroups->-Element** mit einem ** \<VisualStateGroup->** für `CommonStates`hinzu. Definieren Sie `Normal` zwei `MouseOver`Zustände und .

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

Alle Animationen, die in einem ** \<VisualState->** definiert sind, werden angewendet, wenn dieser Status ausgelöst wird. Erstellen Sie Animationen für jeden Status. Animationen werden in einem ** \<Storyboard->-Element** abgelegt. Weitere Informationen zu Storyboards finden Sie unter [Storyboards Übersicht](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

- Normal

  Dieser Zustand animiert die Ellipsenfüllung und stellt `Background` sie in der Farbe des Steuerelements wieder her.

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- MouseOver

  Dieser Zustand animiert `Background` die Ellipsenfarbe `Yellow`zu einer neuen Farbe: .

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

Die ** \<ControlTemplate->** sollten nun wie folgt aussehen.

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

Führen Sie das Projekt aus. Beachten Sie, dass beim Bewegen der Maus über die Schaltfläche die Farbe der ** \<Ellipse->** animiert wird.

![Maus bewegt sich über die WPF-Taste, um die Füllfarbe zu ändern](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a>Nächste Schritte

- [Erstellen eines Stils für ein Steuerelement in WPF](../fundamentals/styles-templates-create-apply-style.md)
- [Stile und Vorlagen in WPF](../fundamentals/styles-templates-overview.md)
- [Überblick über XAML-Ressourcen](../fundamentals/xaml-resources-define.md)
