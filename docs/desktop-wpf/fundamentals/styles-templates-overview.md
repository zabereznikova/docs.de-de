---
title: Stile und Vorlagen
description: Erfahren Sie mehr über XAML-Ressourcen in Windows Presentation Foundation (WPF) für .NET Core. Verstehen der Typen von XAML-Ressourcen im Zusammenhang mit Stilen und Designs.
author: thraka
ms.author: adegeo
ms.date: 09/09/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: f845e739ec3cae502d1e4fd6631f987c5364a42e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433097"
---
# <a name="styles-and-templates-in-wpf"></a>Stile und Vorlagen in WPF

Das Styling und die Vorlagenerstellung von Windows Presentation Foundation (WPF) beziehen sich auf eine Reihe von Features, mit denen Entwickler und Designer visuell überzeugende Effekte und ein konsistentes Erscheinungsbild für ihr Produkt erstellen können. Wenn Sie das Erscheinungsbild einer App anpassen, möchten Sie ein starkes Styling- und Vorlagenmodell, das die Wartung und Freigabe des Erscheinungsbilds innerhalb und zwischen Apps ermöglicht. WPF stellt dieses Modell bereit.

Ein weiteres Merkmal des WPF-Stylingmodells ist die Trennung von Präsentation und Logik. Designer können an der Darstellung einer App arbeiten, indem sie nur XAML verwenden, während Entwickler gleichzeitig mit der Programmierlogik arbeiten, indem sie C- oder Visual Basic verwenden.

Diese Übersicht konzentriert sich auf die Styling- und Vorlagenaspekte der App und diskutiert keine Datenbindungskonzepte. Weitere Informationen zur Datenbindung finden Sie unter [Übersicht über die Datenbindung](../data/data-binding-overview.md).

Es ist wichtig, Ressourcen zu verstehen, die die Wiederverwendung von Stilen und Vorlagen ermöglichen. Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](xaml-resources-define.md).

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sample"></a>Beispiel

Der in dieser Übersicht bereitgestellte Beispielcode basiert auf einer [einfachen Foto-Browsing-Anwendung,](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating) die in der folgenden Abbildung gezeigt wird.

