---
title: Übersicht über das Erstellen von Steuerelementen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], authoring overview
- authoring overview for controls [WPF]
ms.assetid: 3d864748-cff0-4e63-9b23-d8e5a635b28f
ms.openlocfilehash: 2326520039085beb5f5294e23db67b67f9d7d7da
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243270"
---
# <a name="control-authoring-overview"></a>Übersicht über die Steuerung der Erstellung

Dank der Erweiterbarkeit des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Steuerelementmodells ist das Erstellen neuer Steuerelemente nur selten erforderlich. In bestimmten Fällen lässt sich das Erstellen benutzerdefinierter Steuerelemente dennoch nicht vermeiden. In diesem Thema werden die Funktionen, dank deren Sie auf das Erstellen neuer Steuerelementen in den meisten Fällen verzichten können, sowie verschiedene Modelle zum Erstellen von Steuerelementen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] behandelt. Außerdem wird in diesem Thema auch das Erstellen eines neuen Steuerelements veranschaulicht.

<a name="when_to_write_a_new_control"></a>

## <a name="alternatives-to-writing-a-new-control"></a>Alternativen zum Erstellen eines neuen Steuerelements

In der Vergangenheit waren Sie bei der Anpassung eines vorhandenen Steuerelements auf die Bearbeitung seiner Standardeigenschaften beschränkt. Sie konnten z.B. die Hintergrundfarbe, die Rahmenbreite sowie die Schriftgröße ändern. Falls Sie die Darstellung oder das Verhalten eines Steuerelements über diese vordefinierten Parameter hinaus erweitern wollten, waren Sie auf das Erstellen eines neuen Steuerelements angewiesen. Die übliche Vorgehensweise war die Vererbung von einem vorhandenen Steuerelement samt der Überschreibung der für das Zeichnen des Steuerelements zuständigen Methode.  Diese Option steht Ihnen zwar weiterhin zur Verfügung, mit dem reichen Inhaltsmodel von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sowie seinen Stilen, Vorlagen und Triggern können Sie jedoch die vorhandenen Steuerelemente auf eine vielfältige Art und Weise anzupassen. In der folgenden Liste finden Sie Beispiele für die Verwendung dieser Funktionen zum Erstellen einer benutzerdefinierten und konsistenten Umgebung, ohne ein neues Steuerelement erstellen zu müssen.

- **Multimediainhalte.** Viele [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Standardsteuerelemente unterstützen Multimediainhalte. Beispielsweise ist die Content-Eigenschaft von a <xref:System.Windows.Controls.Button> vom Typ <xref:System.Object>, so <xref:System.Windows.Controls.Button>dass theoretisch alles auf einer angezeigt werden kann.  Damit eine Schaltfläche ein Bild und einen Text anzeigt, können Sie ein Bild und eine <xref:System.Windows.Controls.TextBlock> zu einem <xref:System.Windows.Controls.StackPanel> hinzufügen und der <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft zuweisen. Da die Steuerelemente visuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Elemente sowie beliebige Daten anzeigen können, ist es zwecks der Unterstützung einer komplexen Visualisierung selten notwendig, neue Steuerelemente zu erstellen oder vorhandene Steuerelemente zu ändern. Weitere Informationen zum Inhaltsmodell <xref:System.Windows.Controls.Button> für und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]anderen Inhaltsmodellen finden Sie unter [WPF-Inhaltsmodell](wpf-content-model.md).

- **Stile.** A <xref:System.Windows.Style> ist eine Auflistung von Werten, die Eigenschaften für ein Steuerelement darstellen. Mit Stilen können Sie eine wiederverwendbare Darstellung der erwünschten Gestaltung und des erwünschten Verhaltens der Steuerelemente erstellen, ohne ein neues Steuerelement erstellen zu müssen. Angenommen, alle Steuerelemente <xref:System.Windows.Controls.TextBlock> sollen rot sein, Arial-Schriftart mit einer Schriftgröße von 14. Sie können einen Stil als eine Ressource anlegen und die jeweiligen Eigenschaften entsprechend festlegen. Dann <xref:System.Windows.Controls.TextBlock> wird jedes, das Sie Ihrer Anwendung hinzufügen, das gleiche Erscheinungsbild haben.

- **Datenvorlagen.** Mit <xref:System.Windows.DataTemplate> A können Sie anpassen, wie Daten in einem Steuerelement angezeigt werden. Beispielsweise kann <xref:System.Windows.DataTemplate> a verwendet werden, um anzugeben, <xref:System.Windows.Controls.ListBox>wie Daten in einer angezeigt werden.  Weitere Beispiele finden Sie unter [Übersicht über Datenvorlagen](../data/data-templating-overview.md).  Zusätzlich zum Anpassen der Darstellung von <xref:System.Windows.DataTemplate> Daten kann ein UI-Elemente enthalten, was Ihnen eine große Flexibilität bei benutzerdefinierten Benutzeroberflächen bietet.  Beispielsweise können Sie <xref:System.Windows.DataTemplate>mithilfe einer erstellen, <xref:System.Windows.Controls.ComboBox> in der jedes Element ein Kontrollkästchen enthält.

