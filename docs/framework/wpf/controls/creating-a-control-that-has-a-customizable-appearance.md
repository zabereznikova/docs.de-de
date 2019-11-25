---
title: Erstellen eines Steuerelements mit einer anpassbaren Darstellung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], customizing
- VisualStateManager [WPF], managing the state of a control
- ControlTemplate [WPF], customizing appearance
- controls [WPF], defining the visual structure and behavior of
- customizing appearance [WPF], ControlTemplate
- managing control states [WPF], VisualStateManager
- VisualStateManager [WPF], best practice
ms.assetid: 9e356d3d-a3d0-4b01-a25f-2d43e4d53fe5
ms.openlocfilehash: d9cf092cf47d4fb70b15033d039777d3279b633a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283573"
---
# <a name="creating-a-control-that-has-a-customizable-appearance"></a>Erstellen eines Steuerelements mit einer anpassbaren Darstellung

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet Ihnen die Möglichkeit, ein Steuerelement zu erstellen, dessen Darstellung angepasst werden kann. Beispielsweise können Sie das Erscheinungsbild eines <xref:System.Windows.Controls.CheckBox> ändern, das über die Durchsetzung der Einstellungs Eigenschaften hinausgeht, indem Sie eine neue <xref:System.Windows.Controls.ControlTemplate>erstellen. Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.CheckBox>, die eine Standard <xref:System.Windows.Controls.ControlTemplate> und eine <xref:System.Windows.Controls.CheckBox> verwendet, die ein benutzerdefiniertes <xref:System.Windows.Controls.ControlTemplate>verwendet.

