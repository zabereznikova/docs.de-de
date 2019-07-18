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
ms.openlocfilehash: 291edaf49fd8de27bfe0dc10f24cb865793cadc6
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67660368"
---
# <a name="control-authoring-overview"></a>Übersicht über das Erstellen von Steuerelementen

Dank der Erweiterbarkeit des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Steuerelementmodells ist das Erstellen neuer Steuerelemente nur selten erforderlich. In bestimmten Fällen lässt sich das Erstellen benutzerdefinierter Steuerelemente dennoch nicht vermeiden. In diesem Thema werden die Funktionen, dank deren Sie auf das Erstellen neuer Steuerelementen in den meisten Fällen verzichten können, sowie verschiedene Modelle zum Erstellen von Steuerelementen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] behandelt. Außerdem wird in diesem Thema auch das Erstellen eines neuen Steuerelements veranschaulicht.

<a name="when_to_write_a_new_control"></a>

## <a name="alternatives-to-writing-a-new-control"></a>Alternativen zum Erstellen eines neuen Steuerelements

In der Vergangenheit waren Sie bei der Anpassung eines vorhandenen Steuerelements auf die Bearbeitung seiner Standardeigenschaften beschränkt. Sie konnten z.B. die Hintergrundfarbe, die Rahmenbreite sowie die Schriftgröße ändern. Falls Sie die Darstellung oder das Verhalten eines Steuerelements über diese vordefinierten Parameter hinaus erweitern wollten, waren Sie auf das Erstellen eines neuen Steuerelements angewiesen. Die übliche Vorgehensweise war die Vererbung von einem vorhandenen Steuerelement samt der Überschreibung der für das Zeichnen des Steuerelements zuständigen Methode.  Diese Option steht Ihnen zwar weiterhin zur Verfügung, mit dem reichen Inhaltsmodel von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sowie seinen Stilen, Vorlagen und Triggern können Sie jedoch die vorhandenen Steuerelemente auf eine vielfältige Art und Weise anzupassen. In der folgenden Liste finden Sie Beispiele für die Verwendung dieser Funktionen zum Erstellen einer benutzerdefinierten und konsistenten Umgebung, ohne ein neues Steuerelement erstellen zu müssen.

- **Multimediainhalte.** Viele [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Standardsteuerelemente unterstützen Multimediainhalte. Z. B. die Content-Eigenschaft von einem <xref:System.Windows.Controls.Button> ist vom Typ <xref:System.Object>, theoretisch alles angezeigt werden kann, auf eine <xref:System.Windows.Controls.Button>.  Um eine Schaltfläche ein Bild und Text angezeigt haben, können Sie ein Bild hinzufügen und eine <xref:System.Windows.Controls.TextBlock> auf eine <xref:System.Windows.Controls.StackPanel> und weisen Sie die <xref:System.Windows.Controls.StackPanel> auf die <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft. Da die Steuerelemente visuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Elemente sowie beliebige Daten anzeigen können, ist es zwecks der Unterstützung einer komplexen Visualisierung selten notwendig, neue Steuerelemente zu erstellen oder vorhandene Steuerelemente zu ändern. Weitere Informationen über das Inhaltsmodell für <xref:System.Windows.Controls.Button> und andere Inhalte Modelle im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], finden Sie unter [WPF-Inhaltsmodell](wpf-content-model.md).

- **Stile.** Ein <xref:System.Windows.Style> ist eine Sammlung von Werten, die Eigenschaften für ein Steuerelement darstellen. Mit Stilen können Sie eine wiederverwendbare Darstellung der erwünschten Gestaltung und des erwünschten Verhaltens der Steuerelemente erstellen, ohne ein neues Steuerelement erstellen zu müssen. Nehmen wir beispielsweise an, dass Sie alle möchten Ihre <xref:System.Windows.Controls.TextBlock> Steuerelemente roten der Schriftart Arial mit Schriftgrad 14 aufweisen. Sie können einen Stil als eine Ressource anlegen und die jeweiligen Eigenschaften entsprechend festlegen. Und dann jede <xref:System.Windows.Controls.TextBlock> , dass Sie Ihre Anwendung hinzufügen, werden die gleiche Darstellung aufweisen.