- **Steuerelementvorlagen.** Viele Steuerelemente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ControlTemplate> verwenden eine, um die Struktur und Darstellung des Steuerelements zu definieren, wodurch die Darstellung eines Steuerelements von der Funktionalität des Steuerelements getrennt wird. Sie können die Darstellung eines Steuerelements <xref:System.Windows.Controls.ControlTemplate>drastisch ändern, indem Sie seine neu definieren.  Nehmen wir z.B. an, dass Sie ein Steuerelement wie eine Ampel aussehen lassen möchten. Dieses Steuerelement hat eine einfache Benutzeroberfläche und Funktionalität.  Das Steuerelement besteht aus drei Kreisen, von denen jeweils nur ein einziger leuchten kann. Nach einiger Überlegung erkennen <xref:System.Windows.Controls.RadioButton> Sie vielleicht, dass a die Funktionalität bietet, dass <xref:System.Windows.Controls.RadioButton> nur eine nach der anderen ausgewählt wird, aber das Standardbild des sieht nicht aus wie das Licht einer Ampel.  Da <xref:System.Windows.Controls.RadioButton> der eine Steuerelementvorlage verwendet, um sein Erscheinungsbild <xref:System.Windows.Controls.ControlTemplate> zu definieren, ist es einfach, die an die Anforderungen des Steuerelements angepassten Einstellungen neu zu definieren und die Tasten zu verwenden, um die Ampel zu erstellen.

  > [!NOTE]
  > Obwohl <xref:System.Windows.Controls.RadioButton> a eine <xref:System.Windows.DataTemplate>verwenden <xref:System.Windows.DataTemplate> kann, reicht a in diesem Beispiel nicht aus.  Der <xref:System.Windows.DataTemplate> definiert die Darstellung des Inhalts eines Steuerelements. Im Fall von <xref:System.Windows.Controls.RadioButton>, ist der Inhalt alles, was rechts <xref:System.Windows.Controls.RadioButton> neben dem Kreis erscheint, der angibt, ob der ausgewählt ist.  Im Beispiel mit der Ampel brauchen Sie lediglich das Optionsfeld als einen Kreis darzustellen, das „aufleuchten“ kann. Da sich die Darstellungsanforderung für die Stopplight <xref:System.Windows.Controls.RadioButton>so stark von der <xref:System.Windows.Controls.ControlTemplate>Standarddarstellung des unterscheidet, ist es erforderlich, die neu zu definieren.  Im Allgemeinen <xref:System.Windows.DataTemplate> wird a zum Definieren des Inhalts (oder <xref:System.Windows.Controls.ControlTemplate> der Daten) eines Steuerelements und a zum Definieren der Struktur eines Steuerelements verwendet.

- **Trigger.** Mit <xref:System.Windows.Trigger> A können Sie die Darstellung und das Verhalten eines Steuerelements dynamisch ändern, ohne ein neues Steuerelement zu erstellen. Angenommen, Sie haben <xref:System.Windows.Controls.ListBox> mehrere Steuerelemente in der Anwendung <xref:System.Windows.Controls.ListBox> und möchten, dass die Elemente in jedem Element fett und rot sein sollen, wenn sie ausgewählt werden. Ihr erster Instinkt besteht möglicherweise darin, eine <xref:System.Windows.Controls.ListBox> Klasse zu <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> erstellen, die von der Methode erbt und sie überschreibt, um <xref:System.Windows.Controls.ListBoxItem> die Darstellung des ausgewählten Elements zu ändern, aber ein besserer Ansatz besteht darin, einem Stil von a einen Trigger hinzuzufügen, der die Darstellung des ausgewählten Elements ändert. Mit Triggern können Sie Eigenschaftswerte bearbeiten oder basierend auf den Eigenschaftswerten Aktionen ausführen. An <xref:System.Windows.EventTrigger> ermöglicht es Ihnen, Aktionen auszuführen, wenn ein Ereignis eintritt.

Weitere Informationen zu Stilen, Vorlagen und Triggern finden Sie unter [Erstellen von Formaten und Vorlagen](styling-and-templating.md).

Im Allgemeinen gilt: wenn das benötigte Steuerelement die Funktionalität eines vorhandenen Steuerelements nachmacht, aber anders aussehen soll, lohnt es sich zuerst zu überlegen, ob Sie mit einem der in diesem Abschnitt beschriebenen Verfahren die vorhandene Darstellung des Steuerelements ändern können.

<a name="models_for_control_authoring"></a>

## <a name="models-for-control-authoring"></a>Modelle für das Erstellen von Steuerelementen

