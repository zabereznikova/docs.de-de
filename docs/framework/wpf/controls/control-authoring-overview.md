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
ms.openlocfilehash: 3ea5519259ba2ee31bfd6bc25f6bedf1f1250799
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401546"
---
# <a name="control-authoring-overview"></a>Übersicht über das Erstellen von Steuerelementen

Dank der Erweiterbarkeit des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Steuerelementmodells ist das Erstellen neuer Steuerelemente nur selten erforderlich. In bestimmten Fällen lässt sich das Erstellen benutzerdefinierter Steuerelemente dennoch nicht vermeiden. In diesem Thema werden die Funktionen, dank deren Sie auf das Erstellen neuer Steuerelementen in den meisten Fällen verzichten können, sowie verschiedene Modelle zum Erstellen von Steuerelementen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] behandelt. Außerdem wird in diesem Thema auch das Erstellen eines neuen Steuerelements veranschaulicht.

<a name="when_to_write_a_new_control"></a>

## <a name="alternatives-to-writing-a-new-control"></a>Alternativen zum Erstellen eines neuen Steuerelements

In der Vergangenheit waren Sie bei der Anpassung eines vorhandenen Steuerelements auf die Bearbeitung seiner Standardeigenschaften beschränkt. Sie konnten z.B. die Hintergrundfarbe, die Rahmenbreite sowie die Schriftgröße ändern. Falls Sie die Darstellung oder das Verhalten eines Steuerelements über diese vordefinierten Parameter hinaus erweitern wollten, waren Sie auf das Erstellen eines neuen Steuerelements angewiesen. Die übliche Vorgehensweise war die Vererbung von einem vorhandenen Steuerelement samt der Überschreibung der für das Zeichnen des Steuerelements zuständigen Methode.  Diese Option steht Ihnen zwar weiterhin zur Verfügung, mit dem reichen Inhaltsmodel von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sowie seinen Stilen, Vorlagen und Triggern können Sie jedoch die vorhandenen Steuerelemente auf eine vielfältige Art und Weise anzupassen. In der folgenden Liste finden Sie Beispiele für die Verwendung dieser Funktionen zum Erstellen einer benutzerdefinierten und konsistenten Umgebung, ohne ein neues Steuerelement erstellen zu müssen.

- **Multimediainhalte.** Viele [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Standardsteuerelemente unterstützen Multimediainhalte. Die Content-Eigenschaft eines <xref:System.Windows.Controls.Button> ist beispielsweise vom Typ <xref:System.Object>, sodass theoretisch alles auf einem <xref:System.Windows.Controls.Button>angezeigt werden kann.  Wenn eine Schaltfläche ein Bild und Text anzeigen soll, können Sie ein Bild und ein <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.StackPanel> einem hinzufügen <xref:System.Windows.Controls.ContentControl.Content%2A> und das <xref:System.Windows.Controls.StackPanel> der-Eigenschaft zuweisen. Da die Steuerelemente visuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Elemente sowie beliebige Daten anzeigen können, ist es zwecks der Unterstützung einer komplexen Visualisierung selten notwendig, neue Steuerelemente zu erstellen oder vorhandene Steuerelemente zu ändern. Weitere Informationen zum Inhalts Modell für <xref:System.Windows.Controls.Button> und andere Inhalts Modelle in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]finden Sie unter [WPF-Inhalts Modell](wpf-content-model.md).

- **Stile.** Eine <xref:System.Windows.Style> ist eine Auflistung von Werten, die Eigenschaften für ein Steuerelement darstellen. Mit Stilen können Sie eine wiederverwendbare Darstellung der erwünschten Gestaltung und des erwünschten Verhaltens der Steuerelemente erstellen, ohne ein neues Steuerelement erstellen zu müssen. Angenommen, Sie möchten, dass alle <xref:System.Windows.Controls.TextBlock> Steuerelemente eine rote, Arial Schriftart mit einem Schrift Grad von 14 haben. Sie können einen Stil als eine Ressource anlegen und die jeweiligen Eigenschaften entsprechend festlegen. Dann wird <xref:System.Windows.Controls.TextBlock> jedes, das Sie der Anwendung hinzufügen, dasselbe Aussehen.