![Formatierte ListView](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

In diesem einfachen Foto-Beispiel werden Stile und Vorlagen verwendet, um eine visuell ansprechende Benutzeroberfläche zu erstellen. Das Beispiel <xref:System.Windows.Controls.TextBlock> besteht aus <xref:System.Windows.Controls.ListBox> zwei Elementen und einem Steuerelement, das an eine Liste von Bildern gebunden ist.

Das vollständige Beispiel finden Sie unter [Einführung zum Beispiel zu Stilen und Vorlagen](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="styles"></a>Stile

Sie können sich <xref:System.Windows.Style> eine als bequeme Möglichkeit vorstellen, eine Reihe von Eigenschaftswerten auf mehrere Elemente anzuwenden. Sie können einen Stil für jedes Element <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> verwenden, <xref:System.Windows.Window> das <xref:System.Windows.Controls.Button>von oder von einem oder einem abgeleitet wird.

Die häufigste Möglichkeit zum Deklarieren eines `Resources` Stils ist als Ressource im Abschnitt in einer XAML-Datei. Da Stile Ressourcen sind, befolgen sie die gleichen Bereichsregeln, die für alle Ressourcen gelten. Einfach ausgedrückt, wobei Sie einen Stil deklarieren, wirkt sich darauf aus, wo der Stil angewendet werden kann. Wenn Sie beispielsweise den Stil im Stammelement Ihrer App-Definitions-XAML-Datei deklarieren, kann der Stil an beliebiger Stelle in ihrer App verwendet werden.

Der folgende XAML-Code deklariert z. `TextBlock`B. zwei `TextBlock` Formatvorlagen für eine , eine, die automatisch auf alle Elemente angewendet wird, und eine andere, auf die explizit verwiesen werden muss.

[!code-xaml[SnippetDefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

Hier ist ein Beispiel für die oben deklarierten Stile, die verwendet werden.

[!code-xaml[SnippetTextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

![Formatierte Textblöcke](./media/styles-and-templates-overview/stylingintro-textblocks.png)

Weitere Informationen finden Sie unter [Erstellen eines Stils für ein Steuerelement](styles-templates-create-apply-style.md).

## <a name="controltemplates"></a>ControlTemplates

In WPF <xref:System.Windows.Controls.ControlTemplate> definiert das eines Steuerelements die Darstellung des Steuerelements. Sie können die Struktur und das Erscheinungsbild <xref:System.Windows.Controls.ControlTemplate> eines Steuerelements ändern, indem Sie ein neues Steuerelement definieren und einem Steuerelement zuweisen. In vielen Fällen bieten Vorlagen ihnen genügend Flexibilität, sodass Sie keine eigenen benutzerdefinierten Steuerelemente schreiben müssen.

Für jedes Steuerelement ist eine Standardvorlage der [Control.Template-Eigenschaft](xref:System.Windows.Controls.Control.Template) zugewiesen. Die Vorlage verbindet die visuelle Darstellung des Steuerelements mit den Funktionen des Steuerelements. Da Sie eine Vorlage in XAML definieren, können Sie die Darstellung des Steuerelements ändern, ohne Code zu schreiben. Jede Vorlage ist für ein bestimmtes <xref:System.Windows.Controls.Button>Steuerelement, z. B. eine , konzipiert.

Üblicherweise deklarieren Sie eine `Resources` Vorlage als Ressource im Abschnitt einer XAML-Datei. Wie bei allen Ressourcen gelten scoping-Regeln.

Steuerelementvorlagen sind viel mehr beteiligt als ein Stil. Dies liegt daran, dass die Steuerelementvorlage die visuelle Darstellung des gesamten Steuerelements neu schreibt, während ein Stil einfach Eigenschaftenänderungen auf das vorhandene Steuerelement anwendet. Da jedoch die Vorlage eines Steuerelements durch Festlegen der [Control.Template-Eigenschaft](xref:System.Windows.Controls.Control.Template) angewendet wird, können Sie eine Vorlage mithilfe eines Stils definieren oder festlegen.

Designer ermöglichen es Ihnen im Allgemeinen, eine Kopie einer vorhandenen Vorlage zu erstellen und zu ändern. Wählen Sie beispielsweise im Visual Studio `CheckBox` WPF-Designer ein Steuerelement aus, und klicken Sie dann mit der rechten Maustaste, und wählen Sie **Vorlage** > erstellen**erstellen**. Dieser Befehl generiert einen Stil, der *eine Vorlage definiert.*

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

Das Bearbeiten einer Kopie einer Vorlage ist eine hervorragende Möglichkeit, um zu erfahren, wie Vorlagen funktionieren. Anstatt eine neue leere Vorlage zu erstellen, ist es einfacher, eine Kopie zu bearbeiten und einige Aspekte der visuellen Präsentation zu ändern.

Ein Beispiel finden Sie unter [Erstellen einer Vorlage für ein Steuerelement](../themes/how-to-create-apply-template.md).

### <a name="templatebinding"></a>TemplateBinding

Möglicherweise haben Sie bemerkt, dass die im vorherigen Abschnitt definierte Vorlagenressource die [TemplateBinding Markup Extension](../../framework/wpf/advanced/templatebinding-markup-extension.md)verwendet. A `TemplateBinding` ist eine optimierte Form einer Bindung für Vorlagenszenarien, analog zu einer Bindung, die mit `{Binding RelativeSource={RelativeSource TemplatedParent}}`erstellt wurde. `TemplateBinding`ist nützlich, um Teile der Vorlage an die Eigenschaften des Steuerelements zu binden. Beispielsweise verfügt jedes Steuerelement <xref:System.Windows.Controls.Control.BorderThickness> über eine Eigenschaft. Verwenden `TemplateBinding` Sie a, um zu verwalten, welches Element in der Vorlage von dieser Steuerelementeinstellung betroffen ist.

### <a name="contentcontrol-and-itemscontrol"></a>ContentControl und ItemsControl

Wenn <xref:System.Windows.Controls.ContentPresenter> a in <xref:System.Windows.Controls.ControlTemplate> der <xref:System.Windows.Controls.ContentControl>deklariert <xref:System.Windows.Controls.ContentPresenter> wird, bindet <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> der <xref:System.Windows.Controls.ContentControl.Content%2A> automatisch an die und-Eigenschaften. Ebenso bindet <xref:System.Windows.Controls.ItemsPresenter> ein, <xref:System.Windows.Controls.ControlTemplate> das <xref:System.Windows.Controls.ItemsControl> sich im eines <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> <xref:System.Windows.Controls.ItemsControl.Items%2A> befindet, automatisch an die und Eigenschaften.

## <a name="datatemplates"></a>Datatemplates

In dieser Beispiel-App <xref:System.Windows.Controls.ListBox> gibt es ein Steuerelement, das an eine Liste von Fotos gebunden ist.

[!code-xaml[ListBox](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window3.xaml#SnippetListBox)]

Dies <xref:System.Windows.Controls.ListBox> sieht derzeit wie folgt aus.

![ListBox vor dem Anwenden einer Vorlage](./media/styles-and-templates-overview/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")

Die meisten Steuerelemente verfügen über Inhalte, und dieser Inhalt stammt häufig aus Daten, an die Sie binden. In diesem Beispiel sind die Daten die Liste der Fotos. In WPF definieren <xref:System.Windows.DataTemplate> Sie die visuelle Darstellung von Daten. Grundsätzlich bestimmt das, <xref:System.Windows.DataTemplate> was Sie in eine setzen, wie die Daten in der gerenderten App aussehen.

In unserer Beispiel-App `Photo` verfügt `Source` jedes benutzerdefinierte Objekt über eine Eigenschaft vom Typ string, die den Dateipfad des Bildes angibt. Derzeit werden die Fotoobjekte als Dateipfade angezeigt.

[!code-csharp[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Photo.cs#PhotoClass)]
[!code-vb[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/Photo.vb#PhotoClass)]

Damit die Fotos als Bilder angezeigt <xref:System.Windows.DataTemplate> werden, erstellen Sie eine als Ressource.

[!code-xaml[DataTemplate](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window4.xaml#SnippetDataTemplate)]

Beachten Sie, dass <xref:System.Windows.DataTemplate.DataType%2A> die <xref:System.Windows.Style.TargetType%2A> Eigenschaft <xref:System.Windows.Style>der Eigenschaft des ähnelt. Wenn <xref:System.Windows.DataTemplate> Sie sich im Ressourcenabschnitt befinden, wird, wenn Sie die <xref:System.Windows.DataTemplate.DataType%2A> Eigenschaft für einen Typ angeben und a `x:Key`auslassen, der <xref:System.Windows.DataTemplate> angewendet, wenn dieser Typ angezeigt wird. Sie haben immer die <xref:System.Windows.DataTemplate> Möglichkeit, `x:Key` die mit einem `StaticResource` zuzuweisen <xref:System.Windows.DataTemplate> und dann als <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> eine <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> für Eigenschaften festzulegen, die Typen annehmen, z. B. die Eigenschaft oder die Eigenschaft.

Im Wesentlichen <xref:System.Windows.DataTemplate> definiert das im obigen Beispiel, dass jedes Mal, wenn ein `Photo` Objekt vorhanden ist, es als innerhalb <xref:System.Windows.Controls.Image> einer <xref:System.Windows.Controls.Border>angezeigt werden sollte. <xref:System.Windows.DataTemplate>Damit sieht unsere App nun so aus.

![Fotobild](./media/styles-and-templates-overview/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")

Das Datenvorlagenmodell stellt weitere Funktionen bereit. Wenn Sie z. B. Sammlungsdaten anzeigen, die <xref:System.Windows.Controls.Menu> andere <xref:System.Windows.Controls.TreeView>Sammlungen mit <xref:System.Windows.HierarchicalDataTemplate>einem <xref:System.Windows.Controls.HeaderedItemsControl> Typ wie einem oder einem enthalten, gibt es die . Eine weitere Daten-Templating-Funktion ist die , mit der <xref:System.Windows.Controls.DataTemplateSelector>Sie eine <xref:System.Windows.DataTemplate> basierend auf benutzerdefinierter Logik auswählen können. Weitere Informationen finden Sie unter im Artikel [Übersicht über Datenvorlagen](../../framework/wpf/data/data-templating-overview.md), der eine ausführlichere Erläuterung der verschiedenen Vorlagenfunktionen bereitstellt.

## <a name="triggers"></a>Trigger

Ein Trigger legt Eigenschaften fest oder startet Aktionen, z.B. eine Animation, wenn sich ein Eigenschaftswert ändert oder ein Ereignis ausgelöst wird. <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>und <xref:System.Windows.DataTemplate> alle `Triggers` verfügen über eine Eigenschaft, die eine Reihe von Triggern enthalten kann. Es gibt mehrere Arten von Triggern.

### <a name="propertytriggers"></a>PropertyTriggers

A, <xref:System.Windows.Trigger> das Eigenschaftswerte festlegt oder Aktionen basierend auf dem Wert einer Eigenschaft startet, wird als Eigenschaftstrigger bezeichnet.

Um die Verwendung von Eigenschaftstriggern <xref:System.Windows.Controls.ListBoxItem> zu veranschaulichen, können Sie jede einzelne teilweise transparent machen, sofern sie nicht ausgewählt ist. Der folgende Stil <xref:System.Windows.UIElement.Opacity%2A> legt <xref:System.Windows.Controls.ListBoxItem> den `0.5`Wert von a bis fest. Wenn <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> die `true`Eigenschaft jedoch <xref:System.Windows.UIElement.Opacity%2A> ist, `1.0`wird die auf festgelegt.

[!code-xaml[PropertyTrigger](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window5.xaml#SnippetPropertyTrigger)]

In diesem <xref:System.Windows.Trigger> Beispiel wird ein verwendet, um <xref:System.Windows.Trigger> einen Eigenschaftswert festzulegen, aber beachten Sie, dass die Klasse auch über die und <xref:System.Windows.TriggerBase.EnterActions%2A> <xref:System.Windows.TriggerBase.ExitActions%2A> Eigenschaften verfügt, die einen Trigger zum Ausführen von Aktionen ermöglichen.

Beachten Sie, dass die <xref:System.Windows.FrameworkElement.MaxHeight%2A> `75`Eigenschaft des auf festgelegt <xref:System.Windows.Controls.ListBoxItem> ist. In der folgenden Abbildung ist das dritte Element das ausgewählte Element.

![Formatierte ListView](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

### <a name="eventtriggers-and-storyboards"></a>EventTrigger und Storyboards

Ein anderer Typ <xref:System.Windows.EventTrigger>von Triggern ist der , der eine Reihe von Aktionen basierend auf dem Auftreten eines Ereignisses startet. Die <xref:System.Windows.EventTrigger> folgenden Objekte geben z. B. an, <xref:System.Windows.FrameworkElement.MaxHeight%2A> dass die Eigenschaft, `90` wenn `0.2` der Mauszeiger in den <xref:System.Windows.Controls.ListBoxItem>eingibt, mit einem Wert von über einem zweiten Zeitraum animiert wird. Wenn sich die Maus vom Element weg bewegt, gibt die Eigenschaft auf den ursprünglichen Wert über einen Zeitraum von `1` Sekunden an. Beachten Sie, dass es <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> nicht erforderlich <xref:System.Windows.ContentElement.MouseLeave> ist, einen Wert für die Animation anzugeben. Dies liegt daran, dass die Animation den ursprünglichen Wert nachverfolgen kann.

[!code-xaml[StyleEventTriggers](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window6.xaml#SnippetStyleEventTriggers)]

Weitere Informationen finden Sie in der [Storyboards-Übersicht](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

In der folgenden Abbildung zeigt die Maus auf das dritte Element.

![Styling-Beispiel-Screenshot](./media/styles-and-templates-overview/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>MultiTrigger, DataTrigger und MultiDataTrigger

Zusätzlich zu <xref:System.Windows.Trigger> <xref:System.Windows.EventTrigger>und gibt es andere Arten von Triggern. <xref:System.Windows.MultiTrigger>können Sie Eigenschaftswerte basierend auf mehreren Bedingungen festlegen. Sie <xref:System.Windows.DataTrigger> verwenden <xref:System.Windows.MultiDataTrigger> und wenn die Eigenschaft Ihrer Bedingung datengebunden ist.

## <a name="visual-states"></a>Visuelle Zustände

Steuerelemente befinden sich immer in einem bestimmten **Zustand**. Wenn sich die Maus beispielsweise über die Oberfläche eines Steuerelements bewegt, wird `MouseOver`das Steuerelement als in einem gemeinsamen Zustand von betrachtet. Ein Steuerelement ohne einen bestimmten Zustand wird `Normal` als im gemeinsamen Zustand betrachtet. Staaten werden in Gruppen aufgeteilt, und die zuvor `CommonStates`genannten Staaten sind Teil der Staatsgruppe . Die meisten Steuerelemente `CommonStates` haben `FocusStates`zwei Statusgruppen: und . Von jeder Statusgruppe, die auf ein Steuerelement angewendet wird, befindet `CommonStates.MouseOver` `FocusStates.Unfocused`sich ein Steuerelement immer in einem Zustand jeder Gruppe, z. B. und . Ein Steuerelement kann sich jedoch nicht in zwei verschiedenen Zuständen innerhalb derselben Gruppe befinden, z. `CommonStates.Normal` B. und `CommonStates.Disabled`. Hier ist eine Tabelle der Zustände, die die meisten Steuerelemente erkennen und verwenden.

| VisualState-Name | VisualStateGroup-Name | BESCHREIBUNG |
| ---------------- | --------------------- | ----------- |
| Normal           | CommonStates          | Der Standardzustand |
| MouseOver        | CommonStates          | Der Mauszeiger ist über dem Steuerelement positioniert. |
| Gedrückt          | CommonStates          | Das Steuerelement wird gedrückt. |
| Disabled         | CommonStates          | Das Steuerelement ist deaktiviert. |
| Mit Fokus          | FocusStates           | Der Fokus liegt auf dem Steuerelement. |
| Ohne Fokus        | FocusStates           | Der Fokus liegt nicht auf dem Steuerelement. |

Durch Definieren <xref:System.Windows.VisualStateManager?displayProperty=fullName> eines im Stammelement einer Steuerelementvorlage können Sie Animationen auslösen, wenn ein Steuerelement in einen bestimmten Zustand wechselt. Der `VisualStateManager` erklärt, welche <xref:System.Windows.VisualStateGroup> <xref:System.Windows.VisualState> Kombinationen von und zu beobachten. Wenn das Steuerelement in einen überwachten `VisaulStateManager` Zustand wechselt, wird die von der definierte Animation gestartet.

Der folgende XAML-Code überwacht `CommonStates.MouseOver` z. B. den Status, um die Füllfarbe des Elements mit dem Namen zu `backgroundElement`animieren. Wenn das Steuerelement `CommonStates.Normal` in den Zustand zurückkehrt, `backgroundElement` wird die Füllfarbe des benannten Elements wiederhergestellt.

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

Weitere Informationen zu Storyboards finden Sie unter [Storyboards Übersicht](../../framework/wpf/graphics-multimedia/storyboards-overview.md).

## <a name="shared-resources-and-themes"></a>Gemeinsame Ressourcen und Themen

Eine typische WPF-App kann über mehrere UI-Ressourcen verfügen, die in der gesamten App angewendet werden. Zusammen genommen kann dieser Satz von Ressourcen als das Thema für die App betrachtet werden. WPF bietet Unterstützung für das Verpacken von UI-Ressourcen als Design, <xref:System.Windows.ResourceDictionary> indem ein Ressourcenwörterbuch verwendet wird, das als Klasse gekapselt ist.

WPF-Designs werden mithilfe des Styling- und Vorlagenmechanismus definiert, den WPF zum Anpassen der Visuellen eines beliebigen Elements verfügbar macht.

WPF-Designressourcen werden in eingebetteten Ressourcenwörterbüchern gespeichert. Diese Ressourcenverzeichnisse müssen in einer signierten Assembly eingebettet werden und werden entweder in der gleichen Assembly wie der Code selbst oder in einer parallele Assembly eingebettet. Für PresentationFramework.dll, die Assembly, die WPF-Steuerelemente enthält, befinden sich Designressourcen in einer Reihe von nebeneinander gerichteten Assemblys.

Das Design wird zu dem letzten Ort, an dem bei der Suche nach dem Stil eines Elements gesucht wird. In der Regel beginnt die Suche mit der Elementstruktur, indem sie nach einer geeigneten Ressource sucht, dann in der App-Ressourcensammlung nachschaut und schließlich das System abfragt. Dies gibt App-Entwicklern die Möglichkeit, den Stil für jedes Objekt auf Baum- oder App-Ebene neu zu definieren, bevor sie das Design erreichen.

Sie können Ressourcenwörterbücher als einzelne Dateien definieren, mit denen Sie ein Design in mehreren Apps wiederverwenden können. Sie können auch austauschbare Designs erstellen, indem Sie mehrere Ressourcenverzeichnisse definieren, welche dieselben Ressourcentypen bereitstellen, jedoch mit unterschiedlichen Werten. Das Neudefinieren dieser Stile oder anderer Ressourcen auf App-Ebene ist der empfohlene Ansatz zum Enthäuten einer App.

Um eine Reihe von Ressourcen, einschließlich Stile und Vorlagen, für alle Apps freizugeben, können Sie eine XAML-Datei erstellen und eine <xref:System.Windows.ResourceDictionary> definieren, die Verweise auf eine `shared.xaml` Datei enthält.

```xaml
<ResourceDictionary.MergedDictionaries>
  <ResourceDictionary Source="Shared.xaml" />
</ResourceDictionary.MergedDictionaries>
```

Es ist die `shared.xaml`Freigabe von , <xref:System.Windows.ResourceDictionary> die selbst eine definiert, die eine Reihe von Stil- und Pinselressourcen enthält, die es den Steuerelementen in einer App ermöglicht, ein konsistentes Aussehen zu haben.

Weitere Informationen finden Sie unter [Zusammengeführte Ressourcenwörterbücher](../../framework/wpf/advanced/merged-resource-dictionaries.md).

Wenn Sie ein Design für Ihr benutzerdefiniertes Steuerelement erstellen, lesen Sie den Abschnitt **Definieren von Ressourcen auf Themaebene** in der Übersicht zur [Steuerelementerstellung](../../framework/wpf/controls/control-authoring-overview.md#defining-resources-at-the-theme-level).

## <a name="see-also"></a>Weitere Informationen

- [Paket-URI in WPF](../../framework/wpf/app-development/pack-uris-in-wpf.md)
- [Vorgehensweise: Suchen von Elementen, die mit einer ControlTemplate generiert wurden](../../framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)
- [Suchen von DataTemplate-generierten Elementen](../../framework/wpf/data/how-to-find-datatemplate-generated-elements.md)