Dank dem umfangreichen Inhaltsmodell sowie Stilen, Vorlagen und Triggern können Sie in den meisten Fällen auf das Erstellen neuer Steuerelemente verzichten. Falls Sie jedoch ein neues Steuerelement erstellen müssen, ist es wichtig Modelle für das Erstellen von Steuerelementen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu verstehen. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet drei allgemeine Modelle zum Erstellen der Steuerelemente, die jeweils verschiedene Funktionen und Flexibilitätsgrade bieten. Die Basisklassen für die <xref:System.Windows.Controls.UserControl> <xref:System.Windows.Controls.Control>drei <xref:System.Windows.FrameworkElement>Modelle sind , und .

### <a name="deriving-from-usercontrol"></a>Ableiten von UserControl

Die einfachste Möglichkeit zum Erstellen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eines Steuerelements <xref:System.Windows.Controls.UserControl>in besteht darin, von abzuleiten. Wenn Sie ein Steuerelement erstellen, <xref:System.Windows.Controls.UserControl>das von erbt, fügen Sie vorhandene Komponenten <xref:System.Windows.Controls.UserControl>zum [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]hinzu, benennen die Komponenten und verweisen Ereignishandler in . Anschließend können Sie auf die benannten Elemente verweisen und die Ereignishandler im Code definieren. Dieses Entwicklungsmodell ähnelt sehr dem Modell für die Anwendungsentwicklung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Wenn sie richtig <xref:System.Windows.Controls.UserControl> erstellt wurde, kann a die Vorteile von Rich Content, Styles und Triggern nutzen. Wenn Ihr Steuerelement jedoch von <xref:System.Windows.Controls.UserControl>erbt, können Personen, die Ihr <xref:System.Windows.DataTemplate> <xref:System.Windows.Controls.ControlTemplate> Steuerelement verwenden, ein steuerelement eisern oder dessen Aussehen nicht anpassen.  Es ist notwendig, von <xref:System.Windows.Controls.Control> der Klasse oder einer ihrer <xref:System.Windows.Controls.UserControl>abgeleiteten Klassen (außer ) abzuleiten, um ein benutzerdefiniertes Steuerelement zu erstellen, das Vorlagen unterstützt.

#### <a name="benefits-of-deriving-from-usercontrol"></a>Vorteile des Ableitens von UserControl

Ziehen Sie die <xref:System.Windows.Controls.UserControl> Ableitung in Betracht, wenn alle der folgenden Punkte gelten:

- Sie möchten das Steuerelement auf eine ähnliche Art und Weise erstellen, wie Sie Ihre Anwendung erstellt haben.

- Ihr Steuerelement besteht ausschließlich aus vorhandenen Komponenten.

- Es muss keine komplexe Anpassung unterstützt werden.

### <a name="deriving-from-control"></a>Ableiten von Control

Ableitung von <xref:System.Windows.Controls.Control> der Klasse ist das Modell, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das von den meisten vorhandenen Steuerelementen verwendet wird. Wenn Sie ein Steuerelement erstellen, <xref:System.Windows.Controls.Control> das von der Klasse erbt, definieren Sie deren Darstellung mithilfe von Vorlagen. Dadurch trennen Sie die Funktionslogik von der visuellen Darstellung. Sie können auch die Entkopplung der Benutzeroberfläche und der Logik sicherstellen, indem Sie <xref:System.Windows.Controls.ControlTemplate> Befehle und Bindungen anstelle von Ereignissen verwenden und das Verweisen auf Elemente in der, wann immer möglich, vermeiden.  Wenn die Benutzeroberfläche und die Logik des Steuerelements ordnungsgemäß entkoppelt sind, kann ein Benutzer des Steuerelements <xref:System.Windows.Controls.ControlTemplate> die Steuerelemente neu definieren, um die Darstellung anzupassen. Obwohl das <xref:System.Windows.Controls.Control> Erstellen eines Benutzers <xref:System.Windows.Controls.UserControl>nicht so <xref:System.Windows.Controls.Control> einfach ist wie das Erstellen einer , bietet ein Benutzerdiebe die größte Flexibilität.

#### <a name="benefits-of-deriving-from-control"></a>Vorteile des Ableitens von Control

Erwägen Sie, <xref:System.Windows.Controls.Control> von anstelle <xref:System.Windows.Controls.UserControl> der Verwendung der Klasse abzuleiten, wenn eine der folgenden Optionen zutrifft:

- Sie möchten, dass das Erscheinungsbild Ihres <xref:System.Windows.Controls.ControlTemplate>Steuerelements über anpassbar ist.

- Das Steuerelement soll verschiedene Designs unterstützen.

### <a name="deriving-from-frameworkelement"></a>Ableitung von FrameworkElement

Steuerelemente, die <xref:System.Windows.Controls.UserControl> <xref:System.Windows.Controls.Control> von vorhandenen Elementen ableiten oder sich auf das Komponieren basieren. Für viele Szenarien ist dies eine akzeptable Lösung, <xref:System.Windows.FrameworkElement> da sich <xref:System.Windows.Controls.ControlTemplate>jedes Objekt, von dem erbt, in einem befinden kann. Es gibt jedoch Situationen, in denen die Darstellung eines Steuerelements mehr als die Funktionalität einer einfachen Elementzusammensetzung erfordert. Für diese Szenarien ist es <xref:System.Windows.FrameworkElement> die richtige Wahl, sich auf eine Komponente zu stützen.