- **Datenvorlagen.** Mit <xref:System.Windows.DataTemplate> einem können Sie anpassen, wie Daten auf einem-Steuerelement angezeigt werden. So <xref:System.Windows.DataTemplate> kann z. b. verwendet werden, um anzugeben, wie Daten in <xref:System.Windows.Controls.ListBox>einem angezeigt werden.  Weitere Beispiele finden Sie unter [Übersicht über Datenvorlagen](../data/data-templating-overview.md).  Zusätzlich zur Anpassung der Darstellung von Daten kann ein <xref:System.Windows.DataTemplate> Benutzeroberflächen Elemente enthalten, die Ihnen einen großen Flexibilität in benutzerdefinierten Benutzeroberflächen bieten.  Beispielsweise können Sie mit <xref:System.Windows.DataTemplate>einem eine <xref:System.Windows.Controls.ComboBox> erstellen, in der jedes Element ein Kontrollkästchen enthält.

- **Steuerelementvorlagen.** Viele Steuerelemente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in verwenden <xref:System.Windows.Controls.ControlTemplate> ein, um die Struktur und die Darstellung des Steuer Elements zu definieren, die die Darstellung eines-Steuer Elements von der Funktionalität des-Steuer Elements trennt. Sie können die Darstellung eines Steuer Elements drastisch ändern, indem Sie dessen <xref:System.Windows.Controls.ControlTemplate>neu definieren.  Nehmen wir z.B. an, dass Sie ein Steuerelement wie eine Ampel aussehen lassen möchten. Dieses Steuerelement hat eine einfache Benutzeroberfläche und Funktionalität.  Das Steuerelement besteht aus drei Kreisen, von denen jeweils nur ein einziger leuchten kann. Nach einiger Reflektion können Sie feststellen, <xref:System.Windows.Controls.RadioButton> dass ein-Wert die Funktionalität von nur einem gleichzeitig ausgewählten bietet, aber die Standarddarstellung <xref:System.Windows.Controls.RadioButton> des sieht nicht so aus, wie die Lichter auf einem stoplight.  Da eine Steuerelement Vorlage <xref:System.Windows.Controls.ControlTemplate> verwendet,umdieDarstellungzudefinieren,isteseinfach,das-Elementsozudefinieren,dassesdenAnforderungendes-SteuerElementsentspricht,undmithilfevonOptionsFelderndasstoplightzumachen.<xref:System.Windows.Controls.RadioButton>

  > [!NOTE]
  > Obwohl eine eine <xref:System.Windows.DataTemplate>verwenden <xref:System.Windows.DataTemplate> kann, ist in diesem Beispiel nicht ausreichend. <xref:System.Windows.Controls.RadioButton>  <xref:System.Windows.DataTemplate> Definiert die Darstellung des Inhalts eines-Steuer Elements. Im Fall eines <xref:System.Windows.Controls.RadioButton>wird der Inhalt auf der rechten Seite des Kreises angezeigt, der angibt, <xref:System.Windows.Controls.RadioButton> ob ausgewählt ist.  Im Beispiel mit der Ampel brauchen Sie lediglich das Optionsfeld als einen Kreis darzustellen, das „aufleuchten“ kann. Da sich die Darstellungs Anforderung für das Ampel von der Standarddarstellung von <xref:System.Windows.Controls.RadioButton>unterscheidet, muss die <xref:System.Windows.Controls.ControlTemplate>neu definiert werden.  Im Allgemeinen wird <xref:System.Windows.DataTemplate> eine zum Definieren des Inhalts (oder der Daten) eines-Steuer Elements verwendet, <xref:System.Windows.Controls.ControlTemplate> und ein wird verwendet, um zu definieren, wie ein Steuerelement strukturiert ist.

- **Trigger.** Mit <xref:System.Windows.Trigger> einem können Sie die Darstellung und das Verhalten eines Steuer Elements dynamisch ändern, ohne ein neues Steuerelement erstellen zu müssen. Angenommen, Sie verfügen über mehrere <xref:System.Windows.Controls.ListBox> Steuerelemente in der Anwendung und möchten, dass die Elemente in den einzelnen <xref:System.Windows.Controls.ListBox> Steuerelementen Fett und rot sind, wenn Sie ausgewählt werden. Der erste Instinkt besteht darin, eine Klasse zu erstellen, die von <xref:System.Windows.Controls.ListBox> erbt und <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> die-Methode überschreibt, um die Darstellung des ausgewählten Elements zu ändern. ein besserer Ansatz ist jedoch das Hinzufügen eines <xref:System.Windows.Controls.ListBoxItem> -Auslösers zu einem Stil von, der die Darstellung von das ausgewählte Element. Mit Triggern können Sie Eigenschaftswerte bearbeiten oder basierend auf den Eigenschaftswerten Aktionen ausführen. Mit <xref:System.Windows.EventTrigger> können Sie Aktionen ausführen, wenn ein Ereignis auftritt.

