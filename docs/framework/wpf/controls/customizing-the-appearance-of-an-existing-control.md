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
ms.openlocfilehash: 63a0b724b71c4a4901c2dedcf502045a75ec405c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933730"
---
# <a name="customizing-the-appearance-of-an-existing-control-by-creating-a-controltemplate"></a>Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate
<a name="introduction"></a>Ein <xref:System.Windows.Controls.ControlTemplate> gibt die visuelle Struktur und das visuelle Verhalten eines-Steuer Elements an. Sie können die Darstellung eines Steuer Elements anpassen, indem Sie ihm ein <xref:System.Windows.Controls.ControlTemplate>neues-Element geben. Wenn Sie ein <xref:System.Windows.Controls.ControlTemplate>-Element erstellen, ersetzen Sie die Darstellung eines vorhandenen Steuer Elements, ohne seine Funktionalität zu ändern. Sie können z. b. die Schaltflächen in der Anwendungs Runde anstelle der standardmäßigen quadratischen Form erstellen, aber die Schaltfläche gibt <xref:System.Windows.Controls.Primitives.ButtonBase.Click> immer noch das-Ereignis aus.  
  
 In diesem Thema <xref:System.Windows.Controls.ControlTemplate>werden die verschiedenen Teile eines erläutert, das Erstellen eines <xref:System.Windows.Controls.ControlTemplate> einfachen für <xref:System.Windows.Controls.Button>eine erläutert und erläutert, wie Sie den Steuerelement Vertrag eines Steuer Elements verstehen, damit Sie seine Darstellung anpassen können. Da Sie einen <xref:System.Windows.Controls.ControlTemplate> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]erstellen, können Sie die Darstellung eines Steuer Elements ändern, ohne Code schreiben zu müssen. Benutzerdefinierte Steuerelementvorlagen können Sie auch mit Designern erstellen, z.B. mit dem Microsoft Expression Blend. Dieses Thema zeigt Beispiele in der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , die die Darstellung <xref:System.Windows.Controls.Button> eines anpassen und das gesamte Beispiel am Ende des Themas auflistet. Weitere Informationen zum Verwenden von Expression Blend finden Sie unter [Formatieren eines Steuerelements, das Vorlagen unterstützt](https://go.microsoft.com/fwlink/?LinkId=161153).  
  
 Die folgenden Abbildungen zeigen einen <xref:System.Windows.Controls.Button> , der das <xref:System.Windows.Controls.ControlTemplate> verwendet, das in diesem Thema erstellt wird.  
  
 ![Eine Schaltfläche mit einer benutzerdefinierten Steuerelement Vorlage.](./media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet  
  
 ![Eine Schaltfläche mit einem roten Rahmen.](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet, und über der sich ein Mauszeiger befindet.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Voraussetzungen  
 Es wird vorausgesetzt, dass Sie sich mit dem Erstellen und mit der Verwendung von Steuerelementen und Formaten auskennen. Anweisungen dazu finden Sie unter [Steuerelemente](index.md). Die in diesem Thema erläuterten Konzepte gelten für Elemente, die von <xref:System.Windows.Controls.Control> der-Klasse erben, <xref:System.Windows.Controls.UserControl>mit Ausnahme von. Ein <xref:System.Windows.Controls.ControlTemplate> kann nicht auf ein <xref:System.Windows.Controls.UserControl>angewendet werden.  
  
<a name="when_you_should_create_a_controltemplate"></a>   
## <a name="when-you-should-create-a-controltemplate"></a>Der richtige Zeitpunkt für das Erstellen einer ControlTemplate  
 -Steuerelemente verfügen über viele Eigenschaften <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>z. <xref:System.Windows.Controls.Control.FontFamily%2A>b., und, die Sie festlegen können, um verschiedene Aspekte der Darstellung des Steuer Elements anzugeben. die Änderungen, die Sie vornehmen können, indem Sie diese Eigenschaften festlegen, sind jedoch begrenzt. Beispielsweise können Sie die <xref:System.Windows.Controls.Control.Foreground%2A> -Eigenschaft auf blau und <xref:System.Windows.Controls.Control.FontStyle%2A> auf eine <xref:System.Windows.Controls.CheckBox>kursiv festlegen.  
  
 Ohne die Möglichkeit, eine neue <xref:System.Windows.Controls.ControlTemplate> für-Steuerelemente zu erstellen, würden alle Steuerelemente in jeder [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierten Anwendung dieselbe allgemeine Darstellung aufweisen, was die Möglichkeit zum Erstellen einer Anwendung mit einem benutzerdefinierten Erscheinungsbild einschränken würde. Standardmäßig hat jede <xref:System.Windows.Controls.CheckBox> ähnliche Merkmale. Beispielsweise <xref:System.Windows.Controls.CheckBox> befindet sich der Inhalt von immer rechts neben dem Auswahl Indikator, und das Häkchen wird immer verwendet, um anzugeben <xref:System.Windows.Controls.CheckBox> , dass ausgewählt ist.  
  
 Sie erstellen eine <xref:System.Windows.Controls.ControlTemplate> , wenn Sie die Darstellung des Steuer Elements nach dem Festlegen der anderen Eigenschaften im Steuerelement anpassen möchten. Angenommen, Sie möchten, dass sich der Inhalt des Kontrollkästchens über dem Auswahl Indikator <xref:System.Windows.Controls.CheckBox> befindet, und Sie möchten, dass ein X anzeigt, dass ausgewählt ist. <xref:System.Windows.Controls.CheckBox> Diese Änderungen werden in der <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.CheckBox>von angegeben.  
  
 Die folgende Abbildung zeigt einen <xref:System.Windows.Controls.CheckBox> , der einen Standard <xref:System.Windows.Controls.ControlTemplate>Wert verwendet.  
  
 ![Ein Kontrollkästchen mit der Standard Steuerelement Vorlage.](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
Ein Kontrollkästchen, das die Standardsteuerelementvorlage verwendet  
  
 Die folgende Abbildung zeigt einen <xref:System.Windows.Controls.CheckBox> , der einen Benutzer <xref:System.Windows.Controls.ControlTemplate> definierten verwendet, um den Inhalt <xref:System.Windows.Controls.CheckBox> der oberhalb des Auswahl Indikators zu platzieren, und <xref:System.Windows.Controls.CheckBox> ein X anzeigt, wenn der ausgewählt wird.  
  
 ![Ein Kontrollkästchen mit einer benutzerdefinierten Steuerelement Vorlage.](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
Ein Kontrollkästchen, das eine benutzerdefinierte Steuerelementvorlage verwendet  
  
 Der <xref:System.Windows.Controls.ControlTemplate> für den <xref:System.Windows.Controls.CheckBox> in diesem Beispiel ist relativ komplex. Daher wird in diesem Thema ein einfacheres Beispiel für <xref:System.Windows.Controls.ControlTemplate> das Erstellen <xref:System.Windows.Controls.Button>eines für ein verwendet.  
  
<a name="changing_the_visual_structure_of_a_control"></a>   
## <a name="changing-the-visual-structure-of-a-control"></a>Ändern der visuellen Struktur eines Steuerelements  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]handelt es sich bei einem Steuerelement <xref:System.Windows.FrameworkElement> oft um zusammengesetzte Objekte. Wenn Sie ein <xref:System.Windows.Controls.ControlTemplate>erstellen, werden Objekte <xref:System.Windows.FrameworkElement> kombiniert, um ein einzelnes Steuerelement zu erstellen. Ein <xref:System.Windows.Controls.ControlTemplate> darf nur einen <xref:System.Windows.FrameworkElement> als Stamm Element aufweisen. Das Stamm Element enthält normalerweise <xref:System.Windows.FrameworkElement> andere Objekte. Die visuelle Struktur wird durch die Kombination dieser Objekte bestimmt.  
  
 Im folgenden Beispiel wird eine Benutzer <xref:System.Windows.Controls.ControlTemplate> definierte <xref:System.Windows.Controls.Button>für erstellt. Der <xref:System.Windows.Controls.ControlTemplate> erstellt die visuelle Struktur <xref:System.Windows.Controls.Button>von. In diesem Beispiel wird die Darstellung der Schaltfläche nicht geändert, wenn Sie den Mauszeiger darüber bewegen oder sie anklicken. Das Ändern der Darstellung einer Schaltfläche, die sich in einem anderen Zustand befindet, wird weiter unten in diesem Thema erläutert.  
  
 In diesem Beispiel besteht die visuelle Struktur aus den folgenden Bausteinen:  
  
- Ein <xref:System.Windows.Controls.Border> mit `RootElement` dem Namen, der <xref:System.Windows.FrameworkElement>als Stamm der Vorlage fungiert.  
  
- Ein <xref:System.Windows.Controls.Grid> , das ein untergeordnetes `RootElement`Element von ist.  
  
- Ein <xref:System.Windows.Controls.ContentPresenter> , der den Inhalt der Schaltfläche anzeigt. Ermöglicht <xref:System.Windows.Controls.ContentPresenter> das Anzeigen eines beliebigen Objekt Typs.  
  
 [!code-xaml[VSMButtonTemplate#BasicTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]  
  
### <a name="preserving-the-functionality-of-a-controls-properties-by-using-templatebinding"></a>Beibehalten der Funktionalität von Steuerelementeigenschaften durch die Verwendung von TemplateBinding  
 Wenn Sie ein neues <xref:System.Windows.Controls.ControlTemplate>erstellen, können Sie auch die öffentlichen Eigenschaften verwenden, um die Darstellung des Steuer Elements zu ändern. Die [TemplateBinding](../advanced/templatebinding-markup-extension.md) -Markup Erweiterung bindet eine Eigenschaft eines Elements, das sich in <xref:System.Windows.Controls.ControlTemplate> der befindet, an eine öffentliche Eigenschaft, die vom-Steuerelement definiert wird. Bei der Verwendung von [TemplateBinding](../advanced/templatebinding-markup-extension.md) können Steuerelementeigenschaften als Parameter der Vorlage fungieren. D.h., beim Festlegen einer Steuerelementeigenschaft wird dieser Wert an das Element mit [TemplateBinding](../advanced/templatebinding-markup-extension.md) übergeben.  
  
 Im folgenden Beispiel wird der Teil des vorangehenden Beispiels wiederholt, in dem die [TemplateBinding](../advanced/templatebinding-markup-extension.md) -Markup Erweiterung verwendet wird, um Eigenschaften <xref:System.Windows.Controls.ControlTemplate> von Elementen in an die öffentlichen Eigenschaften zu binden, die durch die Schaltfläche definiert werden.  
  
 [!code-xaml[VSMButtonTemplate#TemplateBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]  
  
 In diesem Beispiel <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> ist die <xref:System.Windows.Controls.Grid> Eigenschaften Vorlage von an <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>gebunden. Da <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> Vorlagen gebunden ist, können Sie mehrere Schaltflächen erstellen, die dieselbe <xref:System.Windows.Controls.ControlTemplate> verwenden, und <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> für jede Schaltfläche auf verschiedene Werte festlegen. Wenn <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> keine Vorlage an eine Eigenschaft eines Elements <xref:System.Windows.Controls.ControlTemplate>im gebunden war, wirkt sich das Festlegen <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> des einer Schaltfläche nicht auf die Darstellung der Schaltfläche aus.  
  
 Beachten Sie, dass die Namen der beiden Eigenschaften nicht identisch sein müssen. Im <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> vorherigen Beispiel <xref:System.Windows.Controls.Button> ist die-Eigenschaft der-Vorlage <xref:System.Windows.Controls.ContentPresenter>an die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType> -Eigenschaft des gebunden. Dadurch kann der Inhalt der Schaltfläche horizontal positioniert werden. <xref:System.Windows.Controls.ContentPresenter>verfügt nicht über eine-Eigenschaft `HorizontalContentAlignment`mit dem <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> Namen, kann aber <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>an gebunden werden. Stellen Sie sicher, dass die Ziel und Quelleigenschaften dem selben Typ entsprechen, wenn Sie eine Eigenschaft an eine Vorlage binden.  
  
 Die <xref:System.Windows.Controls.Control> -Klasse definiert mehrere Eigenschaften, die von der-Steuerelement Vorlage verwendet werden müssen, um beim Festlegen eine Auswirkung auf das-Steuerelement zu haben. Wie die die-Eigenschaft verwendet,hängtvonder-Eigenschaftab.<xref:System.Windows.Controls.ControlTemplate> Die <xref:System.Windows.Controls.ControlTemplate> -Eigenschaft muss auf eine der folgenden Arten verwendet werden:  
  
- Ein Element in der <xref:System.Windows.Controls.ControlTemplate> Vorlage wird an die-Eigenschaft gebunden.  
  
- Ein Element in der <xref:System.Windows.Controls.ControlTemplate> erbt die-Eigenschaft von einem <xref:System.Windows.FrameworkElement>übergeordneten Element.  
  
 In der folgenden Tabelle werden die visuellen Eigenschaften aufgelistet, die von einem <xref:System.Windows.Controls.Control> -Steuerelement der-Klasse geerbt wurden. In der Tabelle wird außerdem angegeben, ob die standardmäßige Steuerelementvorlage eines Steuerelements den geerbten Eigenschaftswert verwendet, oder ob er vorlagengebunden sein muss.  
  
|Eigenschaft|Verwendete Methode|  
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
  
 In der Tabelle werden nur die visuellen Eigenschaften aufgelistet, <xref:System.Windows.Controls.Control> die von der-Klasse geerbt wurden. Abgesehen von den in der Tabelle aufgeführten Eigenschaften kann ein Steuerelement auch die <xref:System.Windows.FrameworkElement.DataContext%2A>Eigenschaften, <xref:System.Windows.FrameworkElement.Language%2A>und vom übergeordneten Framework- <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> Element erben.  
  
 <xref:System.Windows.Controls.ContentPresenter> Wenn sich der <xref:System.Windows.Controls.ControlTemplate> in einem <xref:System.Windows.Controls.ContentControl>befindet, <xref:System.Windows.Controls.ContentPresenter> bindet auch automatisch an die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> -Eigenschaft und die- <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft. Ebenso bindet ein <xref:System.Windows.Controls.ItemsPresenter> , das sich <xref:System.Windows.Controls.ControlTemplate> im von <xref:System.Windows.Controls.ItemsControl> befindet, automatisch an die- <xref:System.Windows.Controls.ItemsControl.Items%2A> Eigenschaft <xref:System.Windows.Controls.ItemsPresenter> und die-Eigenschaft.  
  
 Im folgenden Beispiel werden zwei Schaltflächen erstellt, <xref:System.Windows.Controls.ControlTemplate> die die verwenden, die im vorherigen Beispiel definiert sind. Im Beispiel werden die <xref:System.Windows.Controls.Control.Background%2A>Eigenschaften <xref:System.Windows.Controls.Control.Foreground%2A>, und <xref:System.Windows.Controls.Control.FontSize%2A> auf den einzelnen Schaltflächen festgelegt. Das Festlegen <xref:System.Windows.Controls.Control.Background%2A> der-Eigenschaft hat einen Effekt, da Sie in der <xref:System.Windows.Controls.ControlTemplate>Vorlage gebunden ist. Obwohl die- <xref:System.Windows.Controls.Control.Foreground%2A> Eigenschaft <xref:System.Windows.Controls.Control.FontSize%2A> und die-Eigenschaft nicht Vorlagen gebunden sind, wirkt sich dies auf die Festlegung aus, da ihre Werte geerbt werden.  
  
 [!code-xaml[VSMButtonTemplate#ButtonDeclaration](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]  
  
 Das Ergebnis des vorhergehenden Beispiels ähnelt der folgenden Abbildung.  
  
 ![Zwei Schaltflächen, eine blaue und eine violette.](./media/ndp-buttontwo.png "NDP_ButtonTwo")  
Zwei Schaltflächen mit unterschiedlichen Hintergrundfarben  
  
<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>   
## <a name="changing-the-appearance-of-a-control-depending-on-its-state"></a>Ändern der Darstellung eines Steuerelements in Abhängigkeit von dessen Zustand  
 Der Unterschied zwischen einer Schaltfläche in der Standarddarstellung und der Schaltfläche aus dem vorhergehenden Beispiel besteht darin, dass die Darstellung der Standardschaltfläche je nach Zustand leicht geändert wird. So wird zum Beispiel die Standarddarstellung der Schaltfläche geändert, wenn sie angeklickt wird, oder wenn sich der Mauszeiger über der Schaltfläche befindet. Obwohl die <xref:System.Windows.Controls.ControlTemplate> Funktionalität eines Steuer Elements nicht ändert, ändert es das visuelle Verhalten des Steuer Elements. Das visuelle Verhalten beschreibt die Darstellung des Steuerelements in bestimmten Zuständen. Betrachten Sie das Schaltflächenbeispiel, um den Unterschied zwischen der Funktionalität und dem visuellen Verhalten besser zu verstehen. Die Funktionalität der Schaltfläche besteht darin, <xref:System.Windows.Controls.Primitives.ButtonBase.Click> das-Ereignis zu erhöhen, wenn darauf geklickt wird, aber das visuelle Verhalten der Schaltfläche besteht darin, die Darstellung zu ändern, wenn darauf gezeigt oder geklickt wird.  
  
 Mit- <xref:System.Windows.VisualState> Objekten können Sie die Darstellung eines-Steuer Elements angeben, wenn es sich in einem bestimmten Zustand befindet. Ein <xref:System.Windows.VisualState> enthält ein <xref:System.Windows.Media.Animation.Storyboard> -Element, das die Darstellung der Elemente in der <xref:System.Windows.Controls.ControlTemplate>ändert. Sie müssen keinen Code schreiben, um dies zu erreichen, da die Logik des Steuer Elements den Zustand mithilfe <xref:System.Windows.VisualStateManager>von ändert. Wenn das Steuerelement in den Zustand eintritt <xref:System.Windows.VisualState.Name%2A?displayProperty=nameWithType> <xref:System.Windows.Media.Animation.Storyboard> , der durch die-Eigenschaft angegeben wird, beginnt. Wenn das Steuerelement den Zustand verlässt, <xref:System.Windows.Media.Animation.Storyboard> wird beendet.  
  
 Das folgende Beispiel zeigt <xref:System.Windows.VisualState> die, die die Darstellung <xref:System.Windows.Controls.Button> eines ändert, wenn sich der Mauszeiger darüber befindet. Der <xref:System.Windows.Media.Animation.Storyboard> ändert die Rahmenfarbe der Schaltfläche durch Ändern der Farbe `BorderBrush`von. Wenn Sie <xref:System.Windows.Controls.ControlTemplate> auf das Beispiel am Anfang dieses Themas verweisen, erinnern Sie sich, dass `BorderBrush` der Name <xref:System.Windows.Media.SolidColorBrush> der ist, die dem <xref:System.Windows.Controls.Border.Background%2A> von <xref:System.Windows.Controls.Border>zugewiesen ist.  
  
 [!code-xaml[VSMButtonTemplate#4](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]  
  
 Die Zustände werden für ein Steuerelement innerhalb des Steuerelementvertrags definiert. Weitere Informationen diesbezüglich finden Sie im weiteren Verlauf dieses Themas unter [Anpassen von anderen Steuerelementen mit Steuerelementverträgen](#customizing_other_controls_by_understanding_the_control_contract). In der folgenden Tabelle sind die Zustände aufgeführt, die für <xref:System.Windows.Controls.Button>die angegeben sind.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|Der Standardzustand|  
|MouseOver|CommonStates|Der Mauszeiger ist über dem Steuerelement positioniert.|  
|Gedrückt|CommonStates|Das Steuerelement wird gedrückt.|  
|Disabled|CommonStates|Das Steuerelement ist deaktiviert.|  
|Focused|FocusStates|Der Fokus liegt auf dem Steuerelement.|  
|Ohne Fokus|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|  
  
 `MouseOver` `Normal` `Pressed` `Disabled` Definiert zwei Statusgruppen: die `CommonStates` Gruppe enthält die Zustände,, und. <xref:System.Windows.Controls.Button> Die Gruppe `FocusStates` enthält die Zustände `Focused` und `Unfocused`. Zustände innerhalb einer Zustandsgruppe schließen sich gegenseitig aus. Das Steuerelement befindet sich immer in genau einem Zustand aus jeder Gruppe. <xref:System.Windows.Controls.Button> Ein kann z. b. den Fokus haben, auch wenn sich der Mauszeiger nicht darüber befindet <xref:System.Windows.Controls.Button> , sodass `Focused` ein im Zustand den `MouseOver`Zustand, `Pressed`oder `Normal` aufweisen kann.  
  
 Objekte werden Objekten hinzugefügt <xref:System.Windows.VisualState>. <xref:System.Windows.VisualStateGroup> Sie fügen <xref:System.Windows.VisualStateGroup> der <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> angefügten-Eigenschaft-Objekte hinzu. Im folgenden Beispiel werden die <xref:System.Windows.VisualState> -Objekte für `Normal` `MouseOver`die Zustände, `Pressed` und definiert, die alle in der `CommonStates` Gruppe sind. Der <xref:System.Windows.VisualState.Name%2A> von jedem <xref:System.Windows.VisualState> entspricht dem Namen in der vorherigen Tabelle. Der Zustand `Disabled` sowie die Zustände der `FocusStates`-Gruppe wurden ausgelassen, um das Beispiel kurz zu halten. Sie werden jedoch vom vollständigen Beispiel am Ende dieses Themas umfasst.  
  
> [!NOTE]
> Stellen Sie sicher, dass <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> Sie die angefügte- <xref:System.Windows.FrameworkElement> Eigenschaft im <xref:System.Windows.Controls.ControlTemplate>Stamm des-Objekts festlegen.  
  
 [!code-xaml[VSMButtonTemplate#VisualStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]  
  
 Das Ergebnis des vorhergehenden Beispiels ähnelt den folgenden Abbildungen.  
  
 ![Eine Schaltfläche mit einer benutzerdefinierten Steuerelement Vorlage.](./media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet  
  
 ![Eine Schaltfläche mit einem roten Rahmen.](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet, wenn darüber sich der Mauszeiger befindet  
  
 ![Der Rahmen ist auf einer gedrückten Schaltfläche transparent.](./media/ndp-buttonpressed.png "NDP_ButtonPressed")  
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet, wenn sie gedrückt wird  
  
 Die visuellen Zustände für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente finden Sie unter [Steuerelementformate und -vorlagen](control-styles-and-templates.md).  
  
<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>   
## <a name="specifying-the-behavior-of-a-control-when-it-transitions-between-states"></a>Festlegen des Steuerelementverhaltens beim Wechsel zwischen Zuständen  
 Im vorhergehenden Beispiel wird die Darstellung der Schaltfläche auch beim Anklicken der Schaltfläche geändert. Diesen Effekt sieht der Nutzer allerdings nicht, falls die Schaltfläche kürzer als eine ganze Sekunde lang gedrückt wird. Standardmäßig wird die Animation nach einer Sekunde sichtbar. Da Benutzer wahrscheinlich in viel kürzerer Zeit auf eine Schaltfläche klicken und diese freigeben, ist das visuelle Feedback nicht wirksam, wenn Sie <xref:System.Windows.Controls.ControlTemplate> die in Ihrem Standardzustand belassen.  
  
 Sie können den Zeitraum angeben, in dem eine Animation ausgeführt wird, um einen reibungslosen Übergang eines Steuer Elements von einem Zustand in einen <xref:System.Windows.VisualTransition> anderen durchzuführen <xref:System.Windows.Controls.ControlTemplate>, indem Sie-Objekte hinzufügen. Wenn Sie einen <xref:System.Windows.VisualTransition>erstellen, geben Sie einen oder mehrere der folgenden Informationen an:  
  
- Die Zeitspanne für einen Wechsel zwischen Zuständen.  
  
- Zusätzliche Änderungen der Darstellung des Steuerelements im Moment des Übergangs.  
  
- Gibt an, <xref:System.Windows.VisualTransition> auf welche Zustände der angewendet wird.  
  
### <a name="specifying-the-duration-of-a-transition"></a>Festlegen der Dauer eines Übergangs  
 Sie können angeben, wie lange ein Übergang dauert, indem <xref:System.Windows.VisualTransition.GeneratedDuration%2A> Sie die-Eigenschaft festlegen. Das vorangehende Beispiel verfügt <xref:System.Windows.VisualState> über einen, der angibt, dass der Rahmen der Schaltfläche transparent wird, wenn die Schaltfläche gedrückt wird, die Animation aber zu lange dauert, wenn die Schaltfläche schnell gedrückt und freigegeben wird. Mit einem <xref:System.Windows.VisualTransition> können Sie angeben, wie lange das Steuerelement für den Übergang in den gedrückten Zustand benötigt wird. Im folgenden Beispiel wird die Zeitspanne für den Übergang in den gedrückten Zustand auf eine Hundertstelsekunde festgelegt.  
  
 [!code-xaml[VSMButtonTemplate#PressedTransition](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]  
  
### <a name="specifying-changes-to-the-controls-appearance-during-a-transition"></a>Festlegen von Änderungen an der Darstellung der Steuerelemente während eines Übergangs  
 Das <xref:System.Windows.VisualTransition> -Element <xref:System.Windows.Media.Animation.Storyboard> enthält ein, das beginnt, wenn das Steuerelement zwischen Zuständen übergeht. Sie können beispielsweise eine bestimmte Animation festlegen, die bei einem Übergang aus dem Zustand `MouseOver` in den Zustand `Normal` angezeigt wird. Im folgenden Beispiel wird eine <xref:System.Windows.VisualTransition> erstellt, die angibt, dass der Rahmen der Schaltfläche, wenn der Benutzer den Mauszeiger von der Schaltfläche weg bewegt, in blau, dann in gelb und dann in schwarz in 1,5 Sekunden wechselt.  
  
 [!code-xaml[VSMButtonTemplate#8](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]  
  
### <a name="specifying-when-a-visualtransition-is-applied"></a>Festlegen der Bedingungen für einen visuellen Übergang  
 Eine <xref:System.Windows.VisualTransition> kann so eingeschränkt werden, dass Sie nur auf bestimmte Zustände angewendet wird, oder Sie kann jedes Mal angewendet werden, wenn das Steuerelement zwischen Zuständen übergeht. Im vorangehenden Beispiel wird der <xref:System.Windows.VisualTransition> angewendet, wenn das-Steuerelement `MouseOver` vom-Zustand in `Normal` den-Zustand wechselt. im obigen Beispiel wird <xref:System.Windows.VisualTransition> der angewendet, wenn das Steuerelement in `Pressed` den Zustand wechselt. Sie schränken durch Festlegen <xref:System.Windows.VisualTransition> der-Eigenschaft und der <xref:System.Windows.VisualTransition.To%2A> - <xref:System.Windows.VisualTransition.From%2A> Eigenschaft ein, wenn angewendet wird. In der folgenden Tabelle sind die Beschränkungsebenen aufgelistet, von der restriktivsten bis zu der am wenigsten restriktiven.  
  
|Art der Einschränkung|From-Wert|To-Wert|  
|-------------------------|-------------------|-----------------|  
|Aus einem angegebenen Zustand in einen anderen angegebenen Zustand|Der Name eines<xref:System.Windows.VisualState>|Der Name eines<xref:System.Windows.VisualState>|  
|Aus einem beliebigen Zustand in einen angegebenen Zustand|Nicht festgelegt|Der Name eines<xref:System.Windows.VisualState>|  
|Aus einem angegebenen Zustand in einen beliebigen Zustand|Der Name eines<xref:System.Windows.VisualState>|Nicht festgelegt|  
|Aus einem beliebigen Zustand in einen beliebigen Zustand|Nicht festgelegt|Nicht festgelegt|  
  
 Sie können mehrere <xref:System.Windows.VisualTransition> -Objekte in einem <xref:System.Windows.VisualStateGroup> -Objekt verwenden, die auf denselben Zustand verweisen, aber Sie werden in der Reihenfolge verwendet, in der die vorherige Tabelle angegeben ist. Im folgenden Beispiel gibt es zwei <xref:System.Windows.VisualTransition> -Objekte. Wenn das `Pressed` Steuerelement vom-Zustand in den `MouseOver` -Zustand übergeht, wird das <xref:System.Windows.VisualTransition.From%2A> <xref:System.Windows.VisualTransition> - <xref:System.Windows.VisualTransition.To%2A> Element verwendet, das sowohl als auch festgelegt ist. Wenn das Steuerelement von einem anderen Zustand als `Pressed` in den Zustand `MouseOver` wechselt, wird der andere Zustand verwendet.  
  
 [!code-xaml[VSMButtonTemplate#7](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]  
  
 Der <xref:System.Windows.VisualStateGroup> verfügt über <xref:System.Windows.VisualStateGroup.Transitions%2A> eine-Eigenschaft, <xref:System.Windows.VisualTransition> die die-Objekte enthält <xref:System.Windows.VisualState> , die auf <xref:System.Windows.VisualStateGroup>die-Objekte in der angewendet werden. Als Autor können Sie beliebig alle <xref:System.Windows.VisualTransition> gewünschten einschließen. <xref:System.Windows.Controls.ControlTemplate> Wenn jedoch die- <xref:System.Windows.VisualTransition.To%2A> Eigenschaft und die-Eigenschaft auf Zustands Namen festgelegt sind, <xref:System.Windows.VisualStateGroup>die nicht <xref:System.Windows.VisualTransition> in der- <xref:System.Windows.VisualTransition.From%2A> Eigenschaft sind, wird der ignoriert.  
  
 Das folgende Beispiel zeigt die <xref:System.Windows.VisualStateGroup> für die `CommonStates`. Im Beispiel wird ein <xref:System.Windows.VisualTransition> für jeden der folgenden Übergänge der Schaltfläche definiert.  
  
- In den Zustand `Pressed`.  
  
- In den Zustand `MouseOver`.  
  
- Aus dem Zustand `Pressed` in den Zustand `MouseOver`.  
  
- Aus dem Zustand `MouseOver` in den Zustand `Normal`.  
  
 [!code-xaml[VSMButtonTemplate#VisualTransitions](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]  
  
<a name="customizing_other_controls_by_understanding_the_control_contract"></a>   
## <a name="customizing-other-controls-by-understanding-the-control-contract"></a>Anpassen von anderen Steuerelementen mit Steuerelementverträgen  
 Ein-Steuerelement, <xref:System.Windows.Controls.ControlTemplate> das ein-Objekt verwendet, um die <xref:System.Windows.FrameworkElement> visuelle Struktur (mithilfe von-Objekten) <xref:System.Windows.VisualState> und visuelles Verhalten (mithilfe von-Objekten) anzugeben, verwendet das Parts-Steuerelement Modell Viele Steuerelemente des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4 verwenden dieses Modell. Die Teile, die <xref:System.Windows.Controls.ControlTemplate> ein Autor beachten muss, werden über den Steuerelement Vertrag kommuniziert. Sobald Sie sich mit den Bausteinen des Steuerelementvertrags auskennen, können Sie die Darstellung beliebiger Steuerelemente anpassen, die das Teilsteuerelementen-Modell verwenden.  
  
 Ein Steuerelementvertrag besteht aus drei Elementen:  
  
- Den visuellen Elementen, die die Logik des Steuerelements verwenden.  
  
- Den Zuständen des Steuerelements und den Gruppen, zu denen die einzelnen Zustände gehören.  
  
- Den öffentlichen Eigenschaften, die die visuelle Darstellung des Steuerelements beeinflussen.  
  
### <a name="visual-elements-in-the-control-contract"></a>Visuelle Elemente im Steuerelementvertrag  
 Manchmal interagiert die Logik eines Steuer Elements mit <xref:System.Windows.FrameworkElement> einem-Element, <xref:System.Windows.Controls.ControlTemplate>das sich in befindet. Das Steuerelement kann z.B. ein Ereignis für ein zugehöriges Element behandeln. Wenn ein Steuerelement erwartet, dass ein <xref:System.Windows.FrameworkElement> bestimmtes in <xref:System.Windows.Controls.ControlTemplate>der gefunden wird, muss es diese Informationen <xref:System.Windows.Controls.ControlTemplate> an den Autor übermitteln. Das-Steuerelement <xref:System.Windows.TemplatePartAttribute> verwendet, um den Typ des erwarteten Elements und den Namen des Elements zu übermitteln. Der <xref:System.Windows.Controls.Button> besitzt <xref:System.Windows.Controls.ComboBox>keine Teile in seinem Steuerelement Vertrag, aber andere Steuerelemente, wie z. b. die, Do. <xref:System.Windows.FrameworkElement>  
  
 Das folgende Beispiel zeigt die <xref:System.Windows.TemplatePartAttribute> -Objekte, die für die <xref:System.Windows.Controls.ComboBox> -Klasse angegeben werden. Die Logik von <xref:System.Windows.Controls.ComboBox> erwartet, dass `PART_EditableTextBox` ein <xref:System.Windows.Controls.TextBox> mit dem Namen <xref:System.Windows.Controls.Primitives.Popup> und `PART_Popup` ein mit <xref:System.Windows.Controls.ControlTemplate>der Bezeichnung in der gefunden werden.  
  
 [!code-csharp[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]  
  
 Das folgende <xref:System.Windows.Controls.ControlTemplate> Beispiel zeigt ein vereinfachtes für das <xref:System.Windows.Controls.ComboBox> -Element, das die Elemente enthält, <xref:System.Windows.TemplatePartAttribute> die von den <xref:System.Windows.Controls.ComboBox> -Objekten der-Klasse angegeben werden.  
  
 [!code-xaml[VSMButtonTemplate#ComboBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]  
  
### <a name="states-in-the-control-contract"></a>Zustände im Steuerelementvertrag  
 Die Zustände eines Steuerelements sind ebenfalls Teil des Steuerelementvertrags. Im Beispiel für das Erstellen <xref:System.Windows.Controls.ControlTemplate> eines für <xref:System.Windows.Controls.Button> einen wird gezeigt, wie die Darstellung eines <xref:System.Windows.Controls.Button> in Abhängigkeit von seinen Zuständen angegeben wird. Sie erstellen ein <xref:System.Windows.VisualState> -Objekt für jeden angegebenen Zustand und <xref:System.Windows.VisualState> platzieren alle-Objekte <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A> , <xref:System.Windows.VisualStateGroup>die ein gemeinsam verwenden, wie unter Ändern des Erscheinungs Bilds eines Steuer Elements in [Abhängigkeit von dessen Status weiter](#changing_the_appearance_of_a_control_depending_on_its_state) oben in diesem Thema beschrieben. Steuerelemente von Drittanbietern sollten Zustände mithilfe <xref:System.Windows.TemplateVisualStateAttribute>von angeben, mit denen Designer-Tools, wie z. b. Expression Blend, die Zustände des Steuer Elements für das Erstellen von Steuerelement Vorlagen verfügbar machen können.  
  
 Den Steuerelementvertrag für Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Steuerelementformate und -vorlagen](control-styles-and-templates.md).  
  
### <a name="properties-in-the-control-contract"></a>Eigenschaften im Steuerelementvertrag  
 Die öffentlichen Eigenschaften, die sich auf das Steuerelement visuell auswirken, sind ebenfalls im Steuerelementvertrag enthalten. Sie können diese Eigenschaften festlegen, um die Darstellung des Steuer Elements zu ändern, ohne <xref:System.Windows.Controls.ControlTemplate>eine neue zu erstellen. Sie können auch die [TemplateBinding](../advanced/templatebinding-markup-extension.md) -Markup Erweiterung verwenden, um Eigenschaften von Elementen in zu binden <xref:System.Windows.Controls.ControlTemplate> , die in den öffentlichen Eigenschaften von definiert <xref:System.Windows.Controls.Button>sind, die durch definiert werden.  
  
 Das folgende Beispiel zeigt den Steuerelementvertrag für die Schaltfläche.  
  
 [!code-csharp[VSMButtonTemplate#ButtonContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]  
  
 Wenn Sie einen <xref:System.Windows.Controls.ControlTemplate>erstellen, ist es oft am einfachsten, mit einem <xref:System.Windows.Controls.ControlTemplate> vorhandenen zu beginnen und Änderungen daran vorzunehmen. Sie können eine der folgenden Aktionen ausführen, um eine vorhandene <xref:System.Windows.Controls.ControlTemplate>zu ändern:  
  
- Verwenden Sie einen Designer, z.B. Expression Blend, der eine grafische Benutzeroberfläche zum Erstellen von Steuerelementvorlagen bereitstellt. Weitere Informationen finden Sie unter [Formatieren eines Steuerelements, das Vorlagen unterstützt](https://go.microsoft.com/fwlink/?LinkId=161153).  
  
- Der Standard <xref:System.Windows.Controls.ControlTemplate> Wert wird angezeigt und bearbeitet. Standard-Steuerelementvorlagen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], finden Sie unter [Default WPF Themes](https://go.microsoft.com/fwlink/?LinkID=158252) (Standard-WPF-Designs).  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>Vollständiges Beispiel  
 Das folgende Beispiel zeigt den <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.ControlTemplate> in diesem Thema erläuterten Vorgang.  
  
 [!code-xaml[VSMButtonTemplate#3](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von Formaten und Vorlagen](styling-and-templating.md)
