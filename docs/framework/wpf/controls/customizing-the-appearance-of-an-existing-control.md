---
title: Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.assetid: 678dd116-43a2-4b8c-82b5-6b826f126e31
ms.openlocfilehash: 6d7401f9614e663351968dc6a2f85548735a176d
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460420"
---
# <a name="customizing-the-appearance-of-an-existing-control-by-creating-a-controltemplate"></a>Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate
<a name="introduction"></a>Ein-<xref:System.Windows.Controls.ControlTemplate> das die visuelle Struktur und das visuelle Verhalten eines-Steuer Elements angibt. Sie können die Darstellung eines Steuer Elements anpassen, indem Sie ihm eine neue <xref:System.Windows.Controls.ControlTemplate>geben. Wenn Sie eine <xref:System.Windows.Controls.ControlTemplate>erstellen, ersetzen Sie die Darstellung eines vorhandenen Steuer Elements, ohne seine Funktionalität zu ändern. Sie können z. b. die Schaltflächen in der Anwendungs Runde anstelle der standardmäßigen quadratischen Form erstellen, aber die Schaltfläche erhöht weiterhin das <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis.

 In diesem Thema werden die verschiedenen Teile einer <xref:System.Windows.Controls.ControlTemplate>erläutert, das Erstellen eines einfachen <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.Button>erläutert und erläutert, wie Sie den Steuerelement Vertrag eines Steuer Elements verstehen, damit Sie seine Darstellung anpassen können. Da Sie eine <xref:System.Windows.Controls.ControlTemplate> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]erstellen, können Sie die Darstellung eines Steuer Elements ändern, ohne Code schreiben zu müssen. Sie können auch einen Designer, z. b. Blend für Visual Studio, verwenden, um benutzerdefinierte Steuerelement Vorlagen zu erstellen. Dieses Thema zeigt Beispiele in den [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], die die Darstellung eines <xref:System.Windows.Controls.Button> anpassen und das gesamte Beispiel am Ende des Themas auflistet. Weitere Informationen zum Verwenden von Blend für Visual Studio finden Sie unter Formatieren [eines Steuer Elements, das Vorlagen unterstützt](https://go.microsoft.com/fwlink/?LinkId=161153).

 Die folgenden Abbildungen zeigen eine <xref:System.Windows.Controls.Button>, die den in diesem Thema erstellten <xref:System.Windows.Controls.ControlTemplate> verwendet.

 ![Schaltfläche mit einer benutzerdefinierten Steuerelementvorlage.](./media/ndp-buttonnormal.png "NDP_ButtonNormal")
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet

 ![Schaltfläche mit einem roten Rahmen.](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet, und über der sich ein Mauszeiger befindet.

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Erforderliche Voraussetzungen
 Es wird vorausgesetzt, dass Sie sich mit dem Erstellen und mit der Verwendung von Steuerelementen und Formaten auskennen. Anweisungen dazu finden Sie unter [Steuerelemente](index.md). Die in diesem Thema erläuterten Konzepte gelten für Elemente, die von der <xref:System.Windows.Controls.Control>-Klasse erben, mit Ausnahme des <xref:System.Windows.Controls.UserControl>. Eine <xref:System.Windows.Controls.ControlTemplate> kann nicht auf eine <xref:System.Windows.Controls.UserControl>angewendet werden.

<a name="when_you_should_create_a_controltemplate"></a>
## <a name="when-you-should-create-a-controltemplate"></a>Der richtige Zeitpunkt für das Erstellen einer ControlTemplate
 Steuerelemente verfügen über viele Eigenschaften, z. b. <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>und <xref:System.Windows.Controls.Control.FontFamily%2A>, die Sie festlegen können, um verschiedene Aspekte der Darstellung des Steuer Elements anzugeben. die Änderungen, die Sie vornehmen können, indem Sie diese Eigenschaften festlegen, sind jedoch begrenzt. Beispielsweise können Sie die <xref:System.Windows.Controls.Control.Foreground%2A>-Eigenschaft auf Blue festlegen und in einem <xref:System.Windows.Controls.CheckBox>auf kursiv <xref:System.Windows.Controls.Control.FontStyle%2A>.

 Ohne die Möglichkeit, eine neue <xref:System.Windows.Controls.ControlTemplate> für Steuerelemente zu erstellen, hätten alle Steuerelemente in jeder [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]basierten Anwendung dieselbe allgemeine Darstellung, was die Fähigkeit zum Erstellen einer Anwendung mit einem benutzerdefinierten Erscheinungsbild einschränken würde. Standardmäßig hat jede <xref:System.Windows.Controls.CheckBox> ähnliche Merkmale. Beispielsweise befindet sich der Inhalt des <xref:System.Windows.Controls.CheckBox> immer rechts neben dem Auswahl Indikator, und das Häkchen wird immer verwendet, um anzugeben, dass die <xref:System.Windows.Controls.CheckBox> ausgewählt ist.

 Sie erstellen eine <xref:System.Windows.Controls.ControlTemplate>, wenn Sie die Darstellung des Steuer Elements nach dem Festlegen der anderen Eigenschaften im Steuerelement anpassen möchten. Angenommen, Sie möchten, dass der Inhalt des Kontrollkästchens über dem Auswahl Indikator ist, und Sie möchten, dass ein X anzeigt, dass die <xref:System.Windows.Controls.CheckBox> ausgewählt ist. <xref:System.Windows.Controls.CheckBox> Sie geben diese Änderungen in der <xref:System.Windows.Controls.ControlTemplate> des <xref:System.Windows.Controls.CheckBox>an.

 Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.CheckBox>, die einen Standard <xref:System.Windows.Controls.ControlTemplate>verwendet.

 ![Kontrollkästchen mit der Standardsteuerelementvorlage.](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")
Ein Kontrollkästchen, das die Standardsteuerelementvorlage verwendet

 Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.CheckBox>, die eine benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate> verwendet, um den Inhalt des <xref:System.Windows.Controls.CheckBox> über dem Auswahl Indikator zu platzieren, und ein X anzeigt, wenn die <xref:System.Windows.Controls.CheckBox> ausgewählt ist.

 ![Kontrollkästchen mit einer benutzerdefinierten Steuerelementvorlage.](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")
Ein Kontrollkästchen, das eine benutzerdefinierte Steuerelementvorlage verwendet

 Die <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.CheckBox> in diesem Beispiel ist relativ komplex. Daher wird in diesem Thema ein einfacheres Beispiel für das Erstellen eines <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.Button>verwendet.

<a name="changing_the_visual_structure_of_a_control"></a>
## <a name="changing-the-visual-structure-of-a-control"></a>Ändern der visuellen Struktur eines Steuerelements
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]handelt es sich bei einem Steuerelement oft um zusammengesetzte <xref:System.Windows.FrameworkElement> Objekte. Wenn Sie eine <xref:System.Windows.Controls.ControlTemplate>erstellen, kombinieren Sie <xref:System.Windows.FrameworkElement> Objekte, um ein einzelnes Steuerelement zu erstellen. Ein <xref:System.Windows.Controls.ControlTemplate> darf nur über ein <xref:System.Windows.FrameworkElement> als Stamm Element verfügen. Das root-Element enthält normalerweise andere <xref:System.Windows.FrameworkElement>-Objekte. Die visuelle Struktur wird durch die Kombination dieser Objekte bestimmt.

 Im folgenden Beispiel wird eine benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate> für die-<xref:System.Windows.Controls.Button>erstellt. Der <xref:System.Windows.Controls.ControlTemplate> erstellt die visuelle Struktur des <xref:System.Windows.Controls.Button>. In diesem Beispiel wird die Darstellung der Schaltfläche nicht geändert, wenn Sie den Mauszeiger darüber bewegen oder sie anklicken. Das Ändern der Darstellung einer Schaltfläche, die sich in einem anderen Zustand befindet, wird weiter unten in diesem Thema erläutert.

 In diesem Beispiel besteht die visuelle Struktur aus den folgenden Bausteinen:

- Eine <xref:System.Windows.Controls.Border> mit dem Namen `RootElement`, die als Stamm <xref:System.Windows.FrameworkElement>der Vorlage fungiert.

- Eine <xref:System.Windows.Controls.Grid>, die ein untergeordnetes Element von `RootElement`ist.

- Eine <xref:System.Windows.Controls.ContentPresenter>, die den Inhalt der Schaltfläche anzeigt. Der <xref:System.Windows.Controls.ContentPresenter> ermöglicht das Anzeigen eines beliebigen Objekt Typs.

 [!code-xaml[VSMButtonTemplate#BasicTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]

### <a name="preserving-the-functionality-of-a-controls-properties-by-using-templatebinding"></a>Beibehalten der Funktionalität von Steuerelementeigenschaften durch die Verwendung von TemplateBinding
 Wenn Sie einen neuen <xref:System.Windows.Controls.ControlTemplate>erstellen, können Sie weiterhin die öffentlichen Eigenschaften verwenden, um die Darstellung des Steuer Elements zu ändern. Die [TemplateBinding](../advanced/templatebinding-markup-extension.md) -Markup Erweiterung bindet eine Eigenschaft eines Elements, das sich im <xref:System.Windows.Controls.ControlTemplate> befindet, an eine öffentliche Eigenschaft, die vom Steuerelement definiert wird. Bei der Verwendung von [TemplateBinding](../advanced/templatebinding-markup-extension.md) können Steuerelementeigenschaften als Parameter der Vorlage fungieren. D.h., beim Festlegen einer Steuerelementeigenschaft wird dieser Wert an das Element mit [TemplateBinding](../advanced/templatebinding-markup-extension.md) übergeben.

 Im folgenden Beispiel wird der Teil des vorangehenden Beispiels wiederholt, in dem die [TemplateBinding](../advanced/templatebinding-markup-extension.md) -Markup Erweiterung verwendet wird, um Eigenschaften von Elementen im <xref:System.Windows.Controls.ControlTemplate> an öffentliche Eigenschaften zu binden, die durch die Schaltfläche definiert werden.

 [!code-xaml[VSMButtonTemplate#TemplateBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]

 In diesem Beispiel ist die <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType>-Eigenschaften Vorlage der <xref:System.Windows.Controls.Grid> an <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>gebunden. Da <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> Vorlagen gebunden ist, können Sie mehrere Schaltflächen erstellen, die denselben <xref:System.Windows.Controls.ControlTemplate> verwenden, und die <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> auf den einzelnen Schaltflächen auf unterschiedliche Werte festlegen. Wenn <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> keine Vorlage an eine Eigenschaft eines Elements im <xref:System.Windows.Controls.ControlTemplate>gebunden war, hat das Festlegen des <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> einer Schaltfläche keine Auswirkung auf die Darstellung der Schaltfläche.

 Beachten Sie, dass die Namen der beiden Eigenschaften nicht identisch sein müssen. Im vorherigen Beispiel ist die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType>-Eigenschaft des <xref:System.Windows.Controls.Button> Vorlage an die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>-Eigenschaft der <xref:System.Windows.Controls.ContentPresenter>gebunden. Dadurch kann der Inhalt der Schaltfläche horizontal positioniert werden. <xref:System.Windows.Controls.ContentPresenter> verfügt nicht über eine Eigenschaft mit dem Namen `HorizontalContentAlignment`, aber <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> kann an <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>gebunden werden. Stellen Sie sicher, dass die Ziel und Quelleigenschaften dem selben Typ entsprechen, wenn Sie eine Eigenschaft an eine Vorlage binden.

 Die <xref:System.Windows.Controls.Control>-Klasse definiert mehrere Eigenschaften, die von der Steuerelement Vorlage verwendet werden müssen, um beim Festlegen eine Auswirkung auf das Steuerelement zu haben. Die Verwendung der-Eigenschaft durch den <xref:System.Windows.Controls.ControlTemplate> hängt von der-Eigenschaft ab. Die-<xref:System.Windows.Controls.ControlTemplate> muss die-Eigenschaft auf eine der folgenden Arten verwenden:

- Ein Element in der <xref:System.Windows.Controls.ControlTemplate>-Vorlage wird an die-Eigenschaft gebunden.

- Ein-Element im-<xref:System.Windows.Controls.ControlTemplate> erbt die-Eigenschaft von einem übergeordneten <xref:System.Windows.FrameworkElement>.

 In der folgenden Tabelle werden die visuellen Eigenschaften aufgelistet, die von einem Steuerelement der <xref:System.Windows.Controls.Control>-Klasse geerbt wurden. In der Tabelle wird außerdem angegeben, ob die standardmäßige Steuerelementvorlage eines Steuerelements den geerbten Eigenschaftswert verwendet, oder ob er vorlagengebunden sein muss.

|property|Verwendete Methode|
|--------------|------------------|
|<xref:System.Windows.Controls.Control.Background%2A>|Vorlagenbindung|
|<xref:System.Windows.Controls.Control.BorderThickness%2A>|Vorlagenbindung|
|<xref:System.Windows.Controls.Control.BorderBrush%2A>|Vorlagenbindung|
|<xref:System.Windows.Controls.Control.FontFamily%2A>|Eigenschaftenvererbung oder Vorlagenbindung|
|<xref:System.Windows.Controls.Control.FontSize%2A>|Eigenschaftenvererbung oder Vorlagenbindung|
|<xref:System.Windows.Controls.Control.FontStretch%2A>|Eigenschaftenvererbung oder Vorlagenbindung|
|<xref:System.Windows.Controls.Control.FontWeight%2A>|Eigenschaftenvererbung oder Vorlagenbindung|
|<xref:System.Windows.Controls.Control.Foreground%2A>|Eigenschaftenvererbung oder Vorlagenbindung|
|<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>|Vorlagenbindung|
|<xref:System.Windows.Controls.Control.Padding%2A>|Vorlagenbindung|
|<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>|Vorlagenbindung|

 In der Tabelle werden nur die visuellen Eigenschaften aufgelistet, die von der <xref:System.Windows.Controls.Control>-Klasse geerbt wurden. Abgesehen von den in der Tabelle aufgeführten Eigenschaften kann ein Steuerelement auch die Eigenschaften <xref:System.Windows.FrameworkElement.DataContext%2A>, <xref:System.Windows.FrameworkElement.Language%2A>und <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> vom übergeordneten Framework-Element erben.

 Wenn sich die <xref:System.Windows.Controls.ContentPresenter> im <xref:System.Windows.Controls.ControlTemplate> eines <xref:System.Windows.Controls.ContentControl>befindet, werden die <xref:System.Windows.Controls.ContentPresenter> automatisch an die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>-und <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaften gebunden. Ebenso wird eine <xref:System.Windows.Controls.ItemsPresenter>, die sich in der <xref:System.Windows.Controls.ControlTemplate> eines <xref:System.Windows.Controls.ItemsControl> befindet, automatisch an die Eigenschaften <xref:System.Windows.Controls.ItemsControl.Items%2A> und <xref:System.Windows.Controls.ItemsPresenter> gebunden.

 Im folgenden Beispiel werden zwei Schaltflächen erstellt, die die im vorhergehenden Beispiel definierten <xref:System.Windows.Controls.ControlTemplate> verwenden. Im Beispiel werden die Eigenschaften <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>und <xref:System.Windows.Controls.Control.FontSize%2A> auf den einzelnen Schaltflächen festgelegt. Das Festlegen der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft hat einen Effekt, da Sie im <xref:System.Windows.Controls.ControlTemplate>Vorlagen gebunden ist. Obwohl die Eigenschaften <xref:System.Windows.Controls.Control.Foreground%2A> und <xref:System.Windows.Controls.Control.FontSize%2A> nicht Vorlagen gebunden sind, wirkt sich dies auf die Festlegung aus, da ihre Werte geerbt werden.

 [!code-xaml[VSMButtonTemplate#ButtonDeclaration](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]

 Das Ergebnis des vorhergehenden Beispiels ähnelt der folgenden Abbildung.

 ![Zwei Schaltflächen, eine blaue und eine violette.](./media/ndp-buttontwo.png "NDP_ButtonTwo")
Zwei Schaltflächen mit unterschiedlichen Hintergrundfarben

<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>
## <a name="changing-the-appearance-of-a-control-depending-on-its-state"></a>Ändern der Darstellung eines Steuerelements in Abhängigkeit von dessen Zustand
 Der Unterschied zwischen einer Schaltfläche in der Standarddarstellung und der Schaltfläche aus dem vorhergehenden Beispiel besteht darin, dass die Darstellung der Standardschaltfläche je nach Zustand leicht geändert wird. So wird zum Beispiel die Standarddarstellung der Schaltfläche geändert, wenn sie angeklickt wird, oder wenn sich der Mauszeiger über der Schaltfläche befindet. Obwohl das <xref:System.Windows.Controls.ControlTemplate> die Funktionalität eines Steuer Elements nicht ändert, ändert es das visuelle Verhalten des Steuer Elements. Das visuelle Verhalten beschreibt die Darstellung des Steuerelements in bestimmten Zuständen. Betrachten Sie das Schaltflächenbeispiel, um den Unterschied zwischen der Funktionalität und dem visuellen Verhalten besser zu verstehen. Die Funktionalität der Schaltfläche besteht darin, das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>-Ereignis aufzurichten, wenn darauf geklickt wird, aber das visuelle Verhalten der Schaltfläche besteht darin, die Darstellung zu ändern, wenn darauf gezeigt oder geklickt wird.

 Mit <xref:System.Windows.VisualState>-Objekten können Sie die Darstellung eines Steuer Elements angeben, wenn es sich in einem bestimmten Zustand befindet. Ein <xref:System.Windows.VisualState> enthält eine <xref:System.Windows.Media.Animation.Storyboard>, die die Darstellung der Elemente in der <xref:System.Windows.Controls.ControlTemplate>ändert. Sie müssen keinen Code schreiben, um dies zu erreichen, da die Logik des Steuer Elements den Zustand mithilfe des <xref:System.Windows.VisualStateManager>ändert. Wenn das Steuerelement in den Zustand eintritt, der durch die <xref:System.Windows.VisualState.Name%2A?displayProperty=nameWithType>-Eigenschaft angegeben wird, beginnt die <xref:System.Windows.Media.Animation.Storyboard>. Wenn das Steuerelement den Zustand verlässt, wird der <xref:System.Windows.Media.Animation.Storyboard> angehalten.

 Das folgende Beispiel zeigt die <xref:System.Windows.VisualState>, die die Darstellung einer <xref:System.Windows.Controls.Button> ändert, wenn sich der Mauszeiger darüber befindet. Der <xref:System.Windows.Media.Animation.Storyboard> ändert die Rahmenfarbe der Schaltfläche durch Ändern der Farbe des `BorderBrush`. Wenn Sie am Anfang dieses Themas auf das <xref:System.Windows.Controls.ControlTemplate> Beispiel verweisen, erinnern Sie sich, dass `BorderBrush` der Name des <xref:System.Windows.Media.SolidColorBrush> ist, das dem <xref:System.Windows.Controls.Border.Background%2A> der <xref:System.Windows.Controls.Border>zugewiesen ist.

 [!code-xaml[VSMButtonTemplate#4](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]

 Die Zustände werden für ein Steuerelement innerhalb des Steuerelementvertrags definiert. Weitere Informationen diesbezüglich finden Sie im weiteren Verlauf dieses Themas unter [Anpassen von anderen Steuerelementen mit Steuerelementverträgen](#customizing_other_controls_by_understanding_the_control_contract). In der folgenden Tabelle sind die Zustände aufgeführt, die für die <xref:System.Windows.Controls.Button>angegeben werden.

|VisualState-Name|VisualStateGroup-Name|Beschreibung|
|----------------------|---------------------------|-----------------|
|Normal|CommonStates|Der Standardzustand|
|MouseOver|CommonStates|Der Mauszeiger befindet sich auf dem Steuerelement.|
|Gedrückt|CommonStates|Das Steuerelement wird gedrückt.|
|Deaktiviert|CommonStates|Das Steuerelement ist deaktiviert.|
|Mit Fokus|FocusStates|Der Fokus liegt auf dem Steuerelement.|
|Ohne Fokus|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|

 Die <xref:System.Windows.Controls.Button> definiert zwei Statusgruppen: die `CommonStates` Gruppe enthält die Zustände `Normal`, `MouseOver`, `Pressed`und `Disabled`. Die Gruppe `FocusStates` enthält die Zustände `Focused` und `Unfocused`. Zustände innerhalb einer Zustandsgruppe schließen sich gegenseitig aus. Das Steuerelement befindet sich immer in genau einem Zustand aus jeder Gruppe. Beispielsweise kann ein <xref:System.Windows.Controls.Button> den Fokus auch dann haben, wenn sich der Mauszeiger nicht darüber befindet, sodass sich ein <xref:System.Windows.Controls.Button> im `Focused` Zustand im Zustand `MouseOver`, `Pressed`oder `Normal` befinden kann.

 <xref:System.Windows.VisualStateGroup> Objekten fügen Sie <xref:System.Windows.VisualState> Objekte hinzu. Sie fügen <xref:System.Windows.VisualStateGroup> Objekte der angefügten Eigenschaft <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> hinzu. Im folgenden Beispiel werden die <xref:System.Windows.VisualState>-Objekte für die Zustände "`Normal`", "`MouseOver`" und "`Pressed`" definiert, die sich alle in der `CommonStates` Gruppe befinden. Die <xref:System.Windows.VisualState.Name%2A> der einzelnen <xref:System.Windows.VisualState> entspricht dem Namen in der obigen Tabelle. Der Zustand `Disabled` sowie die Zustände der `FocusStates`-Gruppe wurden ausgelassen, um das Beispiel kurz zu halten. Sie werden jedoch vom vollständigen Beispiel am Ende dieses Themas umfasst.

> [!NOTE]
> Stellen Sie sicher, dass Sie die <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> angefügte-Eigenschaft für die Stamm <xref:System.Windows.FrameworkElement> der <xref:System.Windows.Controls.ControlTemplate>festlegen.

 [!code-xaml[VSMButtonTemplate#VisualStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]

 Das Ergebnis des vorhergehenden Beispiels ähnelt den folgenden Abbildungen.

 ![Schaltfläche mit einer benutzerdefinierten Steuerelementvorlage.](./media/ndp-buttonnormal.png "NDP_ButtonNormal")
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet

 ![Schaltfläche mit einem roten Rahmen.](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet, wenn darüber sich der Mauszeiger befindet

 ![Der Rahmen ist beim Klicken auf die Schaltfläche transparent.](./media/ndp-buttonpressed.png "NDP_ButtonPressed")
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet, wenn sie gedrückt wird

 Die visuellen Zustände für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente finden Sie unter [Steuerelementformate und -vorlagen](control-styles-and-templates.md).

<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>
## <a name="specifying-the-behavior-of-a-control-when-it-transitions-between-states"></a>Festlegen des Steuerelementverhaltens beim Wechsel zwischen Zuständen
 Im vorhergehenden Beispiel wird die Darstellung der Schaltfläche auch beim Anklicken der Schaltfläche geändert. Diesen Effekt sieht der Nutzer allerdings nicht, falls die Schaltfläche kürzer als eine ganze Sekunde lang gedrückt wird. Standardmäßig wird die Animation nach einer Sekunde sichtbar. Da Benutzer wahrscheinlich in viel kürzerer Zeit auf eine Schaltfläche klicken und diese freigeben, ist das visuelle Feedback nicht wirksam, wenn Sie die <xref:System.Windows.Controls.ControlTemplate> im Standardzustand belassen.

 Sie können den Zeitraum angeben, in dem eine Animation ausgeführt wird, um einen reibungslosen Übergang eines Steuer Elements von einem Zustand in einen anderen durchzuführen, indem <xref:System.Windows.VisualTransition> Objekte der <xref:System.Windows.Controls.ControlTemplate>hinzugefügt werden. Wenn Sie eine <xref:System.Windows.VisualTransition>erstellen, geben Sie mindestens eine der folgenden Informationen an:

- Die Zeitspanne für einen Wechsel zwischen Zuständen.

- Zusätzliche Änderungen der Darstellung des Steuerelements im Moment des Übergangs.

- Gibt an, auf welchen Status der <xref:System.Windows.VisualTransition> angewendet wird.

### <a name="specifying-the-duration-of-a-transition"></a>Festlegen der Dauer eines Übergangs
 Sie können angeben, wie lange ein Übergang dauert, indem Sie die <xref:System.Windows.VisualTransition.GeneratedDuration%2A>-Eigenschaft festlegen. Das vorangehende Beispiel weist eine <xref:System.Windows.VisualState> auf, die angibt, dass der Rahmen der Schaltfläche transparent wird, wenn die Schaltfläche gedrückt wird, die Animation aber zu lange dauert, wenn die Schaltfläche schnell gedrückt und freigegeben wird. Mit einem <xref:System.Windows.VisualTransition> können Sie angeben, wie lange das Steuerelement für den Übergang in den gedrückten Zustand benötigt wird. Im folgenden Beispiel wird die Zeitspanne für den Übergang in den gedrückten Zustand auf eine Hundertstelsekunde festgelegt.

 [!code-xaml[VSMButtonTemplate#PressedTransition](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]

### <a name="specifying-changes-to-the-controls-appearance-during-a-transition"></a>Festlegen von Änderungen an der Darstellung der Steuerelemente während eines Übergangs
 Die <xref:System.Windows.VisualTransition> enthält eine <xref:System.Windows.Media.Animation.Storyboard>, die beginnt, wenn das Steuerelement zwischen Zuständen übergeht. Sie können beispielsweise eine bestimmte Animation festlegen, die bei einem Übergang aus dem Zustand `MouseOver` in den Zustand `Normal` angezeigt wird. Im folgenden Beispiel wird eine <xref:System.Windows.VisualTransition> erstellt, die angibt, dass der Rahmen der Schaltfläche, wenn der Benutzer den Mauszeiger von der Schaltfläche weg bewegt, in blau, dann in gelb und dann in schwarz in 1,5 Sekunden wechselt.

 [!code-xaml[VSMButtonTemplate#8](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]

### <a name="specifying-when-a-visualtransition-is-applied"></a>Festlegen der Bedingungen für einen visuellen Übergang
 Eine <xref:System.Windows.VisualTransition> kann so eingeschränkt werden, dass Sie nur auf bestimmte Zustände angewendet wird, oder Sie kann jedes Mal angewendet werden, wenn das Steuerelement zwischen den Zuständen übergeht. Im vorherigen Beispiel wird der <xref:System.Windows.VisualTransition> angewendet, wenn das Steuerelement vom `MouseOver` Zustand in den `Normal` Zustand wechselt. im obigen Beispiel wird der <xref:System.Windows.VisualTransition> angewendet, wenn das Steuerelement in den `Pressed`-Zustand wechselt. Sie schränken das Anwenden einer <xref:System.Windows.VisualTransition> ein, indem Sie die Eigenschaften <xref:System.Windows.VisualTransition.To%2A> und <xref:System.Windows.VisualTransition.From%2A> festlegen. In der folgenden Tabelle sind die Beschränkungsebenen aufgelistet, von der restriktivsten bis zu der am wenigsten restriktiven.

|Art der Einschränkung|From-Wert|To-Wert|
|-------------------------|-------------------|-----------------|
|Aus einem angegebenen Zustand in einen anderen angegebenen Zustand|Der Name einer <xref:System.Windows.VisualState>|Der Name einer <xref:System.Windows.VisualState>|
|Aus einem beliebigen Zustand in einen angegebenen Zustand|Nicht festgelegt|Der Name einer <xref:System.Windows.VisualState>|
|Aus einem angegebenen Zustand in einen beliebigen Zustand|Der Name einer <xref:System.Windows.VisualState>|Nicht festgelegt|
|Aus einem beliebigen Zustand in einen beliebigen Zustand|Nicht festgelegt|Nicht festgelegt|

 Sie können mehrere <xref:System.Windows.VisualTransition> Objekte in einem <xref:System.Windows.VisualStateGroup> haben, die auf denselben Zustand verweisen, aber Sie werden in der Reihenfolge verwendet, in der die vorherige Tabelle angegeben ist. Im folgenden Beispiel gibt es zwei <xref:System.Windows.VisualTransition>-Objekte. Wenn das Steuerelement vom `Pressed` Zustand in den `MouseOver`-Zustand übergeht, wird der <xref:System.Windows.VisualTransition> verwendet, der sowohl <xref:System.Windows.VisualTransition.From%2A> als auch <xref:System.Windows.VisualTransition.To%2A> festgelegt ist. Wenn das Steuerelement von einem anderen Zustand als `Pressed` in den Zustand `MouseOver` wechselt, wird der andere Zustand verwendet.

 [!code-xaml[VSMButtonTemplate#7](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]

 Der <xref:System.Windows.VisualStateGroup> verfügt über eine <xref:System.Windows.VisualStateGroup.Transitions%2A>-Eigenschaft, die die <xref:System.Windows.VisualTransition>-Objekte enthält, die auf die <xref:System.Windows.VisualState> Objekte im <xref:System.Windows.VisualStateGroup>angewendet werden. Als <xref:System.Windows.Controls.ControlTemplate> Autor können Sie alle gewünschten <xref:System.Windows.VisualTransition> einschließen. Wenn die Eigenschaften <xref:System.Windows.VisualTransition.To%2A> und <xref:System.Windows.VisualTransition.From%2A> jedoch auf Zustands Namen festgelegt sind, die nicht im <xref:System.Windows.VisualStateGroup>sind, wird der <xref:System.Windows.VisualTransition> ignoriert.

 Das folgende Beispiel zeigt die <xref:System.Windows.VisualStateGroup> für die `CommonStates`. Im Beispiel wird eine <xref:System.Windows.VisualTransition> für jeden der folgenden Übergänge der Schaltfläche definiert.

- In den Zustand `Pressed`.

- In den Zustand `MouseOver`.

- Aus dem Zustand `Pressed` in den Zustand `MouseOver`.

- Aus dem Zustand `MouseOver` in den Zustand `Normal`.

 [!code-xaml[VSMButtonTemplate#VisualTransitions](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]

<a name="customizing_other_controls_by_understanding_the_control_contract"></a>
## <a name="customizing-other-controls-by-understanding-the-control-contract"></a>Anpassen von anderen Steuerelementen mit Steuerelementverträgen
 Ein Steuerelement, das eine <xref:System.Windows.Controls.ControlTemplate> zum Angeben der visuellen Struktur (mithilfe <xref:System.Windows.FrameworkElement>-Objekten) und des visuellen Verhaltens (mithilfe <xref:System.Windows.VisualState>-Objekten) verwendet, verwendet das Parts-Steuerelement Modell. Viele Steuerelemente des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4 verwenden dieses Modell. Die Teile, die ein <xref:System.Windows.Controls.ControlTemplate> Autor beachten muss, werden über den Steuerelement Vertrag kommuniziert. Sobald Sie sich mit den Bausteinen des Steuerelementvertrags auskennen, können Sie die Darstellung beliebiger Steuerelemente anpassen, die das Teilsteuerelementen-Modell verwenden.

 Ein Steuerelementvertrag besteht aus drei Elementen:

- Den visuellen Elementen, die die Logik des Steuerelements verwenden.

- Den Zuständen des Steuerelements und den Gruppen, zu denen die einzelnen Zustände gehören.

- Den öffentlichen Eigenschaften, die die visuelle Darstellung des Steuerelements beeinflussen.

### <a name="visual-elements-in-the-control-contract"></a>Visuelle Elemente im Steuerelementvertrag
 Manchmal interagiert die Logik eines Steuer Elements mit einer <xref:System.Windows.FrameworkElement>, die sich in der <xref:System.Windows.Controls.ControlTemplate>befindet. Das Steuerelement kann z.B. ein Ereignis für ein zugehöriges Element behandeln. Wenn ein Steuerelement erwartet, dass ein bestimmtes <xref:System.Windows.FrameworkElement> im <xref:System.Windows.Controls.ControlTemplate>gefunden wird, muss es die Informationen an den <xref:System.Windows.Controls.ControlTemplate> Autor übermitteln. Das-Steuerelement verwendet die <xref:System.Windows.TemplatePartAttribute>, um den Typ des erwarteten Elements und den Namen des Elements zu übermitteln. Der <xref:System.Windows.Controls.Button> verfügt nicht über <xref:System.Windows.FrameworkElement> Teile in seinem Steuerelement Vertrag, aber andere Steuerelemente, wie z. b. die <xref:System.Windows.Controls.ComboBox>,.

 Im folgenden Beispiel werden die <xref:System.Windows.TemplatePartAttribute>-Objekte gezeigt, die für die <xref:System.Windows.Controls.ComboBox>-Klasse angegeben sind. In der Logik von <xref:System.Windows.Controls.ComboBox> wird erwartet, dass eine <xref:System.Windows.Controls.TextBox> mit dem Namen `PART_EditableTextBox` und eine <xref:System.Windows.Controls.Primitives.Popup> mit dem Namen `PART_Popup` im <xref:System.Windows.Controls.ControlTemplate>gefunden werden.

 [!code-csharp[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]

 Das folgende Beispiel zeigt einen vereinfachten <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ComboBox>, die die Elemente enthält, die von den <xref:System.Windows.TemplatePartAttribute>-Objekten der <xref:System.Windows.Controls.ComboBox>-Klasse angegeben werden.

 [!code-xaml[VSMButtonTemplate#ComboBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]

### <a name="states-in-the-control-contract"></a>Zustände im Steuerelementvertrag
 Die Zustände eines Steuerelements sind ebenfalls Teil des Steuerelementvertrags. Im Beispiel für das Erstellen einer <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.Button> wird gezeigt, wie die Darstellung eines <xref:System.Windows.Controls.Button> in Abhängigkeit von seinen Zuständen angegeben wird. Sie erstellen eine <xref:System.Windows.VisualState> für jeden angegebenen Zustand und platzieren alle <xref:System.Windows.VisualState> Objekte, die ein <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A> gemeinsam verwenden, in einer <xref:System.Windows.VisualStateGroup>, wie in [Ändern der Darstellung eines Steuer Elements abhängig von dessen Status weiter](#changing_the_appearance_of_a_control_depending_on_its_state) oben in diesem Thema beschrieben. Steuerelemente von Drittanbietern sollten mithilfe der-<xref:System.Windows.TemplateVisualStateAttribute>Zustände angeben. Dadurch können Designer Tools, wie z. b. die [XAML-Designer](/visualstudio/xaml-tools/designing-xaml-in-visual-studio) in Visual Studio und Blend für Visual Studio, die Zustände des Steuer Elements für das Erstellen von Steuerelement Vorlagen verfügbar machen.

 Den Steuerelementvertrag für Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Steuerelementformate und -vorlagen](control-styles-and-templates.md).

### <a name="properties-in-the-control-contract"></a>Eigenschaften im Steuerelementvertrag
 Die öffentlichen Eigenschaften, die sich auf das Steuerelement visuell auswirken, sind ebenfalls im Steuerelementvertrag enthalten. Sie können diese Eigenschaften festlegen, um die Darstellung des Steuer Elements zu ändern, ohne eine neue <xref:System.Windows.Controls.ControlTemplate>erstellen zu müssen. Sie können die [TemplateBinding](../advanced/templatebinding-markup-extension.md) -Markup Erweiterung auch verwenden, um Eigenschaften von Elementen im <xref:System.Windows.Controls.ControlTemplate> an öffentliche Eigenschaften zu binden, die vom <xref:System.Windows.Controls.Button>definiert werden.

 Das folgende Beispiel zeigt den Steuerelementvertrag für die Schaltfläche.

 [!code-csharp[VSMButtonTemplate#ButtonContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]

 Wenn Sie einen <xref:System.Windows.Controls.ControlTemplate>erstellen, ist es oft am einfachsten, mit einem vorhandenen <xref:System.Windows.Controls.ControlTemplate> zu beginnen und Änderungen daran vorzunehmen. Sie können eine der folgenden Aktionen ausführen, um eine vorhandene <xref:System.Windows.Controls.ControlTemplate>zu ändern:

- Verwenden Sie einen Designer, z. b. Blend für Visual Studio, der eine grafische Benutzeroberfläche zum Erstellen von Steuerelement Vorlagen bereitstellt. Weitere Informationen finden Sie unter [Formatieren eines Steuerelements, das Vorlagen unterstützt](https://go.microsoft.com/fwlink/?LinkId=161153).

- Standard <xref:System.Windows.Controls.ControlTemplate> und bearbeiten. Standard-Steuerelementvorlagen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], finden Sie unter [Default WPF Themes](https://go.microsoft.com/fwlink/?LinkID=158252) (Standard-WPF-Designs).

<a name="complete_example"></a>
## <a name="complete-example"></a>Vollständiges Beispiel
 Das folgende Beispiel zeigt die gesamte <xref:System.Windows.Controls.Button><xref:System.Windows.Controls.ControlTemplate>, die in diesem Thema erläutert wird.

 [!code-xaml[VSMButtonTemplate#3](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]

## <a name="see-also"></a>Siehe auch

- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
