---
title: Stile und Vorlagen
description: Erfahren Sie mehr über XAML-Ressourcen in Windows Presentation Foundation (WPF) für .NET Core. Informieren Sie sich über die Typen von XAML-Ressourcen im Zusammenhang mit Stilen und Designs.
author: thraka
ms.author: adegeo
ms.date: 09/09/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: f845e739ec3cae502d1e4fd6631f987c5364a42e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433097"
---
# <a name="styles-and-templates-in-wpf"></a>Stile und Vorlagen in WPF

Stile und Vorlagen in Windows Presentation Foundation (WPF) beziehen sich auf eine Reihe von Funktionen, mit denen Entwickler und Designer visuell überzeugende Effekte und ein einheitliches Erscheinungsbild für ihr Produkt erstellen können. Wenn Sie die Darstellung einer App anpassen, benötigen Sie ein leistungsfähiges Stil- und Vorlagenmodell, das die Wartung und Freigabe des Erscheinungsbilds innerhalb der jeweiligen und zwischen Apps ermöglicht. WPF stellt dieses Modell bereit.

Eine weitere Funktion des WPF-Stilmodells ist die Trennung von Darstellung und Programmlogik. Designer können die Darstellung einer App nur mithilfe von XAML bearbeiten, während Entwickler mit C# oder Visual Basic an der Programmierlogik arbeiten.

Diese Übersicht konzentriert sich auf die Aspekte der Stile und Vorlagen der App und geht nicht auf Datenbindungskonzepte ein. Weitere Informationen zur Datenbindung finden Sie unter [Übersicht über die Datenbindung](../data/data-binding-overview.md).

Es ist wichtig, die Ressourcen zu kennen, die die Wiederverwendung von Stilen und Vorlagen ermöglichen. Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](xaml-resources-define.md).

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sample"></a>Beispiel

Der Beispielcode in dieser Übersicht basiert auf einer [einfachen Anwendung zum Suchen von Fotos](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating), die in der folgenden Abbildung gezeigt wird.