- **Datenvorlagen.** Ein <xref:System.Windows.DataTemplate> können Sie anpassen, wie Daten in einem Steuerelement angezeigt werden. Z. B. eine <xref:System.Windows.DataTemplate> kann verwendet werden, um anzugeben, wie Daten in angezeigt werden eine <xref:System.Windows.Controls.ListBox>.  Weitere Beispiele finden Sie unter [Übersicht über Datenvorlagen](../data/data-templating-overview.md).  Zusätzlich zur Anpassung der Darstellung von Daten, eine <xref:System.Windows.DataTemplate> können Elemente der Benutzeroberfläche umfassen die bietet Ihnen ein hohes Maß an Flexibilität in benutzerdefinierte Benutzeroberflächen.  Z. B. durch Verwendung einer <xref:System.Windows.DataTemplate>, können Sie erstellen eine <xref:System.Windows.Controls.ComboBox> in dem jedes Element ein Kontrollkästchen enthält.

- **Steuerelementvorlagen.** Viele Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwenden eine <xref:System.Windows.Controls.ControlTemplate> definieren die Struktur des Steuerelements und die Darstellung der getrennt von der Darstellung eines Steuerelements über die Funktionalität des Steuerelements. Sie können die Darstellung eines Steuerelements erheblich ändern, durch Neudefinieren der <xref:System.Windows.Controls.ControlTemplate>.  Nehmen wir z.B. an, dass Sie ein Steuerelement wie eine Ampel aussehen lassen möchten. Dieses Steuerelement hat eine einfache Benutzeroberfläche und Funktionalität.  Das Steuerelement besteht aus drei Kreisen, von denen jeweils nur ein einziger leuchten kann. Nach einiger Überlegung stellen Sie fest, die eine <xref:System.Windows.Controls.RadioButton> bietet die Funktionalität der nur eine zeilenweise, aber die standarddarstellung der ausgewählten der <xref:System.Windows.Controls.RadioButton> nichts sieht die Lichter an eine Ampel.  Da die <xref:System.Windows.Controls.RadioButton> eine Steuerelementvorlage verwendet, um seine Darstellung zu definieren ist einfach neu definieren die <xref:System.Windows.Controls.ControlTemplate> auf die Anforderungen an das Steuerelement, und Optionsfelder Ampel darstellen lassen.

  > [!NOTE]
  > Obwohl eine <xref:System.Windows.Controls.RadioButton> können eine <xref:System.Windows.DataTemplate>, <xref:System.Windows.DataTemplate> reicht nicht aus, in diesem Beispiel.  Die <xref:System.Windows.DataTemplate> definiert die Darstellung des Inhalts eines Steuerelements. Im Fall von einem <xref:System.Windows.Controls.RadioButton>, den Inhalt handelt, was auf der rechten Seite des Kreises angezeigt wird, der angibt, ob die <xref:System.Windows.Controls.RadioButton> ausgewählt ist.  Im Beispiel mit der Ampel brauchen Sie lediglich das Optionsfeld als einen Kreis darzustellen, das „aufleuchten“ kann. Da die Notwendigkeit der Darstellung der Ampel sich die standarddarstellung ist das <xref:System.Windows.Controls.RadioButton>, es ist erforderlich, neu definieren die <xref:System.Windows.Controls.ControlTemplate>.  Im Allgemeinen eine <xref:System.Windows.DataTemplate> dient zum Definieren der Inhalte oder Daten, ein Steuerelement und einen <xref:System.Windows.Controls.ControlTemplate> dient zum Definieren der Struktur eines Steuerelements ist.

- **Trigger.** Ein <xref:System.Windows.Trigger> können Sie das Aussehen und Verhalten eines Steuerelements dynamisch ändern, ohne ein neues Steuerelement erstellen zu müssen. Nehmen wir beispielsweise an, Sie verfügen über mehrere <xref:System.Windows.Controls.ListBox> -Steuerelemente in Ihrer Anwendung und möchten Sie die Elemente in jedem <xref:System.Windows.Controls.ListBox> fett und Rot sein, wenn sie ausgewählt werden. Möglicherweise zuerst eine Klasse erstellen, die von erbt <xref:System.Windows.Controls.ListBox> und überschreiben die <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> Methode so ändern Sie die Darstellung des ausgewählten Elements ist jedoch ein besserer Ansatz besteht darin, einen Trigger hinzugefügt haben, einem Stil ein <xref:System.Windows.Controls.ListBoxItem> , die die Darstellung der Änderungen das ausgewählte Element. Mit Triggern können Sie Eigenschaftswerte bearbeiten oder basierend auf den Eigenschaftswerten Aktionen ausführen. Ein <xref:System.Windows.EventTrigger> ermöglicht es Ihnen, Aktionen, wenn ein Ereignis auftritt.

