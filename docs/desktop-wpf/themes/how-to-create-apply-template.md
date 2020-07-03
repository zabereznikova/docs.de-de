---
title: 'Erstellen einer Vorlage in WPF: .NET-Desktop'
description: In diesem Artikel erfahren Sie, wie Sie eine Vorlage für ein Steuerelement in Windows Presentation Foundation und .NET Core erstellen und darauf verweisen.
author: adegeo
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
ms.openlocfilehash: c372659676b450cde789c96e45c7ec5de2aea194
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325727"
---
# <a name="create-a-template-for-a-control"></a>Erstellen einer Vorlage für ein Steuerelement

Mit Windows Presentation Foundation (WPF) können Sie die visuelle Struktur und das Verhalten eines vorhandenen Steuerelements mit Ihrer eigenen wiederverwendbaren Vorlage anpassen. Vorlagen können global auf Anwendungen, Fenster und Seiten oder direkt auf Steuerelemente angewendet werden. Die meisten Szenarien, in denen Sie ein neues Steuerelement erstellen müssen, können stattdessen durch Erstellen einer neuen Vorlage für ein vorhandenes Steuerelement abgedeckt werden.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

In diesem Artikel erfahren Sie, wie Sie eine neue <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.Button>-Steuerelement erstellen.

## <a name="when-to-create-a-controltemplate"></a>Wann sollte eine ControlTemplate erstellt werden?

Steuerelemente verfügen über viele Eigenschaften, etwa über <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A> und <xref:System.Windows.Controls.Control.FontFamily%2A>. Diese Eigenschaften steuern verschiedene Aspekte der Darstellung des Steuerelements, aber die Änderungen, die Sie vornehmen können, indem Sie diese Eigenschaften festlegen, sind eingeschränkt. Beispielsweise können Sie die <xref:System.Windows.Controls.Control.Foreground%2A>-Eigenschaft auf „Blue“ festlegen und <xref:System.Windows.Controls.Control.FontStyle%2A> für ein <xref:System.Windows.Controls.CheckBox>-Element auf kursiv. Sie erstellen eine <xref:System.Windows.Controls.ControlTemplate>, wenn Sie die Darstellung des Steuerelements über das hinaus ändern möchten, was durch das Festlegen anderer Steuerelementeigenschaften möglich ist.

In den meisten Benutzeroberflächen weis eine Schaltfläche dieselbe allgemeine Darstellung auf: ein Rechteck mit Text. Wenn Sie eine abgerundete Schaltfläche erstellen möchten, können Sie ein neues Steuerelement erstellen, das von der Schaltfläche erbt oder die Funktionalität der Schaltfläche neu erstellt. Außerdem würde das neue Benutzersteuerelement das abgerundete visuelle Element bereitstellen.

Sie können vermeiden, neue Steuerelemente zu erstellen, indem Sie das visuelle Layout eines vorhandenen Steuerelements anpassen. Mit einer abgerundeten Schaltfläche erstellen Sie eine <xref:System.Windows.Controls.ControlTemplate> mit dem gewünschten visuellen Layout.

Wenn Sie jedoch ein Steuerelement mit neuen Funktionen, anderen Eigenschaften und neuen Einstellungen benötigen, erstellen Sie ein neues <xref:System.Windows.Controls.UserControl>-Element.

## <a name="prerequisites"></a>Voraussetzungen

Erstellen Sie eine neue WPF-Anwendung, und legen Sie in *MainWindow.xaml* (oder in einem anderen Fenster Ihrer Wahl) die folgenden Eigenschaften für das **\<Window>** -Element fest:

|     |     |
| --- | --- |
| **Title**         | `Template Intro Sample` |
| **SizeToContent** | `WidthAndHeight` |
| **MinWidth**      | `250` |

Legen Sie den Inhalt des **\<Window>** -Elements auf den folgenden XAML-Code fest:

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

Schließlich sollte die Datei *MainWindow.xaml* ähnlich wie im Folgenden aussehen:

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

Wenn Sie die Anwendung ausführen, sieht dies wie folgt aus:

