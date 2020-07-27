---
title: Übersicht über das Erstellen von Steuerelementen
description: Die Erweiterbarkeit von Windows Presentation Foundation-Steuerelementen minimiert die Notwendigkeit, benutzerdefinierte Steuerelemente zu erstellen. Erfahren Sie, wie Sie ggf. ein neues Steuerelement erstellen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], authoring overview
- authoring overview for controls [WPF]
ms.assetid: 3d864748-cff0-4e63-9b23-d8e5a635b28f
ms.openlocfilehash: 600eb193613846d7eeeb626a6dfd317d2592f809
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166338"
---
# <a name="control-authoring-overview"></a>Übersicht über die Dokument Erstellung

Dank der Erweiterbarkeit des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Steuerelementmodells ist das Erstellen neuer Steuerelemente nur selten erforderlich. In bestimmten Fällen lässt sich das Erstellen benutzerdefinierter Steuerelemente dennoch nicht vermeiden. In diesem Thema werden die Funktionen, dank deren Sie auf das Erstellen neuer Steuerelementen in den meisten Fällen verzichten können, sowie verschiedene Modelle zum Erstellen von Steuerelementen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] behandelt. Außerdem wird in diesem Thema auch das Erstellen eines neuen Steuerelements veranschaulicht.

<a name="when_to_write_a_new_control"></a>

## <a name="alternatives-to-writing-a-new-control"></a>Alternativen zum Erstellen eines neuen Steuerelements

In der Vergangenheit waren Sie bei der Anpassung eines vorhandenen Steuerelements auf die Bearbeitung seiner Standardeigenschaften beschränkt. Sie konnten z.B. die Hintergrundfarbe, die Rahmenbreite sowie die Schriftgröße ändern. Falls Sie die Darstellung oder das Verhalten eines Steuerelements über diese vordefinierten Parameter hinaus erweitern wollten, waren Sie auf das Erstellen eines neuen Steuerelements angewiesen. Die übliche Vorgehensweise war die Vererbung von einem vorhandenen Steuerelement samt der Überschreibung der für das Zeichnen des Steuerelements zuständigen Methode.  Diese Option steht Ihnen zwar weiterhin zur Verfügung, mit dem reichen Inhaltsmodel von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sowie seinen Stilen, Vorlagen und Triggern können Sie jedoch die vorhandenen Steuerelemente auf eine vielfältige Art und Weise anzupassen. In der folgenden Liste finden Sie Beispiele für die Verwendung dieser Funktionen zum Erstellen einer benutzerdefinierten und konsistenten Umgebung, ohne ein neues Steuerelement erstellen zu müssen.