![Formatierte ListView](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

In diesem einfachen Foto-Beispiel werden Stile und Vorlagen verwendet, um eine visuell ansprechende Benutzeroberfläche zu erstellen. Das Beispiel verfügt über zwei <xref:System.Windows.Controls.TextBlock>-Elemente und ein <xref:System.Windows.Controls.ListBox>-Steuerelement, das an eine Liste von Bildern gebunden ist.

Das vollständige Beispiel finden Sie unter [Einführung zum Beispiel zu Stilen und Vorlagen](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="styles"></a>Stile

<xref:System.Windows.Style> ist eine einfache Möglichkeit, mehrere Eigenschaftswerte auf mehrere Elemente anzuwenden. Stile lassen sich auf alle Elemente anwenden, die von <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> abgeleitet sind, z. B. <xref:System.Windows.Window> oder <xref:System.Windows.Controls.Button>.

Stile werden üblicherweise deklariert, indem sie im Abschnitt `Resources` einer XAML-Datei als Ressource deklariert werden. Da es sich bei Stilen um Ressourcen handelt, unterliegen sie denselben Regeln für Gültigkeitsbereiche, die für alle Ressourcen gelten. Einfach ausgedrückt: Wo Sie einen Stil deklarieren, wirkt sich darauf aus, wo der Stil angewendet werden kann. Wenn Sie den Stil z. B. im Stammelement Ihrer XAML-Datei mit der App-Definition deklarieren, kann der Stil überall in der App verwendet werden.

Der folgende XAML-Code deklariert beispielsweise zwei Stile für einen `TextBlock`: einen Stil, der automatisch auf alle `TextBlock`-Elemente angewendet wird, und einen anderen Stil, auf den explizit verwiesen werden muss.

[!code-xaml[SnippetDefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

Im Folgenden finden Sie ein Beispiel der oben deklarierten Stile, die verwendet werden.

[!code-xaml[SnippetTextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

![Formatierte TextBlocks](./media/styles-and-templates-overview/stylingintro-textblocks.png)

Weitere Informationen finden Sie unter [Erstellen eines Stils für ein Steuerelement](styles-templates-create-apply-style.md).

## <a name="controltemplates"></a>ControlTemplates

In WPF definiert die <xref:System.Windows.Controls.ControlTemplate> eines Steuerelements die Darstellung des Steuerelements. Sie können die Struktur und die Darstellung eines Steuerelements ändern, indem Sie eine neue <xref:System.Windows.Controls.ControlTemplate> definieren und einem Steuerelement zuweisen. In vielen Fällen erhalten Sie durch Vorlagen ausreichende Flexibilität, um keine eigenen benutzerdefinierten Steuerelemente schreiben zu müssen.

Jedes Steuerelement verfügt über eine Standardvorlage, die der [Control.Template](xref:System.Windows.Controls.Control.Template)-Eigenschaft zugewiesen ist. Die Vorlage verbindet die visuelle Darstellung des Steuerelements mit den Funktionen des Steuerelements. Da Sie eine Vorlage in XAML definieren, können Sie die Darstellung des Steuerelements ändern, ohne Code schreiben zu müssen. Jede Vorlage ist für ein bestimmtes Steuerelement konzipiert (z. B. ein <xref:System.Windows.Controls.Button>-Element).

Im Allgemeinen deklarieren Sie eine Vorlage im Abschnitt `Resources` einer XAML-Datei als Ressource. Wie bei allen Ressourcen gelten Gültigkeitsbreichsregeln.

Steuerelementvorlagen sind viel komplexer als ein Stil. Dies liegt daran, dass die Steuerelementvorlage die visuelle Darstellung des gesamten Steuerelements erneut schreibt, während ein Stil einfach Eigenschaftsänderungen auf das vorhandene Steuerelement anwendet. Da jedoch die Vorlage eines Steuerelements durch Festlegen der [Control.Template](xref:System.Windows.Controls.Control.Template)-Eigenschaft angewendet wird, können Sie einen Stil verwenden, um eine Vorlage zu definieren oder festzulegen.

Designer ermöglichen es Ihnen im Allgemeinen, eine Kopie einer vorhandenen Vorlage zu erstellen und zu ändern. Wählen Sie im WPF-Designer von Visual Studio beispielsweise ein `CheckBox`-Steuerelement aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **Vorlage bearbeiten** > **Kopie erstellen** aus. Mit diesem Befehl wird ein *Stil generiert, der eine Vorlagen definiert*.

```xaml
<Style x:Key="CheckBoxStyle1" TargetType="{x:Type CheckBox}">
    <Setter Property="FocusVisualStyle" Value="{StaticResource FocusVisual1}"/>
    <Setter Property="Background" Value="{StaticResource OptionMark.Static.Background1}"/>
    <Setter Property="BorderBrush" Value="{StaticResource OptionMark.Static.Border1}"/>
    <Setter Property="Foreground" Value="{DynamicResource {x:Static SystemColors.ControlTextBrushKey}}"/>
    <Setter Property="BorderThickness" Value="1"/>
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type CheckBox}">
                <Grid x:Name="templateRoot" Background="Transparent" SnapsToDevicePixels="True">
                    <Grid.ColumnDefinitions>
                        <ColumnDefinition Width="Auto"/>
                        <ColumnDefinition Width="*"/>
                    </Grid.ColumnDefinitions>
                    <Border x:Name="checkBoxBorder" Background="{TemplateBinding Background}" BorderThickness="{TemplateBinding BorderThickness}" BorderBrush="{TemplateBinding BorderBrush}" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="1" VerticalAlignment="{TemplateBinding VerticalContentAlignment}">
                        <Grid x:Name="markGrid">
                            <Path x:Name="optionMark" Data="F1 M 9.97498,1.22334L 4.6983,9.09834L 4.52164,9.09834L 0,5.19331L 1.27664,3.52165L 4.255,6.08833L 8.33331,1.52588e-005L 9.97498,1.22334 Z " Fill="{StaticResource OptionMark.Static.Glyph1}" Margin="1" Opacity="0" Stretch="None"/>
                            <Rectangle x:Name="indeterminateMark" Fill="{StaticResource OptionMark.Static.Glyph1}" Margin="2" Opacity="0"/>
                        </Grid>
                    </Border>
                    <ContentPresenter x:Name="contentPresenter" Grid.Column="1" Focusable="False" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" RecognizesAccessKey="True" SnapsToDevicePixels="{TemplateBinding SnapsToDevicePixels}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}"/>
                </Grid>
                <ControlTemplate.Triggers>
                    <Trigger Property="HasContent" Value="true">
                        <Setter Property="FocusVisualStyle" Value="{StaticResource OptionMarkFocusVisual1}"/>
                        <Setter Property="Padding" Value="4,-1,0,0"/>

... content removed to save space ...
```

Das Bearbeiten einer Kopie einer Vorlage ist eine gute Möglichkeit, um zu erfahren, wie Vorlagen funktionieren. Anstatt eine neue leere Vorlage zu erstellen, ist es einfacher, eine Kopie zu bearbeiten und einige Aspekte der visuellen Darstellung zu ändern.

Ein Beispiel dazu finden Sie unter [Erstellen einer Vorlage für ein Steuerelement](../themes/how-to-create-apply-template.md).

### <a name="templatebinding"></a>TemplateBinding

Möglicherweise haben Sie bemerkt, dass die im vorherigen Abschnitt definierte Vorlagenressource die [TemplateBinding-Markuperweiterung](../../framework/wpf/advanced/templatebinding-markup-extension.md) verwendet. Eine `TemplateBinding` ist die optimierte Form einer Bindung für Vorlagenszenarien, die einer mit `{Binding RelativeSource={RelativeSource TemplatedParent}}` erstellten Bindung entspricht. `TemplateBinding` ist nützlich, um Teile der Vorlage an die Eigenschaften des Steuerelements zu binden. Jedes Steuerelement verfügt beispielsweise über eine <xref:System.Windows.Controls.Control.BorderThickness>-Eigenschaft. Verwenden Sie eine `TemplateBinding`, um zu verwalten, welches Element in der Vorlage von dieser Steuerelementeinstellung betroffen ist.

### <a name="contentcontrol-and-itemscontrol"></a>ContentControl und ItemsControl

Wenn ein <xref:System.Windows.Controls.ContentPresenter> in der <xref:System.Windows.Controls.ControlTemplate> eines <xref:System.Windows.Controls.ContentControl>-Elements deklariert wird, wird der <xref:System.Windows.Controls.ContentPresenter> automatisch an die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>- und <xref:System.Windows.Controls.ContentControl.Content%2A>-Eigenschaften gebunden. Ebenso wird ein <xref:System.Windows.Controls.ItemsPresenter>, der sich in der <xref:System.Windows.Controls.ControlTemplate> eines <xref:System.Windows.Controls.ItemsControl>-Elements befindet, automatisch an die Eigenschaften <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> und <xref:System.Windows.Controls.ItemsControl.Items%2A> gebunden.

## <a name="datatemplates"></a>DataTemplates

In dieser Beispiel-App gibt es ein <xref:System.Windows.Controls.ListBox>-Steuerelement, das an eine Liste von Fotos gebunden ist.

[!code-xaml[ListBox](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window3.xaml#SnippetListBox)]

Diese <xref:System.Windows.Controls.ListBox> sieht zurzeit wie folgt aus.

![ListBox vor dem Anwenden einer Vorlage](./media/styles-and-templates-overview/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")

Die meisten Steuerelemente verfügen über Inhalte, und dieser Inhalt stammt häufig aus Daten, an die Sie binden. In diesem Beispiel sind die Daten die Liste der Fotos. In WPF verwenden Sie eine <xref:System.Windows.DataTemplate>, um die visuelle Darstellung von Daten zu definieren. Ihre Eingabe in <xref:System.Windows.DataTemplate> bestimmt im Grunde genommen, wie die Daten in der gerenderten App aussehen.

In unserer Beispiel-App verfügt jedes benutzerdefinierte `Photo`-Objekt über eine `Source`-Eigenschaft vom Typ „string“ (Zeichenfolge), die den Pfad des Bilds angibt. Derzeit werden die Fotoobjekte als Dateipfade angezeigt.

[!code-csharp[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Photo.cs#PhotoClass)]
[!code-vb[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/Photo.vb#PhotoClass)]

Damit die Fotos als Bilder angezeigt werden, erstellen Sie eine <xref:System.Windows.DataTemplate>-Klasse als Ressource.

[!code-xaml[DataTemplate](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window4.xaml#SnippetDataTemplate)]

Beachten Sie, dass die <xref:System.Windows.DataTemplate.DataType%2A>-Eigenschaft mit der <xref:System.Windows.Style.TargetType%2A>-Eigenschaft von <xref:System.Windows.Style> vergleichbar ist. Wenn sich Ihre <xref:System.Windows.DataTemplate> im Abschnitt „Resources“ befindet und Sie die <xref:System.Windows.DataTemplate.DataType%2A>-Eigenschaft für einen Typ angeben und einen `x:Key` auslassen, wird die <xref:System.Windows.DataTemplate> immer dann angewendet, wenn dieser Typ angezeigt wird. Sie haben immer die Möglichkeit, die <xref:System.Windows.DataTemplate> einem `x:Key` zuzuweisen und dann als `StaticResource` für Eigenschaften festzulegen, die <xref:System.Windows.DataTemplate>-Typen annehmen, z. B. die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>-Eigenschaft oder die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>-Eigenschaft.

Im Wesentlichen definiert das <xref:System.Windows.DataTemplate> im Beispiel oben, dass jedes Mal, wenn ein `Photo`-Objekt vorhanden ist, dieses als <xref:System.Windows.Controls.Image> innerhalb eines <xref:System.Windows.Controls.Border>-Elements angezeigt werden soll. Mit dieser <xref:System.Windows.DataTemplate> sieht unsere App nun wie folgt aus.

![Fotobild](./media/styles-and-templates-overview/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")

Das Datenvorlagenmodell stellt weitere Funktionen bereit. Wenn Sie z. B. Sammlungsdaten anzeigen, die andere Sammlungen enthalten, die einen <xref:System.Windows.Controls.HeaderedItemsControl>-Typ wie <xref:System.Windows.Controls.Menu> oder <xref:System.Windows.Controls.TreeView> verwenden, ist die <xref:System.Windows.HierarchicalDataTemplate> vorhanden. Eine weitere Datenvorlagenfunktion ist das <xref:System.Windows.Controls.DataTemplateSelector>-Element, das es Ihnen ermöglicht, basierend auf benutzerdefinierter Progammlogik eine zu verwendende <xref:System.Windows.DataTemplate> auszuwählen. Weitere Informationen finden Sie unter im Artikel [Übersicht über Datenvorlagen](../../framework/wpf/data/data-templating-overview.md), der eine ausführlichere Erläuterung der verschiedenen Vorlagenfunktionen bereitstellt.

## <a name="triggers"></a>Trigger

Ein Trigger legt Eigenschaften fest oder startet Aktionen, z.B. eine Animation, wenn sich ein Eigenschaftswert ändert oder ein Ereignis ausgelöst wird. <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>und <xref:System.Windows.DataTemplate> verfügen alle über eine `Triggers`-Eigenschaft, die eine Reihe von Triggern enthalten kann. Es gibt mehrere Typen von Triggern.

### <a name="propertytriggers"></a>PropertyTriggers

Ein <xref:System.Windows.Trigger>, der Eigenschaftswerte festlegt oder Aktionen basierend auf einem Eigenschaftswert auslöst, wird als Eigenschaftstrigger bezeichnet.

Um die Verwendung von Eigenschaftstriggern zu veranschaulichen, können Sie jede <xref:System.Windows.Controls.ListBoxItem>-Klasse teilweise transparent anzeigen, es sei denn, sie ist aktiviert. Im folgenden Stil wird der <xref:System.Windows.UIElement.Opacity%2A>-Wert eines <xref:System.Windows.Controls.ListBoxItem> auf `0.5`festgelegt. Wenn die <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A>-Eigenschaft `true` ist, wird <xref:System.Windows.UIElement.Opacity%2A> jedoch auf `1.0` festgelegt.

[!code-xaml[PropertyTrigger](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window5.xaml#SnippetPropertyTrigger)]

In diesem Beispiel wird ein <xref:System.Windows.Trigger> verwendet, um einen Eigenschaftswert festzulegen, aber beachten Sie, dass die <xref:System.Windows.Trigger>-Klasse auch über die Eigenschaften <xref:System.Windows.TriggerBase.EnterActions%2A> und <xref:System.Windows.TriggerBase.ExitActions%2A> verfügt, die es dem Trigger ermöglichen, Aktionen auszuführen.

Beachten Sie, dass die <xref:System.Windows.FrameworkElement.MaxHeight%2A>-Eigenschaft von <xref:System.Windows.Controls.ListBoxItem> auf `75` festgelegt ist. In der folgenden Abbildung ist das dritte Element das ausgewählte Element.

![Formatierte ListView](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

### <a name="eventtriggers-and-storyboards"></a>EventTrigger und Storyboards

Ein weiterer Trigger ist <xref:System.Windows.EventTrigger>, der eine Reihe von Aktionen startet, die auf dem Vorkommen eines Ereignisses basieren. Die folgenden <xref:System.Windows.EventTrigger>-Objekte geben z. B. an, dass die <xref:System.Windows.FrameworkElement.MaxHeight%2A>-Eigenschaft, wenn das <xref:System.Windows.Controls.ListBoxItem>-Element durch den Mauszeiger aktiviert wird, auf einen Wert von `90` über einen zweiten Zeitraum von `0.2` animiert wird. Wenn sich die Maus vom Element weg bewegt, gibt die Eigenschaft auf den ursprünglichen Wert über einen Zeitraum von `1` Sekunden an. Beachten Sie, dass es nicht notwendig ist, einen <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>-Wert für die <xref:System.Windows.ContentElement.MouseLeave>-Animation anzugeben. Dies liegt daran, dass die Animation den ursprünglichen Wert nachverfolgen kann.

[!code-xaml[StyleEventTriggers](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window6.xaml#SnippetStyleEventTriggers)]

Weitere Informationen finden Sie in der [Übersicht über Storyboards](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

In der folgenden Abbildung zeigt die Maus auf das dritte Element.

![Screenshot: Stilbeispiel](./media/styles-and-templates-overview/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>MultiTrigger, DataTrigger und MultiDataTrigger

Zusätzlich zu <xref:System.Windows.Trigger> und <xref:System.Windows.EventTrigger>gibt es auch andere Typen von Triggern. Mit <xref:System.Windows.MultiTrigger> können Sie Eigenschaftswerte auf Grundlage mehrerer Kriterien festlegen. Sie verwenden <xref:System.Windows.DataTrigger> und <xref:System.Windows.MultiDataTrigger>, wenn die-Eigenschaft Ihrer Bedingung datengebunden ist.

## <a name="visual-states"></a>Visuelle Zustände

Steuerelemente befinden sich immer in einem bestimmten **Zustand**. Wenn die Maus z. B. über die Oberfläche eines Steuerelements bewegt wird, wird das Steuerelement als im allgemeinen Zustand `MouseOver` betrachtet. Ein Steuerelement ohne einen bestimmten Zustand wird als im allgemeinen Zustand `Normal` betrachtet. Zustände werden in Gruppen unterteilt, und die zuvor erwähnten Zustände sind Teil der Statusgruppe `CommonStates`. Die meisten Steuerelemente verfügen über zwei Statusgruppen: `CommonStates` und `FocusStates`. Für jede Zustandsgruppe, die auf ein Steuerelement angewendet wird, befindet sich ein Steuerelement immer in einem Zustand jeder Gruppe, z. B. `CommonStates.MouseOver` und `FocusStates.Unfocused`. Ein Steuerelement kann sich jedoch nicht in zwei verschiedenen Zuständen innerhalb derselben Gruppe befinden, etwa in `CommonStates.Normal` und `CommonStates.Disabled`. Im Folgenden finden Sie eine Tabelle mit Zuständen, die die meisten Steuerelemente erkennen und verwenden.

| VisualState-Name | VisualStateGroup-Name | Beschreibung |
| ---------------- | --------------------- | ----------- |
| Normal           | CommonStates          | Der Standardzustand |
| MouseOver        | CommonStates          | Der Mauszeiger ist über dem Steuerelement positioniert. |
| Gedrückt          | CommonStates          | Das Steuerelement wird gedrückt. |
| Deaktiviert         | CommonStates          | Das Steuerelement ist deaktiviert. |
| Focused          | FocusStates           | Der Fokus liegt auf dem Steuerelement. |
| Ohne Fokus        | FocusStates           | Der Fokus liegt nicht auf dem Steuerelement. |

Wenn Sie ein <xref:System.Windows.VisualStateManager?displayProperty=fullName>-Element für das Stammelement einer Steuerelementvorlage definieren, können Sie Animationen auslösen, wenn ein Steuerelement in einen bestimmten Zustand wechselt. Der `VisualStateManager` deklariert, welche Kombinationen von <xref:System.Windows.VisualStateGroup> und <xref:System.Windows.VisualState> überwacht werden. Wenn das Steuerelement einen überwachten Zustand eintritt, wird die von `VisaulStateManager` definierte Animation gestartet.

Der folgende XAML-Code überwacht z. B. den `CommonStates.MouseOver`-Zustand, um die Füllfarbe des Elements mit dem Namen `backgroundElement` zu animieren. Wenn das Steuerelement in den `CommonStates.Normal`-Zustand zurückkehrt, wird die Füllfarbe des Elements mit dem Namen `backgroundElement` wiederhergestellt.

```xaml
<ControlTemplate x:Key="roundbutton" TargetType="Button">
    <Grid>
        <VisualStateManager.VisualStateGroups>
            <VisualStateGroup Name="CommonStates">
                <VisualState Name="Normal">
                    <ColorAnimation Storyboard.TargetName="backgroundElement"
                                    Storyboard.TargetProperty="(Shape.Fill).(SolidColorBrush.Color)"
                                    To="{TemplateBinding Background}"
                                    Duration="0:0:0.3"/>
                </VisualState>
                <VisualState Name="MouseOver">
                    <ColorAnimation Storyboard.TargetName="backgroundElement"
                                    Storyboard.TargetProperty="(Shape.Fill).(SolidColorBrush.Color)"
                                    To="Yellow"
                                    Duration="0:0:0.3"/>
                </VisualState>
            </VisualStateGroup>
        </VisualStateManager.VisualStateGroups>

        ...
```

Weitere Informationen zu Storyboards finden Sie unter [Übersicht über Storyboards](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

## <a name="shared-resources-and-themes"></a>Gemeinsam genutzte Ressourcen und Designs

Eine typische WPF-Anwendung kann über mehrere Benutzeroberflächenressourcen verfügen, die in der gesamten App angewendet werden. Dieser Satz von Ressourcen wird im Ganzen als das Design der App bezeichnet. WPF bietet Unterstützung beim Packen der Benutzeroberflächenressourcen als Design mithilfe eines Ressourcenverzeichnisse, die als <xref:System.Windows.ResourceDictionary>-Klasse gekapselt ist.

WPF-Designs werden mithilfe des Mechanismus für Stile und Vorlagen definiert, der von WPF zum Anpassen der visuellen Objekte eines Elements bereitgestellt wird.

WPF-Designressourcen werden in eingebetteten Ressourcenverzeichnissen gespeichert. Diese Ressourcenverzeichnisse müssen in einer signierten Assembly eingebettet werden und werden entweder in der gleichen Assembly wie der Code selbst oder in einer parallele Assembly eingebettet. Im Fall von „PresentationFramework.dll“ (der Assembly, die WPF-Steuerelemente enthält) befinden sich Designressourcen in einer Reihe von parallelen Assemblys.

Das Design wird zu dem letzten Ort, an dem bei der Suche nach dem Stil eines Elements gesucht wird. In der Regel beginnt die Suche, indem sie die Elementstruktur aufwärts durchläuft und nach einer geeigneten Ressource sucht. Dann wird die Suche in der Ressourcensammlung der App fortgesetzt, und schließlich wird das System abgefragt. Auf diese Weise können App-Entwickler der Stil für alle Objekte auf Struktur- oder Anwendungsebene neu definieren, bevor das Design erreicht wird.

Sie können Ressourcenverzeichnisse als einzelne Dateien definieren, die es Ihnen ermöglichen, ein Design in mehreren Apps wiederzuverwenden. Sie können auch austauschbare Designs erstellen, indem Sie mehrere Ressourcenverzeichnisse definieren, welche dieselben Ressourcentypen bereitstellen, jedoch mit unterschiedlichen Werten. Das Neudefinieren dieser Stile oder anderer Ressourcen auf Anwendungsebene ist die empfohlene Vorgehensweise für das Skinning von Apps.

Um eine Reihe von Ressourcen wie Stile und Vorlagen anwendungsübergreifend freizugeben, können Sie eine XAML-Datei erstellen und ein <xref:System.Windows.ResourceDictionary>-Element definieren, das Verweise auf eine `shared.xaml`-Datei enthält.

```xaml
<ResourceDictionary.MergedDictionaries>
  <ResourceDictionary Source="Shared.xaml" />
</ResourceDictionary.MergedDictionaries>
```

Es ist die gemeinsame Nutzung von `shared.xaml`, die selbst ein <xref:System.Windows.ResourceDictionary>-Element definiert, die eine Reihe von Stil- und Pinselressourcen enthält, die es den Steuerelementen in einer App ermöglichen, ein einheitliches Aussehen aufzuweisen.

Weitere Informationen finden Sie unter [Gemergte Ressourcenverzeichnisse](../../framework/wpf/advanced/merged-resource-dictionaries.md).

Wenn Sie ein Design für Ihr benutzerdefiniertes Steuerelement erstellen, finden Sie im Abschnitt **Definieren von Ressourcen auf Designebene** der [Übersicht über das Erstellen von Steuerelementen](../../framework/wpf/controls/control-authoring-overview.md#defining-resources-at-the-theme-level) weitere Informationen.

## <a name="see-also"></a>Siehe auch

- [Paket-URI in WPF](../../framework/wpf/app-development/pack-uris-in-wpf.md)
- [How to: Suchen von Elementen, die mit einer ControlTemplate generiert wurden](../../framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)
- [Suchen von Elementen, die mit einer DataTemplate generiert wurden](../../framework/wpf/data/how-to-find-datatemplate-generated-elements.md)