![WPF-Fenster mit zwei Schaltflächen ohne Stilangabe](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a>Erstellen einer ControlTemplate

Eine <xref:System.Windows.Controls.ControlTemplate> wird üblicherweise deklariert, indem sie im Abschnitt `Resources` einer XAML-Datei als Ressource deklariert wird. Da es sich bei Vorlagen um Ressourcen handelt, unterliegen sie denselben Gültigkeitsbereichsregeln, die für alle Ressourcen gelten. Einfach ausgedrückt: Wo Sie eine Vorlage deklarieren, wirkt sich darauf aus, wo die Vorlage angewendet werden kann. Wenn Sie die Vorlage beispielsweise im Stammelement der XAML-Anwendungsdefinitionsdatei deklarieren, kann die Vorlage überall in Ihrer Anwendung verwendet werden. Wenn Sie die Vorlage in einem Fenster definieren, können nur die Steuerelemente in diesem Fenster die Vorlage verwenden.

Fügen Sie zunächst der Datei *MainWindow.xaml* ein `Window.Resources`-Element hinzu:

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

Erstellen Sie ein neues **\<ControlTemplate>** -Element mit den folgenden Eigenschaften:

|     |     |
| --- | --- |
| **x:Key**         | `roundbutton` |
| **TargetType**    | `Button` |

Diese Steuerelementvorlage ist einfach:

- ein Stammelement für das-Steuerelement, ein <xref:System.Windows.Controls.Grid>
- ein <xref:System.Windows.Shapes.Ellipse>-Element, um das abgerundete Aussehen der Schaltfläche zu zeichnen
- ein <xref:System.Windows.Controls.ContentPresenter>-Element, um den benutzerdefinierten Schaltflächeninhalt anzuzeigen

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a>TemplateBinding

Beim Erstellen einer neuen <xref:System.Windows.Controls.ControlTemplate> können Sie weiterhin die öffentlichen Eigenschaften verwenden, um die Darstellung der Steuerelemente anzupassen. Die [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md)-Markuperweiterung bindet eine Eigenschaft eines in der <xref:System.Windows.Controls.ControlTemplate> enthaltenen Elements an eine vom Steuerelement definierte öffentliche Eigenschaft. Bei Verwendung einer [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) können Steuerelementeigenschaften als Parameter der Vorlage fungieren. D.h., beim Festlegen einer Steuerelementeigenschaft wird dieser Wert an das Element mit [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) übergeben.

### <a name="ellipse"></a>Ellipse

Beachten Sie, dass die Eigenschaften **:::no-loc text="Fill":::** und **:::no-loc text="Stroke":::** des Elements **\<Ellipse>** an die Eigenschaften <xref:System.Windows.Controls.Control.Foreground> und <xref:System.Windows.Controls.Control.Background> des Steuerelements gebunden sind.

### <a name="contentpresenter"></a>ContentPresenter

Der Vorlage wird auch ein [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter)-Element hinzugefügt. Da diese Vorlage für eine Schaltfläche konzipiert ist, müssen Sie berücksichtigen, dass die Schaltfläche von <xref:System.Windows.Controls.ContentControl> erbt. Die Schaltfläche stellt den Inhalt des Elements dar. Sie können beliebige Elemente innerhalb der Schaltfläche festlegen, z. B. Nur-Text oder sogar ein anderes Steuerelement. Beide folgenden Schaltflächen sind gültig:

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

In den beiden vorherigen Beispielen werden der Text und das Kontrollkästchen als [Button.Content](xref:System.Windows.Controls.ContentControl.Content)-Eigenschaft festgelegt. Was als Inhalt festgelegt wird, kann durch ein **\<ContentPresenter>** -Element dargestellt werden, was die Vorlage auch umsetzt.

Wenn die <xref:System.Windows.Controls.ControlTemplate> auf einen <xref:System.Windows.Controls.ContentControl>-Typ angewendet wird, z. B. auf ein `Button`-Element, wird nach einem <xref:System.Windows.Controls.ContentPresenter>-Element in der-Elementstruktur gesucht. Wenn der `ContentPresenter` gefunden wird, bindet die Vorlage automatisch die <xref:System.Windows.Controls.ContentControl.Content>-Eigenschaft des Steuerelements an den `ContentPresenter`.

## <a name="use-the-template"></a>Verwenden der Vorlage

Suchen Sie die Schaltflächen, die zu Beginn dieses Artikels deklariert wurden.

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

Legen Sie die <xref:System.Windows.Controls.Control.Template>-Eigenschaft der zweiten Schaltfläche auf die `roundbutton`-Ressource fest:

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

Wenn Sie das Projekt ausführen und das Ergebnis untersuchen, sehen Sie, dass die Schaltfläche einen abgerundeten Hintergrund aufweist.

![WPF-Fenster mit einer ovalen Vorlagenschaltfläche](media/create-apply-template/styled-button.png)

Vielleicht haben Sie bemerkt, dass die Schaltfläche kein Kreis ist, sondern verzerrt ist. Aufgrund der Art und Weise, wie das **\<Ellipse>** -Element funktioniert, wird es immer erweitert, um den verfügbaren Platz auszufüllen. Vereinheitlichen Sie den Kreis, indem Sie die Eigenschaften der Schaltfläche **:::no-loc text="width":::** und **:::no-loc text="height":::** in den gleichen Wert ändern:

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![WPF-Fenster mit einer runden Vorlagenschaltfläche](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a>Hinzufügen eines Triggers

Obwohl eine Schaltfläche mit einer angewendeten Vorlage anders aussieht, verhält sie sich wie jede andere Schaltfläche. Wenn Sie auf die Schaltfläche klicken, wird das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>-Ereignis ausgelöst. Möglicherweise haben Sie jedoch bemerkt, dass die visuellen Elemente der Schaltfläche nicht geändert werden, wenn Sie den Mauszeiger über die Schaltfläche bewegen. Diese visuellen Interaktionen werden alle durch die Vorlage definiert.

Durch die dynamischen Ereignis- und Eigenschaftensysteme, die von WPF bereitgestellt werden, können Sie eine bestimmte Eigenschaft für einen Wert beobachten und die Vorlage ggf. neu formatieren. In diesem Beispiel beobachten Sie die <xref:System.Windows.UIElement.IsMouseOver>-Eigenschaft der Schaltfläche. Wenn sich der Mauszeiger über dem Steuerelement befindet, formatieren Sie das **\<Ellipse>** -Element mit einer neuen Farbe. Dieser Triggertyp wird als *PropertyTrigger* bezeichnet.

Damit dies funktioniert, müssen Sie **\<Ellipse>** einen Namen hinzufügen, auf den Sie verweisen können. Vergeben Sie den Namen **backgroundElement**.

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

Fügen Sie als nun der [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers)-Sammlung einen neuen <xref:System.Windows.Trigger> hinzu. Der Trigger überwacht das `IsMouseOver`-Ereignis für den Wert `true`.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

Fügen Sie **\<Trigger>** nun ein **\<Setter>** -Element hinzu, das die **Fill**-Eigenschaft von **\<Ellipse>** in eine neue Farbe ändert.

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

Führen Sie das Projekt aus. Beachten Sie, dass sich beim Bewegen der Maus über die Schaltfläche die Farbe des **\<Ellipse>** -Elements ändert.

![Mausbewegung über die WPF-Schaltfläche, um die Füllfarbe zu ändern](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a>Verwenden eines VisualState

Visuelle Zustände werden von einem-Steuerelement definiert und ausgelöst. Wenn die Maus z. B. über das Steuerelement bewegt wird, wird der `CommonStates.MouseOver`-Zustand ausgelöst. Sie können Eigenschaftsänderungen auf der Grundlage des aktuellen Zustands des Steuerelements animieren. Im vorherigen Abschnitt wurde ein **\<PropertyTrigger>** -Element verwendet, um den Vordergrund der Schaltfläche in `AliceBlue` zu ändern, wenn die `IsMouseOver`-Eigenschaft auf `true` festgelegt war. Erstellen Sie stattdessen einen visuellen Zustand, der die Änderung dieser Farbe animiert und für einen fließenden Übergang sorgt. Weitere Informationen zu *VisualStates* finden Sie unter [Stile und Vorlagen in WPF](../fundamentals/styles-templates-overview.md#visual-states).

Wenn Sie das **\<PropertyTrigger>** -Element in einen animierten visuellen Zustand konvertieren möchten, entfernen Sie zunächst das **\<ControlTemplate.Triggers>** -Element aus der Vorlage.

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

Fügen Sie als Nächstes im **\<Grid>** -Stamm der Steuerelementvorlage das **\<VisualStateManager.VisualStateGroups>** -Element mit einem **\<VisualStateGroup>** -Element für `CommonStates` hinzu. Definieren Sie zwei Zustände, `Normal` und `MouseOver`.

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

Alle in einem **\<VisualState>** -Element definierten Animationen werden angewendet, wenn dieser Zustand ausgelöst wird. Erstellen Sie Animationen für jeden Zustand. Animationen werden in einem **\<Storyboard>** -Element abgelegt. Weitere Informationen zu Storyboards finden Sie unter [Übersicht über Storyboards](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

- Normal

  Dieser Zustand animiert die Ellipsenfüllung und stellt sie in der Farbe `Background` des Steuerelements wieder her.

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- MouseOver

  Dieser Zustand animiert die Farbe `Background` der Ellipse in eine neue Farbe: `Yellow`.

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

Das **\<ControlTemplate>** -Element sollte nun wie folgt aussehen.

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

Führen Sie das Projekt aus. Beachten Sie, dass beim Bewegen der Maus über die Schaltfläche die Farbe des **\<Ellipse>** -Elements animiert wird.

![Mausbewegung über die WPF-Schaltfläche, um die Füllfarbe zu ändern](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a>Nächste Schritte

- [Erstellen eines Stils für ein Steuerelement in WPF](../fundamentals/styles-templates-create-apply-style.md)
- [Stile und Vorlagen in WPF](../fundamentals/styles-templates-overview.md)
- [Überblick über XAML-Ressourcen](../fundamentals/xaml-resources-define.md)