- **Multimediainhalte.** Viele [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Standardsteuerelemente unterstützen Multimediainhalte. Die Content-Eigenschaft eines ist beispielsweise <xref:System.Windows.Controls.Button> vom Typ <xref:System.Object> , sodass theoretisch alles auf einem angezeigt werden kann <xref:System.Windows.Controls.Button> .  Wenn eine Schaltfläche ein Bild und Text anzeigen soll, können Sie ein Bild und ein einem hinzufügen <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.StackPanel> und das der- <xref:System.Windows.Controls.StackPanel> Eigenschaft zuweisen <xref:System.Windows.Controls.ContentControl.Content%2A> . Da die Steuerelemente visuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Elemente sowie beliebige Daten anzeigen können, ist es zwecks der Unterstützung einer komplexen Visualisierung selten notwendig, neue Steuerelemente zu erstellen oder vorhandene Steuerelemente zu ändern. Weitere Informationen zum Inhalts Modell für <xref:System.Windows.Controls.Button> und andere Inhalts Modelle in finden Sie unter [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [WPF-Inhalts Modell](wpf-content-model.md).

- **Tanz.** Eine <xref:System.Windows.Style> ist eine Auflistung von Werten, die Eigenschaften für ein Steuerelement darstellen. Mit Stilen können Sie eine wiederverwendbare Darstellung der erwünschten Gestaltung und des erwünschten Verhaltens der Steuerelemente erstellen, ohne ein neues Steuerelement erstellen zu müssen. Angenommen, Sie möchten, dass alle Steuer <xref:System.Windows.Controls.TextBlock> Elemente eine rote, Arial Schriftart mit einem Schrift Grad von 14 haben. Sie können einen Stil als eine Ressource anlegen und die jeweiligen Eigenschaften entsprechend festlegen. Dann <xref:System.Windows.Controls.TextBlock> wird jedes, das Sie der Anwendung hinzufügen, dasselbe Aussehen.

- **Datenvorlagen.** <xref:System.Windows.DataTemplate>Mit einem können Sie anpassen, wie Daten auf einem-Steuerelement angezeigt werden. So kann z. b <xref:System.Windows.DataTemplate> . verwendet werden, um anzugeben, wie Daten in einem angezeigt werden <xref:System.Windows.Controls.ListBox> .  Weitere Beispiele finden Sie unter [Übersicht über Datenvorlagen](../data/data-templating-overview.md).  Zusätzlich zur Anpassung der Darstellung von Daten kann ein Benutzeroberflächen <xref:System.Windows.DataTemplate> Elemente enthalten, die Ihnen einen großen Flexibilität in benutzerdefinierten Benutzeroberflächen bieten.  Beispielsweise können Sie mit einem eine <xref:System.Windows.DataTemplate> erstellen, <xref:System.Windows.Controls.ComboBox> in der jedes Element ein Kontrollkästchen enthält.

- **Steuerelement Vorlagen.** Viele Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwenden ein <xref:System.Windows.Controls.ControlTemplate> , um die Struktur und die Darstellung des Steuer Elements zu definieren, die die Darstellung eines-Steuer Elements von der Funktionalität des-Steuer Elements trennt. Sie können die Darstellung eines Steuer Elements drastisch ändern, indem Sie dessen neu definieren <xref:System.Windows.Controls.ControlTemplate> .  Nehmen wir z.B. an, dass Sie ein Steuerelement wie eine Ampel aussehen lassen möchten. Dieses Steuerelement hat eine einfache Benutzeroberfläche und Funktionalität.  Das Steuerelement besteht aus drei Kreisen, von denen jeweils nur ein einziger leuchten kann. Nach einiger Reflektion können Sie feststellen, dass ein-Wert <xref:System.Windows.Controls.RadioButton> die Funktionalität von nur einem gleichzeitig ausgewählten bietet, aber die Standarddarstellung des <xref:System.Windows.Controls.RadioButton> sieht nicht so aus, wie die Lichter auf einem stoplight.  Da <xref:System.Windows.Controls.RadioButton> eine Steuerelement Vorlage verwendet, um die Darstellung zu definieren, ist es einfach, das-Element so zu definieren, dass es <xref:System.Windows.Controls.ControlTemplate> den Anforderungen des-Steuer Elements entspricht, und mithilfe von Options Feldern das stoplight zu machen.

  > [!NOTE]
  > Obwohl eine eine <xref:System.Windows.Controls.RadioButton> verwenden kann <xref:System.Windows.DataTemplate> , <xref:System.Windows.DataTemplate> ist in diesem Beispiel nicht ausreichend.  <xref:System.Windows.DataTemplate>Definiert die Darstellung des Inhalts eines-Steuer Elements. Im Fall eines <xref:System.Windows.Controls.RadioButton> wird der Inhalt auf der rechten Seite des Kreises angezeigt, der angibt, ob <xref:System.Windows.Controls.RadioButton> ausgewählt ist.  Im Beispiel mit der Ampel brauchen Sie lediglich das Optionsfeld als einen Kreis darzustellen, das „aufleuchten“ kann. Da sich die Darstellungs Anforderung für das Ampel von der Standarddarstellung von unterscheidet <xref:System.Windows.Controls.RadioButton> , muss die neu definiert werden <xref:System.Windows.Controls.ControlTemplate> .  Im allgemeinen <xref:System.Windows.DataTemplate> wird eine zum Definieren des Inhalts (oder der Daten) eines-Steuer Elements verwendet, und ein <xref:System.Windows.Controls.ControlTemplate> wird verwendet, um zu definieren, wie ein Steuerelement strukturiert ist.

- **Auslöst.** <xref:System.Windows.Trigger>Mit einem können Sie die Darstellung und das Verhalten eines Steuer Elements dynamisch ändern, ohne ein neues Steuerelement erstellen zu müssen. Angenommen, Sie verfügen über mehrere Steuer <xref:System.Windows.Controls.ListBox> Elemente in der Anwendung und möchten, dass die Elemente in den einzelnen Steuerelementen <xref:System.Windows.Controls.ListBox> Fett und rot sind, wenn Sie ausgewählt werden. Der erste Instinkt besteht darin, eine Klasse zu erstellen, die von erbt <xref:System.Windows.Controls.ListBox> und die- <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> Methode überschreibt, um die Darstellung des ausgewählten Elements zu ändern. ein besserer Ansatz ist jedoch das Hinzufügen eines-Auslösers zu einem Stil von, mit <xref:System.Windows.Controls.ListBoxItem> dem die Darstellung des ausgewählten Elements geändert wird. Mit Triggern können Sie Eigenschaftswerte bearbeiten oder basierend auf den Eigenschaftswerten Aktionen ausführen. <xref:System.Windows.EventTrigger>Mit können Sie Aktionen ausführen, wenn ein Ereignis auftritt.

Weitere Informationen zu Stilen, Vorlagen und Triggern finden Sie unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

Im Allgemeinen gilt: wenn das benötigte Steuerelement die Funktionalität eines vorhandenen Steuerelements nachmacht, aber anders aussehen soll, lohnt es sich zuerst zu überlegen, ob Sie mit einem der in diesem Abschnitt beschriebenen Verfahren die vorhandene Darstellung des Steuerelements ändern können.

<a name="models_for_control_authoring"></a>

## <a name="models-for-control-authoring"></a>Modelle für das Erstellen von Steuerelementen

Dank dem umfangreichen Inhaltsmodell sowie Stilen, Vorlagen und Triggern können Sie in den meisten Fällen auf das Erstellen neuer Steuerelemente verzichten. Falls Sie jedoch ein neues Steuerelement erstellen müssen, ist es wichtig Modelle für das Erstellen von Steuerelementen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu verstehen. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet drei allgemeine Modelle zum Erstellen der Steuerelemente, die jeweils verschiedene Funktionen und Flexibilitätsgrade bieten. Die Basisklassen für die drei Modelle sind <xref:System.Windows.Controls.UserControl> , <xref:System.Windows.Controls.Control> und <xref:System.Windows.FrameworkElement> .

### <a name="deriving-from-usercontrol"></a>Ableiten von UserControl

Die einfachste Möglichkeit zum Erstellen eines Steuer Elements in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist das Ableiten von von <xref:System.Windows.Controls.UserControl> . Wenn Sie ein Steuerelement erstellen, das von erbt <xref:System.Windows.Controls.UserControl> , fügen Sie vorhandene Komponenten hinzu <xref:System.Windows.Controls.UserControl> , benennen Sie die Komponenten, und verweisen Sie auf Ereignishandler in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] . Anschließend können Sie auf die benannten Elemente verweisen und die Ereignishandler im Code definieren. Dieses Entwicklungsmodell ähnelt sehr dem Modell für die Anwendungsentwicklung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Wenn Sie ordnungsgemäß erstellt wurde, <xref:System.Windows.Controls.UserControl> kann ein die Vorteile von umfangreichen Inhalten, Stilen und Triggern nutzen. Wenn das Steuerelement jedoch von erbt <xref:System.Windows.Controls.UserControl> , können Personen, die Ihr Steuerelement verwenden, keine oder verwenden <xref:System.Windows.DataTemplate> , <xref:System.Windows.Controls.ControlTemplate> um die Darstellung anzupassen.  Es ist notwendig, von der- <xref:System.Windows.Controls.Control> Klasse oder einer ihrer abgeleiteten Klassen (mit Ausnahme von <xref:System.Windows.Controls.UserControl> ) abzuleiten, um ein benutzerdefiniertes Steuerelement zu erstellen, das Vorlagen unterstützt.

#### <a name="benefits-of-deriving-from-usercontrol"></a>Vorteile des Ableitens von UserControl

Sie können ableiten von ableiten, <xref:System.Windows.Controls.UserControl> wenn Folgendes zutrifft:

- Sie möchten das Steuerelement auf eine ähnliche Art und Weise erstellen, wie Sie Ihre Anwendung erstellt haben.

- Ihr Steuerelement besteht ausschließlich aus vorhandenen Komponenten.

- Es muss keine komplexe Anpassung unterstützt werden.

### <a name="deriving-from-control"></a>Ableiten von Control

Die Ableitung von der- <xref:System.Windows.Controls.Control> Klasse ist das Modell, das von den meisten vorhandenen Steuerelementen verwendet wird [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] . Wenn Sie ein Steuerelement erstellen, das von der-Klasse erbt <xref:System.Windows.Controls.Control> , definieren Sie seine Darstellung mithilfe von Vorlagen. Dadurch trennen Sie die Funktionslogik von der visuellen Darstellung. Sie können auch sicherstellen, dass die Benutzeroberfläche und die Logik entkoppelt werden, indem Sie anstelle von Ereignissen Befehle und Bindungen verwenden und Verweise auf Elemente in der vermeiden, <xref:System.Windows.Controls.ControlTemplate> Wenn dies möglich ist.  Wenn die Benutzeroberfläche und die Logik des Steuer Elements ordnungsgemäß entkoppelt sind, kann ein Benutzer des Steuer Elements das Steuerelement neu definieren, <xref:System.Windows.Controls.ControlTemplate> um seine Darstellung anzupassen. Obwohl das Entwickeln eines benutzerdefinierten <xref:System.Windows.Controls.Control> nicht so einfach ist wie <xref:System.Windows.Controls.UserControl> das Entwickeln eines, bietet ein benutzerdefiniertes <xref:System.Windows.Controls.Control> die größte Flexibilität.

#### <a name="benefits-of-deriving-from-control"></a>Vorteile des Ableitens von Control

Wenn eine der folgenden Bedingungen zutrifft, empfiehlt es sich, von abzuleiten, <xref:System.Windows.Controls.Control> anstatt die-Klasse zu verwenden <xref:System.Windows.Controls.UserControl> :

- Sie möchten, dass die Darstellung des Steuer Elements über den anpassbar ist <xref:System.Windows.Controls.ControlTemplate> .

- Das Steuerelement soll verschiedene Designs unterstützen.

### <a name="deriving-from-frameworkelement"></a>Ableitung von FrameworkElement

Steuerelemente, die von abgeleitet werden <xref:System.Windows.Controls.UserControl> oder auf das Verfassen <xref:System.Windows.Controls.Control> vorhandener Elemente basieren. In vielen Szenarios ist dies eine akzeptable Lösung, da jedes Objekt, das von erbt, <xref:System.Windows.FrameworkElement> in einem vorhanden sein kann <xref:System.Windows.Controls.ControlTemplate> . Es gibt jedoch Situationen, in denen die Darstellung eines Steuerelements mehr als die Funktionalität einer einfachen Elementzusammensetzung erfordert. Für diese Szenarios ist die Grundlage einer Komponente auf <xref:System.Windows.FrameworkElement> die richtige Wahl.

Es gibt zwei Standardmethoden für die Erstellung von <xref:System.Windows.FrameworkElement> -basierten Komponenten: direktes Rendering und benutzerdefinierte Element Komposition. Das direkte Rendering umfasst das <xref:System.Windows.UIElement.OnRender%2A> Überschreiben der-Methode von <xref:System.Windows.FrameworkElement> und das Bereitstellen von <xref:System.Windows.Media.DrawingContext> Vorgängen, die explizit die visuellen Komponenten Dies ist die Methode, die von und verwendet wird <xref:System.Windows.Controls.Image> <xref:System.Windows.Controls.Border> . Die benutzerdefinierte Element Komposition umfasst die Verwendung von Objekten des Typs <xref:System.Windows.Media.Visual> , um das Erscheinungsbild der Komponente zu erstellen. Beispiele finden Sie unter [Verwenden von DrawingVisual-Objekten](../graphics-multimedia/using-drawingvisual-objects.md). <xref:System.Windows.Controls.Primitives.Track>ist ein Beispiel für ein Steuer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element in, das die benutzerdefinierte Element Komposition verwendet. Sie können auch direktes Rendering und benutzerdefinierte Elementzusammensetzung innerhalb eines Steuerelements kombinieren.

#### <a name="benefits-of-deriving-from-frameworkelement"></a>Vorteile der Ableitung von FrameworkElement

Sie können ableiten, <xref:System.Windows.FrameworkElement> Wenn eine der folgenden Bedingungen zutrifft:

- Sie brauchen eine genaue Steuerung der Darstellung Ihres Steuerelements, die darüber hinausgeht, was mit einer einfachen Elementzusammensetzung möglich ist.

- Sie möchten die Darstellung Ihres Steuerelements definieren, indem Sie Ihre eigene Renderinglogik definieren.

- Sie möchten vorhandene Elemente auf neuartige Weise verfassen, die über die Möglichkeiten von und hinaus <xref:System.Windows.Controls.UserControl> gehen <xref:System.Windows.Controls.Control> .

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

- Definieren Sie einen <xref:System.Windows.DependencyProperty> Bezeichner mit `ValueProperty` dem Namen als `public` `static` `readonly` Feld.

- Registrieren Sie den Eigenschaftsnamen beim Eigenschaften System, indem <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType> Sie aufrufen, um Folgendes anzugeben:

  - Der Name der Eigenschaft.

  - Den Typ der Eigenschaft.

  - Den Typ, der die Eigenschaft besitzt.

  - Die Metadaten für die Eigenschaft. Die Metadaten enthalten den Standardwert der Eigenschaft, a <xref:System.Windows.CoerceValueCallback> und <xref:System.Windows.PropertyChangedCallback> .

- Definieren Sie eine CLR-Wrapper Eigenschaft `Value` mit dem Namen, die dem Namen entspricht, der verwendet wird, um die Abhängigkeits Eigenschaft zu registrieren, indem Sie die- `get` und-Accessoren der Eigenschaft implementieren `set` . Beachten Sie, dass die `get` -und- `set` Accessoren nur <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> bzw. aufzurufen. Es wird empfohlen, dass die Accessoren von Abhängigkeits Eigenschaften keine zusätzliche Logik enthalten, da Clients und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Accessoren umgehen und direkt abrufen können <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> . Falls eine Eigenschaft z.B. an eine Datenquelle gebunden ist, wird die `set`-Zugriffmethode der Eigenschaft nicht aufgerufen.  Anstatt den Get-und Set-Accessoren zusätzliche Logik hinzuzufügen, verwenden Sie die Delegaten <xref:System.Windows.ValidateValueCallback> , <xref:System.Windows.CoerceValueCallback> und, <xref:System.Windows.PropertyChangedCallback> um auf den Wert zu reagieren oder den Wert zu überprüfen, wenn er sich ändert.  Weitere Informationen zu diesen Rückrufen finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](../advanced/dependency-property-callbacks-and-validation.md).