Weitere Informationen zu Stilen, Vorlagen und Triggern finden Sie unter [Erstellen von Formaten und Vorlagen](styling-and-templating.md).

Im Allgemeinen gilt: wenn das benötigte Steuerelement die Funktionalität eines vorhandenen Steuerelements nachmacht, aber anders aussehen soll, lohnt es sich zuerst zu überlegen, ob Sie mit einem der in diesem Abschnitt beschriebenen Verfahren die vorhandene Darstellung des Steuerelements ändern können.

<a name="models_for_control_authoring"></a>

## <a name="models-for-control-authoring"></a>Modelle für das Erstellen von Steuerelementen

Dank dem umfangreichen Inhaltsmodell sowie Stilen, Vorlagen und Triggern können Sie in den meisten Fällen auf das Erstellen neuer Steuerelemente verzichten. Falls Sie jedoch ein neues Steuerelement erstellen müssen, ist es wichtig Modelle für das Erstellen von Steuerelementen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu verstehen. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet drei allgemeine Modelle zum Erstellen der Steuerelemente, die jeweils verschiedene Funktionen und Flexibilitätsgrade bieten. Die Basisklassen für die drei Modelle sind <xref:System.Windows.Controls.UserControl>, <xref:System.Windows.Controls.Control>und <xref:System.Windows.FrameworkElement>.

### <a name="deriving-from-usercontrol"></a>Ableiten von UserControl

Die einfachste Möglichkeit zum Erstellen eines Steuer Elements [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in ist das ableiten <xref:System.Windows.Controls.UserControl>von von. Wenn Sie ein Steuerelement erstellen, das von <xref:System.Windows.Controls.UserControl>erbt, fügen Sie vorhandene Komponenten <xref:System.Windows.Controls.UserControl>hinzu, benennen Sie die Komponenten, und verweisen Sie auf [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]Ereignishandler in. Anschließend können Sie auf die benannten Elemente verweisen und die Ereignishandler im Code definieren. Dieses Entwicklungsmodell ähnelt sehr dem Modell für die Anwendungsentwicklung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Wenn Sie ordnungsgemäß erstellt <xref:System.Windows.Controls.UserControl> wurde, kann ein die Vorteile von umfangreichen Inhalten, Stilen und Triggern nutzen. Wenn das Steuerelement jedoch von <xref:System.Windows.Controls.UserControl>erbt, können Personen, die Ihr Steuerelement verwenden, keine <xref:System.Windows.DataTemplate> oder <xref:System.Windows.Controls.ControlTemplate> verwenden, um die Darstellung anzupassen.  Es ist notwendig, von der <xref:System.Windows.Controls.Control> -Klasse oder einer ihrer abgeleiteten Klassen ( <xref:System.Windows.Controls.UserControl>mit Ausnahme von) abzuleiten, um ein benutzerdefiniertes Steuerelement zu erstellen, das Vorlagen unterstützt.

#### <a name="benefits-of-deriving-from-usercontrol"></a>Vorteile des Ableitens von UserControl

Sie können ableiten <xref:System.Windows.Controls.UserControl> von ableiten, wenn Folgendes zutrifft:

- Sie möchten das Steuerelement auf eine ähnliche Art und Weise erstellen, wie Sie Ihre Anwendung erstellt haben.

- Ihr Steuerelement besteht ausschließlich aus vorhandenen Komponenten.

- Es muss keine komplexe Anpassung unterstützt werden.

### <a name="deriving-from-control"></a>Ableiten von Control

Die Ableitung von <xref:System.Windows.Controls.Control> der-Klasse ist das Modell, das von den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] meisten vorhandenen Steuerelementen verwendet wird. Wenn Sie ein Steuerelement erstellen, das von der <xref:System.Windows.Controls.Control> -Klasse erbt, definieren Sie seine Darstellung mithilfe von Vorlagen. Dadurch trennen Sie die Funktionslogik von der visuellen Darstellung. Sie können auch sicherstellen, dass die Benutzeroberfläche und die Logik entkoppelt werden, indem Sie anstelle von Ereignissen Befehle und Bindungen verwenden <xref:System.Windows.Controls.ControlTemplate> und Verweise auf Elemente in der vermeiden, wenn dies möglich ist.  Wenn die Benutzeroberfläche und die Logik des Steuer Elements ordnungsgemäß entkoppelt sind, kann ein Benutzer des Steuer Elements <xref:System.Windows.Controls.ControlTemplate> das Steuerelement neu definieren, um seine Darstellung anzupassen. Obwohl das Entwickeln eines <xref:System.Windows.Controls.Control> benutzerdefinierten nicht so einfach ist wie <xref:System.Windows.Controls.UserControl>das Entwickeln eines <xref:System.Windows.Controls.Control> , bietet ein benutzerdefiniertes die größte Flexibilität.

