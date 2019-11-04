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
ms.openlocfilehash: fe7704b9366bf46f0c9965f78ce441000ead6334
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460782"
---
# <a name="control-authoring-overview"></a>Übersicht über das Erstellen von Steuerelementen

Dank der Erweiterbarkeit des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Steuerelementmodells ist das Erstellen neuer Steuerelemente nur selten erforderlich. In bestimmten Fällen lässt sich das Erstellen benutzerdefinierter Steuerelemente dennoch nicht vermeiden. In diesem Thema werden die Funktionen, dank deren Sie auf das Erstellen neuer Steuerelementen in den meisten Fällen verzichten können, sowie verschiedene Modelle zum Erstellen von Steuerelementen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] behandelt. Außerdem wird in diesem Thema auch das Erstellen eines neuen Steuerelements veranschaulicht.

<a name="when_to_write_a_new_control"></a>

## <a name="alternatives-to-writing-a-new-control"></a>Alternativen zum Erstellen eines neuen Steuerelements

In der Vergangenheit waren Sie bei der Anpassung eines vorhandenen Steuerelements auf die Bearbeitung seiner Standardeigenschaften beschränkt. Sie konnten z.B. die Hintergrundfarbe, die Rahmenbreite sowie die Schriftgröße ändern. Falls Sie die Darstellung oder das Verhalten eines Steuerelements über diese vordefinierten Parameter hinaus erweitern wollten, waren Sie auf das Erstellen eines neuen Steuerelements angewiesen. Die übliche Vorgehensweise war die Vererbung von einem vorhandenen Steuerelement samt der Überschreibung der für das Zeichnen des Steuerelements zuständigen Methode.  Diese Option steht Ihnen zwar weiterhin zur Verfügung, mit dem reichen Inhaltsmodel von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sowie seinen Stilen, Vorlagen und Triggern können Sie jedoch die vorhandenen Steuerelemente auf eine vielfältige Art und Weise anzupassen. In der folgenden Liste finden Sie Beispiele für die Verwendung dieser Funktionen zum Erstellen einer benutzerdefinierten und konsistenten Umgebung, ohne ein neues Steuerelement erstellen zu müssen.

- **Multimediainhalte.** Viele [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Standardsteuerelemente unterstützen Multimediainhalte. Beispielsweise ist die Content-Eigenschaft eines <xref:System.Windows.Controls.Button> vom Typ <xref:System.Object>, sodass in einem <xref:System.Windows.Controls.Button>theoretisch alles angezeigt werden kann.  Wenn eine Schaltfläche ein Bild und Text anzeigen soll, können Sie einem <xref:System.Windows.Controls.StackPanel> ein Bild und eine <xref:System.Windows.Controls.TextBlock> hinzufügen und die <xref:System.Windows.Controls.StackPanel> der <xref:System.Windows.Controls.ContentControl.Content%2A>-Eigenschaft zuweisen. Da die Steuerelemente visuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Elemente sowie beliebige Daten anzeigen können, ist es zwecks der Unterstützung einer komplexen Visualisierung selten notwendig, neue Steuerelemente zu erstellen oder vorhandene Steuerelemente zu ändern. Weitere Informationen zum Inhalts Modell für <xref:System.Windows.Controls.Button> und andere Inhalts Modelle in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]finden Sie unter [WPF-Inhalts Modell](wpf-content-model.md).

- **Stile.** Ein <xref:System.Windows.Style> ist eine Auflistung von Werten, die Eigenschaften für ein Steuerelement darstellen. Mit Stilen können Sie eine wiederverwendbare Darstellung der erwünschten Gestaltung und des erwünschten Verhaltens der Steuerelemente erstellen, ohne ein neues Steuerelement erstellen zu müssen. Angenommen, Sie möchten, dass alle <xref:System.Windows.Controls.TextBlock> Steuerelemente eine rote, Arial Schriftart mit einem Schrift Grad von 14 haben. Sie können einen Stil als eine Ressource anlegen und die jeweiligen Eigenschaften entsprechend festlegen. Anschließend wird jede <xref:System.Windows.Controls.TextBlock>, die Sie der Anwendung hinzufügen, dieselbe Darstellung aufweisen.