Weitere Informationen zu Stilen, Vorlagen und Triggern finden Sie unter [Erstellen von Formaten und Vorlagen](styling-and-templating.md).

Im Allgemeinen gilt: wenn das benötigte Steuerelement die Funktionalität eines vorhandenen Steuerelements nachmacht, aber anders aussehen soll, lohnt es sich zuerst zu überlegen, ob Sie mit einem der in diesem Abschnitt beschriebenen Verfahren die vorhandene Darstellung des Steuerelements ändern können.

<a name="models_for_control_authoring"></a>

## <a name="models-for-control-authoring"></a>Modelle für das Erstellen von Steuerelementen

Dank dem umfangreichen Inhaltsmodell sowie Stilen, Vorlagen und Triggern können Sie in den meisten Fällen auf das Erstellen neuer Steuerelemente verzichten. Falls Sie jedoch ein neues Steuerelement erstellen müssen, ist es wichtig Modelle für das Erstellen von Steuerelementen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu verstehen. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet drei allgemeine Modelle zum Erstellen der Steuerelemente, die jeweils verschiedene Funktionen und Flexibilitätsgrade bieten. Die Basisklassen für die drei Modelle sind <xref:System.Windows.Controls.UserControl>, <xref:System.Windows.Controls.Control>, und <xref:System.Windows.FrameworkElement>.

### <a name="deriving-from-usercontrol"></a>Ableiten von UserControl

Die einfachste Möglichkeit zum Erstellen eines Steuerelements in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist eine Ableitung <xref:System.Windows.Controls.UserControl>. Wenn Sie ein Steuerelement erstellen, erbt von <xref:System.Windows.Controls.UserControl>, Sie die vorhandene Komponenten zum Hinzufügen der <xref:System.Windows.Controls.UserControl>, benennen Sie die Komponenten und verweisen Sie Ereignishandler in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Anschließend können Sie auf die benannten Elemente verweisen und die Ereignishandler im Code definieren. Dieses Entwicklungsmodell ähnelt sehr dem Modell für die Anwendungsentwicklung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Wenn ordnungsgemäß erstellt eine <xref:System.Windows.Controls.UserControl> nutzen die Vorteile der umfangreiche Inhalte, Stile und Trigger. Allerdings, wenn das Steuerelement erbt <xref:System.Windows.Controls.UserControl>, Personen, die das Steuerelement werden nicht in der Lage, mit einem <xref:System.Windows.DataTemplate> oder <xref:System.Windows.Controls.ControlTemplate> um ihre Darstellung anzupassen.  Es ist erforderlich, für die Ableitung der <xref:System.Windows.Controls.Control> Klasse oder einer ihrer abgeleiteten Klassen (außer <xref:System.Windows.Controls.UserControl>) um ein benutzerdefiniertes Steuerelement zu erstellen, das Vorlagen unterstützt.

#### <a name="benefits-of-deriving-from-usercontrol"></a>Vorteile des Ableitens von UserControl

Erwägen Sie eine Ableitung von <xref:System.Windows.Controls.UserControl> wenn Folgendes zutrifft:

- Sie möchten das Steuerelement auf eine ähnliche Art und Weise erstellen, wie Sie Ihre Anwendung erstellt haben.

- Ihr Steuerelement besteht ausschließlich aus vorhandenen Komponenten.

- Es muss keine komplexe Anpassung unterstützt werden.

### <a name="deriving-from-control"></a>Ableiten von Control

Ableiten von der <xref:System.Windows.Controls.Control> -Klasse ist das Modell, das meisten der vorhandenen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente. Wenn Sie ein Steuerelement erstellen, erbt die <xref:System.Windows.Controls.Control> -Klasse, definieren Sie seine Darstellung mithilfe von Vorlagen. Dadurch trennen Sie die Funktionslogik von der visuellen Darstellung. Sie können auch sicherstellen, die Entkopplung von der Benutzeroberfläche und Logik mithilfe der Befehle und Bindungen anstelle von Ereignissen und vermeiden Verweise auf Elemente in der <xref:System.Windows.Controls.ControlTemplate> wann immer möglich.  Wenn die Benutzeroberfläche und die Logik Ihres Steuerelements korrekt entkoppelt ist, kann ein Benutzer des Steuerelements des Steuerelements redefine <xref:System.Windows.Controls.ControlTemplate> um ihre Darstellung anzupassen. Obwohl das Erstellen einer benutzerdefinierten <xref:System.Windows.Controls.Control> ist nicht so einfach wie das Erstellen von einer <xref:System.Windows.Controls.UserControl>, eine benutzerdefinierte <xref:System.Windows.Controls.Control> bietet die größte Flexibilität.