![Kontrollkästchen mit der Standardsteuerelementvorlage.](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")
Ein Kontrollkästchen, das die Standardsteuerelementvorlage verwendet

![Kontrollkästchen mit einer benutzerdefinierten Steuerelementvorlage.](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")
Ein Kontrollkästchen, das eine benutzerdefinierte Steuerelementvorlage verwendet

Wenn Sie das Modell "Teile und Zustände" befolgen, wenn Sie ein Steuerelement erstellen, kann die Darstellung des Steuer Elements angepasst werden. Designer Tools, wie z. b. Blend für Visual Studio, unterstützen das Modell "Teile und Zustände". Wenn Sie also diesem Modell folgen, kann Ihr Steuerelement in diesen Anwendungs Typen angepasst werden.  In diesem Thema werden das Modell der Teile und Zustände erläutert und erläutert, wie es befolgt wird, wenn Sie ein eigenes Steuerelement erstellen. In diesem Thema wird ein Beispiel für ein benutzerdefiniertes Steuerelement (`NumericUpDown`) verwendet, um die Philosophie dieses Modells zu veranschaulichen.  Das `NumericUpDown` Steuerelement zeigt einen numerischen Wert an, den ein Benutzer erhöhen oder verringern kann, indem er auf die Schaltflächen des Steuer Elements klickt.  Die folgende Abbildung zeigt das `NumericUpDown` Steuerelement, das in diesem Thema erläutert wird.

![Benutzerdefiniertes NumericUpDown-Steuerelement.](./media/ndp-numericupdown.png "NDP_NumericUPDown")
Ein benutzerdefiniertes NumericUpDown-Steuerelement

Dieses Thema enthält folgende Abschnitte:

- [Erforderliche Komponenten](#prerequisites)

- [Teile und Zustände-Modell](#parts_and_states_model)

- [Definieren der visuellen Struktur und des visuellen Verhaltens eines Steuer Elements in einer ControlTemplate](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)

- [Verwenden von Teilen der ControlTemplate im Code](#using_parts_of_the_controltemplate_in_code)

- [Bereitstellen des Steuerungs Vertrags](#providing_the_control_contract)

- [Vervollständigen eines Beispiels](#complete_example)

<a name="prerequisites"></a>

## <a name="prerequisites"></a>Erforderliche Voraussetzungen

In diesem Thema wird davon ausgegangen, dass Sie wissen, wie Sie eine neue <xref:System.Windows.Controls.ControlTemplate> für ein vorhandenes Steuerelement erstellen, mit den Elementen in einem Steuerelement Vertrag vertraut sind und die Konzepte verstehen, die unter [Erstellen einer Vorlage für ein Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element erläutert werden.

> [!NOTE]
> Um ein Steuerelement zu erstellen, dessen Darstellung angepasst werden kann, müssen Sie ein Steuerelement erstellen, das von der <xref:System.Windows.Controls.Control>-Klasse oder einer ihrer Unterklassen außer <xref:System.Windows.Controls.UserControl>erbt.  Ein Steuerelement, das von <xref:System.Windows.Controls.UserControl> erbt, ist ein Steuerelement, das schnell erstellt werden kann, aber keinen <xref:System.Windows.Controls.ControlTemplate> verwendet, und Sie können seine Darstellung nicht anpassen.

<a name="parts_and_states_model"></a>

## <a name="parts-and-states-model"></a>Teile und Zustände-Modell

Das Modell Parts and States gibt an, wie die visuelle Struktur und das visuelle Verhalten eines Steuer Elements definiert werden. Gehen Sie folgendermaßen vor, um das Modell für Teile und Zustände zu befolgen:

- Definieren der visuellen Struktur und des visuellen Verhaltens in der <xref:System.Windows.Controls.ControlTemplate> eines Steuer Elements.

- Befolgen Sie bestimmte bewährte Methoden, wenn die Logik des Steuer Elements mit Teilen der Steuerelement Vorlage interagiert.

- Geben Sie einen Steuerungs Vertrag an, um anzugeben, was in der <xref:System.Windows.Controls.ControlTemplate>enthalten sein soll.

Wenn Sie die visuelle Struktur und das visuelle Verhalten in der <xref:System.Windows.Controls.ControlTemplate> eines Steuer Elements definieren, können Anwendungs Autoren die visuelle Struktur und das visuelle Verhalten Ihres Steuer Elements ändern, indem Sie eine neue <xref:System.Windows.Controls.ControlTemplate> erstellen, anstatt Code zu schreiben.   Sie müssen einen Steuerungs Vertrag bereitstellen, der Anwendungs Autoren mitteilt, welche <xref:System.Windows.FrameworkElement> Objekte und Zustände im <xref:System.Windows.Controls.ControlTemplate>definiert werden sollen. Beachten Sie einige bewährte Methoden, wenn Sie mit den Teilen in der <xref:System.Windows.Controls.ControlTemplate> interagieren, damit das Steuerelement eine unvollständige <xref:System.Windows.Controls.ControlTemplate>ordnungsgemäß behandelt.  Wenn Sie diese drei Prinzipien befolgen, können Anwendungs Autoren eine <xref:System.Windows.Controls.ControlTemplate> für Ihr Steuerelement genauso einfach wie für die Steuerelemente erstellen, die mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ausgeliefert werden.  Diese Empfehlungen werden im folgenden Abschnitt ausführlich erläutert.

<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>

## <a name="defining-the-visual-structure-and-visual-behavior-of-a-control-in-a-controltemplate"></a>Definieren der visuellen Struktur und des visuellen Verhaltens eines Steuer Elements in einer ControlTemplate

Wenn Sie das benutzerdefinierte Steuerelement mithilfe des Modells Teile und Zustände erstellen, definieren Sie die visuelle Struktur und das visuelle Verhalten des Steuer Elements in dessen <xref:System.Windows.Controls.ControlTemplate> und nicht in seiner Logik.  Die visuelle Struktur eines Steuer Elements ist die Zusammensetzung von <xref:System.Windows.FrameworkElement>-Objekten, die das-Steuerelement bilden.  Das visuelle Verhalten ist die Methode, mit der das Steuerelement angezeigt wird, wenn es sich in einem bestimmten Zustand befindet.   Weitere Informationen zum Erstellen einer <xref:System.Windows.Controls.ControlTemplate>, die die visuelle Struktur und das visuelle Verhalten eines-Steuer Elements angibt, finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.

Im Beispiel für das `NumericUpDown` Steuerelement enthält die visuelle Struktur zwei <xref:System.Windows.Controls.Primitives.RepeatButton> Steuerelemente und eine <xref:System.Windows.Controls.TextBlock>.  Wenn Sie diese Steuerelemente im Code des `NumericUpDown`-Steuer Elements hinzufügen, z. b. in Ihrem Konstruktor, können die Positionen dieser Steuerelemente unveränderlich sein.  Anstatt die visuelle Struktur und das visuelle Verhalten des Steuer Elements im Code zu definieren, sollten Sie es im <xref:System.Windows.Controls.ControlTemplate>definieren.  Anschließend können Anwendungsentwickler die Position der Schaltflächen und <xref:System.Windows.Controls.TextBlock> anpassen und angeben, welches Verhalten auftritt, wenn `Value` negativ ist, da der <xref:System.Windows.Controls.ControlTemplate> ersetzt werden kann.

Das folgende Beispiel zeigt die visuelle Struktur des `NumericUpDown`-Steuer Elements, das eine <xref:System.Windows.Controls.Primitives.RepeatButton> zur Erhöhung `Value`, eine <xref:System.Windows.Controls.Primitives.RepeatButton> zum Verringern der `Value`und eine <xref:System.Windows.Controls.TextBlock> zum Anzeigen `Value`enthält.

[!code-xaml[VSMCustomControl#VisualStructure](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]

Ein visuelles Verhalten des `NumericUpDown` Steuer Elements besteht darin, dass sich der Wert in einer roten Schriftart befindet, wenn er negativ ist.  Wenn Sie die <xref:System.Windows.Controls.TextBlock.Foreground%2A> des <xref:System.Windows.Controls.TextBlock> im Code ändern, wenn die `Value` negativ ist, zeigt der `NumericUpDown` immer einen roten negativen Wert an. Sie geben das visuelle Verhalten des Steuer Elements in der <xref:System.Windows.Controls.ControlTemplate> an, indem Sie dem <xref:System.Windows.Controls.ControlTemplate><xref:System.Windows.VisualState> Objekte hinzufügen.  Im folgenden Beispiel werden die <xref:System.Windows.VisualState>-Objekte für die Zustände `Positive` und `Negative` gezeigt.  `Positive` und `Negative` schließen sich gegenseitig aus (das Steuerelement ist immer in genau einem der beiden), sodass die <xref:System.Windows.VisualState> Objekte in einem einzigen <xref:System.Windows.VisualStateGroup>abgelegt werden.  Wenn das Steuerelement in den `Negative` Zustand wechselt, wird der <xref:System.Windows.Controls.TextBlock.Foreground%2A> des <xref:System.Windows.Controls.TextBlock> rot.  Wenn sich das Steuerelement im `Positive` Zustand befindet, wird der <xref:System.Windows.Controls.TextBlock.Foreground%2A> auf seinen ursprünglichen Wert zurückgegeben.  Die Definition von <xref:System.Windows.VisualState> Objekten in einem <xref:System.Windows.Controls.ControlTemplate> wird in [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element ausführlicher erläutert.

> [!NOTE]
> Stellen Sie sicher, dass Sie die <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> angefügte-Eigenschaft für die Stamm <xref:System.Windows.FrameworkElement> der <xref:System.Windows.Controls.ControlTemplate>festlegen.

[!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]

<a name="using_parts_of_the_controltemplate_in_code"></a>

## <a name="using-parts-of-the-controltemplate-in-code"></a>Verwenden von Teilen der ControlTemplate im Code

Ein <xref:System.Windows.Controls.ControlTemplate> Autor kann <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.VisualState> Objekte entweder absichtlich oder versehentlich weglassen, aber die Logik des Steuer Elements benötigt möglicherweise diese Teile, um ordnungsgemäß zu funktionieren. Das Teile-und Status Modell gibt an, dass das Steuerelement für eine <xref:System.Windows.Controls.ControlTemplate>, die <xref:System.Windows.FrameworkElement>-oder <xref:System.Windows.VisualState>-Objekten fehlt, widerstandsfähig sein sollte.  Das Steuerelement sollte keine Ausnahme auslösen oder einen Fehler melden, wenn ein <xref:System.Windows.FrameworkElement>, <xref:System.Windows.VisualState>oder <xref:System.Windows.VisualStateGroup> in der <xref:System.Windows.Controls.ControlTemplate>fehlt. In diesem Abschnitt werden die empfohlenen Vorgehensweisen für die Interaktion mit <xref:System.Windows.FrameworkElement> Objekten und das Verwalten von Zuständen beschrieben.

### <a name="anticipate-missing-frameworkelement-objects"></a>Fehlende FrameworkElement-Objekte erwarten

Wenn Sie <xref:System.Windows.FrameworkElement> Objekte im <xref:System.Windows.Controls.ControlTemplate>definieren, muss die Logik des Steuer Elements ggf. mit einigen interagieren.  Beispielsweise abonniert das `NumericUpDown`-Steuerelement das <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis der Schaltflächen, um `Value` zu vergrößern oder zu verringern, und legt die <xref:System.Windows.Controls.TextBlock.Text%2A>-Eigenschaft des <xref:System.Windows.Controls.TextBlock> auf `Value`fest. Wenn ein benutzerdefiniertes <xref:System.Windows.Controls.ControlTemplate> die <xref:System.Windows.Controls.TextBlock> oder Schaltflächen auslässt, ist es akzeptabel, dass das Steuerelement einige seiner Funktionen verliert, Sie sollten jedoch sicherstellen, dass das Steuerelement keinen Fehler verursacht. Wenn eine <xref:System.Windows.Controls.ControlTemplate> z. b. die Schaltflächen zum Ändern `Value`nicht enthält, verliert der `NumericUpDown` diese Funktionalität, aber eine Anwendung, die die <xref:System.Windows.Controls.ControlTemplate> verwendet, wird weiterhin ausgeführt.

Mit den folgenden Vorgehensweisen wird sichergestellt, dass das Steuerelement ordnungsgemäß auf fehlende <xref:System.Windows.FrameworkElement> Objekte antwortet:

1. Legen Sie für jede <xref:System.Windows.FrameworkElement>, auf die Sie im Code verweisen müssen, das `x:Name`-Attribut fest.

2. Definieren Sie für jede <xref:System.Windows.FrameworkElement> private Eigenschaften, mit denen Sie interagieren müssen.

3. Abonnieren und kündigen Sie alle Ereignisse an, die Ihr Steuerelement im Set-Accessor der <xref:System.Windows.FrameworkElement>-Eigenschaft behandelt.

4. Legen Sie die <xref:System.Windows.FrameworkElement> Eigenschaften fest, die Sie in Schritt 2 in der <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>-Methode definiert haben. Dies ist der früheste, dass die <xref:System.Windows.FrameworkElement> in der <xref:System.Windows.Controls.ControlTemplate> für das-Steuerelement verfügbar ist. Verwenden Sie den `x:Name` des <xref:System.Windows.FrameworkElement>, um ihn aus dem <xref:System.Windows.Controls.ControlTemplate>zu erhalten.

5. Überprüfen Sie, ob der <xref:System.Windows.FrameworkElement> vor dem Zugriff auf seine Member nicht `null` wird.  Wenn Sie `null`, melden Sie keinen Fehler.

In den folgenden Beispielen wird veranschaulicht, wie das `NumericUpDown`-Steuerelement mit <xref:System.Windows.FrameworkElement> Objekten in Übereinstimmung mit den Empfehlungen in der vorangehenden Liste interagiert.

In dem Beispiel, in dem die visuelle Struktur des `NumericUpDown`-Steuer Elements im <xref:System.Windows.Controls.ControlTemplate>definiert ist, wird für die <xref:System.Windows.Controls.Primitives.RepeatButton>, die vergrößert wird `Value` das `x:Name`-Attribut auf `UpButton`festgelegt.  Im folgenden Beispiel wird eine Eigenschaft mit dem Namen `UpButtonElement` deklariert, die die im <xref:System.Windows.Controls.ControlTemplate>deklarierte <xref:System.Windows.Controls.Primitives.RepeatButton> darstellt. Wenn `UpDownElement` nicht `null`ist, wird vom `set` Accessor zuerst das Abonnieren des <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignisses der Schaltfläche übernommen, dann wird die-Eigenschaft festgelegt, und anschließend wird das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>-Ereignis abonniert. Es ist auch eine Eigenschaft definiert, die hier nicht für den anderen <xref:System.Windows.Controls.Primitives.RepeatButton>, `DownButtonElement`aufgerufen wird.

[!code-csharp[VSMCustomControl#UpButtonProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
[!code-vb[VSMCustomControl#UpButtonProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]

Das folgende Beispiel zeigt die <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> für das `NumericUpDown`-Steuerelement.  Im Beispiel wird die <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>-Methode verwendet, um die <xref:System.Windows.FrameworkElement> Objekte aus der <xref:System.Windows.Controls.ControlTemplate>zu erhalten.  Beachten Sie, dass das Beispiel vor Fällen schützt, in denen <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> eine <xref:System.Windows.FrameworkElement> mit dem angegebenen Namen findet, der nicht den erwarteten Typ hat. Es ist auch eine bewährte Vorgehensweise, Elemente zu ignorieren, die die angegebenen `x:Name` haben, jedoch den falschen Typ aufweisen.

[!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
[!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]

Indem Sie die in den vorherigen Beispielen gezeigten Verfahren befolgen, stellen Sie sicher, dass das Steuerelement weiterhin ausgeführt wird, wenn der <xref:System.Windows.Controls.ControlTemplate> ein <xref:System.Windows.FrameworkElement>fehlt.

### <a name="use-the-visualstatemanager-to-manage-states"></a>Verwenden von VisualStateManager zum Verwalten von Zuständen

Der <xref:System.Windows.VisualStateManager> verfolgt die Zustände eines Steuer Elements nach und führt die erforderliche Logik für den Übergang zwischen Zuständen aus. Wenn Sie <xref:System.Windows.VisualState> Objekte zum <xref:System.Windows.Controls.ControlTemplate>hinzufügen, fügen Sie diese einem <xref:System.Windows.VisualStateGroup> hinzu und fügen den <xref:System.Windows.VisualStateGroup> der angefügten-Eigenschaft des <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> hinzu, damit der <xref:System.Windows.VisualStateManager> darauf zugreifen kann.

Im folgenden Beispiel wird das vorherige Beispiel wiederholt, das die <xref:System.Windows.VisualState>-Objekte zeigt, die den `Positive`-und `Negative` Zuständen des-Steuer Elements entsprechen. Der <xref:System.Windows.Media.Animation.Storyboard> im `Negative`<xref:System.Windows.VisualState> die <xref:System.Windows.Controls.TextBlock.Foreground%2A> des <xref:System.Windows.Controls.TextBlock> rot.   Wenn sich das `NumericUpDown` Steuerelement im `Negative` Zustand befindet, beginnt das Storyboard im `Negative` Zustand.  Anschließend wird der <xref:System.Windows.Media.Animation.Storyboard> im `Negative` Zustand beendet, wenn das Steuerelement wieder in den Zustand `Positive` zurückkehrt.  Die `Positive`<xref:System.Windows.VisualState> muss keine <xref:System.Windows.Media.Animation.Storyboard> enthalten, da die `Negative` die ursprüngliche Farbe zurückgibt, wenn der <xref:System.Windows.Media.Animation.Storyboard> für die <xref:System.Windows.Controls.TextBlock.Foreground%2A> angehalten wird.

[!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]

Beachten Sie, dass dem <xref:System.Windows.Controls.TextBlock> ein Name zugewiesen ist, der <xref:System.Windows.Controls.TextBlock> sich aber nicht im Steuerelement Vertrag für `NumericUpDown` befindet, da die Logik des Steuer Elements nie auf die <xref:System.Windows.Controls.TextBlock>verweist.  Elemente, auf die in der <xref:System.Windows.Controls.ControlTemplate> verwiesen wird, müssen jedoch nicht Teil des Steuerelement Vertrags sein, da eine neue <xref:System.Windows.Controls.ControlTemplate> für das Steuerelement möglicherweise nicht auf dieses Element verweisen muss.  Beispielsweise kann eine Person, die eine neue <xref:System.Windows.Controls.ControlTemplate> für `NumericUpDown` erstellt, nicht angeben, dass `Value` negativ ist, indem die <xref:System.Windows.Controls.Control.Foreground%2A>geändert wird.  In diesem Fall verweist weder der Code noch der <xref:System.Windows.Controls.ControlTemplate> auf die <xref:System.Windows.Controls.TextBlock> nach dem Namen.

Die Logik des Steuer Elements ist dafür verantwortlich, den Zustand des Steuer Elements zu ändern. Das folgende Beispiel zeigt, dass das `NumericUpDown`-Steuerelement die <xref:System.Windows.VisualStateManager.GoToState%2A>-Methode aufruft, um in den `Positive`-Zustand zu wechseln, wenn `Value` 0 oder größer ist, und der `Negative` Zustand, wenn `Value` kleiner als 0 ist.

[!code-csharp[VSMCustomControl#ValueStateChange](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
[!code-vb[VSMCustomControl#ValueStateChange](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]

Die <xref:System.Windows.VisualStateManager.GoToState%2A>-Methode führt die erforderliche Logik aus, um die Storyboards entsprechend zu starten und zu unterbinden. Wenn ein Steuerelement <xref:System.Windows.VisualStateManager.GoToState%2A> aufruft, um seinen Zustand zu ändern, führt der <xref:System.Windows.VisualStateManager> Folgendes aus:

- Wenn die <xref:System.Windows.VisualState>, zu der das Steuerelement <xref:System.Windows.Media.Animation.Storyboard>wird, beginnt das Storyboard. Wenn der <xref:System.Windows.VisualState>, von dem das Steuerelement stammt, über eine <xref:System.Windows.Media.Animation.Storyboard>verfügt, wird das Storyboard beendet.

- Wenn sich das Steuerelement bereits im angegebenen Zustand befindet, <xref:System.Windows.VisualStateManager.GoToState%2A> keine Aktion durch und gibt `true`zurück.

- Wenn der angegebene Status nicht im <xref:System.Windows.Controls.ControlTemplate> `control`vorhanden ist, führt <xref:System.Windows.VisualStateManager.GoToState%2A> keine Aktion aus und gibt `false`zurück.

#### <a name="best-practices-for-working-with-the-visualstatemanager"></a>Bewährte Methoden für die Arbeit mit dem visualstatus Manager

Es wird empfohlen, dass Sie die folgenden Schritte ausführen, um die Zustände Ihres Steuer Elements beizubehalten:

- Verwenden Sie die Eigenschaften, um den Status zu verfolgen.

- Erstellen Sie eine Hilfsmethode, um zwischen Zuständen zu wechseln.

Das `NumericUpDown`-Steuerelement verwendet seine `Value`-Eigenschaft, um zu verfolgen, ob es sich im `Positive` oder `Negative` Zustand befindet.  Das `NumericUpDown`-Steuerelement definiert auch die `Focused` und `UnFocused` Zustände, die die <xref:System.Windows.UIElement.IsFocused%2A>-Eigenschaft nachverfolgt. Wenn Sie Zustände verwenden, die nicht auf natürliche Weise einer Eigenschaft des Steuer Elements entsprechen, können Sie eine private Eigenschaft definieren, um den Status zu verfolgen.

Eine einzelne Methode, die alle Zustände aktualisiert, zentralisiert Aufrufe des <xref:System.Windows.VisualStateManager> und sorgt dafür, dass Ihr Code verwaltbar ist. Das folgende Beispiel zeigt die-Hilfsmethode des `NumericUpDown`-Steuer Elements, `UpdateStates`. Wenn `Value` größer oder gleich 0 ist, befindet sich der <xref:System.Windows.Controls.Control> im `Positive` Zustand.  Wenn `Value` kleiner als 0 ist, befindet sich das Steuerelement im `Negative` Zustand.  Wenn <xref:System.Windows.UIElement.IsFocused%2A> `true`ist, befindet sich das Steuerelement im `Focused` Zustand. Andernfalls befindet er sich im `Unfocused` Zustand.  Das Steuerelement kann `UpdateStates` immer dann aufzurufen, wenn der Zustand geändert werden muss, unabhängig davon, welcher Zustand geändert wird.

[!code-csharp[VSMCustomControl#UpdateStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
[!code-vb[VSMCustomControl#UpdateStates](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]

Wenn Sie einen Zustands Amen an <xref:System.Windows.VisualStateManager.GoToState%2A> übergeben, wenn sich das Steuerelement bereits in diesem Zustand befindet, <xref:System.Windows.VisualStateManager.GoToState%2A> nichts bewirkt, müssen Sie nicht auf den aktuellen Zustand des Steuer Elements überprüfen.  Wenn `Value` z. b. von einer negativen Zahl in eine andere negative Zahl wechselt, wird das Storyboard für den `Negative` Zustand nicht unterbrochen, und dem Benutzer wird keine Änderung im Steuerelement angezeigt.

Der <xref:System.Windows.VisualStateManager> verwendet <xref:System.Windows.VisualStateGroup> Objekte, um zu bestimmen, welcher Zustand beim Abrufen von <xref:System.Windows.VisualStateManager.GoToState%2A>beendet werden soll. Das-Steuerelement ist für jedes <xref:System.Windows.VisualStateGroup>, das in seiner <xref:System.Windows.Controls.ControlTemplate> definiert ist, immer in einem Zustand und verlässt nur einen Status, wenn es vom gleichen <xref:System.Windows.VisualStateGroup>in einen anderen Zustand wechselt. Beispielsweise definiert der <xref:System.Windows.Controls.ControlTemplate> des `NumericUpDown` Steuer Elements die `Positive` und `Negative`<xref:System.Windows.VisualState> Objekte in einer <xref:System.Windows.VisualStateGroup> und die `Focused`-und `Unfocused`Objekte in einer anderen <xref:System.Windows.VisualState>. (Die `Focused` und `Unfocused`<xref:System.Windows.VisualState> im Abschnitt " [Complete example](#complete_example) " in diesem Thema definiert, wenn das Steuerelement vom `Positive` Zustand in den Zustand "`Negative`" wechselt, oder umgekehrt, verbleibt das Steuerelement entweder im `Focused` oder `Unfocused` Zustand.

Es gibt drei typische Orte, an denen sich der Zustand eines Steuer Elements ändern kann:

- Wenn der <xref:System.Windows.Controls.ControlTemplate> auf die <xref:System.Windows.Controls.Control>angewendet wird.

- Wenn eine Eigenschaft geändert wird.

- Wenn ein Ereignis auftritt.

In den folgenden Beispielen wird veranschaulicht, wie der Status des `NumericUpDown`-Steuer Elements in diesen Fällen aktualisiert wird.

Sie sollten den Zustand des Steuer Elements in der <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>-Methode aktualisieren, damit das Steuerelement im richtigen Zustand angezeigt wird, wenn der <xref:System.Windows.Controls.ControlTemplate> angewendet wird. Im folgenden Beispiel wird `UpdateStates` in <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> aufgerufen, um sicherzustellen, dass sich das Steuerelement in den entsprechenden Zuständen befindet.  Nehmen Sie beispielsweise an, dass Sie ein `NumericUpDown`-Steuerelement erstellen und dann seine <xref:System.Windows.Controls.Control.Foreground%2A> auf grün und `Value` auf-5 festlegen.  Wenn Sie `UpdateStates` nicht aufzurufen, wenn die <xref:System.Windows.Controls.ControlTemplate> auf das `NumericUpDown`-Steuerelement angewendet wird, befindet sich das Steuerelement nicht im `Negative` Zustand, und der Wert ist grün anstelle von rot.  Sie müssen `UpdateStates` abrufen, um das Steuerelement in den `Negative` Zustand zu versetzen.

[!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
[!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]

Sie müssen häufig die Zustände eines Steuer Elements aktualisieren, wenn sich eine Eigenschaft ändert. Das folgende Beispiel zeigt die gesamte `ValueChangedCallback`-Methode. Da `ValueChangedCallback` bei `Value` Änderungen aufgerufen wird, ruft die-Methode `UpdateStates` auf, falls `Value` von positiv in negativ oder umgekehrt geändert wurde. Es ist zulässig, `UpdateStates` aufzurufen, wenn `Value` sich ändert, aber positiv oder negativ bleibt, da das Steuerelement in diesem Fall den Status nicht ändert.

[!code-csharp[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
[!code-vb[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]

Möglicherweise müssen Sie auch die Zustände aktualisieren, wenn ein Ereignis auftritt. Das folgende Beispiel zeigt, dass der `NumericUpDown` `UpdateStates` auf dem <xref:System.Windows.Controls.Control> aufruft, um das <xref:System.Windows.UIElement.GotFocus>-Ereignis zu behandeln.

[!code-csharp[VSMCustomControl#OnGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
[!code-vb[VSMCustomControl#OnGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]

Der <xref:System.Windows.VisualStateManager> unterstützt Sie bei der Verwaltung der Zustände Ihres Steuer Elements. Wenn Sie die <xref:System.Windows.VisualStateManager>verwenden, stellen Sie sicher, dass das Steuerelement ordnungsgemäß zwischen den Zuständen übergeht.  Wenn Sie die Empfehlungen befolgen, die in diesem Abschnitt zum Arbeiten mit dem <xref:System.Windows.VisualStateManager>beschrieben werden, bleibt der Code des Steuer Elements lesbar und wartungsfähig.

<a name="providing_the_control_contract"></a>

## <a name="providing-the-control-contract"></a>Bereitstellen des Steuerungs Vertrags

Sie stellen einen Steuerungs Vertrag bereit, damit <xref:System.Windows.Controls.ControlTemplate> Autoren wissen, was in die Vorlage eingefügt werden muss. Ein Steuerelementvertrag besteht aus drei Elementen:

- Den visuellen Elementen, die die Logik des Steuerelements verwenden.

- Den Zuständen des Steuerelements und den Gruppen, zu denen die einzelnen Zustände gehören.

- Den öffentlichen Eigenschaften, die die visuelle Darstellung des Steuerelements beeinflussen.

Eine Person, die eine neue <xref:System.Windows.Controls.ControlTemplate> erstellt, muss wissen, welche <xref:System.Windows.FrameworkElement> Objekte von der Logik des Steuer Elements verwendet werden, welchen Typ jedes Objekt hat und wie der Name ist. Ein <xref:System.Windows.Controls.ControlTemplate> Autor muss auch den Namen jedes möglichen Zustands, in dem sich das Steuerelement befinden kann, und den <xref:System.Windows.VisualStateGroup>, in dem sich der Zustand befindet, kennen.

Wenn Sie zum `NumericUpDown` Beispiel zurückkehren, erwartet das Steuerelement, dass die <xref:System.Windows.Controls.ControlTemplate> über die folgenden <xref:System.Windows.FrameworkElement> Objekte verfügen:

- Eine <xref:System.Windows.Controls.Primitives.RepeatButton> mit dem Namen `UpButton`.

- Eine <xref:System.Windows.Controls.Primitives.RepeatButton> mit dem Namen `DownButton.`

 Das Steuerelement kann die folgenden Zustände aufweisen:

- Im `ValueStates`<xref:System.Windows.VisualStateGroup>

  - `Positive`

  - `Negative`

- Im `FocusStates`<xref:System.Windows.VisualStateGroup>

  - `Focused`

  - `Unfocused`

Um anzugeben, welche <xref:System.Windows.FrameworkElement> Objekte das Steuerelement erwartet, verwenden Sie das <xref:System.Windows.TemplatePartAttribute>, das den Namen und den Typ der erwarteten Elemente angibt.  Um die möglichen Zustände eines Steuer Elements anzugeben, verwenden Sie den <xref:System.Windows.TemplateVisualStateAttribute>, der den Namen des Zustands angibt und <xref:System.Windows.VisualStateGroup>, zu dem er gehört.  Fügen Sie die <xref:System.Windows.TemplatePartAttribute> und <xref:System.Windows.TemplateVisualStateAttribute> in die Klassendefinition des-Steuer Elements ein.

Jede öffentliche Eigenschaft, die sich auf die Darstellung des Steuer Elements auswirkt, ist auch Bestandteil des Steuerelement Vertrags.

Im folgenden Beispiel werden das <xref:System.Windows.FrameworkElement> Objekt und die Zustände für das `NumericUpDown` Steuerelement angegeben.

[!code-csharp[VSMCustomControl#ControlContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
[!code-vb[VSMCustomControl#ControlContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]

<a name="complete_example"></a>

## <a name="complete-example"></a>Vollständiges Beispiel

Im folgenden Beispiel wird die gesamte <xref:System.Windows.Controls.ControlTemplate> für das `NumericUpDown`-Steuerelement dargestellt.

[!code-xaml[VSMCustomControl#NUDTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]

Das folgende Beispiel zeigt die Logik für das `NumericUpDown`.

[!code-csharp[VSMCustomControl#ControlLogic](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
[!code-vb[VSMCustomControl#ControlLogic](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]

## <a name="see-also"></a>Siehe auch

- [Erstellen einer Vorlage für ein Steuerelement](../../../desktop-wpf/themes/how-to-create-apply-template.md)
- [Anpassung von Steuerelementen](control-customization.md)