- **Datenvorlagen.** Mit einem <xref:System.Windows.DataTemplate> können Sie anpassen, wie Daten in einem Steuerelement angezeigt werden. Beispielsweise kann ein <xref:System.Windows.DataTemplate> verwendet werden, um anzugeben, wie Daten in einem <xref:System.Windows.Controls.ListBox>angezeigt werden.  Weitere Beispiele finden Sie unter [Übersicht über Datenvorlagen](../data/data-templating-overview.md).  Zusätzlich zur Anpassung der Darstellung von Daten kann eine <xref:System.Windows.DataTemplate> Benutzeroberflächen Elemente enthalten, die Ihnen ein hohes Maß an Flexibilität in benutzerdefinierten Benutzeroberflächen bietet.  Beispielsweise können Sie mithilfe einer <xref:System.Windows.DataTemplate>eine <xref:System.Windows.Controls.ComboBox> erstellen, in der jedes Element ein Kontrollkästchen enthält.

- **Steuerelementvorlagen.** Viele Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine <xref:System.Windows.Controls.ControlTemplate> verwenden, um die Struktur und die Darstellung des Steuer Elements zu definieren, die die Darstellung eines-Steuer Elements von der Funktionalität des-Steuer Elements trennt. Sie können die Darstellung eines Steuer Elements drastisch ändern, indem Sie dessen <xref:System.Windows.Controls.ControlTemplate>neu definieren.  Nehmen wir z.B. an, dass Sie ein Steuerelement wie eine Ampel aussehen lassen möchten. Dieses Steuerelement hat eine einfache Benutzeroberfläche und Funktionalität.  Das Steuerelement besteht aus drei Kreisen, von denen jeweils nur ein einziger leuchten kann. Nach einiger Reflektion können Sie feststellen, dass eine <xref:System.Windows.Controls.RadioButton> nur jeweils die Funktionalität der einzelnen Elemente bietet, aber die Standarddarstellung des <xref:System.Windows.Controls.RadioButton> sieht nicht so aus, wie die Beleuchtung in einem stoplight.  Da die <xref:System.Windows.Controls.RadioButton> eine Steuerelement Vorlage zum Definieren Ihrer Darstellung verwendet, ist es einfach, die <xref:System.Windows.Controls.ControlTemplate> so zu definieren, dass Sie den Anforderungen des Steuer Elements entspricht, und mithilfe von Options Feldern das stoplight zu machen.

  > [!NOTE]
  > Obwohl eine <xref:System.Windows.Controls.RadioButton> einen <xref:System.Windows.DataTemplate>verwenden kann, ist in diesem Beispiel ein <xref:System.Windows.DataTemplate> nicht ausreichend.  Der <xref:System.Windows.DataTemplate> der die Darstellung des Inhalts eines Steuer Elements definiert. Im Fall einer <xref:System.Windows.Controls.RadioButton>wird der Inhalt auf der rechten Seite des Kreises angezeigt, der angibt, ob die <xref:System.Windows.Controls.RadioButton> ausgewählt ist.  Im Beispiel mit der Ampel brauchen Sie lediglich das Optionsfeld als einen Kreis darzustellen, das „aufleuchten“ kann. Da sich die Darstellungs Anforderung für das Ampel von der Standarddarstellung der <xref:System.Windows.Controls.RadioButton>unterscheidet, ist es erforderlich, die <xref:System.Windows.Controls.ControlTemplate>neu zu definieren.  Im Allgemeinen wird eine <xref:System.Windows.DataTemplate> zum Definieren des Inhalts (oder der Daten) eines Steuer Elements verwendet, und ein <xref:System.Windows.Controls.ControlTemplate> wird verwendet, um zu definieren, wie ein Steuerelement strukturiert ist.

- **Trigger.** Mit einem <xref:System.Windows.Trigger> können Sie die Darstellung und das Verhalten eines Steuer Elements dynamisch ändern, ohne ein neues Steuerelement erstellen zu müssen. Angenommen, Sie verfügen über mehrere <xref:System.Windows.Controls.ListBox>-Steuerelemente in Ihrer Anwendung und möchten, dass die Elemente in den einzelnen <xref:System.Windows.Controls.ListBox> Fett und rot sind, wenn Sie ausgewählt werden. Der erste Instinkt besteht darin, eine Klasse zu erstellen, die von <xref:System.Windows.Controls.ListBox> erbt, und die <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A>-Methode außer Kraft zu setzen, um die Darstellung des ausgewählten Elements zu ändern. ein besserer Ansatz ist jedoch das Hinzufügen eines Auslösers zu einem Stil eines <xref:System.Windows.Controls.ListBoxItem>, der das Aussehen des ausgewählten Elements ändert. . Mit Triggern können Sie Eigenschaftswerte bearbeiten oder basierend auf den Eigenschaftswerten Aktionen ausführen. Mit einem <xref:System.Windows.EventTrigger> können Sie bei Auftreten eines Ereignisses Aktionen ausführen.