#### <a name="benefits-of-deriving-from-control"></a>Vorteile des Ableitens von Control

Wenn eine der <xref:System.Windows.Controls.Control> folgenden Bedingungen zutrifft, <xref:System.Windows.Controls.UserControl> empfiehlt es sich, von abzuleiten, anstatt die-Klasse zu verwenden:

- Sie möchten, dass die Darstellung des Steuer Elements über den <xref:System.Windows.Controls.ControlTemplate>anpassbar ist.

- Das Steuerelement soll verschiedene Designs unterstützen.

### <a name="deriving-from-frameworkelement"></a>Ableitung von FrameworkElement

Steuerelemente, die <xref:System.Windows.Controls.UserControl> von <xref:System.Windows.Controls.Control> abgeleitet werden oder auf das Verfassen vorhandener Elemente basieren. In vielen Szenarios ist dies eine akzeptable Lösung, da jedes Objekt, das von <xref:System.Windows.FrameworkElement> erbt, in einem <xref:System.Windows.Controls.ControlTemplate>vorhanden sein kann. Es gibt jedoch Situationen, in denen die Darstellung eines Steuerelements mehr als die Funktionalität einer einfachen Elementzusammensetzung erfordert. Für diese Szenarios ist die Grundlage einer <xref:System.Windows.FrameworkElement> Komponente auf die richtige Wahl.

Es gibt zwei Standardmethoden für die <xref:System.Windows.FrameworkElement>Erstellung von-basierten Komponenten: direktes Rendering und benutzerdefinierte Element Komposition. Das direkte Rendering umfasst das <xref:System.Windows.UIElement.OnRender%2A> überschreiben <xref:System.Windows.FrameworkElement> der- <xref:System.Windows.Media.DrawingContext> Methode von und das Bereitstellen von Vorgängen, die explizit die visuellen Komponenten Dies ist die Methode, die <xref:System.Windows.Controls.Image> von <xref:System.Windows.Controls.Border>und verwendet wird. Die benutzerdefinierte Element Komposition umfasst die Verwendung <xref:System.Windows.Media.Visual> von Objekten des Typs, um das Erscheinungsbild der Komponente zu erstellen. Beispiele finden Sie unter [Verwenden von DrawingVisual-Objekten](../graphics-multimedia/using-drawingvisual-objects.md). <xref:System.Windows.Controls.Primitives.Track>ist ein Beispiel für ein Steuerelement [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in, das die benutzerdefinierte Element Komposition verwendet. Sie können auch direktes Rendering und benutzerdefinierte Elementzusammensetzung innerhalb eines Steuerelements kombinieren.

#### <a name="benefits-of-deriving-from-frameworkelement"></a>Vorteile der Ableitung von FrameworkElement

Sie können ableiten <xref:System.Windows.FrameworkElement> , wenn eine der folgenden Bedingungen zutrifft:

- Sie brauchen eine genaue Steuerung der Darstellung Ihres Steuerelements, die darüber hinausgeht, was mit einer einfachen Elementzusammensetzung möglich ist.

- Sie möchten die Darstellung Ihres Steuerelements definieren, indem Sie Ihre eigene Renderinglogik definieren.

- Sie möchten vorhandene Elemente auf neuartige Weise verfassen, die über die Möglichkeiten von <xref:System.Windows.Controls.UserControl> und <xref:System.Windows.Controls.Control>hinausgehen.

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

- Definieren Sie <xref:System.Windows.DependencyProperty> einen Bezeichner mit `public` dem `ValueProperty` `static` Namen`readonly` als Feld.

- Registrieren Sie den Eigenschaftsnamen beim Eigenschaften System, indem <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType>Sie aufrufen, um Folgendes anzugeben:

  - Der Name der Eigenschaft.

  - Den Typ der Eigenschaft.

  - Den Typ, der die Eigenschaft besitzt.

  - Die Metadaten für die Eigenschaft. Die Metadaten enthalten den Standardwert der Eigenschaft, a <xref:System.Windows.CoerceValueCallback> <xref:System.Windows.PropertyChangedCallback>und.

- Definieren Sie eine CLR-Wrapper `Value`Eigenschaft mit dem Namen, die dem Namen entspricht, der verwendet wird, um die Abhängigkeits Eigenschaft zu `get` registrieren `set` , indem Sie die-und-Accessoren der Eigenschaft implementieren. Beachten Sie, `get` dass `set` die-und- <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> Accessoren nur bzw. aufzurufen. Es wird empfohlen, dass die Accessoren von Abhängigkeits Eigenschaften keine zusätzliche Logik enthalten, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] da Clients und die Accessoren umgehen <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> direkt abrufen können. Falls eine Eigenschaft z.B. an eine Datenquelle gebunden ist, wird die `set`-Zugriffmethode der Eigenschaft nicht aufgerufen.  Anstatt den Get-und Set-Accessoren zusätzliche Logik hinzuzufügen, verwenden <xref:System.Windows.ValidateValueCallback>Sie <xref:System.Windows.CoerceValueCallback>die Delegaten, und <xref:System.Windows.PropertyChangedCallback> , um auf den Wert zu reagieren oder den Wert zu überprüfen, wenn er sich ändert.  Weitere Informationen zu diesen Rückrufen finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](../advanced/dependency-property-callbacks-and-validation.md).