Es gibt zwei Standardmethoden zum Erstellen <xref:System.Windows.FrameworkElement>von -basierten Komponenten: direktes Rendern und benutzerdefinierte Elementzusammensetzung. Das direkte Rendering <xref:System.Windows.UIElement.OnRender%2A> umfasst <xref:System.Windows.FrameworkElement> das <xref:System.Windows.Media.DrawingContext> Überschreiben der Methode und bereitstellung von Vorgängen, die die visuellen Komponenten explizit definieren. Dies ist die <xref:System.Windows.Controls.Image> <xref:System.Windows.Controls.Border>Methode, die von und verwendet wird. Bei der benutzerdefinierten Elementzusammensetzung werden Objekte vom Typ <xref:System.Windows.Media.Visual> verwendet, um die Darstellung der Komponente zu erstellen. Beispiele finden Sie unter [Verwenden von DrawingVisual-Objekten](../graphics-multimedia/using-drawingvisual-objects.md). <xref:System.Windows.Controls.Primitives.Track>ist ein Beispiel für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein Steuerelement, in dem eine benutzerdefinierte Elementzusammensetzung verwendet wird. Sie können auch direktes Rendering und benutzerdefinierte Elementzusammensetzung innerhalb eines Steuerelements kombinieren.

#### <a name="benefits-of-deriving-from-frameworkelement"></a>Vorteile der Ableitung von FrameworkElement

Erwägen Sie, <xref:System.Windows.FrameworkElement> daraus abzuleiten, wenn einer der folgenden Punkte zutrifft:

- Sie brauchen eine genaue Steuerung der Darstellung Ihres Steuerelements, die darüber hinausgeht, was mit einer einfachen Elementzusammensetzung möglich ist.

- Sie möchten die Darstellung Ihres Steuerelements definieren, indem Sie Ihre eigene Renderinglogik definieren.

- Sie wollen vorhandene Elemente auf neuartige Weise zusammenstellen, <xref:System.Windows.Controls.UserControl> <xref:System.Windows.Controls.Control>die über das hinausgehen, was mit und möglich ist.

<a name="control_authoring_basics"></a>

## <a name="control-authoring-basics"></a>Grundlagen des Erstellens von Steuerelementen

Wie bereits erläutert, ist eine der leistungsstärksten Funktionen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Möglichkeit, über die Festlegung grundlegender Eigenschaften eines Steuerelements zur Bearbeitung seiner Darstellung und seines Verhaltens hinausgehen zu können, ohne ein benutzerdefiniertes Steuerelement erstellen zu müssen. Die Funktionen für Stil, Datenbindung und Trigger werden durch das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaftensystem und das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignissystem ermöglicht. In den folgenden Abschnitten werden einige Verfahren beschrieben, die Sie unabhängig von dem zum Erstellen des benutzerdefinierten Steuerelements verwendeten Modell befolgen sollten, um Benutzern Ihres benutzerdefinierten Steuerelements das Zugreifen auf diese Funktionen auf die gleiche Art und Weise zu ermöglichen, wie es bei einem in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthaltenen Steuerelement möglich wäre.

### <a name="use-dependency-properties"></a>Verwenden von Abhängigkeitseigenschaften

Falls es sich bei einer Eigenschaft um eine Abhängigkeitseigenschaft handelt, können Sie folgendermaßen vorgehen:

- Die Eigenschaft in einem Stil festlegen.

- Die Eigenschaft an eine Datenquelle binden.

- Eine dynamische Ressource als den Wert der Eigenschaft verwenden.

- Die Eigenschaft animieren.

Falls Sie möchten, dass eine Eigenschaft Ihres Steuerelements eine dieser Funktionen unterstützt, sollten Sie die Eigenschaft als eine Abhängigkeitseigenschaft implementieren. Im folgenden Beispiel wird eine Abhängigkeitseigenschaft mit dem Namen `Value` wie folgt definiert:

- Definieren <xref:System.Windows.DependencyProperty> Sie `ValueProperty` einen `public` `static` `readonly` Bezeichner, der als Feld benannt ist.

- Registrieren Sie den Eigenschaftsnamen beim <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType>Eigenschaftensystem, indem Sie Folgendes angeben:

  - Der Name der Eigenschaft.

  - Der Typ der Eigenschaft.

  - Den Typ, der die Eigenschaft besitzt.

  - Die Metadaten für die Eigenschaft. Die Metadaten enthalten den Standardwert <xref:System.Windows.CoerceValueCallback> der <xref:System.Windows.PropertyChangedCallback>Eigenschaft, a und a.