Weitere Informationen zu Stilen, Vorlagen und Triggern finden Sie unter [Erstellen von Formaten und Vorlagen](styling-and-templating.md).

Im Allgemeinen gilt: wenn das benötigte Steuerelement die Funktionalität eines vorhandenen Steuerelements nachmacht, aber anders aussehen soll, lohnt es sich zuerst zu überlegen, ob Sie mit einem der in diesem Abschnitt beschriebenen Verfahren die vorhandene Darstellung des Steuerelements ändern können.

<a name="models_for_control_authoring"></a>

## <a name="models-for-control-authoring"></a>Modelle für das Erstellen von Steuerelementen

Dank dem umfangreichen Inhaltsmodell sowie Stilen, Vorlagen und Triggern können Sie in den meisten Fällen auf das Erstellen neuer Steuerelemente verzichten. Falls Sie jedoch ein neues Steuerelement erstellen müssen, ist es wichtig Modelle für das Erstellen von Steuerelementen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu verstehen. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet drei allgemeine Modelle zum Erstellen der Steuerelemente, die jeweils verschiedene Funktionen und Flexibilitätsgrade bieten. Die Basisklassen für die drei Modelle sind <xref:System.Windows.Controls.UserControl>, <xref:System.Windows.Controls.Control>und <xref:System.Windows.FrameworkElement>.

### <a name="deriving-from-usercontrol"></a>Ableiten von UserControl

Die einfachste Möglichkeit zum Erstellen eines Steuer Elements in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist die Ableitung von <xref:System.Windows.Controls.UserControl>. Wenn Sie ein Steuerelement erstellen, das von <xref:System.Windows.Controls.UserControl>erbt, fügen Sie dem <xref:System.Windows.Controls.UserControl>vorhandene Komponenten hinzu, benennen Sie die Komponenten, und verweisen Sie in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]auf Ereignishandler. Anschließend können Sie auf die benannten Elemente verweisen und die Ereignishandler im Code definieren. Dieses Entwicklungsmodell ähnelt sehr dem Modell für die Anwendungsentwicklung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Wenn eine <xref:System.Windows.Controls.UserControl> ordnungsgemäß erstellt wurde, können Sie die Vorteile von umfangreichen Inhalten, Stilen und Triggern nutzen. Wenn Ihr Steuerelement jedoch von <xref:System.Windows.Controls.UserControl>erbt, können Personen, die Ihr Steuerelement verwenden, keine <xref:System.Windows.DataTemplate> oder <xref:System.Windows.Controls.ControlTemplate> verwenden, um die Darstellung anzupassen.  Zum Erstellen eines benutzerdefinierten Steuer Elements, das Vorlagen unterstützt, muss eine Ableitung von der <xref:System.Windows.Controls.Control>-Klasse oder einer ihrer abgeleiteten Klassen (außer <xref:System.Windows.Controls.UserControl>) durchzuführen sein.

#### <a name="benefits-of-deriving-from-usercontrol"></a>Vorteile des Ableitens von UserControl

Nehmen Sie die Ableitung von <xref:System.Windows.Controls.UserControl> in Erwägung, wenn Folgendes zutrifft:

- Sie möchten das Steuerelement auf eine ähnliche Art und Weise erstellen, wie Sie Ihre Anwendung erstellt haben.

- Ihr Steuerelement besteht ausschließlich aus vorhandenen Komponenten.

- Es muss keine komplexe Anpassung unterstützt werden.

### <a name="deriving-from-control"></a>Ableiten von Control

Die Ableitung von der <xref:System.Windows.Controls.Control> Klasse ist das Modell, das von den meisten vorhandenen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelementen verwendet wird. Wenn Sie ein Steuerelement erstellen, das von der <xref:System.Windows.Controls.Control>-Klasse erbt, definieren Sie seine Darstellung mithilfe von Vorlagen. Dadurch trennen Sie die Funktionslogik von der visuellen Darstellung. Sie können auch sicherstellen, dass die Benutzeroberfläche und die Logik entkoppelt werden, indem Sie anstelle von Ereignissen Befehle und Bindungen verwenden und Verweise auf Elemente in der <xref:System.Windows.Controls.ControlTemplate> vermeiden, wenn dies möglich ist.  Wenn die Benutzeroberfläche und die Logik des Steuer Elements ordnungsgemäß entkoppelt sind, kann ein Benutzer des Steuer Elements die <xref:System.Windows.Controls.ControlTemplate> des Steuer Elements neu definieren, um seine Darstellung anzupassen. Obwohl das Entwickeln eines benutzerdefinierten <xref:System.Windows.Controls.Control> nicht so einfach ist wie das Entwickeln eines <xref:System.Windows.Controls.UserControl>, bietet ein benutzerdefiniertes <xref:System.Windows.Controls.Control> die größte Flexibilität.