- Definieren Sie eine Methode für <xref:System.Windows.CoerceValueCallback> das `CoerceValue`benannte. `CoerceValue` stellt sicher, dass `Value` größer oder gleich `MinValue` und kleiner oder gleich `MaxValue` ist.

- Definieren Sie eine Methode für <xref:System.Windows.PropertyChangedCallback>den mit `OnValueChanged`dem Namen. `OnValueChanged`erstellt ein <xref:System.Windows.RoutedPropertyChangedEventArgs%601> -Objekt und bereitet darauf vor `ValueChanged` , das-Routing Ereignis zu erhöhen. Routingereignisse werden im nächsten Abschnitt erläutert.

[!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
[!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]

Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../advanced/custom-dependency-properties.md).

### <a name="use-routed-events"></a>Verwenden von Routingereignissen

Ebenso wie Abhängigkeits Eigenschaften das Konzept von CLR-Eigenschaften mit zusätzlicher Funktionalität erweitern, erweitern Routing Ereignisse das Konzept von CLR-Standard Ereignissen. Beim Erstellen eines neuen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelements empfiehlt es sich, Ihr Ereignis als ein Routingereignis zu implementieren, da Routingereignisse folgendes Verhalten unterstützen:

- Ereignisse für mehrere Steuerelemente können über ein übergeordnetes Steuerelement behandelt werden. Falls es sich bei dem Ereignis um ein Bubbling-Ereignis handelt, kann ein einzelnes übergeordnetes Element in der Elementstruktur das Ereignis abonnieren. Anschließend können Anwendungsentwickler mit einem Handler auf das Ereignis mehrerer Steuerelemente reagieren. Wenn das Steuerelement z. b. ein Teil der einzelnen Elemente in <xref:System.Windows.Controls.ListBox> einer ist (da es in einer <xref:System.Windows.DataTemplate>enthalten ist), kann der Anwendungsentwickler den Ereignishandler für das <xref:System.Windows.Controls.ListBox>-Ereignis des Steuer Elements im definieren. Beim Auftreten des Ereignisses bei einem der Steuerelemente wird der Ereignishandler aufgerufen.

- Routing Ereignisse können in einem <xref:System.Windows.EventSetter>verwendet werden, wodurch Anwendungsentwickler den Handler eines Ereignisses innerhalb eines Stils angeben können.

- Routing Ereignisse können in <xref:System.Windows.EventTrigger>verwendet werden, was zum Animieren von Eigenschaften mithilfe [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]von nützlich ist. Weitere Informationen finden Sie unter [Übersicht über Animation](../graphics-multimedia/animation-overview.md).

Im folgenden Beispiel wird ein Routingereignis wie folgt definiert:

- Definieren Sie <xref:System.Windows.RoutedEvent> einen Bezeichner mit `public` dem `ValueChangedEvent` `static` Namen`readonly` als Feld.

- Registrieren Sie das-Routing Ereignis, <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType> indem Sie die-Methode aufrufen. Das Beispiel gibt die folgenden Informationen an, wenn <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>aufgerufen wird:

  - Der Name des Ereignisses lautet `ValueChanged`.

  - Die Routing Strategie ist <xref:System.Windows.RoutingStrategy.Bubble>. Dies bedeutet, dass ein Ereignishandler für die Quelle (das Objekt, das das Ereignis auslöst) zuerst aufgerufen wird. Anschließend werden die Ereignishandler für die übergeordneten Elemente der Quelle nacheinander aufgerufen, beginnend mit dem Ereignishandler am nächstgelegenen übergeordnetes Element.

  - Der Typ des Ereignis Handlers ist <xref:System.Windows.RoutedPropertyChangedEventHandler%601>, erstellt mit einem <xref:System.Decimal> -Typ.

  - `NumericUpDown` ist der besitzende Typ des Ereignisses.