#### <a name="benefits-of-deriving-from-control"></a>Vorteile des Ableitens von Control

Erwägen Sie eine Ableitung von <xref:System.Windows.Controls.Control> anstelle der <xref:System.Windows.Controls.UserControl> Klasse, wenn eine der folgenden Bedingungen zutrifft:

- Die Darstellung des Steuerelements über anpassbar sein sollen die <xref:System.Windows.Controls.ControlTemplate>.

- Das Steuerelement soll verschiedene Designs unterstützen.

### <a name="deriving-from-frameworkelement"></a>Ableitung von FrameworkElement

Steuerelemente, die abgeleitet <xref:System.Windows.Controls.UserControl> oder <xref:System.Windows.Controls.Control> basieren auf dem Zusammensetzen vorhandener Elemente. In vielen Fällen ist es sich hierbei um eine akzeptable Lösung, da jedes Objekt, das von erbt <xref:System.Windows.FrameworkElement> kann eine <xref:System.Windows.Controls.ControlTemplate>. Es gibt jedoch Situationen, in denen die Darstellung eines Steuerelements mehr als die Funktionalität einer einfachen Elementzusammensetzung erfordert. Wenn Sie eine Komponente für diese Szenarien auf <xref:System.Windows.FrameworkElement> ist die richtige Wahl.

Es gibt zwei Standardmethoden zum Erstellen von <xref:System.Windows.FrameworkElement>-basierte Komponenten: direkte Rendering und benutzerdefinierte elementzusammensetzung. Direkte Rendering beinhaltet das Überschreiben der <xref:System.Windows.UIElement.OnRender%2A> -Methode der <xref:System.Windows.FrameworkElement> und <xref:System.Windows.Media.DrawingContext> Vorgänge, die visuelle Struktur der Komponente explizit zu definieren. Dies ist die Methode ein, die <xref:System.Windows.Controls.Image> und <xref:System.Windows.Controls.Border>. Benutzerdefinierte elementzusammensetzung umfasst das Verwenden von Objekten des Typs <xref:System.Windows.Media.Visual> um die Darstellung Ihrer Komponente zu erstellen. Beispiele finden Sie unter [Verwenden von DrawingVisual-Objekten](../graphics-multimedia/using-drawingvisual-objects.md). <xref:System.Windows.Controls.Primitives.Track> ist ein Beispiel für ein Steuerelement [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , die benutzerdefinierte elementkomposition verwendet. Sie können auch direktes Rendering und benutzerdefinierte Elementzusammensetzung innerhalb eines Steuerelements kombinieren.

#### <a name="benefits-of-deriving-from-frameworkelement"></a>Vorteile der Ableitung von FrameworkElement

Erwägen Sie eine Ableitung von <xref:System.Windows.FrameworkElement> Wenn einer der folgenden Bedingungen zutrifft:

- Sie brauchen eine genaue Steuerung der Darstellung Ihres Steuerelements, die darüber hinausgeht, was mit einer einfachen Elementzusammensetzung möglich ist.

- Sie möchten die Darstellung Ihres Steuerelements definieren, indem Sie Ihre eigene Renderinglogik definieren.

- Sie möchten vorhandene Elemente in einer Weise neu zu erstellen, die Möglichkeiten hinausgehen <xref:System.Windows.Controls.UserControl> und <xref:System.Windows.Controls.Control>.

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

- Definieren einer <xref:System.Windows.DependencyProperty> Bezeichner, die mit dem Namen `ValueProperty` als eine `public` `static` `readonly` Feld.

- Der Eigenschaftenname im Eigenschaftensystem registriert, durch den Aufruf <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType>, um Folgendes anzugeben:

  - Den Namen der Eigenschaft.

  - Den Typ der Eigenschaft.

  - Den Typ, der die Eigenschaft besitzt.

  - Die Metadaten für die Eigenschaft. Die Metadaten enthält den Wert der Eigenschaft standardmäßig, eine <xref:System.Windows.CoerceValueCallback> und <xref:System.Windows.PropertyChangedCallback>.

- Eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Wrappereigenschaft mit dem Namen `Value` wird definiert. Es ist der gleiche Name, mit dem die Abhängigkeitseigenschaft registriert wurde, indem die `get` und `set` Zugriffmethoden der Eigenschaft implementiert wurden. Beachten Sie, dass die `get` und `set` Accessoren nur rufen <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> bzw. Es wird empfohlen, dass die zugriffmethoden von Abhängigkeitseigenschaften keine zusätzlichen Logik enthalten, da Clients und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] umgehen können, der Accessoren und rufen <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> direkt. Falls eine Eigenschaft z.B. an eine Datenquelle gebunden ist, wird die `set`-Zugriffmethode der Eigenschaft nicht aufgerufen.  Anstatt zum Hinzufügen von zusätzlichen Logik zu Get und set-Accessor, verwenden Sie die <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.CoerceValueCallback>, und <xref:System.Windows.PropertyChangedCallback> Delegaten zu reagieren bzw. Überprüfen Sie den Wert ein, wenn sich diese ändern.  Weitere Informationen zu diesen Rückrufen finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](../advanced/dependency-property-callbacks-and-validation.md).