#### <a name="benefits-of-deriving-from-control"></a>Vorteile des Ableitens von Control

Wenn eine der folgenden Bedingungen zutrifft, sollten Sie ggf. von <xref:System.Windows.Controls.Control> ableiten, anstatt die <xref:System.Windows.Controls.UserControl>-Klasse zu verwenden:

- Sie möchten, dass die Darstellung des Steuer Elements über die <xref:System.Windows.Controls.ControlTemplate>anpassbar ist.

- Das Steuerelement soll verschiedene Designs unterstützen.

### <a name="deriving-from-frameworkelement"></a>Ableitung von FrameworkElement

Steuerelemente, die von <xref:System.Windows.Controls.UserControl> oder <xref:System.Windows.Controls.Control> abgeleitet werden, basieren auf dem Verfassen vorhandener Elemente. In vielen Szenarios ist dies eine akzeptable Lösung, da jedes Objekt, das von <xref:System.Windows.FrameworkElement> erbt, sich in einem <xref:System.Windows.Controls.ControlTemplate>befinden kann. Es gibt jedoch Situationen, in denen die Darstellung eines Steuerelements mehr als die Funktionalität einer einfachen Elementzusammensetzung erfordert. In diesen Szenarien ist die Basis einer Komponente auf <xref:System.Windows.FrameworkElement> die richtige Wahl.

Es gibt zwei Standardmethoden zum Entwickeln von <xref:System.Windows.FrameworkElement>basierten Komponenten: direktes Rendering und benutzerdefinierte Element Komposition. Das direkte Rendering umfasst das Überschreiben der <xref:System.Windows.UIElement.OnRender%2A> Methode <xref:System.Windows.FrameworkElement> und das Bereitstellen von <xref:System.Windows.Media.DrawingContext> Vorgängen, die die visuellen Komponenten explizit definieren. Dies ist die Methode, die von <xref:System.Windows.Controls.Image> und <xref:System.Windows.Controls.Border>verwendet wird. Die benutzerdefinierte Element Komposition umfasst die Verwendung von Objekten vom Typ <xref:System.Windows.Media.Visual>, um die Darstellung der Komponente zu erstellen. Beispiele finden Sie unter [Verwenden von DrawingVisual-Objekten](../graphics-multimedia/using-drawingvisual-objects.md). <xref:System.Windows.Controls.Primitives.Track> ist ein Beispiel für ein Steuerelement in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], das die benutzerdefinierte Element Komposition verwendet. Sie können auch direktes Rendering und benutzerdefinierte Elementzusammensetzung innerhalb eines Steuerelements kombinieren.

#### <a name="benefits-of-deriving-from-frameworkelement"></a>Vorteile der Ableitung von FrameworkElement

Wenn eine der folgenden Bedingungen zutrifft, empfiehlt es sich, von <xref:System.Windows.FrameworkElement> abzuleiten:

- Sie brauchen eine genaue Steuerung der Darstellung Ihres Steuerelements, die darüber hinausgeht, was mit einer einfachen Elementzusammensetzung möglich ist.

- Sie möchten die Darstellung Ihres Steuerelements definieren, indem Sie Ihre eigene Renderinglogik definieren.

- Sie möchten vorhandene Elemente auf neuartige Weise zusammenstellen, die über die Möglichkeiten hinausgehen, die mit <xref:System.Windows.Controls.UserControl> und <xref:System.Windows.Controls.Control>möglich sind.

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

- Definieren Sie einen <xref:System.Windows.DependencyProperty> Bezeichner mit dem Namen `ValueProperty` als `public` `static` `readonly` Feld.

- Registrieren Sie den Eigenschaftsnamen beim Eigenschaften System, indem Sie <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType>aufrufen, um Folgendes anzugeben:

  - Den Namen der Eigenschaft.

  - Den Typ der Eigenschaft.

  - Den Typ, der die Eigenschaft besitzt.

  - Die Metadaten für die Eigenschaft. Die Metadaten enthalten den Standardwert der Eigenschaft, eine <xref:System.Windows.CoerceValueCallback> und eine <xref:System.Windows.PropertyChangedCallback>.