- Ein öffentliches Ereignis mit dem Namen `ValueChanged`, das die Zugriffsmethoden-Deklarationen umfasst, wird deklariert. Im Beispiel wird <xref:System.Windows.UIElement.AddHandler%2A> in der `add` Accessordeklaration <xref:System.Windows.UIElement.RemoveHandler%2A> und in `remove` der Accessordeklaration aufgerufen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , um die Ereignis Dienste zu verwenden.

- Eine geschützte virtuelle Methode mit dem Namen `OnValueChanged`, die das`ValueChanged`-Ereignis auslöst, wird erstellt.

[!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
[!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]

Weitere Informationen finden Sie unter [ Übersicht über Routingereignisse ](../advanced/routed-events-overview.md) und [Vorgehensweise: Erstellen eines benutzerdefinierten Routingereignisses](../advanced/how-to-create-a-custom-routed-event.md).

### <a name="use-binding"></a>Verwendung von Bindungen

Erwägen Sie Datenbindungen, um die Benutzeroberfläche Ihres Steuerelements von der Logik zu entkoppeln. Dies ist besonders wichtig, wenn Sie die Darstellung des Steuer Elements mithilfe eines <xref:System.Windows.Controls.ControlTemplate>definieren. Bei der Verwendung einer Datenbindung können Sie u.U. auf die Verweise auf bestimmte Teile der Benutzeroberfläche aus dem Code verzichten. Es empfiehlt sich, <xref:System.Windows.Controls.ControlTemplate> Verweise auf Elemente in zu vermeiden, denn wenn der Code auf Elemente verweist, die sich in der <xref:System.Windows.Controls.ControlTemplate> befinden und die <xref:System.Windows.Controls.ControlTemplate> geändert wird, muss das Element, auf das verwiesen wird, in <xref:System.Windows.Controls.ControlTemplate>das neue eingeschlossen werden.

Im folgenden Beispiel wird die <xref:System.Windows.Controls.TextBlock> `NumericUpDown` des-Steuer Elements aktualisiert, und es wird ein Name zugewiesen, und im Code wird anhand des Namens auf das Textfeld verwiesen.

[!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]

[!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
[!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]

Im folgenden Beispiel wird eine Bindung für den selben Zweck verwendet.

[!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]

Weitere Informationen zu Datenbindungen finden Sie unter [Übersicht über Datenbindung](../data/data-binding-overview.md).

### <a name="design-for-designers"></a>Darstellung für Designer

Um Support für benutzerdefinierte WPF-Steuerelemente in [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] zu erhalten (z.B. bezüglich der Eigenschaftenbearbeitung mit dem Eigenschaftenfenster), befolgen Sie die folgenden Richtlinien.  Weitere Informationen zum entwickeln für finden Sie [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]unter [Entwerfen von XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).

#### <a name="dependency-properties"></a>Abhängigkeitseigenschaften

Stellen Sie sicher, dass `get` CLR `set` und Accessoren wie zuvor beschrieben in "Abhängigkeits Eigenschaften verwenden" implementiert werden. Designer können Wrapper zur Prüfung des Vorhandenseins einer Abhängigkeitseigenschaft verwenden. Diese müssen, genauso wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und Clients des Steuerelements, beim Abrufen oder Festlegen der Eigenschaft jedoch keine Zugriffsmethoden aufrufen.

#### <a name="attached-properties"></a>Angefügte Eigenschaften

Angefügte Eigenschaften für benutzerdefinierte Steuerelemente sind unter Einhaltung der folgenden Richtlinien zu implementieren:

- Verwenden Sie `public` eine `static` `readonly` <xref:System.Windows.DependencyProperty.RegisterAttached%2A>derForm PropertyName,`Property` die mithilfe der-Methode erstellt wurde.  <xref:System.Windows.DependencyProperty> Der an übergebenen Eigenschaften Name muss <xref:System.Windows.DependencyProperty.RegisterAttached%2A> mit *propertyName*identisch sein.

- Implementieren Sie die `public` `static` CLR-Methoden mit den Namen `Set` *PropertyName* und `Get` *PropertyName*. Beide Methoden sollten eine von <xref:System.Windows.DependencyProperty> abgeleitete Klasse als das erste Argument akzeptieren. Die `Set`*PropertyName*-Methode akzeptiert auch ein Argument, dessen Typ mit dem registrierten Datentyp der Eigenschaft übereinstimmt. Die `Get`*PropertyName*-Methode sollte einen Wert zurückgeben, der den gleichen Typ aufweist. Falls die `Set`*PropertyName*-Methode fehlt, wird die Eigenschaft als schreibgeschützt gekennzeichnet.

- `Set`*PropertyName* und `Get` *propertyName* müssen direkt an die <xref:System.Windows.DependencyObject.GetValue%2A> -Methode und die- <xref:System.Windows.DependencyObject.SetValue%2A> Methode für das Ziel Abhängigkeits Objekt weiterleiten. Designer können auf die angefügte Eigenschaft entweder über einen Aufruf des Wrappers für die Methode zugreifen, oder indem sie das Zielabhängigkeitsobjekt direkt aufrufen.

Weitere Informationen zu angefügten Eigenschaften finden Sie in der [Übersicht über angefügte Eigenschaften](../advanced/attached-properties-overview.md).

### <a name="define-and-use-shared-resources"></a>Definieren und Verwenden von freigegebenen Ressourcen

Sie können Ihr Steuerelement entweder in die Assembly Ihrer Anwendung, oder in eine separate Assembly einbinden, die in mehreren Anwendungen verwendet werden kann. Der Großteil der in diesem Thema erläuterten Informationen gilt unabhängig von der von Ihnen verwendeten Methode.  Ein wesentlicher Unterschied ist dennoch zu beachten.  Falls Sie ein Steuerelement in die Assembly einer Anwendung einbinden, können Sie der App.xaml-Datei globale Ressourcen hinzufügen. Einer Assembly, die nur Steuerelemente enthält, ist jedoch <xref:System.Windows.Application> kein Objekt zugeordnet, sodass keine app. XAML-Datei verfügbar ist.

Wenn eine Anwendung nach einer Ressource sucht,wird auf drei Ebenen in der folgenden Reihenfolge gesucht:

1. Die Elementebene.

   Das System beginnt mit dem Element, das auf die Ressource verweist, und sucht anschließend die Ressourcen des logischen übergeordneten Elements durch. Dieser Schritt wir wiederholt, bis das Stammelement erreicht ist.

2. Die Anwendungsebene.

   Ressourcen, die durch <xref:System.Windows.Application> das-Objekt definiert werden.

3. Die Designebene.

   Ressourcenverzeichnisse werden auf der Designebene in einem Themes-Unterordner gespeichert.  Die Dateien im Themes-Ordner entsprechen den Designs.  Dort könnten Sie beispielsweise Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml, etc. finden.  Möglicherweise ist auch eine Datei mit dem Namen generic.xaml enthalten.  Bei einer Suche nach einer Ressource auf der Designebene wird zunächst in der designspezifischen Datei und dann in der Datei generic.xaml gesucht.

Falls Ihr Steuerelement in einer anderen Assembly als die Anwendung liegt, müssen Sie Ihre globale Ressourcen auf die Elementen- oder Designebene umspeichern. Beide Methoden haben ihre Vorteile.

#### <a name="defining-resources-at-the-element-level"></a>Definieren von Ressourcen auf der Elementebene

Sie können freigegebene Ressourcen auf der Elementebene definieren, indem Sie ein benutzerdefiniertes Ressourcenverzeichnis erstellen und es mit dem Ressourcenverzeichnis Ihres Steuerelements zusammenführen.  Falls Sie sich für diese Methode entscheiden, können Sie die Ressourcendatei beliebig benennen und sie im Ordner speichern, wo Ihre Steuerelemente liegen. Für Ressourcen auf der Elementebene können ebenso einfache Zeichenfolgen als Schlüssel verwendet werden. Im folgenden Beispiel wird eine <xref:System.Windows.Media.LinearGradientBrush> Ressourcen Datei mit dem Namen Dictionary1. XAML erstellt.

[!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]

Nachdem Sie das Ressourcenverzeichnis definiert haben, müssen Sie es mit dem Ressourcenverzeichnis des Steuerelements zusammenführen.  Hierzu können Sie [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder Code verwenden.

Im folgenden Beispiel wird ein Ressourcenverzeichnis mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zusammengeführt.

[!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]

Der Nachteil dieses Ansatzes besteht darin, dass <xref:System.Windows.ResourceDictionary> jedes Mal, wenn Sie darauf verweisen, ein-Objekt erstellt wird.  Wenn Sie z. b. über 10 benutzerdefinierte Steuerelemente in der Bibliothek verfügen und die freigegebenen Ressourcen Wörterbücher für jedes Steuerelement mithilfe von XAML zusammenführen, erstellen Sie 10 identische <xref:System.Windows.ResourceDictionary> Objekte.  Dies können Sie vermeiden, indem Sie eine statische Klasse erstellen, die die Ressourcen im Code zusammenfasst <xref:System.Windows.ResourceDictionary>und die resultierende zurückgibt.

Im folgenden Beispiel wird eine-Klasse erstellt, die <xref:System.Windows.ResourceDictionary>eine freigegebene zurückgibt.

[!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]

Im folgenden Beispiel wird die freigegebene Ressource mit den Ressourcen eines benutzerdefinierten Steuerelements im Konstruktor des Steuerelements zusammengeführt, bevor sie `InitializeComponent` aufruft.  Da eine statische Eigenschaft <xref:System.Windows.ResourceDictionary> ist,wirdnureinmalerstellt.`SharedDictionaryManager.SharedDictionary` Da das Ressourcenverzeichnis vor dem Aufruf von `InitializeComponent` zusammengeführt worden ist, kann das Steuerelement auf die Ressourcen in seiner [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Datei zugreifen.

[!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]

#### <a name="defining-resources-at-the-theme-level"></a>Definieren von Ressourcen auf der Designebene

Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie Ressourcen für verschiedene Windows-Designs erstellen.  Als Autor des Steuerelements können Sie eine Ressource für ein bestimmtes Design definieren, um die Darstellung Ihres Steuerelements an das jeweils verwendete Design anzupassen. Beispielsweise unter <xref:System.Windows.Controls.Button> scheidet sich die Darstellung eines im klassischen Windows-Design (das Standarddesign für Windows 2000) von einem <xref:System.Windows.Controls.Button> im Windows-Luna-Design (Standarddesign für <xref:System.Windows.Controls.Button> Windows XP), da ein anderes <xref:System.Windows.Controls.ControlTemplate> für jedes Design.

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

Wenn Sie <xref:System.Windows.Controls.ControlTemplate> in einer der Design spezifischen Ressourcenverzeichnis Dateien platzieren, müssen Sie für das Steuerelement einen statischen Konstruktor erstellen und die <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> -Methode für den <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>aufzurufen, wie im folgenden Beispiel gezeigt.

[!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
[!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]

##### <a name="defining-and-referencing-keys-for-theme-resources"></a>Definieren und Angeben von Schlüsseln für Designressourcen

Wenn Sie eine Ressource auf der Elementebene definieren, können Sie ihr als Schlüssel eine Zeichenfolge zuweisen und über diese Zeichenfolge auf sie zugreifen. Wenn Sie eine Ressource auf der Design Ebene definieren, müssen Sie einen <xref:System.Windows.ComponentResourceKey> als Schlüssel verwenden.  Im folgenden Beispiel wird eine Ressource in generic.xaml definiert.

[!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]

Im folgenden Beispiel wird auf die Ressource verwiesen, <xref:System.Windows.ComponentResourceKey> indem als Schlüssel angegeben wird.

[!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]

##### <a name="specifying-the-location-of-theme-resources"></a>Angeben des Speicherorts von Designressourcen

Um die Ressourcen für ein Steuerelement zu finden, muss die Hostinganwendung über die Information verfügen, dass die Assembly Ressourcen enthält, die steuerelementenspezifisch sind. Dies erreichen Sie, indem Sie der <xref:System.Windows.ThemeInfoAttribute> Assembly, die das Steuerelement enthält, hinzufügen. Der <xref:System.Windows.ThemeInfoAttribute> verfügt über <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> eine-Eigenschaft, die den Speicherort der generischen <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> Ressourcen angibt, und eine-Eigenschaft, die den Speicherort der Design spezifischen Ressourcen angibt.

Im folgenden Beispiel werden die <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> - <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> Eigenschaft und <xref:System.Windows.ResourceDictionaryLocation.SourceAssembly>die-Eigenschaft auf festgelegt, um anzugeben, dass sich die generischen und Design spezifischen Ressourcen in derselben Assembly wie das-Steuerelement befinden.

[!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
[!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]

## <a name="see-also"></a>Siehe auch

- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Paket-URI in WPF](../app-development/pack-uris-in-wpf.md)
- [Anpassung von Steuerelementen](control-customization.md)