- Definieren Sie eine Methode für die <xref:System.Windows.CoerceValueCallback> mit dem Namen `CoerceValue`. `CoerceValue` stellt sicher, dass `Value` größer oder gleich `MinValue` und kleiner oder gleich `MaxValue` ist.

- Definieren Sie eine Methode für die <xref:System.Windows.PropertyChangedCallback>mit dem Namen `OnValueChanged`. `OnValueChanged` erstellt eine <xref:System.Windows.RoutedPropertyChangedEventArgs%601> -Objekt und bereitet Sie zum Auslösen der `ValueChanged` Routingereignis. Routingereignisse werden im nächsten Abschnitt erläutert.

[!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
[!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]

Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../advanced/custom-dependency-properties.md).

### <a name="use-routed-events"></a>Verwenden von Routingereignissen

Ebenso wie Abhängigkeitseigenschaften, die das Konzept der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Eigenschaften um zusätzliche Funktionen erweitern, erweitern Routingereignisse das Konzept der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Standardereignisse. Beim Erstellen eines neuen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelements empfiehlt es sich, Ihr Ereignis als ein Routingereignis zu implementieren, da Routingereignisse folgendes Verhalten unterstützen:

- Ereignisse für mehrere Steuerelemente können über ein übergeordnetes Steuerelement behandelt werden. Falls es sich bei dem Ereignis um ein Bubbling-Ereignis handelt, kann ein einzelnes übergeordnetes Element in der Elementstruktur das Ereignis abonnieren. Anschließend können Anwendungsentwickler mit einem Handler auf das Ereignis mehrerer Steuerelemente reagieren. Z. B., wenn das Steuerelement wird von jedem Element in einer <xref:System.Windows.Controls.ListBox> (weil es in enthalten ist ein <xref:System.Windows.DataTemplate>), der Anwendungsentwickler kann den Ereignishandler für das-Ereignis des Steuerelements definieren, auf die <xref:System.Windows.Controls.ListBox>. Beim Auftreten des Ereignisses bei einem der Steuerelemente wird der Ereignishandler aufgerufen.

- Routingereignisse können verwendet werden, eine <xref:System.Windows.EventSetter>, damit Anwendungsentwickler den Handler eines Ereignisses innerhalb eines Stils angeben.

- Routingereignisse können verwendet werden, eine <xref:System.Windows.EventTrigger>, dies ist hilfreich zum Animieren von Eigenschaften mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Weitere Informationen finden Sie unter [Übersicht über Animation](../graphics-multimedia/animation-overview.md).

Im folgenden Beispiel wird ein Routingereignis wie folgt definiert:

- Definieren einer <xref:System.Windows.RoutedEvent> Bezeichner, die mit dem Namen `ValueChangedEvent` als eine `public` `static` `readonly` Feld.

- Registrieren Sie das Routingereignis durch Aufrufen der <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType> Methode. Im Beispiel gibt die folgenden Informationen an, beim Aufrufen <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>:

  - Der Name des Ereignisses lautet `ValueChanged`.

  - Die Routingstrategie ist <xref:System.Windows.RoutingStrategy.Bubble>, was bedeutet, dass ein Ereignishandler für die Quelle (das Objekt, das das Ereignis auslöst) zuerst aufgerufen wird, und klicken Sie dann Ereignishandler für den übergeordneten Elementen von der Quelle nacheinander aufgerufen, beginnend mit dem am nächsten Ereignishandler übergeordnetes Element.

  - Der Typ des ereignishandlers ist <xref:System.Windows.RoutedPropertyChangedEventHandler%601>, erstellte mit einem <xref:System.Decimal> Typ.

  - `NumericUpDown` ist der besitzende Typ des Ereignisses.