- Definieren Sie eine CLR-Wrapper Eigenschaft mit dem Namen `Value`, bei der es sich um den Namen handelt, der zum Registrieren der Abhängigkeits Eigenschaft verwendet wird, indem Sie die `get`-und `set` Accessoren der Eigenschaft implementieren. Beachten Sie, dass die `get`-und `set` Accessoren nur <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> aufzurufen. Es wird empfohlen, dass die Accessoren von Abhängigkeits Eigenschaften keine zusätzliche Logik enthalten, da Clients und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Accessoren umgehen und <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> direkt anrufen können. Falls eine Eigenschaft z.B. an eine Datenquelle gebunden ist, wird die `set`-Zugriffmethode der Eigenschaft nicht aufgerufen.  Anstatt zusätzliche Logik zu den Get-und Set-Accessoren hinzuzufügen, verwenden Sie die <xref:System.Windows.ValidateValueCallback>-, <xref:System.Windows.CoerceValueCallback>-und <xref:System.Windows.PropertyChangedCallback> Delegaten, um auf den Wert zu reagieren oder zu überprüfen, wenn er sich ändert.  Weitere Informationen zu diesen Rückrufen finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](../advanced/dependency-property-callbacks-and-validation.md).

- Definieren Sie eine Methode für die <xref:System.Windows.CoerceValueCallback> mit dem Namen `CoerceValue`. `CoerceValue` stellt sicher, dass `Value` größer oder gleich `MinValue` und kleiner oder gleich `MaxValue` ist.

- Definieren Sie eine Methode für die <xref:System.Windows.PropertyChangedCallback>mit dem Namen `OnValueChanged`. `OnValueChanged` erstellt ein <xref:System.Windows.RoutedPropertyChangedEventArgs%601>-Objekt und bereitet die Erhöhung des `ValueChanged`-Routing Ereignisses vor. Routingereignisse werden im nächsten Abschnitt erläutert.

[!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
[!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]

Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../advanced/custom-dependency-properties.md).

### <a name="use-routed-events"></a>Verwenden von Routingereignissen

Ebenso wie Abhängigkeits Eigenschaften das Konzept von CLR-Eigenschaften mit zusätzlicher Funktionalität erweitern, erweitern Routing Ereignisse das Konzept von CLR-Standard Ereignissen. Beim Erstellen eines neuen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelements empfiehlt es sich, Ihr Ereignis als ein Routingereignis zu implementieren, da Routingereignisse folgendes Verhalten unterstützen:

- Ereignisse für mehrere Steuerelemente können über ein übergeordnetes Steuerelement behandelt werden. Falls es sich bei dem Ereignis um ein Bubbling-Ereignis handelt, kann ein einzelnes übergeordnetes Element in der Elementstruktur das Ereignis abonnieren. Anschließend können Anwendungsentwickler mit einem Handler auf das Ereignis mehrerer Steuerelemente reagieren. Wenn das Steuerelement z. b. ein Teil jedes Elements in einer <xref:System.Windows.Controls.ListBox> ist (da es in einem <xref:System.Windows.DataTemplate>enthalten ist), kann der Anwendungsentwickler den Ereignishandler für das-Ereignis des Steuer Elements auf dem <xref:System.Windows.Controls.ListBox>definieren. Beim Auftreten des Ereignisses bei einem der Steuerelemente wird der Ereignishandler aufgerufen.

- Routing Ereignisse können in einer <xref:System.Windows.EventSetter>verwendet werden, die es Anwendungsentwicklern ermöglicht, den Handler eines Ereignisses innerhalb eines Stils anzugeben.

- Routing Ereignisse können in einem <xref:System.Windows.EventTrigger>verwendet werden, das zum Animieren von Eigenschaften mithilfe von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]nützlich ist. Weitere Informationen finden Sie unter [Übersicht über Animation](../graphics-multimedia/animation-overview.md).

Im folgenden Beispiel wird ein Routingereignis wie folgt definiert:

- Definieren Sie einen <xref:System.Windows.RoutedEvent> Bezeichner mit dem Namen `ValueChangedEvent` als `public` `static` `readonly` Feld.

- Registrieren Sie das-Routing Ereignis, indem Sie die <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType>-Methode aufrufen. Das Beispiel gibt die folgenden Informationen an, wenn <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>aufgerufen wird:

  - Der Name des Ereignisses lautet `ValueChanged`.

  - Die Routing Strategie ist <xref:System.Windows.RoutingStrategy.Bubble>. Dies bedeutet, dass ein Ereignishandler für die Quelle (das Objekt, das das Ereignis auslöst) zuerst aufgerufen wird. Anschließend werden Ereignishandler für die übergeordneten Elemente der Quelle nacheinander aufgerufen, beginnend mit dem Ereignishandler am nächstgelegenen übergeordnetes Element.

  - Der Typ des Ereignis Handlers ist <xref:System.Windows.RoutedPropertyChangedEventHandler%601>, der mit einem <xref:System.Decimal>-Typ erstellt wird.

  - `NumericUpDown` ist der besitzende Typ des Ereignisses.

