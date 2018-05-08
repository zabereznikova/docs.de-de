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
ms.openlocfilehash: bbdc79fabf8dbe344baae66d718d79ac6375db7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="customizing-the-appearance-of-an-existing-control-by-creating-a-controltemplate"></a>Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate
<a name="introduction"></a> Ein <xref:System.Windows.Controls.ControlTemplate> gibt an, die visuelle Struktur und das visuelle Verhalten eines Steuerelements. Sie können die Darstellung eines Steuerelements anpassen, indem Sie ein neues zuweisen <xref:System.Windows.Controls.ControlTemplate>. Beim Erstellen einer <xref:System.Windows.Controls.ControlTemplate>, ersetzen Sie die Darstellung von einem vorhandenen Steuerelement, ohne seine Funktionalität zu ändern. Z. B. möglich die Schaltflächen in der Anwendung anstelle der quadratischen Standardform round, aber die Schaltfläche "" weiterhin löst die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis.  
  
 In diesem Thema wird erläutert, die verschiedenen Bestandteile einer <xref:System.Windows.Controls.ControlTemplate>, veranschaulicht das Erstellen einer einfaches <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.Button>, und erläutert, wie das Steuerelementvertrag eines Steuerelements zu verstehen, sodass Sie dessen Darstellung anpassen können. Da Sie erstellen eine <xref:System.Windows.Controls.ControlTemplate> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können die Darstellung eines Steuerelements ändern, ohne Code schreiben zu müssen. Benutzerdefinierte Steuerelementvorlagen können Sie auch mit Designern erstellen, z.B. mit dem Microsoft Expression Blend. In diesem Thema wird gezeigt, in Beispielen der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , das Anpassen der Darstellung von einer <xref:System.Windows.Controls.Button> und das vollständige Beispiel am Ende dieses Themas aufgeführt. Weitere Informationen zum Verwenden von Expression Blend finden Sie unter [Formatieren eines Steuerelements, das Vorlagen unterstützt](http://go.microsoft.com/fwlink/?LinkId=161153).  
  
 Die folgenden Abbildungen zeigen ein <xref:System.Windows.Controls.Button> , verwendet die <xref:System.Windows.Controls.ControlTemplate> , die in diesem Thema erstellt wird.  
  
 ![Schaltfläche mit einer benutzerdefinierten Steuerelementvorlage. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet  
  
 ![Eine Schaltfläche mit einem roten Rahmen. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet, und über der sich ein Mauszeiger befindet.  
  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Voraussetzungen  
 Es wird vorausgesetzt, dass Sie sich mit dem Erstellen und mit der Verwendung von Steuerelementen und Formaten auskennen. Anweisungen dazu finden Sie unter [Steuerelemente](../../../../docs/framework/wpf/controls/index.md). Die in diesem Thema erläuterten Konzepte gelten auch für Elemente, die von erben die <xref:System.Windows.Controls.Control> -Klasse, mit Ausnahme der <xref:System.Windows.Controls.UserControl>. Sie können nicht angewendet werden eine <xref:System.Windows.Controls.ControlTemplate> auf eine <xref:System.Windows.Controls.UserControl>.  
  
<a name="when_you_should_create_a_controltemplate"></a>   
## <a name="when-you-should-create-a-controltemplate"></a>Der richtige Zeitpunkt für das Erstellen einer ControlTemplate  
 Steuerelemente verfügen über zahlreiche Eigenschaften wie z. B. <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, und <xref:System.Windows.Controls.Control.FontFamily%2A>, die Sie können festlegen, um verschiedene Aspekte der Darstellung des Steuerelements angeben, aber die Änderungen, die Sie vornehmen können, durch Festlegen dieser Eigenschaften sind beschränkt. Sie können z. B. Festlegen der <xref:System.Windows.Controls.Control.Foreground%2A> Eigenschaft Blau und <xref:System.Windows.Controls.Control.FontStyle%2A> auf kursiv auf eine <xref:System.Windows.Controls.CheckBox>.  
  
 Ohne die Fähigkeit zum Erstellen eines neuen <xref:System.Windows.Controls.ControlTemplate> für Steuerelemente, alle Steuerelemente in jeder [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]--basierten Anwendung, die Fähigkeit zum Erstellen einer Anwendung mit einem benutzerdefinierten Aussehen und Verhalten zu begrenzen, würde die gleiche allgemeine Darstellung aufweisen. Standardmäßig jede <xref:System.Windows.Controls.CheckBox> verfügt über ähnliche Merkmale aufweisen. Z. B. den Inhalt der <xref:System.Windows.Controls.CheckBox> ist immer auf der rechten Seite des Indikators, Auswahl, und Sie auf das Häkchen wird immer verwendet, um anzugeben, dass die <xref:System.Windows.Controls.CheckBox> ausgewählt ist.  
  
 Sie erstellen eine <xref:System.Windows.Controls.ControlTemplate> Wenn Sie die Darstellung des Steuerelements hinter festlegen die anderen Eigenschaften tut anpassen möchten. Im Beispiel für die <xref:System.Windows.Controls.CheckBox>, angenommen, Sie wünschen, dass der Inhalt dieses Kontrollkästchen, um über den Auswahlindikator liegen und Sie möchten ein X an, dass die <xref:System.Windows.Controls.CheckBox> ausgewählt ist. Geben Sie diese Änderungen in der <xref:System.Windows.Controls.ControlTemplate> von der <xref:System.Windows.Controls.CheckBox>.  
  
 Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.CheckBox> , verwendet den Standardwert <xref:System.Windows.Controls.ControlTemplate>.  
  
 ![Kontrollkästchen mit der Standardsteuerelementvorlage. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
Ein Kontrollkästchen, das die Standardsteuerelementvorlage verwendet  
  
 Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.CheckBox> , verwendet eine benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate> , platzieren den Inhalt der <xref:System.Windows.Controls.CheckBox> über den Auswahlindikator für die und zeigt ein "X" bei der <xref:System.Windows.Controls.CheckBox> ausgewählt ist.  
  
 ![Kontrollkästchen mit einer benutzerdefinierten Steuerelementvorlage. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
Ein Kontrollkästchen, das eine benutzerdefinierte Steuerelementvorlage verwendet  
  
 Die <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.CheckBox> in diesem Beispiel ist relativ komplex, deshalb in diesem Thema wird, ein einfacheres Beispiel zum Erstellen verwendet einer <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.Button>.  
  
<a name="changing_the_visual_structure_of_a_control"></a>   
## <a name="changing-the-visual-structure-of-a-control"></a>Ändern der visuellen Struktur eines Steuerelements  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ein Steuerelement ist häufig eine zusammengesetzte <xref:System.Windows.FrameworkElement> Objekte. Beim Erstellen einer <xref:System.Windows.Controls.ControlTemplate>, kombinieren Sie <xref:System.Windows.FrameworkElement> Objekte, um ein einzelnes Steuerelement zu erstellen. Ein <xref:System.Windows.Controls.ControlTemplate> benötigen nur einen <xref:System.Windows.FrameworkElement> als Stammelement. Das Stammelement enthält in der Regel andere <xref:System.Windows.FrameworkElement> Objekte. Die visuelle Struktur wird durch die Kombination dieser Objekte bestimmt.  
  
 Das folgende Beispiel erstellt eine benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Button>. Die <xref:System.Windows.Controls.ControlTemplate> erstellt die visuelle Struktur eines der <xref:System.Windows.Controls.Button>. In diesem Beispiel wird die Darstellung der Schaltfläche nicht geändert, wenn Sie den Mauszeiger darüber bewegen oder sie anklicken. Das Ändern der Darstellung einer Schaltfläche, die sich in einem anderen Zustand befindet, wird weiter unten in diesem Thema erläutert.  
  
 In diesem Beispiel besteht die visuelle Struktur aus den folgenden Bausteinen:  
  
-   Ein <xref:System.Windows.Controls.Border> mit dem Namen `RootElement` , dient als Grundlage für die Vorlage Stamm <xref:System.Windows.FrameworkElement>.  
  
-   Ein <xref:System.Windows.Controls.Grid> d. h. ein untergeordnetes Element des `RootElement`.  
  
-   Ein <xref:System.Windows.Controls.ContentPresenter> , die die Schaltfläche Inhalte anzeigt. Die <xref:System.Windows.Controls.ContentPresenter> können jede Art von Objekt angezeigt werden.  
  
 [!code-xaml[VSMButtonTemplate#BasicTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]  
  
### <a name="preserving-the-functionality-of-a-controls-properties-by-using-templatebinding"></a>Beibehalten der Funktionalität von Steuerelementeigenschaften durch die Verwendung von TemplateBinding  
 Beim Erstellen einer neuen <xref:System.Windows.Controls.ControlTemplate>, dennoch empfiehlt die öffentlichen Eigenschaften verwenden, um die Darstellung des Steuerelements zu ändern. Die [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) Markuperweiterung bindet eine Eigenschaft eines Elements, das in der <xref:System.Windows.Controls.ControlTemplate> an eine öffentliche Eigenschaft, die vom Steuerelement definiert ist. Bei der Verwendung von [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) können Steuerelementeigenschaften als Parameter der Vorlage fungieren. D.h., beim Festlegen einer Steuerelementeigenschaft wird dieser Wert an das Element mit [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) übergeben.  
  
 Im folgende Beispiel wird der Teil des vorherigen Beispiels, das verwendet wiederholt der [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) Markuperweiterung Eigenschaften von Elementen zu binden, der in der <xref:System.Windows.Controls.ControlTemplate> auf öffentlichen Eigenschaften, die durch die Schaltfläche definiert werden.  
  
 [!code-xaml[VSMButtonTemplate#TemplateBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]  
  
 In diesem Beispiel wird die <xref:System.Windows.Controls.Grid> hat seine <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> eigenschaftsvorlage gebunden <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>. Da <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> ist Vorlage gebunden werden, können Sie mehrere Schaltflächen, die die gleiche erstellen <xref:System.Windows.Controls.ControlTemplate> und legen Sie die <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> auf jede Schaltfläche unterschiedliche Werte. Wenn <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> wurde nicht von einer Vorlage gebunden an eine Eigenschaft eines Elements in der <xref:System.Windows.Controls.ControlTemplate>wird durch das Festlegen der <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> einer Schaltfläche würde haben keine Auswirkung auf die Darstellung der Schaltfläche.  
  
 Beachten Sie, dass die Namen der beiden Eigenschaften nicht identisch sein müssen. Im vorherigen Beispiel der <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> Eigenschaft von der <xref:System.Windows.Controls.Button> Vorlage gebunden ist die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType> Eigenschaft der <xref:System.Windows.Controls.ContentPresenter>. Dadurch kann der Inhalt der Schaltfläche horizontal positioniert werden. <xref:System.Windows.Controls.ContentPresenter> verfügt nicht über eine Eigenschaft mit dem Namen `HorizontalContentAlignment`, aber <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> gebunden werden kann, um <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>. Stellen Sie sicher, dass die Ziel und Quelleigenschaften dem selben Typ entsprechen, wenn Sie eine Eigenschaft an eine Vorlage binden.  
  
 Die <xref:System.Windows.Controls.Control> Klasse definiert verschiedene Eigenschaften, die von der Steuerelementvorlage verwendet werden müssen, damit sich auf das Steuerelement aus, wenn sie festgelegt wurden. Wie die <xref:System.Windows.Controls.ControlTemplate> verwendet die Eigenschaft hängt von der Eigenschaft. Die <xref:System.Windows.Controls.ControlTemplate> muss die Eigenschaft in einem der folgenden Methoden verwenden:  
  
-   Ein Element in der <xref:System.Windows.Controls.ControlTemplate> Vorlage für die Eigenschaft bindet.  
  
-   Ein Element in der <xref:System.Windows.Controls.ControlTemplate> erbt die Eigenschaft von einem übergeordneten <xref:System.Windows.FrameworkElement>.  
  
 Die folgende Tabelle enthält die visuellen Eigenschaften geerbt, die ein Steuerelement von der <xref:System.Windows.Controls.Control> Klasse. In der Tabelle wird außerdem angegeben, ob die standardmäßige Steuerelementvorlage eines Steuerelements den geerbten Eigenschaftswert verwendet, oder ob er vorlagengebunden sein muss.  
  
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
  
 Die Tabelle enthält nur die visuellen Eigenschaften geerbt von der <xref:System.Windows.Controls.Control> Klasse. Abgesehen von den in der Tabelle aufgeführten Eigenschaften ein Steuerelements kann auch erben die <xref:System.Windows.FrameworkElement.DataContext%2A>, <xref:System.Windows.FrameworkElement.Language%2A>, und <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> Eigenschaften vom Framework übergeordneten Element.  
  
 Auch, wenn die <xref:System.Windows.Controls.ContentPresenter> befindet sich in der <xref:System.Windows.Controls.ControlTemplate> von einer <xref:System.Windows.Controls.ContentControl>, die <xref:System.Windows.Controls.ContentPresenter> automatisch eine Bindung an die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> und <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaften. Ebenso eine <xref:System.Windows.Controls.ItemsPresenter> , die sich in der <xref:System.Windows.Controls.ControlTemplate> von einer <xref:System.Windows.Controls.ItemsControl> automatisch eine Bindung an die <xref:System.Windows.Controls.ItemsControl.Items%2A> und <xref:System.Windows.Controls.ItemsPresenter> Eigenschaften.  
  
 Das folgende Beispiel erstellt zwei Schaltflächen, mit denen die <xref:System.Windows.Controls.ControlTemplate> im vorherigen Beispiel definiert. Im Beispiel wird die <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, und <xref:System.Windows.Controls.Control.FontSize%2A> Eigenschaften auf jeder Schaltfläche. Festlegen der <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft wirkt sich ist Vorlage gebunden, der <xref:System.Windows.Controls.ControlTemplate>. Obwohl die <xref:System.Windows.Controls.Control.Foreground%2A> und <xref:System.Windows.Controls.Control.FontSize%2A> Eigenschaften nicht Vorlage gebunden sind, wird diese Einstellung wirkt sich da ihre Werte geerbt werden.  
  
 [!code-xaml[VSMButtonTemplate#ButtonDeclaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]  
  
 Das Ergebnis des vorhergehenden Beispiels ähnelt der folgenden Abbildung.  
  
 ![Zwei Schaltflächen, eine blaue und eine violette. ] (../../../../docs/framework/wpf/controls/media/ndp-buttontwo.png "NDP_ButtonTwo")  
Zwei Schaltflächen mit unterschiedlichen Hintergrundfarben  
  
<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>   
## <a name="changing-the-appearance-of-a-control-depending-on-its-state"></a>Ändern der Darstellung eines Steuerelements in Abhängigkeit von dessen Zustand  
 Der Unterschied zwischen einer Schaltfläche in der Standarddarstellung und der Schaltfläche aus dem vorhergehenden Beispiel besteht darin, dass die Darstellung der Standardschaltfläche je nach Zustand leicht geändert wird. So wird zum Beispiel die Standarddarstellung der Schaltfläche geändert, wenn sie angeklickt wird, oder wenn sich der Mauszeiger über der Schaltfläche befindet. Obwohl die <xref:System.Windows.Controls.ControlTemplate> ändert sich nicht auf die Funktionalität eines Steuerelements ändert sich das Verhalten des Steuerelements visual. Das visuelle Verhalten beschreibt die Darstellung des Steuerelements in bestimmten Zuständen. Betrachten Sie das Schaltflächenbeispiel, um den Unterschied zwischen der Funktionalität und dem visuellen Verhalten besser zu verstehen. Die Funktionalität der Schaltfläche ist zum Auslösen der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis aus, wenn darauf geklickt wird, aber die Schaltfläche visual Verhalten besteht darin, dessen Darstellung geändert wird, wenn er verweist oder gedrückt.  
  
 Verwenden Sie <xref:System.Windows.VisualState> -Objekten, die Darstellung eines Steuerelements angeben, wenn es in einem bestimmten Zustand befindet. Ein <xref:System.Windows.VisualState> enthält eine <xref:System.Windows.Media.Animation.Storyboard> ändert die Darstellung der Elemente, die in der <xref:System.Windows.Controls.ControlTemplate>. Sie müssen keinen zusätzlichen Code dazu auftreten, da die Logik des Steuerelements mit Zustandsänderungen schreiben, die <xref:System.Windows.VisualStateManager>. Wenn das Steuerelement wechselt in den Status, die von angegeben wird die <xref:System.Windows.VisualState.Name%2A?displayProperty=nameWithType> -Eigenschaft, die <xref:System.Windows.Media.Animation.Storyboard> beginnt. Wenn das Steuerelement den Zustand verlässt den <xref:System.Windows.Media.Animation.Storyboard> beendet.  
  
 Das folgende Beispiel zeigt die <xref:System.Windows.VisualState> , die ändert die Darstellung von einem <xref:System.Windows.Controls.Button> Wenn der Mauszeiger befindet, darauf. Die <xref:System.Windows.Media.Animation.Storyboard> ändert die Rahmenfarbe der Schaltfläche durch Ändern der Farbe der `BorderBrush`. Wenn Sie in finden der <xref:System.Windows.Controls.ControlTemplate> Beispiel am Anfang dieses Themas, erinnern Sie sich `BorderBrush` ist der Name des der <xref:System.Windows.Media.SolidColorBrush> zugewiesen ist, die <xref:System.Windows.Controls.Border.Background%2A> von der <xref:System.Windows.Controls.Border>.  
  
 [!code-xaml[VSMButtonTemplate#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]  
  
 Die Zustände werden für ein Steuerelement innerhalb des Steuerelementvertrags definiert. Weitere Informationen diesbezüglich finden Sie im weiteren Verlauf dieses Themas unter [Anpassen von anderen Steuerelementen mit Steuerelementverträgen](#customizing_other_controls_by_understanding_the_control_contract). Die folgende Tabelle enthält die Zustände, die für die angegeben sind die <xref:System.Windows.Controls.Button>.  
  
|VisualState-Name|VisualStateGroup-Name|Beschreibung|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|Der Standardzustand|  
|MouseOver|CommonStates|Der Mauszeiger ist über dem Steuerelement positioniert.|  
|Gedrückt|CommonStates|Das Steuerelement wird gedrückt.|  
|Deaktiviert|CommonStates|Das Steuerelement ist deaktiviert.|  
|Focused|FocusStates|Der Fokus liegt auf dem Steuerelement.|  
|Ohne Fokus|FocusStates|Der Fokus liegt nicht auf dem Steuerelement.|  
  
 Die <xref:System.Windows.Controls.Button> definiert zwei Statusgruppen: die `CommonStates` Gruppe enthält die `Normal`, `MouseOver`, `Pressed`, und `Disabled` Status. Die Gruppe `FocusStates` enthält die Zustände `Focused` und `Unfocused`. Zustände innerhalb einer Zustandsgruppe schließen sich gegenseitig aus. Das Steuerelement befindet sich immer in genau einem Zustand aus jeder Gruppe. Z. B. eine <xref:System.Windows.Controls.Button> können den Fokus haben, auch wenn der Mauszeiger nicht darauf, also eine <xref:System.Windows.Controls.Button> in der `Focused` kann die `MouseOver`, `Pressed`, oder `Normal` Zustand.  
  
 Sie fügen <xref:System.Windows.VisualState> -Objekte <xref:System.Windows.VisualStateGroup> Objekte. Sie fügen <xref:System.Windows.VisualStateGroup> Datenbankobjekte in der <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> -Eigenschaft. Das folgende Beispiel definiert die <xref:System.Windows.VisualState> von Objekten für die `Normal`, `MouseOver`, und `Pressed` Zustände, die alle in der `CommonStates` Gruppe. Die <xref:System.Windows.VisualState.Name%2A> jedes <xref:System.Windows.VisualState> mit dem Namen in der obigen Tabelle übereinstimmt. Der Zustand `Disabled` sowie die Zustände der `FocusStates`-Gruppe wurden ausgelassen, um das Beispiel kurz zu halten. Sie werden jedoch vom vollständigen Beispiel am Ende dieses Themas umfasst.  
  
> [!NOTE]
>  Achten Sie darauf, dass Sie festlegen der <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> -Eigenschaft auf den Stamm <xref:System.Windows.FrameworkElement> von der <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xaml[VSMButtonTemplate#VisualStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]  
  
 Das Ergebnis des vorhergehenden Beispiels ähnelt den folgenden Abbildungen.  
  
 ![Schaltfläche mit einer benutzerdefinierten Steuerelementvorlage. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet  
  
 ![Eine Schaltfläche mit einem roten Rahmen. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet, wenn darüber sich der Mauszeiger befindet  
  
 ![Der Rahmen ist auf Schaltfläche transparent. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonpressed.png "NDP_ButtonPressed")  
Eine Schaltfläche, die eine benutzerdefinierte Steuerelementvorlage verwendet, wenn sie gedrückt wird  
  
 Die visuellen Zustände für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente finden Sie unter [Steuerelementformate und -vorlagen](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>   
## <a name="specifying-the-behavior-of-a-control-when-it-transitions-between-states"></a>Festlegen des Steuerelementverhaltens beim Wechsel zwischen Zuständen  
 Im vorhergehenden Beispiel wird die Darstellung der Schaltfläche auch beim Anklicken der Schaltfläche geändert. Diesen Effekt sieht der Nutzer allerdings nicht, falls die Schaltfläche kürzer als eine ganze Sekunde lang gedrückt wird. Standardmäßig wird die Animation nach einer Sekunde sichtbar. Da Benutzer wahrscheinlich klicken und eine Schaltfläche in viel weniger Zeit freizugeben, visuelle Feedback werden wirksam, wenn Sie lassen die <xref:System.Windows.Controls.ControlTemplate> im Standardzustand.  
  
 Sie können angeben, dass die Menge an Zeit, die eine Animation für ein Steuerelement von einem Zustand zu einem anderen durch Hinzufügen von reibungslosen Übergang <xref:System.Windows.VisualTransition> -Objekte und die <xref:System.Windows.Controls.ControlTemplate>. Beim Erstellen einer <xref:System.Windows.VisualTransition>, Sie geben eine oder mehrere der folgenden:  
  
-   Die Zeitspanne für einen Wechsel zwischen Zuständen.  
  
-   Zusätzliche Änderungen der Darstellung des Steuerelements im Moment des Übergangs.  
  
-   Welche Zustände der <xref:System.Windows.VisualTransition> auf angewendet wird.  
  
### <a name="specifying-the-duration-of-a-transition"></a>Festlegen der Dauer eines Übergangs  
 Sie können angeben, wie lange dauert ein Übergang durch Festlegen der <xref:System.Windows.VisualTransition.GeneratedDuration%2A> Eigenschaft. Im vorherige Beispiel wurde ein <xref:System.Windows.VisualState> , der angibt, dass die Rahmen der Schaltfläche wird transparent, wenn die Schaltfläche geklickt wird, aber die Animation dauert zu lange bestehen, bemerkbar, wenn die schnell gedrückt und losgelassen wird. Sie können eine <xref:System.Windows.VisualTransition> an die Zeitspanne dauert das Steuerelement für den Übergang in den Zustand "gedrückt". Im folgenden Beispiel wird die Zeitspanne für den Übergang in den gedrückten Zustand auf eine Hundertstelsekunde festgelegt.  
  
 [!code-xaml[VSMButtonTemplate#PressedTransition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]  
  
### <a name="specifying-changes-to-the-controls-appearance-during-a-transition"></a>Festlegen von Änderungen an der Darstellung der Steuerelemente während eines Übergangs  
 Die <xref:System.Windows.VisualTransition> enthält eine <xref:System.Windows.Media.Animation.Storyboard> , die beginnt, wenn das Steuerelement den Zustand wechselt. Sie können beispielsweise eine bestimmte Animation festlegen, die bei einem Übergang aus dem Zustand `MouseOver` in den Zustand `Normal` angezeigt wird. Das folgende Beispiel erstellt eine <xref:System.Windows.VisualTransition> , der angibt, dass bei der Benutzer den Mauszeiger Weg von der Schaltfläche bewegt, Rahmen der Schaltfläche in Blau, dann zu Gelb, dann auf Schwarz in 1,5 Sekunden ändert.  
  
 [!code-xaml[VSMButtonTemplate#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]  
  
### <a name="specifying-when-a-visualtransition-is-applied"></a>Festlegen der Bedingungen für einen visuellen Übergang  
 Ein <xref:System.Windows.VisualTransition> kann für bestimmte Zustände gelten beschränkt werden, oder kann angewendet werden jedes Mal, wenn das Steuerelement Übergänge zwischen Zuständen. Im vorherigen Beispiel der <xref:System.Windows.VisualTransition> wird angewendet, wenn das Steuerelement aus wechselt der `MouseOver` Zustands, in der `Normal` Status; im Beispiel vor, dass die <xref:System.Windows.VisualTransition> wird angewendet, wenn das Steuerelement Gunsten der `Pressed` Zustand. Schränken Sie ein <xref:System.Windows.VisualTransition> angewendet, indem die <xref:System.Windows.VisualTransition.To%2A> und <xref:System.Windows.VisualTransition.From%2A> Eigenschaften. In der folgenden Tabelle sind die Beschränkungsebenen aufgelistet, von der restriktivsten bis zu der am wenigsten restriktiven.  
  
|Art der Einschränkung|From-Wert|To-Wert|  
|-------------------------|-------------------|-----------------|  
|Aus einem angegebenen Zustand in einen anderen angegebenen Zustand|Der Name des ein <xref:System.Windows.VisualState>|Der Name des ein <xref:System.Windows.VisualState>|  
|Aus einem beliebigen Zustand in einen angegebenen Zustand|Nicht festgelegt|Der Name des ein <xref:System.Windows.VisualState>|  
|Aus einem angegebenen Zustand in einen beliebigen Zustand|Der Name des ein <xref:System.Windows.VisualState>|Nicht festgelegt|  
|Aus einem beliebigen Zustand in einen beliebigen Zustand|Nicht festgelegt|Nicht festgelegt|  
  
 Haben Sie mehrere <xref:System.Windows.VisualTransition> Objekte in eine <xref:System.Windows.VisualStateGroup> mit Verweisen auf den gleichen Status, aber sie in der Reihenfolge, der angibt, die vorherige Tabelle verwendet werden. Im folgenden Beispiel werden zwei <xref:System.Windows.VisualTransition> Objekte. Beim Übergang des Steuerelements von der `Pressed` Zustands, in der `MouseOver` Zustand, der <xref:System.Windows.VisualTransition> , besitzt sowohl <xref:System.Windows.VisualTransition.From%2A> und <xref:System.Windows.VisualTransition.To%2A> Satz verwendet wird. Wenn das Steuerelement von einem anderen Zustand als `Pressed` in den Zustand `MouseOver` wechselt, wird der andere Zustand verwendet.  
  
 [!code-xaml[VSMButtonTemplate#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]  
  
 Die <xref:System.Windows.VisualStateGroup> hat eine <xref:System.Windows.VisualStateGroup.Transitions%2A> -Eigenschaft, enthält die <xref:System.Windows.VisualTransition> Objekte, die zum Anwenden der <xref:System.Windows.VisualState> Objekte in der <xref:System.Windows.VisualStateGroup>. Als die <xref:System.Windows.Controls.ControlTemplate> Autor, Sie sind kostenlos einschließen <xref:System.Windows.VisualTransition> werden sollen. Jedoch, wenn die <xref:System.Windows.VisualTransition.To%2A> und <xref:System.Windows.VisualTransition.From%2A> Eigenschaften werden festgelegt, um Namen, die nicht Bestandteil der <xref:System.Windows.VisualStateGroup>, die <xref:System.Windows.VisualTransition> wird ignoriert.  
  
 Das folgende Beispiel zeigt die <xref:System.Windows.VisualStateGroup> für die `CommonStates`. Im Beispiel definiert eine <xref:System.Windows.VisualTransition> für die Schaltfläche folgenden geht.  
  
-   In den Zustand `Pressed`.  
  
-   In den Zustand `MouseOver`.  
  
-   Aus dem Zustand `Pressed` in den Zustand `MouseOver`.  
  
-   Aus dem Zustand `MouseOver` in den Zustand `Normal`.  
  
 [!code-xaml[VSMButtonTemplate#VisualTransitions](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]  
  
<a name="customizing_other_controls_by_understanding_the_control_contract"></a>   
## <a name="customizing-other-controls-by-understanding-the-control-contract"></a>Anpassen von anderen Steuerelementen mit Steuerelementverträgen  
 Ein Steuerelement, das verwendet eine <xref:System.Windows.Controls.ControlTemplate> seiner visuellen Struktur an (mit <xref:System.Windows.FrameworkElement> Objekte) und visuelle Verhalten (mit <xref:System.Windows.VisualState> Objekte) verwendet das Modell Teile. Viele Steuerelemente des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4 verwenden dieses Modell. Die Teile, die eine <xref:System.Windows.Controls.ControlTemplate> Autor Anforderungen zu berücksichtigen sind über den Steuerelementvertrag kommuniziert. Sobald Sie sich mit den Bausteinen des Steuerelementvertrags auskennen, können Sie die Darstellung beliebiger Steuerelemente anpassen, die das Teilsteuerelementen-Modell verwenden.  
  
 Ein Steuerelementvertrag besteht aus drei Elementen:  
  
-   Den visuellen Elementen, die die Logik des Steuerelements verwenden.  
  
-   Den Zuständen des Steuerelements und den Gruppen, zu denen die einzelnen Zustände gehören.  
  
-   Den öffentlichen Eigenschaften, die die visuelle Darstellung des Steuerelements beeinflussen.  
  
### <a name="visual-elements-in-the-control-contract"></a>Visuelle Elemente im Steuerelementvertrag  
 In einigen Fällen Logik eines Steuerelements interagiert mit einer <xref:System.Windows.FrameworkElement> , die sich in der <xref:System.Windows.Controls.ControlTemplate>. Das Steuerelement kann z.B. ein Ereignis für ein zugehöriges Element behandeln. Wenn ein Steuerelement davon ausgeht, einen bestimmten <xref:System.Windows.FrameworkElement> in der <xref:System.Windows.Controls.ControlTemplate>, müssen sie diese Informationen, um übermitteln der <xref:System.Windows.Controls.ControlTemplate> Autor. Das Steuerelement verwendet die <xref:System.Windows.TemplatePartAttribute> vermitteln Sie den Typ eines Elements, der erwartet wird, und wie der Name des Elements sein soll. Die <xref:System.Windows.Controls.Button> verfügt nicht über <xref:System.Windows.FrameworkElement> Teile in die Steuerelementvertrag, aber andere Steuerelemente wie z. B. die <xref:System.Windows.Controls.ComboBox>, führen.  
  
 Das folgende Beispiel zeigt die <xref:System.Windows.TemplatePartAttribute> Objekte, die auf angegeben sind die <xref:System.Windows.Controls.ComboBox> Klasse. Die Logik der <xref:System.Windows.Controls.ComboBox> davon ausgeht, eine <xref:System.Windows.Controls.TextBox> mit dem Namen `PART_EditableTextBox` und ein <xref:System.Windows.Controls.Primitives.Popup> mit dem Namen `PART_Popup` in seiner <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-csharp[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]  
  
 Das folgende Beispiel zeigt eine vereinfachte <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ComboBox> , enthält die Elemente, die vom angegebenen der <xref:System.Windows.TemplatePartAttribute> Objekte auf der <xref:System.Windows.Controls.ComboBox> Klasse.  
  
 [!code-xaml[VSMButtonTemplate#ComboBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]  
  
### <a name="states-in-the-control-contract"></a>Zustände im Steuerelementvertrag  
 Die Zustände eines Steuerelements sind ebenfalls Teil des Steuerelementvertrags. Das Beispiel zum Erstellen einer <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.Button> wird gezeigt, wie die Darstellung des ein <xref:System.Windows.Controls.Button> je nach ihrer Status. Sie erstellen eine <xref:System.Windows.VisualState> für jeden Zustand angegebenen und versetzen Sie alle <xref:System.Windows.VisualState> Objekte dieser Freigabe eine <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A> in einer <xref:System.Windows.VisualStateGroup>, wie in beschrieben [Ändern der Darstellung des Steuerelements in Abhängigkeit von dessen Zustand](#changing_the_appearance_of_a_control_depending_on_its_state) weiter oben in dieser Thema. Steuerelemente von Drittanbietern sollten Zustände angeben, indem die <xref:System.Windows.TemplateVisualStateAttribute>, wodurch die Designer-Tools, z. B. Expression Blend, um die Zustände des Steuerelements für die Erstellung von Steuerelementvorlagen verfügbar zu machen.  
  
 Den Steuerelementvertrag für Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Steuerelementformate und -vorlagen](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
### <a name="properties-in-the-control-contract"></a>Eigenschaften im Steuerelementvertrag  
 Die öffentlichen Eigenschaften, die sich auf das Steuerelement visuell auswirken, sind ebenfalls im Steuerelementvertrag enthalten. Sie können diese Eigenschaften, die Darstellung des Steuerelements zu ändern, ohne das Erstellen einer neuen festlegen <xref:System.Windows.Controls.ControlTemplate>. Können Sie auch die [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) Markuperweiterung Eigenschaften von Elementen zu binden, der in der <xref:System.Windows.Controls.ControlTemplate> auf öffentlichen Eigenschaften, die von definiert werden die <xref:System.Windows.Controls.Button>.  
  
 Das folgende Beispiel zeigt den Steuerelementvertrag für die Schaltfläche.  
  
 [!code-csharp[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]  
  
 Beim Erstellen einer <xref:System.Windows.Controls.ControlTemplate>, ist es oft am einfachsten, beginnen mit einem vorhandenen <xref:System.Windows.Controls.ControlTemplate> und, Änderungen daran vornehmen. Führen Sie eine der folgenden Optionen zum Ändern einer vorhandenen <xref:System.Windows.Controls.ControlTemplate>:  
  
-   Verwenden Sie einen Designer, z.B. Expression Blend, der eine grafische Benutzeroberfläche zum Erstellen von Steuerelementvorlagen bereitstellt. Weitere Informationen finden Sie unter [Formatieren eines Steuerelements, das Vorlagen unterstützt](http://go.microsoft.com/fwlink/?LinkId=161153).  
  
-   Rufen Sie die Standard- <xref:System.Windows.Controls.ControlTemplate> und bearbeiten. Standard-Steuerelementvorlagen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], finden Sie unter [Default WPF Themes](http://go.microsoft.com/fwlink/?LinkID=158252) (Standard-WPF-Designs).  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>Vollständiges Beispiel  
 Das folgende Beispiel zeigt die vollständige <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.ControlTemplate> , die in diesem Thema erläutert wird.  
  
 [!code-xaml[VSMButtonTemplate#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)