- Ein öffentliches Ereignis mit dem Namen `ValueChanged`, das die Zugriffsmethoden-Deklarationen umfasst, wird deklariert. Das Beispiel ruft <xref:System.Windows.UIElement.AddHandler%2A> in die `add` Zugriffsmethoden-Deklaration und <xref:System.Windows.UIElement.RemoveHandler%2A> in die `remove` Zugriffsmethoden-Deklaration mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Ereignisdienste.

- Eine geschützte virtuelle Methode mit dem Namen `OnValueChanged`, die das`ValueChanged`-Ereignis auslöst, wird erstellt.

[!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
[!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]

Weitere Informationen finden Sie unter [ Übersicht über Routingereignisse ](../advanced/routed-events-overview.md) und [Vorgehensweise: Erstellen eines benutzerdefinierten Routingereignisses](../advanced/how-to-create-a-custom-routed-event.md).

### <a name="use-binding"></a>Verwendung von Bindungen

Erwägen Sie Datenbindungen, um die Benutzeroberfläche Ihres Steuerelements von der Logik zu entkoppeln. Dies ist besonders wichtig, wenn Sie mit der Darstellung Ihres Steuerelements definieren eine <xref:System.Windows.Controls.ControlTemplate>. Bei der Verwendung einer Datenbindung können Sie u.U. auf die Verweise auf bestimmte Teile der Benutzeroberfläche aus dem Code verzichten. Es ist eine gute Idee, vermeiden Sie Verweise auf Elemente in der <xref:System.Windows.Controls.ControlTemplate> da bei der Code für Elemente, die verweist in der <xref:System.Windows.Controls.ControlTemplate> und <xref:System.Windows.Controls.ControlTemplate> geändert wird, wird der Verweiselement muss in der neuen aufgenommen werden <xref:System.Windows.Controls.ControlTemplate>.

Das folgende Beispiel aktualisiert die <xref:System.Windows.Controls.TextBlock> von der `NumericUpDown` Steuerelement, ein Name zugewiesen, und verweisen auf das Textfeld im Code mit Namen.

[!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]

[!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
[!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]

Im folgenden Beispiel wird eine Bindung für den selben Zweck verwendet.

[!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]

Weitere Informationen zu Datenbindungen finden Sie unter [Übersicht über Datenbindung](../data/data-binding-overview.md).

### <a name="design-for-designers"></a>Darstellung für Designer

Um Support für benutzerdefinierte WPF-Steuerelemente in [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] zu erhalten (z.B. bezüglich der Eigenschaftenbearbeitung mit dem Eigenschaftenfenster), befolgen Sie die folgenden Richtlinien.  Weitere Informationen zur Entwicklung für die [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)], finden Sie unter [Entwerfen von XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).

#### <a name="dependency-properties"></a>Abhängigkeitseigenschaften

Stellen Sie sicher, dass die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], `get` und `set`-Zugriffsmethoden wie oben beschrieben inplementiert worden sind, siehe „Verwenden von Abhängigkeitseigenschaften“. Designer können Wrapper zur Prüfung des Vorhandenseins einer Abhängigkeitseigenschaft verwenden. Diese müssen, genauso wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und Clients des Steuerelements, beim Abrufen oder Festlegen der Eigenschaft jedoch keine Zugriffsmethoden aufrufen.

#### <a name="attached-properties"></a>Angefügte Eigenschaften

Angefügte Eigenschaften für benutzerdefinierte Steuerelemente sind unter Einhaltung der folgenden Richtlinien zu implementieren:

- Haben eine `public` `static` `readonly` <xref:System.Windows.DependencyProperty> des Formulars *PropertyName* `Property` , die erstellt wurde, mithilfe der <xref:System.Windows.DependencyProperty.RegisterAttached%2A> Methode. Der Eigenschaftenname, der an übergebene <xref:System.Windows.DependencyProperty.RegisterAttached%2A> übereinstimmen *PropertyName*.

- Implementieren Sie die `public` `static` CLR-Methoden mit den Namen `Set` *PropertyName* und `Get` *PropertyName*. Beide Methoden sollten eine von abgeleitete Klasse akzeptieren <xref:System.Windows.DependencyProperty> als das erste Argument. Die `Set`*PropertyName*-Methode akzeptiert auch ein Argument, dessen Typ mit dem registrierten Datentyp der Eigenschaft übereinstimmt. Die `Get`*PropertyName*-Methode sollte einen Wert zurückgeben, der den gleichen Typ aufweist. Falls die `Set`*PropertyName*-Methode fehlt, wird die Eigenschaft als schreibgeschützt gekennzeichnet.