- Ein öffentliches Ereignis mit dem Namen `ValueChanged`, das die Zugriffsmethoden-Deklarationen umfasst, wird deklariert. Im Beispiel wird <xref:System.Windows.UIElement.AddHandler%2A> in der `add` Accessor-Deklaration aufgerufen und in der `remove` Accessor-Deklaration <xref:System.Windows.UIElement.RemoveHandler%2A>, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignis Dienste zu verwenden.

- Eine geschützte virtuelle Methode mit dem Namen `OnValueChanged`, die das`ValueChanged`-Ereignis auslöst, wird erstellt.

[!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
[!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]

Weitere Informationen finden Sie unter [ Übersicht über Routingereignisse ](../advanced/routed-events-overview.md) und [Vorgehensweise: Erstellen eines benutzerdefinierten Routingereignisses](../advanced/how-to-create-a-custom-routed-event.md).

### <a name="use-binding"></a>Verwendung von Bindungen

Erwägen Sie Datenbindungen, um die Benutzeroberfläche Ihres Steuerelements von der Logik zu entkoppeln. Dies ist besonders wichtig, wenn Sie die Darstellung des Steuer Elements mithilfe eines <xref:System.Windows.Controls.ControlTemplate>definieren. Bei der Verwendung einer Datenbindung können Sie u.U. auf die Verweise auf bestimmte Teile der Benutzeroberfläche aus dem Code verzichten. Es empfiehlt sich, Verweise auf Elemente in der <xref:System.Windows.Controls.ControlTemplate> zu vermeiden, denn wenn der Code auf Elemente verweist, die sich im <xref:System.Windows.Controls.ControlTemplate> befinden und die <xref:System.Windows.Controls.ControlTemplate> geändert wird, muss das Element, auf das verwiesen wird, in den neuen <xref:System.Windows.Controls.ControlTemplate>eingeschlossen werden.

Im folgenden Beispiel wird die <xref:System.Windows.Controls.TextBlock> des `NumericUpDown` Steuer Elements aktualisiert, ein Name zugewiesen und im Code anhand des Namens auf das Textfeld verwiesen.

[!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]

[!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
[!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]

Im folgenden Beispiel wird eine Bindung für den selben Zweck verwendet.

[!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]

Weitere Informationen zu Datenbindungen finden Sie unter [Übersicht über Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).

### <a name="design-for-designers"></a>Darstellung für Designer

Um Support für benutzerdefinierte WPF-Steuerelemente in [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] zu erhalten (z.B. bezüglich der Eigenschaftenbearbeitung mit dem Eigenschaftenfenster), befolgen Sie die folgenden Richtlinien.  Weitere Informationen zum entwickeln für die [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]finden Sie unter [Entwerfen von XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).

#### <a name="dependency-properties"></a>Abhängigkeitseigenschaften

Stellen Sie sicher, dass Sie CLR-`get` und `set` Accessoren implementieren, wie zuvor in "Verwenden von Abhängigkeits Eigenschaften" beschrieben. Designer können Wrapper zur Prüfung des Vorhandenseins einer Abhängigkeitseigenschaft verwenden. Diese müssen, genauso wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und Clients des Steuerelements, beim Abrufen oder Festlegen der Eigenschaft jedoch keine Zugriffsmethoden aufrufen.

#### <a name="attached-properties"></a>Angefügte Eigenschaften

Angefügte Eigenschaften für benutzerdefinierte Steuerelemente sind unter Einhaltung der folgenden Richtlinien zu implementieren:

- Sie haben eine `public` `static` `readonly` <xref:System.Windows.DependencyProperty> der Form *propertyName*`Property`, die mithilfe der <xref:System.Windows.DependencyProperty.RegisterAttached%2A>-Methode erstellt wurde. Der an <xref:System.Windows.DependencyProperty.RegisterAttached%2A> übergebenen Eigenschaftsname muss mit *propertyName*identisch sein.

- Implementieren Sie die `public` `static` CLR-Methoden mit den Namen `Set` *PropertyName* und `Get` *PropertyName*. Beide Methoden sollten eine von <xref:System.Windows.DependencyProperty> abgeleitete Klasse als erstes Argument akzeptieren. Die `Set`*PropertyName*-Methode akzeptiert auch ein Argument, dessen Typ mit dem registrierten Datentyp der Eigenschaft übereinstimmt. Die `Get`*PropertyName*-Methode sollte einen Wert zurückgeben, der den gleichen Typ aufweist. Falls die `Set`*PropertyName*-Methode fehlt, wird die Eigenschaft als schreibgeschützt gekennzeichnet.

- `Set` *propertyName* und `Get`*propertyName* müssen direkt an die <xref:System.Windows.DependencyObject.GetValue%2A>-Methode und die <xref:System.Windows.DependencyObject.SetValue%2A>-Methode für das Ziel Abhängigkeits Objekt weitergeleitet werden. Designer können auf die angefügte Eigenschaft entweder über einen Aufruf des Wrappers für die Methode zugreifen, oder indem sie das Zielabhängigkeitsobjekt direkt aufrufen.

Weitere Informationen zu angefügten Eigenschaften finden Sie in der [Übersicht über angefügte Eigenschaften](../advanced/attached-properties-overview.md).

### <a name="define-and-use-shared-resources"></a>Definieren und Verwenden von freigegebenen Ressourcen

Sie können Ihr Steuerelement entweder in die Assembly Ihrer Anwendung, oder in eine separate Assembly einbinden, die in mehreren Anwendungen verwendet werden kann. Der Großteil der in diesem Thema erläuterten Informationen gilt unabhängig von der von Ihnen verwendeten Methode.  Ein wesentlicher Unterschied ist dennoch zu beachten.  Falls Sie ein Steuerelement in die Assembly einer Anwendung einbinden, können Sie der App.xaml-Datei globale Ressourcen hinzufügen. Eine Assembly, die nur Steuerelemente enthält, verfügt jedoch nicht über ein <xref:System.Windows.Application> Objekt, sodass eine APP. XAML-Datei nicht verfügbar ist.

Wenn eine Anwendung nach einer Ressource sucht,wird auf drei Ebenen in der folgenden Reihenfolge gesucht:

1. Die Elementebene.

   Das System beginnt mit dem Element, das auf die Ressource verweist, und sucht anschließend die Ressourcen des logischen übergeordneten Elements durch. Dieser Schritt wir wiederholt, bis das Stammelement erreicht ist.

2. Die Anwendungsebene.

   Vom <xref:System.Windows.Application> Objekt definierte Ressourcen.

3. Die Designebene.

   Ressourcenverzeichnisse werden auf der Designebene in einem Themes-Unterordner gespeichert.  Die Dateien im Themes-Ordner entsprechen den Designs.  Dort könnten Sie beispielsweise Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml, etc. finden.  Möglicherweise ist auch eine Datei mit dem Namen generic.xaml enthalten.  Bei einer Suche nach einer Ressource auf der Designebene wird zunächst in der designspezifischen Datei und dann in der Datei generic.xaml gesucht.

Falls Ihr Steuerelement in einer anderen Assembly als die Anwendung liegt, müssen Sie Ihre globale Ressourcen auf die Elementen- oder Designebene umspeichern. Beide Methoden haben ihre Vorteile.

#### <a name="defining-resources-at-the-element-level"></a>Definieren von Ressourcen auf der Elementebene

Sie können freigegebene Ressourcen auf der Elementebene definieren, indem Sie ein benutzerdefiniertes Ressourcenverzeichnis erstellen und es mit dem Ressourcenverzeichnis Ihres Steuerelements zusammenführen.  Falls Sie sich für diese Methode entscheiden, können Sie die Ressourcendatei beliebig benennen und sie im Ordner speichern, wo Ihre Steuerelemente liegen. Für Ressourcen auf der Elementebene können ebenso einfache Zeichenfolgen als Schlüssel verwendet werden. Im folgenden Beispiel wird eine <xref:System.Windows.Media.LinearGradientBrush> Ressourcen Datei mit dem Namen Dictionary1. XAML erstellt.

[!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]

Nachdem Sie das Ressourcenverzeichnis definiert haben, müssen Sie es mit dem Ressourcenverzeichnis des Steuerelements zusammenführen.  Hierzu können Sie [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder Code verwenden.

Im folgenden Beispiel wird ein Ressourcenverzeichnis mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zusammengeführt.

[!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]

Der Nachteil dieses Ansatzes besteht darin, dass jedes Mal, wenn Sie darauf verweisen, ein <xref:System.Windows.ResourceDictionary> Objekt erstellt wird.  Wenn Sie z. b. über 10 benutzerdefinierte Steuerelemente in der Bibliothek verfügen und die freigegebenen Ressourcen Wörterbücher für jedes Steuerelement mithilfe von XAML zusammenführen, erstellen Sie 10 identische <xref:System.Windows.ResourceDictionary> Objekte.  Dies können Sie vermeiden, indem Sie eine statische Klasse erstellen, die die Ressourcen im Code zusammenführt und die resultierenden <xref:System.Windows.ResourceDictionary>zurückgibt.

Im folgenden Beispiel wird eine-Klasse erstellt, die eine freigegebene <xref:System.Windows.ResourceDictionary>zurückgibt.

[!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]

Im folgenden Beispiel wird die freigegebene Ressource mit den Ressourcen eines benutzerdefinierten Steuerelements im Konstruktor des Steuerelements zusammengeführt, bevor sie `InitializeComponent` aufruft.  Da der `SharedDictionaryManager.SharedDictionary` eine statische Eigenschaft ist, wird die <xref:System.Windows.ResourceDictionary> nur einmal erstellt. Da das Ressourcenverzeichnis vor dem Aufruf von `InitializeComponent` zusammengeführt worden ist, kann das Steuerelement auf die Ressourcen in seiner [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Datei zugreifen.

[!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]

#### <a name="defining-resources-at-the-theme-level"></a>Definieren von Ressourcen auf der Designebene

Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie Ressourcen für verschiedene Windows-Designs erstellen.  Als Autor des Steuerelements können Sie eine Ressource für ein bestimmtes Design definieren, um die Darstellung Ihres Steuerelements an das jeweils verwendete Design anzupassen. Beispielsweise unterscheidet sich die Darstellung eines <xref:System.Windows.Controls.Button> im klassischen Windows-Design (das Standarddesign für Windows 2000) von einem <xref:System.Windows.Controls.Button> im Windows-Luna-Design (Standarddesign für Windows XP), da der <xref:System.Windows.Controls.Button> für jedes Design eine andere <xref:System.Windows.Controls.ControlTemplate> verwendet.

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

Das [C#](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) benutzerdefinierte Steuerelement oder [Visual Basic](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) NumericUpDown-Steuerelement mit Design-und Benutzeroberflächenautomatisierungs-Unterstützung enthält zwei Ressourcen Wörterbücher für das `NumericUpDown`-Steuerelement: eines in Generic. XAML und das andere in Luna. NormalColor. XAML. 

Wenn Sie eine <xref:System.Windows.Controls.ControlTemplate> in eine der Design spezifischen Ressourcenverzeichnis Dateien einfügen, müssen Sie für das Steuerelement einen statischen Konstruktor erstellen und die <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29>-Methode auf dem <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>aufzurufen, wie im folgenden Beispiel gezeigt.

[!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
[!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]

##### <a name="defining-and-referencing-keys-for-theme-resources"></a>Definieren und Angeben von Schlüsseln für Designressourcen

Wenn Sie eine Ressource auf der Elementebene definieren, können Sie ihr als Schlüssel eine Zeichenfolge zuweisen und über diese Zeichenfolge auf sie zugreifen. Wenn Sie eine Ressource auf der Design Ebene definieren, müssen Sie eine <xref:System.Windows.ComponentResourceKey> als Schlüssel verwenden.  Im folgenden Beispiel wird eine Ressource in generic.xaml definiert.

[!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]

Im folgenden Beispiel wird auf die Ressource verwiesen, indem der <xref:System.Windows.ComponentResourceKey> als Schlüssel angegeben wird.

[!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]

##### <a name="specifying-the-location-of-theme-resources"></a>Angeben des Speicherorts von Designressourcen

Um die Ressourcen für ein Steuerelement zu finden, muss die Hostinganwendung über die Information verfügen, dass die Assembly Ressourcen enthält, die steuerelementenspezifisch sind. Dies erreichen Sie, indem Sie die <xref:System.Windows.ThemeInfoAttribute> der Assembly hinzufügen, die das Steuerelement enthält. Der <xref:System.Windows.ThemeInfoAttribute> verfügt über eine <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A>-Eigenschaft, die den Speicherort generischer Ressourcen und eine <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> Eigenschaft angibt, die den Speicherort der Design spezifischen Ressourcen angibt.

Im folgenden Beispiel werden die Eigenschaften <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> und <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> auf <xref:System.Windows.ResourceDictionaryLocation.SourceAssembly>festgelegt, um anzugeben, dass sich die generischen und Design spezifischen Ressourcen in derselben Assembly wie das Steuerelement befinden.

[!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
[!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]

## <a name="see-also"></a>Siehe auch

- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Paket-URI in WPF](../app-development/pack-uris-in-wpf.md)
- [Anpassung von Steuerelementen](control-customization.md)