- Definieren Sie eine CLR-Wrappereigenschaft mit dem Namen `Value`, die denselben Namen hat, `get` `set` der zum Registrieren der Abhängigkeitseigenschaft verwendet wird, indem Sie die Eigenschaften und Accessoren implementieren. Beachten Sie, dass `get` die und `set` Accessors nur anrufen <xref:System.Windows.DependencyObject.GetValue%2A> bzw.. <xref:System.Windows.DependencyObject.SetValue%2A> Es wird empfohlen, dass die Accessoren von Abhängigkeitseigenschaften keine zusätzliche Logik enthalten, da Clients die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Accessoren und den Aufruf <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> direkt umgehen können. Falls eine Eigenschaft z.B. an eine Datenquelle gebunden ist, wird die `set`-Zugriffmethode der Eigenschaft nicht aufgerufen.  Anstatt den get- und set-Accessoren zusätzliche <xref:System.Windows.ValidateValueCallback> <xref:System.Windows.CoerceValueCallback>Logik <xref:System.Windows.PropertyChangedCallback> hinzuzufügen, verwenden Sie die , und delegiert, um auf den Wert zu reagieren oder ihn zu überprüfen, wenn er sich ändert.  Weitere Informationen zu diesen Rückrufen finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](../advanced/dependency-property-callbacks-and-validation.md).

- Definieren Sie eine <xref:System.Windows.CoerceValueCallback> `CoerceValue`Methode für die benannte . `CoerceValue` stellt sicher, dass `Value` größer oder gleich `MinValue` und kleiner oder gleich `MaxValue` ist.

- Definieren Sie eine <xref:System.Windows.PropertyChangedCallback>Methode `OnValueChanged`für die mit dem Namen . `OnValueChanged`erstellt <xref:System.Windows.RoutedPropertyChangedEventArgs%601> ein Objekt und bereitet `ValueChanged` das Routingereignis vor. Routingereignisse werden im nächsten Abschnitt erläutert.

[!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
[!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]

Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../advanced/custom-dependency-properties.md).

### <a name="use-routed-events"></a>Verwenden von Routingereignissen

Genauso wie Abhängigkeitseigenschaften den Begriff der CLR-Eigenschaften um zusätzliche Funktionen erweitern, erweitern geroutete Ereignisse den Begriff der Standard-CLR-Ereignisse. Beim Erstellen eines neuen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelements empfiehlt es sich, Ihr Ereignis als ein Routingereignis zu implementieren, da Routingereignisse folgendes Verhalten unterstützen:

- Ereignisse für mehrere Steuerelemente können über ein übergeordnetes Steuerelement behandelt werden. Falls es sich bei dem Ereignis um ein Bubbling-Ereignis handelt, kann ein einzelnes übergeordnetes Element in der Elementstruktur das Ereignis abonnieren. Anschließend können Anwendungsentwickler mit einem Handler auf das Ereignis mehrerer Steuerelemente reagieren. Wenn ihr Steuerelement z. B. Teil <xref:System.Windows.Controls.ListBox> jedes Elements in einem <xref:System.Windows.DataTemplate>ist (da es in einem enthalten ist), <xref:System.Windows.Controls.ListBox>kann der Anwendungsentwickler den Ereignishandler für das Ereignis des Steuerelements auf der definieren. Beim Auftreten des Ereignisses bei einem der Steuerelemente wird der Ereignishandler aufgerufen.

- Geroutete Ereignisse können <xref:System.Windows.EventSetter>in einem verwendet werden, mit dem Anwendungsentwickler den Handler eines Ereignisses innerhalb eines Stils angeben können.