- `Set` *PropertyName* und `Get` *PropertyName* direkt weiterleiten muss die <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> Zielabhängigkeitsobjekt Methoden für die Ziel-Abhängigkeit. Designer können auf die angefügte Eigenschaft entweder über einen Aufruf des Wrappers für die Methode zugreifen, oder indem sie das Zielabhängigkeitsobjekt direkt aufrufen.

Weitere Informationen zu angefügten Eigenschaften finden Sie in der [Übersicht über angefügte Eigenschaften](../advanced/attached-properties-overview.md).

### <a name="define-and-use-shared-resources"></a>Definieren und Verwenden von freigegebenen Ressourcen

Sie können Ihr Steuerelement entweder in die Assembly Ihrer Anwendung, oder in eine separate Assembly einbinden, die in mehreren Anwendungen verwendet werden kann. Der Großteil der in diesem Thema erläuterten Informationen gilt unabhängig von der von Ihnen verwendeten Methode.  Ein wesentlicher Unterschied ist dennoch zu beachten.  Falls Sie ein Steuerelement in die Assembly einer Anwendung einbinden, können Sie der App.xaml-Datei globale Ressourcen hinzufügen. Aber eine Assembly, die nur Steuerelemente enthält, verfügt nicht über eine <xref:System.Windows.Application> Objekt zugeordnet, sodass eine "App.xaml" nicht verfügbar ist.

Wenn eine Anwendung nach einer Ressource sucht,wird auf drei Ebenen in der folgenden Reihenfolge gesucht:

1. Die Elementebene.

   Das System beginnt mit dem Element, das auf die Ressource verweist, und sucht anschließend die Ressourcen des logischen übergeordneten Elements durch. Dieser Schritt wir wiederholt, bis das Stammelement erreicht ist.

2. Die Anwendungsebene.

   Ressourcen, die von definiert die <xref:System.Windows.Application> Objekt.

3. Die Designebene.

   Ressourcenverzeichnisse werden auf der Designebene in einem Themes-Unterordner gespeichert.  Die Dateien im Themes-Ordner entsprechen den Designs.  Dort könnten Sie beispielsweise Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml, etc. finden.  Möglicherweise ist auch eine Datei mit dem Namen generic.xaml enthalten.  Bei einer Suche nach einer Ressource auf der Designebene wird zunächst in der designspezifischen Datei und dann in der Datei generic.xaml gesucht.

Falls Ihr Steuerelement in einer anderen Assembly als die Anwendung liegt, müssen Sie Ihre globale Ressourcen auf die Elementen- oder Designebene umspeichern. Beide Methoden haben ihre Vorteile.

#### <a name="defining-resources-at-the-element-level"></a>Definieren von Ressourcen auf der Elementebene

Sie können freigegebene Ressourcen auf der Elementebene definieren, indem Sie ein benutzerdefiniertes Ressourcenverzeichnis erstellen und es mit dem Ressourcenverzeichnis Ihres Steuerelements zusammenführen.  Falls Sie sich für diese Methode entscheiden, können Sie die Ressourcendatei beliebig benennen und sie im Ordner speichern, wo Ihre Steuerelemente liegen. Für Ressourcen auf der Elementebene können ebenso einfache Zeichenfolgen als Schlüssel verwendet werden. Das folgende Beispiel erstellt eine <xref:System.Windows.Media.LinearGradientBrush> Ressourcendatei mit dem Namen Dictionary1.XAML angelegt.

[!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]