- Definieren Sie eine Methode für das <xref:System.Windows.CoerceValueCallback> benannte `CoerceValue` . `CoerceValue` stellt sicher, dass `Value` größer oder gleich `MinValue` und kleiner oder gleich `MaxValue` ist.

- Definieren Sie eine Methode für den mit dem <xref:System.Windows.PropertyChangedCallback> Namen `OnValueChanged` . `OnValueChanged`erstellt ein <xref:System.Windows.RoutedPropertyChangedEventArgs%601> -Objekt und bereitet darauf vor, das-Routing Ereignis zu erhöhen `ValueChanged` . Routingereignisse werden im nächsten Abschnitt erläutert.

[!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
[!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]

Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../advanced/custom-dependency-properties.md).

### <a name="use-routed-events"></a>Verwenden von Routingereignissen

Ebenso wie Abhängigkeits Eigenschaften das Konzept von CLR-Eigenschaften mit zusätzlicher Funktionalität erweitern, erweitern Routing Ereignisse das Konzept von CLR-Standard Ereignissen. Beim Erstellen eines neuen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelements empfiehlt es sich, Ihr Ereignis als ein Routingereignis zu implementieren, da Routingereignisse folgendes Verhalten unterstützen:

- Ereignisse für mehrere Steuerelemente können über ein übergeordnetes Steuerelement behandelt werden. Falls es sich bei dem Ereignis um ein Bubbling-Ereignis handelt, kann ein einzelnes übergeordnetes Element in der Elementstruktur das Ereignis abonnieren. Anschließend können Anwendungsentwickler mit einem Handler auf das Ereignis mehrerer Steuerelemente reagieren. Wenn das Steuerelement z. b. ein Teil der einzelnen Elemente in einer ist <xref:System.Windows.Controls.ListBox> (da es in einer enthalten ist <xref:System.Windows.DataTemplate> ), kann der Anwendungsentwickler den Ereignishandler für das-Ereignis des Steuer Elements im definieren <xref:System.Windows.Controls.ListBox> . Beim Auftreten des Ereignisses bei einem der Steuerelemente wird der Ereignishandler aufgerufen.