- Geroutete Ereignisse können <xref:System.Windows.EventTrigger>in einem verwendet werden, was zum [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Animieren von Eigenschaften mithilfe von nützlich ist. Weitere Informationen finden Sie unter [Übersicht über Animation](../graphics-multimedia/animation-overview.md).

Im folgenden Beispiel wird ein Routingereignis wie folgt definiert:

- Definieren <xref:System.Windows.RoutedEvent> Sie `ValueChangedEvent` einen `public` `static` `readonly` Bezeichner, der als Feld benannt ist.

- Registrieren Sie das geroutete Ereignis, indem Sie die <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType> Methode aufrufen. Das Beispiel gibt die folgenden <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>Informationen an, wenn es aufruft:

  - Der Name des Ereignisses lautet `ValueChanged`.

  - Die Routingstrategie <xref:System.Windows.RoutingStrategy.Bubble>lautet , was bedeutet, dass zuerst ein Ereignishandler für die Quelle (das Objekt, das das Ereignis auslöst) aufgerufen wird und dann Ereignishandler für die übergeordneten Elemente der Quelle nacheinander aufgerufen werden, beginnend mit dem Ereignishandler für das nächste übergeordnete Element.

  - Der Typ des Ereignishandlers <xref:System.Windows.RoutedPropertyChangedEventHandler%601>ist <xref:System.Decimal> , der mit einem Typ erstellt wurde.

  - `NumericUpDown` ist der besitzende Typ des Ereignisses.

- Ein öffentliches Ereignis mit dem Namen `ValueChanged`, das die Zugriffsmethoden-Deklarationen umfasst, wird deklariert. Das Beispiel <xref:System.Windows.UIElement.AddHandler%2A> ruft `add` in <xref:System.Windows.UIElement.RemoveHandler%2A> der `remove` Accessordeklaration [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und in der Accessordeklaration auf, die Ereignisdienste zu verwenden.

- Eine geschützte virtuelle Methode mit dem Namen `OnValueChanged`, die das`ValueChanged`-Ereignis auslöst, wird erstellt.

[!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
[!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]

Weitere Informationen finden Sie unter [ Übersicht über Routingereignisse ](../advanced/routed-events-overview.md) und [Vorgehensweise: Erstellen eines benutzerdefinierten Routingereignisses](../advanced/how-to-create-a-custom-routed-event.md).

### <a name="use-binding"></a>Verwendung von Bindungen

Erwägen Sie Datenbindungen, um die Benutzeroberfläche Ihres Steuerelements von der Logik zu entkoppeln. Dies ist besonders wichtig, wenn Sie die <xref:System.Windows.Controls.ControlTemplate>Darstellung des Steuerelements mithilfe einer definieren. Bei der Verwendung einer Datenbindung können Sie u.U. auf die Verweise auf bestimmte Teile der Benutzeroberfläche aus dem Code verzichten. Es ist eine gute Idee, das Verweisen auf <xref:System.Windows.Controls.ControlTemplate> Elemente zu vermeiden, die <xref:System.Windows.Controls.ControlTemplate> sich <xref:System.Windows.Controls.ControlTemplate> in der befinden, da das referenzierte <xref:System.Windows.Controls.ControlTemplate>Element in das neue element aufgenommen werden muss, wenn der Code auf Elemente verweist, die sich im und des geändert haben.

Im folgenden Beispiel <xref:System.Windows.Controls.TextBlock> wird `NumericUpDown` das Steuerelement aktualisiert, ihm einen Namen zugewiesen und das Textfeld im Code nach Namen referenziert.

[!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]

[!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
[!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]

Im folgenden Beispiel wird eine Bindung für den selben Zweck verwendet.

[!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]

Weitere Informationen zu Datenbindungen finden Sie unter [Übersicht über Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).

### <a name="design-for-designers"></a>Darstellung für Designer

Um Unterstützung für benutzerdefinierte WPF-Steuerelemente im WPF-Designer für Visual Studio zu erhalten (z. B. Eigenschaftenbearbeitung mit dem Eigenschaftenfenster), befolgen Sie diese Richtlinien.  Weitere Informationen zum Entwickeln für den WPF-Designer finden Sie [unter Entwerfen von XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).

#### <a name="dependency-properties"></a>Abhängigkeitseigenschaften

Stellen Sie sicher, `get` `set` dass SIE CLR und Accessoren wie zuvor beschrieben unter "Abhängigkeitseigenschaften verwenden" implementieren. Designer können Wrapper zur Prüfung des Vorhandenseins einer Abhängigkeitseigenschaft verwenden. Diese müssen, genauso wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und Clients des Steuerelements, beim Abrufen oder Festlegen der Eigenschaft jedoch keine Zugriffsmethoden aufrufen.

#### <a name="attached-properties"></a>Angefügte Eigenschaften

Angefügte Eigenschaften für benutzerdefinierte Steuerelemente sind unter Einhaltung der folgenden Richtlinien zu implementieren:

- Haben `public` `static` `readonly` <xref:System.Windows.DependencyProperty> Sie einen der Form *PropertyName,* `Property` die mit der <xref:System.Windows.DependencyProperty.RegisterAttached%2A> Methode erstellt wurde. Der Eigenschaftsname, <xref:System.Windows.DependencyProperty.RegisterAttached%2A> an den übergeben wird, muss *mit PropertyName*übereinstimmen.

- Implementieren Sie die `public` `static` CLR-Methoden mit den Namen `Set`*PropertyName* und `Get`*PropertyName*. Beide Methoden sollten eine <xref:System.Windows.DependencyProperty> Klasse akzeptieren, die als erstes Argument abgeleitet wurde. Die `Set`*PropertyName*-Methode akzeptiert auch ein Argument, dessen Typ mit dem registrierten Datentyp der Eigenschaft übereinstimmt. Die `Get`*PropertyName*-Methode sollte einen Wert zurückgeben, der den gleichen Typ aufweist. Falls die `Set`*PropertyName*-Methode fehlt, wird die Eigenschaft als schreibgeschützt gekennzeichnet.

- `Set`*PropertyName* `Get`und *PropertyName* müssen <xref:System.Windows.DependencyObject.GetValue%2A> direkt <xref:System.Windows.DependencyObject.SetValue%2A> an die und Methoden für das Zielabhängigkeitsobjekt weitergeleitet werden. Designer können auf die angefügte Eigenschaft entweder über einen Aufruf des Wrappers für die Methode zugreifen, oder indem sie das Zielabhängigkeitsobjekt direkt aufrufen.

Weitere Informationen zu angefügten Eigenschaften finden Sie in der [Übersicht über angefügte Eigenschaften](../advanced/attached-properties-overview.md).

### <a name="define-and-use-shared-resources"></a>Definieren und Verwenden von freigegebenen Ressourcen

Sie können Ihr Steuerelement entweder in die Assembly Ihrer Anwendung, oder in eine separate Assembly einbinden, die in mehreren Anwendungen verwendet werden kann. Der Großteil der in diesem Thema erläuterten Informationen gilt unabhängig von der von Ihnen verwendeten Methode.  Ein wesentlicher Unterschied ist dennoch zu beachten.  Falls Sie ein Steuerelement in die Assembly einer Anwendung einbinden, können Sie der App.xaml-Datei globale Ressourcen hinzufügen. Einer Assembly, die nur Steuerelemente <xref:System.Windows.Application> enthält, ist jedoch kein Objekt zugeordnet, sodass keine App.xaml-Datei verfügbar ist.

Wenn eine Anwendung nach einer Ressource sucht,wird auf drei Ebenen in der folgenden Reihenfolge gesucht:

1. Die Elementebene.

   Das System beginnt mit dem Element, das auf die Ressource verweist, und sucht anschließend die Ressourcen des logischen übergeordneten Elements durch. Dieser Schritt wir wiederholt, bis das Stammelement erreicht ist.

2. Die Anwendungsebene.

   Ressourcen, die <xref:System.Windows.Application> durch das Objekt definiert sind.

3. Die Designebene.

   Ressourcenverzeichnisse werden auf der Designebene in einem Themes-Unterordner gespeichert.  Die Dateien im Themes-Ordner entsprechen den Designs.  Dort könnten Sie beispielsweise Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml, etc. finden.  Möglicherweise ist auch eine Datei mit dem Namen generic.xaml enthalten.  Bei einer Suche nach einer Ressource auf der Designebene wird zunächst in der designspezifischen Datei und dann in der Datei generic.xaml gesucht.

Falls Ihr Steuerelement in einer anderen Assembly als die Anwendung liegt, müssen Sie Ihre globale Ressourcen auf die Elementen- oder Designebene umspeichern. Beide Methoden haben ihre Vorteile.

#### <a name="defining-resources-at-the-element-level"></a>Definieren von Ressourcen auf der Elementebene

Sie können freigegebene Ressourcen auf Elementebene definieren, indem Sie ein benutzerdefiniertes Ressourcenwörterbuch erstellen und es mit dem Ressourcenwörterbuch des Steuerelements zusammenführen.  Falls Sie sich für diese Methode entscheiden, können Sie die Ressourcendatei beliebig benennen und sie im Ordner speichern, wo Ihre Steuerelemente liegen. Für Ressourcen auf der Elementebene können ebenso einfache Zeichenfolgen als Schlüssel verwendet werden. Im folgenden Beispiel <xref:System.Windows.Media.LinearGradientBrush> wird eine Ressourcendatei mit dem Namen Dictionary1.xaml erstellt.

[!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]

Nachdem Sie das Ressourcenverzeichnis definiert haben, müssen Sie es mit dem Ressourcenverzeichnis des Steuerelements zusammenführen.  Hierzu können Sie [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder Code verwenden.

Im folgenden Beispiel wird ein Ressourcenverzeichnis mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zusammengeführt.

[!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]

Der Nachteil dieses Ansatzes <xref:System.Windows.ResourceDictionary> besteht darin, dass jedes Mal, wenn Sie darauf verweisen, ein Objekt erstellt wird.  Wenn Sie beispielsweise 10 benutzerdefinierte Steuerelemente in Ihrer Bibliothek haben und die freigegebenen Ressourcenwörterbücher für <xref:System.Windows.ResourceDictionary> jedes Steuerelement mithilfe von XAML zusammenführen, erstellen Sie 10 identische Objekte.  Sie können dies vermeiden, indem Sie eine statische Klasse <xref:System.Windows.ResourceDictionary>erstellen, die die Ressourcen im Code zusammenführt und die resultierende zurückgibt.

Im folgenden Beispiel wird eine <xref:System.Windows.ResourceDictionary>Klasse erstellt, die eine freigegebene .

[!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]

Im folgenden Beispiel wird die freigegebene Ressource mit den Ressourcen eines benutzerdefinierten Steuerelements im Konstruktor des Steuerelements zusammengeführt, bevor sie `InitializeComponent` aufruft.  Da `SharedDictionaryManager.SharedDictionary` es sich um <xref:System.Windows.ResourceDictionary> eine statische Eigenschaft handelt, wird die nur einmal erstellt. Da das Ressourcenverzeichnis vor dem Aufruf von `InitializeComponent` zusammengeführt worden ist, kann das Steuerelement auf die Ressourcen in seiner [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Datei zugreifen.

[!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]

#### <a name="defining-resources-at-the-theme-level"></a>Definieren von Ressourcen auf der Designebene

Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie Ressourcen für verschiedene Windows-Designs erstellen.  Als Autor des Steuerelements können Sie eine Ressource für ein bestimmtes Design definieren, um die Darstellung Ihres Steuerelements an das jeweils verwendete Design anzupassen. Beispielsweise unterscheidet sich das <xref:System.Windows.Controls.Button> Erscheinungsbild von a im Windows Classic-Design (das Standarddesign für <xref:System.Windows.Controls.Button> Windows 2000) von einem im Windows <xref:System.Windows.Controls.Button> Luna-Design <xref:System.Windows.Controls.ControlTemplate> (dem Standarddesign für Windows XP), da der für jedes Design eine andere verwendet.

Designspezifische Ressourcen werden in einem Ressourcenverzeichnis mit dem entsprechenden Dateinamen gespeichert. Diese Dateien müssen sich im `Themes`-Verzeichnis befinden, einem Unterordner des Ordners, in dem sich das Steuerelement befindet. In der folgenden Tabelle sind die Ressourcenverzeichnisdateien sowie die den einzelnen Dateien zugeordneten Designs aufgelistet:

|Name der Ressourcenverzeichnisdatei|Windows-Design|
|-----------------------------------|-------------------|
|`Classic.xaml`|Klassische Windows 9x/2000-Darstellung unter Windows XP|
|`Luna.NormalColor.xaml`|Blaues Standard-Design unter Windows XP|
|`Luna.Homestead.xaml`|Olivgrünes Design unter Windows XP|
|`Luna.Metallic.xaml`|Silbernes Design unter Windows XP|
|`Royale.NormalColor.xaml`|Standarddesign von Windows XP Media Center Edition|
|`Aero.NormalColor.xaml`|Standarddesign unter Windows Vista|

Sie müssen nicht für jedes Design eine Ressource definieren. Wenn eine Ressource nicht für ein bestimmtes Design definiert ist, durchsucht das Steuerelement `Classic.xaml` nach der Ressource. Falls die Ressource weder in der Datei, die dem aktuellen Design entspricht, noch in `Classic.xaml` definiert ist, verwendet das Steuerelement die generische Ressource, die sich im Ressourcenverzeichnis mit dem Namen `generic.xaml` befindet.  Die `generic.xaml`-Datei befindet sich im gleichen Ordner mit den designspezifischen Ressourcenverzeichnisdateien. Obwohl `generic.xaml` keinem bestimmten Windows-Design entspricht, ist es dennoch ein Ressourcenverzeichnis auf der Designebene.

Das benutzerdefinierte Steuerelement ["C"](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) oder ["Visual Basic](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) NumericUpDown" mit Design- `NumericUpDown` und UI-Automatisierungsunterstützung enthält zwei Ressourcenwörterbücher für das Steuerelement: eines in generic.xaml und das andere in Luna.NormalColor.xaml.

Wenn Sie <xref:System.Windows.Controls.ControlTemplate> eine in einer der themenspezifischen Ressourcenwörterbuchdateien absetzen, müssen Sie einen <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> statischen <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>Konstruktor für das Steuerelement erstellen und die Methode auf der aufrufen, wie im folgenden Beispiel gezeigt.

[!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
[!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]

##### <a name="defining-and-referencing-keys-for-theme-resources"></a>Definieren und Angeben von Schlüsseln für Designressourcen

Wenn Sie eine Ressource auf der Elementebene definieren, können Sie ihr als Schlüssel eine Zeichenfolge zuweisen und über diese Zeichenfolge auf sie zugreifen. Wenn Sie eine Ressource auf Designebene definieren, <xref:System.Windows.ComponentResourceKey> müssen Sie eine als Schlüssel verwenden.  Im folgenden Beispiel wird eine Ressource in generic.xaml definiert.

[!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]

Im folgenden Beispiel wird auf <xref:System.Windows.ComponentResourceKey> die Ressource verwiesen, indem die als Schlüssel angegeben wird.

[!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]

##### <a name="specifying-the-location-of-theme-resources"></a>Angeben des Speicherorts von Designressourcen

Um die Ressourcen für ein Steuerelement zu finden, muss die Hostinganwendung über die Information verfügen, dass die Assembly Ressourcen enthält, die steuerelementenspezifisch sind. Sie können dies <xref:System.Windows.ThemeInfoAttribute> erreichen, indem Sie die der Assembly hinzufügen, die das Steuerelement enthält. Der <xref:System.Windows.ThemeInfoAttribute> verfügt <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> über eine Eigenschaft, die den <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> Speicherort generischer Ressourcen angibt, und eine Eigenschaft, die den Speicherort der themenspezifischen Ressourcen angibt.

Im folgenden Beispiel <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> werden <xref:System.Windows.ResourceDictionaryLocation.SourceAssembly>die und-Eigenschaften auf festgelegt, um anzugeben, dass sich die generischen und die designspezifischen Ressourcen in derselben Assembly wie das Steuerelement befinden.

[!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
[!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]

## <a name="see-also"></a>Siehe auch

- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Paket-URI in WPF](../app-development/pack-uris-in-wpf.md)
- [Anpassung von Steuerelementen](control-customization.md)