Nachdem Sie das Ressourcenverzeichnis definiert haben, müssen Sie es mit dem Ressourcenverzeichnis des Steuerelements zusammenführen.  Hierzu können Sie [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder Code verwenden.

Im folgenden Beispiel wird ein Ressourcenverzeichnis mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zusammengeführt.

[!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]

Der Nachteil dieses Ansatzes besteht darin, die eine <xref:System.Windows.ResourceDictionary> Objekt erstellt, wenn Sie darauf verweisen.  Z. B. Wenn Sie 10 benutzerdefinierte Steuerelemente in der Bibliothek und die freigegebenen Ressourcenverzeichnisse für jedes Steuerelement mit XAML zusammenführen, Sie erstellen 10 identische <xref:System.Windows.ResourceDictionary> Objekte.  Sie können dies verhindern, erstellen Sie eine statische Klasse, die die Ressourcen im Code zusammenführt, und gibt das resultierende <xref:System.Windows.ResourceDictionary>.

Das folgende Beispiel erstellt eine Klasse, die eine freigegebene gibt <xref:System.Windows.ResourceDictionary>.

[!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]

Im folgenden Beispiel wird die freigegebene Ressource mit den Ressourcen eines benutzerdefinierten Steuerelements im Konstruktor des Steuerelements zusammengeführt, bevor sie `InitializeComponent` aufruft.  Da die `SharedDictionaryManager.SharedDictionary` ist eine statische Eigenschaft, die <xref:System.Windows.ResourceDictionary> wird nur einmal erstellt. Da das Ressourcenverzeichnis vor dem Aufruf von `InitializeComponent` zusammengeführt worden ist, kann das Steuerelement auf die Ressourcen in seiner [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Datei zugreifen.

[!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]

#### <a name="defining-resources-at-the-theme-level"></a>Definieren von Ressourcen auf der Designebene

Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie Ressourcen für verschiedene Windows-Designs erstellen.  Als Autor des Steuerelements können Sie eine Ressource für ein bestimmtes Design definieren, um die Darstellung Ihres Steuerelements an das jeweils verwendete Design anzupassen. Z. B. die Darstellung des eine <xref:System.Windows.Controls.Button> Design (das Standarddesign für Windows 2000) auf der Windows-klassisch unterscheidet sich von einer <xref:System.Windows.Controls.Button> im Windows Luna-Design (das Standarddesign für Windows XP) da die <xref:System.Windows.Controls.Button> verwendet ein anderes <xref:System.Windows.Controls.ControlTemplate> für jedes Design.

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

[Beispiel für benutzerdefiniertes NumericUpDown-Steuerelement mit Unterstützung von Designs und Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=160025) enthält zwei Ressourcenverzeichnisse für das `NumericUpDown`-Steuerelement: jeweils in den Dateien generic.xaml und Luna.NormalColor.xaml.  Um den Unterschied zwischen den beiden Steuerelementvorlagen zu sehen, starten Sie die Anwendung, und wechseln Sie zwischen dem silbernen Design für Windows XP und einem anderen Design. (Unter Windows Vista können Sie die Datei Luna.NormalColor.xaml in Aero.NormalColor.xaml umbenennen und zwischen zwei Designs, z.B. Windows - klassisch und Standarddesign für Windows Vista, wechseln.)

Wenn Sie Einfügen ein <xref:System.Windows.Controls.ControlTemplate> in einer der designspezifischen ressourcenverzeichnisdateien, müssen Sie einen statischen Konstruktor für Ihr Steuerelement und rufen erstellen die <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> Methode für die <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>, wie im folgenden Beispiel gezeigt.

[!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
[!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]

##### <a name="defining-and-referencing-keys-for-theme-resources"></a>Definieren und Angeben von Schlüsseln für Designressourcen

Wenn Sie eine Ressource auf der Elementebene definieren, können Sie ihr als Schlüssel eine Zeichenfolge zuweisen und über diese Zeichenfolge auf sie zugreifen. Wenn Sie eine Ressource auf der Designebene definieren, müssen Sie verwenden eine <xref:System.Windows.ComponentResourceKey> als Schlüssel.  Im folgenden Beispiel wird eine Ressource in generic.xaml definiert.

[!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]

Im folgende Beispiel wird auf die Ressource durch Angabe der <xref:System.Windows.ComponentResourceKey> als Schlüssel.

[!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]

##### <a name="specifying-the-location-of-theme-resources"></a>Angeben des Speicherorts von Designressourcen

Um die Ressourcen für ein Steuerelement zu finden, muss die Hostinganwendung über die Information verfügen, dass die Assembly Ressourcen enthält, die steuerelementenspezifisch sind. Sie erreichen, die durch das Hinzufügen der <xref:System.Windows.ThemeInfoAttribute> auf die Assembly, die das Steuerelement enthält. Die <xref:System.Windows.ThemeInfoAttribute> verfügt über eine <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> -Eigenschaft, die den Speicherort generischer Ressourcen angibt und ein <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> -Eigenschaft, die den Speicherort der designspezifischen Ressourcen angibt.

Im folgenden Beispiel wird die <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> und <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> Eigenschaften <xref:System.Windows.ResourceDictionaryLocation.SourceAssembly>, um anzugeben, dass die generischen und designspezifischen Ressourcen in der gleichen Assembly wie das Steuerelement befinden.

[!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
[!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]

## <a name="see-also"></a>Siehe auch

- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Paket-URI in WPF](../app-development/pack-uris-in-wpf.md)
- [Anpassung von Steuerelementen](control-customization.md)