- Routing Ereignisse können in einem verwendet werden <xref:System.Windows.EventSetter> , wodurch Anwendungsentwickler den Handler eines Ereignisses innerhalb eines Stils angeben können.

- Routing Ereignisse können in verwendet werden <xref:System.Windows.EventTrigger> , was zum Animieren von Eigenschaften mithilfe von nützlich ist [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Weitere Informationen finden Sie unter [Übersicht über Animation](../graphics-multimedia/animation-overview.md).

Im folgenden Beispiel wird ein Routingereignis wie folgt definiert:

- Definieren Sie einen <xref:System.Windows.RoutedEvent> Bezeichner mit `ValueChangedEvent` dem Namen als `public` `static` `readonly` Feld.

- Registrieren Sie das-Routing Ereignis, indem Sie die- <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType> Methode aufrufen. Das Beispiel gibt die folgenden Informationen an, wenn aufgerufen wird <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> :

  - Der Name des Ereignisses lautet `ValueChanged`.

  - Die Routing Strategie ist. <xref:System.Windows.RoutingStrategy.Bubble> Dies bedeutet, dass ein Ereignishandler für die Quelle (das Objekt, das das Ereignis auslöst) zuerst aufgerufen wird. Anschließend werden die Ereignishandler für die übergeordneten Elemente der Quelle nacheinander aufgerufen, beginnend mit dem Ereignishandler auf dem nächstgelegenen übergeordneten Element.

  - Der Typ des Ereignis Handlers ist <xref:System.Windows.RoutedPropertyChangedEventHandler%601> , erstellt mit einem- <xref:System.Decimal> Typ.

  - `NumericUpDown` ist der besitzende Typ des Ereignisses.

- Ein öffentliches Ereignis mit dem Namen `ValueChanged`, das die Zugriffsmethoden-Deklarationen umfasst, wird deklariert. Im Beispiel wird <xref:System.Windows.UIElement.AddHandler%2A> in der `add` Accessordeklaration und <xref:System.Windows.UIElement.RemoveHandler%2A> in der `remove` Accessordeklaration aufgerufen, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ereignis Dienste zu verwenden.

- Eine geschützte virtuelle Methode mit dem Namen `OnValueChanged`, die das`ValueChanged`-Ereignis auslöst, wird erstellt.

[!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
[!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]

Weitere Informationen finden Sie unter [ Übersicht über Routingereignisse ](../advanced/routed-events-overview.md) und [Vorgehensweise: Erstellen eines benutzerdefinierten Routingereignisses](../advanced/how-to-create-a-custom-routed-event.md).

### <a name="use-binding"></a>Verwendung von Bindungen

Erwägen Sie Datenbindungen, um die Benutzeroberfläche Ihres Steuerelements von der Logik zu entkoppeln. Dies ist besonders wichtig, wenn Sie die Darstellung des Steuer Elements mithilfe eines definieren <xref:System.Windows.Controls.ControlTemplate> . Bei der Verwendung einer Datenbindung können Sie u.U. auf die Verweise auf bestimmte Teile der Benutzeroberfläche aus dem Code verzichten. Es empfiehlt sich, Verweise auf Elemente in zu vermeiden, <xref:System.Windows.Controls.ControlTemplate> denn wenn der Code auf Elemente verweist, die sich in der befinden <xref:System.Windows.Controls.ControlTemplate> und die <xref:System.Windows.Controls.ControlTemplate> geändert wird, muss das Element, auf das verwiesen wird, in das neue eingeschlossen werden <xref:System.Windows.Controls.ControlTemplate> .

Im folgenden Beispiel wird die <xref:System.Windows.Controls.TextBlock> des- `NumericUpDown` Steuer Elements aktualisiert, und es wird ein Name zugewiesen, und im Code wird anhand des Namens auf das Textfeld verwiesen.

[!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]

[!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
[!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]

Im folgenden Beispiel wird eine Bindung für den selben Zweck verwendet.

[!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]

Weitere Informationen zu Datenbindungen finden Sie unter [Übersicht über Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).

### <a name="design-for-designers"></a>Darstellung für Designer

Um Unterstützung für benutzerdefinierte WPF-Steuerelemente im WPF-Designer für Visual Studio (z. b. Eigenschaften Bearbeitung mit dem Eigenschaftenfenster) zu erhalten, befolgen Sie diese Richtlinien.  Weitere Informationen zum entwickeln für den WPF-Designer finden Sie unter [Entwerfen von XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).

#### <a name="dependency-properties"></a>Abhängigkeitseigenschaften

Stellen Sie sicher, dass CLR `get` und `set` Accessoren wie zuvor beschrieben in "Abhängigkeits Eigenschaften verwenden" implementiert werden. Designer können Wrapper zur Prüfung des Vorhandenseins einer Abhängigkeitseigenschaft verwenden. Diese müssen, genauso wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und Clients des Steuerelements, beim Abrufen oder Festlegen der Eigenschaft jedoch keine Zugriffsmethoden aufrufen.

#### <a name="attached-properties"></a>Angefügte Eigenschaften

Angefügte Eigenschaften für benutzerdefinierte Steuerelemente sind unter Einhaltung der folgenden Richtlinien zu implementieren:

- `public` `static` `readonly` <xref:System.Windows.DependencyProperty> Verwenden Sie eine der Form *propertyName* `Property` , die mithilfe der- <xref:System.Windows.DependencyProperty.RegisterAttached%2A> Methode erstellt wurde. Der an übergebenen Eigenschaften Name <xref:System.Windows.DependencyProperty.RegisterAttached%2A> muss mit *propertyName*identisch sein.

- Implementieren Sie die `public` `static` CLR-Methoden mit den Namen `Set`*PropertyName* und `Get`*PropertyName*. Beide Methoden sollten eine von abgeleitete Klasse <xref:System.Windows.DependencyProperty> als das erste Argument akzeptieren. Die `Set`*PropertyName*-Methode akzeptiert auch ein Argument, dessen Typ mit dem registrierten Datentyp der Eigenschaft übereinstimmt. Die `Get`*PropertyName*-Methode sollte einen Wert zurückgeben, der den gleichen Typ aufweist. Falls die `Set`*PropertyName*-Methode fehlt, wird die Eigenschaft als schreibgeschützt gekennzeichnet.

- `Set`*PropertyName* und `Get` *propertyName* müssen direkt an die <xref:System.Windows.DependencyObject.GetValue%2A> -Methode und die- <xref:System.Windows.DependencyObject.SetValue%2A> Methode für das Ziel Abhängigkeits Objekt weiterleiten. Designer können auf die angefügte Eigenschaft entweder über einen Aufruf des Wrappers für die Methode zugreifen, oder indem sie das Zielabhängigkeitsobjekt direkt aufrufen.

Weitere Informationen zu angefügten Eigenschaften finden Sie in der [Übersicht über angefügte Eigenschaften](../advanced/attached-properties-overview.md).

### <a name="define-and-use-shared-resources"></a>Definieren und Verwenden von freigegebenen Ressourcen

Sie können Ihr Steuerelement entweder in die Assembly Ihrer Anwendung, oder in eine separate Assembly einbinden, die in mehreren Anwendungen verwendet werden kann. Der Großteil der in diesem Thema erläuterten Informationen gilt unabhängig von der von Ihnen verwendeten Methode.  Ein wesentlicher Unterschied ist dennoch zu beachten.  Falls Sie ein Steuerelement in die Assembly einer Anwendung einbinden, können Sie der App.xaml-Datei globale Ressourcen hinzufügen. Einer Assembly, die nur Steuerelemente enthält <xref:System.Windows.Application> , ist jedoch kein Objekt zugeordnet, sodass keine app. XAML-Datei verfügbar ist.

Wenn eine Anwendung nach einer Ressource sucht,wird auf drei Ebenen in der folgenden Reihenfolge gesucht:

1. Die Elementebene.

   Das System beginnt mit dem Element, das auf die Ressource verweist, und sucht anschließend die Ressourcen des logischen übergeordneten Elements durch. Dieser Schritt wir wiederholt, bis das Stammelement erreicht ist.

2. Die Anwendungsebene.

   Ressourcen, die durch das-Objekt definiert werden <xref:System.Windows.Application> .

3. Die Designebene.

   Ressourcenverzeichnisse werden auf der Designebene in einem Themes-Unterordner gespeichert.  Die Dateien im Themes-Ordner entsprechen den Designs.  Dort könnten Sie beispielsweise Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml, etc. finden.  Möglicherweise ist auch eine Datei mit dem Namen generic.xaml enthalten.  Bei einer Suche nach einer Ressource auf der Designebene wird zunächst in der designspezifischen Datei und dann in der Datei generic.xaml gesucht.

Falls Ihr Steuerelement in einer anderen Assembly als die Anwendung liegt, müssen Sie Ihre globale Ressourcen auf die Elementen- oder Designebene umspeichern. Beide Methoden haben ihre Vorteile.

#### <a name="defining-resources-at-the-element-level"></a>Definieren von Ressourcen auf der Elementebene

Sie können freigegebene Ressourcen auf der Element Ebene definieren, indem Sie ein benutzerdefiniertes Ressourcenverzeichnis erstellen und es mit dem Ressourcen Wörterbuch des Steuer Elements zusammenführen.  Falls Sie sich für diese Methode entscheiden, können Sie die Ressourcendatei beliebig benennen und sie im Ordner speichern, wo Ihre Steuerelemente liegen. Für Ressourcen auf der Elementebene können ebenso einfache Zeichenfolgen als Schlüssel verwendet werden. Im folgenden Beispiel wird eine <xref:System.Windows.Media.LinearGradientBrush> Ressourcen Datei mit dem Namen Dictionary1. XAML erstellt.

[!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]

Nachdem Sie das Ressourcenverzeichnis definiert haben, müssen Sie es mit dem Ressourcenverzeichnis des Steuerelements zusammenführen.  Hierzu können Sie [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder Code verwenden.

Im folgenden Beispiel wird ein Ressourcenverzeichnis mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zusammengeführt.

[!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]

Der Nachteil dieses Ansatzes besteht darin, dass <xref:System.Windows.ResourceDictionary> jedes Mal, wenn Sie darauf verweisen, ein-Objekt erstellt wird.  Wenn Sie z. b. über 10 benutzerdefinierte Steuerelemente in der Bibliothek verfügen und die freigegebenen Ressourcen Wörterbücher für jedes Steuerelement mithilfe von XAML zusammenführen, erstellen Sie 10 identische <xref:System.Windows.ResourceDictionary> Objekte.  Dies können Sie vermeiden, indem Sie eine statische Klasse erstellen, die die Ressourcen im Code zusammenfasst und die resultierende zurückgibt <xref:System.Windows.ResourceDictionary> .

Im folgenden Beispiel wird eine-Klasse erstellt, die eine freigegebene zurückgibt <xref:System.Windows.ResourceDictionary> .

[!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]

Im folgenden Beispiel wird die freigegebene Ressource mit den Ressourcen eines benutzerdefinierten Steuerelements im Konstruktor des Steuerelements zusammengeführt, bevor sie `InitializeComponent` aufruft.  Da `SharedDictionaryManager.SharedDictionary` eine statische Eigenschaft ist, <xref:System.Windows.ResourceDictionary> wird nur einmal erstellt. Da das Ressourcenverzeichnis vor dem Aufruf von `InitializeComponent` zusammengeführt worden ist, kann das Steuerelement auf die Ressourcen in seiner [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Datei zugreifen.

[!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]

#### <a name="defining-resources-at-the-theme-level"></a>Definieren von Ressourcen auf der Designebene

Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie Ressourcen für verschiedene Windows-Designs erstellen.  Als Autor des Steuerelements können Sie eine Ressource für ein bestimmtes Design definieren, um die Darstellung Ihres Steuerelements an das jeweils verwendete Design anzupassen. Beispielsweise unterscheidet sich die Darstellung eines <xref:System.Windows.Controls.Button> im klassischen Windows-Design (das Standarddesign für Windows 2000) von a <xref:System.Windows.Controls.Button> im Windows-Luna-Design (das Standarddesign für Windows XP), da <xref:System.Windows.Controls.Button> für jedes Design eine andere verwendet <xref:System.Windows.Controls.ControlTemplate> .

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

Das benutzerdefinierte [c#](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) -oder [Visual Basic](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) NumericUpDown-Steuerelement mit Design-und Benutzeroberflächenautomatisierungs-Unterstützung enthält zwei Ressourcen Wörterbücher für das- `NumericUpDown` Steuerelement: eines in Generic. XAML und das andere in Luna. NormalColor. XAML.

Wenn Sie in einer <xref:System.Windows.Controls.ControlTemplate> der Design spezifischen Ressourcenverzeichnis Dateien platzieren, müssen Sie für das Steuerelement einen statischen Konstruktor erstellen und die-Methode für <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> den aufzurufen <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> , wie im folgenden Beispiel gezeigt.

[!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
[!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]

##### <a name="defining-and-referencing-keys-for-theme-resources"></a>Definieren und Angeben von Schlüsseln für Designressourcen

Wenn Sie eine Ressource auf der Elementebene definieren, können Sie ihr als Schlüssel eine Zeichenfolge zuweisen und über diese Zeichenfolge auf sie zugreifen. Wenn Sie eine Ressource auf der Design Ebene definieren, müssen Sie einen <xref:System.Windows.ComponentResourceKey> als Schlüssel verwenden.  Im folgenden Beispiel wird eine Ressource in generic.xaml definiert.

[!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]

Im folgenden Beispiel wird auf die Ressource verwiesen, indem <xref:System.Windows.ComponentResourceKey> als Schlüssel angegeben wird.

[!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]

##### <a name="specifying-the-location-of-theme-resources"></a>Angeben des Speicherorts von Designressourcen

Um die Ressourcen für ein Steuerelement zu finden, muss die Hostinganwendung über die Information verfügen, dass die Assembly Ressourcen enthält, die steuerelementenspezifisch sind. Dies erreichen Sie, indem Sie der <xref:System.Windows.ThemeInfoAttribute> Assembly, die das Steuerelement enthält, hinzufügen. Der <xref:System.Windows.ThemeInfoAttribute> verfügt über eine <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> -Eigenschaft, die den Speicherort der generischen Ressourcen angibt, und eine-Eigenschaft, die <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> den Speicherort der Design spezifischen Ressourcen angibt.

Im folgenden Beispiel werden die <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> -Eigenschaft und die-Eigenschaft auf festgelegt <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> <xref:System.Windows.ResourceDictionaryLocation.SourceAssembly> , um anzugeben, dass sich die generischen und Design spezifischen Ressourcen in derselben Assembly wie das-Steuerelement befinden.

[!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
[!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]

## <a name="see-also"></a>Weitere Informationen

- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Paket-URI in WPF](../app-development/pack-uris-in-wpf.md)
- [Anpassung von Steuerelementen](control-customization.md)
