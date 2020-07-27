---
title: Übersicht über Routingereignisse
description: Erfahren Sie mehr über Routing Ereignisse in Windows Presentation Foundation, einschließlich der Art und Weise, wie Sie durch eine Elementstruktur weitergeleitet werden und wie Sie benutzerdefinierte Routing Ereignisse erstellen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached events [WPF]
- grouped button set [WPF]
- routed events [WPF]
- events [WPF], routed
- tunneling [WPF]
- events [WPF], attached
- routing strategies for events [WPF]
- button set [WPF], grouped
- bubbling [WPF]
ms.assetid: 1a2189ae-13b4-45b0-b12c-8de2e49c29d2
ms.openlocfilehash: d18b511a4886c68922cccac14942eb54e5735a71
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164804"
---
# <a name="routed-events-overview"></a>Übersicht über Routingereignisse

Dieses Thema beschreibt das Konzept von Routingereignissen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Das Thema definiert die Terminologie von Routingereignissen, beschreibt, wie Routingereignisse anhand einer Struktur von Elementen weitergeleitet werden und führt Sie in das Erstellen Ihrer eigenen, benutzerdefinierten Routingereignisse ein.

<a name="prerequisites"></a>

## <a name="prerequisites"></a>Voraussetzungen

In diesem Thema wird davon ausgegangen, dass Sie über grundlegende Kenntnisse der Common Language Runtime (CLR) und der objektorientierten Programmierung verfügen, sowie das Konzept der Art und Weise, wie die Beziehungen zwischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elementen als Baumstruktur verstanden werden können. Um den Beispielen in diesem Thema zu folgen, sollten Sie zudem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] verstehen und wissen, wie sehr einfache [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen oder -Seiten geschrieben werden. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: meine erste WPF-Desktop Anwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md) und [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).

<a name="routing"></a>

## <a name="what-is-a-routed-event"></a>Was ist ein Routingereignis?

Stellen Sie sich Routingereignisse entweder aus Sicht der Funktion oder der Implementierung vor. Beide Definitionen werden hier vorgestellt, da Benutzer die Definitionen unterschiedlich hilfreich finden.

Funktionale Definition: Ein Routingereignis ist ein Ereignis, das Ereignishandler auf mehreren Listenern in einer Elementstruktur aufrufen kann, und nicht nur auf dem Objekt, das das Ereignis ausgelöst hat.

Implementierungs Definition: ein Routing Ereignis ist ein CLR-Ereignis, das von einer Instanz der-Klasse unterstützt wird <xref:System.Windows.RoutedEvent> und vom [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Ereignis System verarbeitet wird.

Eine typische [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung enthält viele Elemente. Egal ob im Code erstellt oder in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] deklariert, stehen diese Elemente in einer Beziehung einer Elementstruktur zueinander. Die Ereignisroute kann sich abhängig von der Ereignisdefinition in eine von zwei Richtungen bewegen; im Allgemeinen bewegt sie sich vom Quellelement aus und „steigt“ in der Elementstruktur auf, bis sie den Stamm der Elementstruktur erreicht (normalerweise eine Seite oder ein Fenster). Dieses Bubblingkonzept kommt Ihnen möglicherweise bekannt vor, wenn Sie schon einmal mit dem DHTML-Objektmodell gearbeitet haben.

Betrachten Sie die folgende einfache Elementstruktur:

[!code-xaml[EventOvwSupport#GroupButton](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#groupbutton)]

Diese Elementstruktur erzeugt in etwa Folgendes:

![Schaltflächen Ja, Nein und Abbrechen](./media/routedevent-ovw-1.gif "RoutedEvent_ovw_1")

In dieser vereinfachten Elementstruktur ist die Quelle eines <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignisses eines der <xref:System.Windows.Controls.Button> -Elemente, und je nachdem <xref:System.Windows.Controls.Button> , was geklickt hat, ist das erste Element, das die Möglichkeit hat, das Ereignis zu behandeln. Wenn jedoch kein an den angefügter Handler für <xref:System.Windows.Controls.Button> das-Ereignis verwendet wird, wird das-Ereignis in der-Elementstruktur nach oben bis zum über <xref:System.Windows.Controls.Button> geordneten Element geblasen, das ist <xref:System.Windows.Controls.StackPanel> . Möglicherweise wird das Ereignis auf <xref:System.Windows.Controls.Border> und dann auf den Seiten Stamm der Elementstruktur (nicht angezeigt) weiter oben angezeigt.

Mit anderen Worten: die Ereignis Route für dieses <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis lautet wie folgt:

Button-->StackPanel-->Border-->...

### <a name="top-level-scenarios-for-routed-events"></a>Szenarios auf oberster Ebene für Routingereignisse

Im folgenden finden Sie eine kurze Zusammenfassung der Szenarien, die das Routing Ereignis Konzept motiviert haben, und warum ein typisches CLR-Ereignis für diese Szenarien nicht geeignet war:

**Zusammensetzung und Kapselung von Steuerelementen:** Verschiedene Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügen über ein umfangreiches Inhaltsmodell. Beispielsweise können Sie ein Bild in einer platzieren <xref:System.Windows.Controls.Button> , wodurch die visuelle Struktur der Schaltfläche effektiv erweitert wird. Allerdings darf das hinzugefügte Bild das Treffer Testverhalten nicht unterbrechen, das bewirkt, dass eine Schaltfläche auf einen <xref:System.Windows.Controls.Primitives.ButtonBase.Click> der Inhalte antwortet, auch wenn der Benutzer auf Pixel klickt, die in technischer Hinsicht Teil des Bilds sind.

**Einzelne Handleranfügepunkte:** In Windows Forms müssten Sie denselben Handler mehrmals anfügen, um Ereignisse zu verarbeiten, die aus mehreren Elementen ausgelöst werden könnten. Routingereignisse ermöglichen es Ihnen, diesen Handler nur einmal anzufügen, wie im vorherigen Beispiel gezeigt wurde, und verwenden Handlerlogik, um ggf. zu bestimmen, woher das Ereignis stammt. Dies kann z.B. der Handler für die zuvor gezeigte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sein:

[!code-csharp[EventOvwSupport#GroupButtonCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#groupbuttoncodebehind)]
[!code-vb[EventOvwSupport#GroupButtonCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#groupbuttoncodebehind)]

**Klassenbehandlung:** Routingereignisse akzeptieren einen statischen Handler, der von der Klasse definiert ist. Dieser Klassenhandler hat die Möglichkeit, ein Ereignis vor angefügten Instanzhandlern zu behandeln.

**Verweisen auf ein Ereignis ohne Reflektion:** Bestimmte Code- und Markuptechniken erfordern eine Möglichkeit, ein bestimmtes Ereignis zu identifizieren. Ein Routing Ereignis erstellt ein <xref:System.Windows.RoutedEvent> Feld als Bezeichner, das eine robuste Ereignis Identifikationstechnik bereitstellt, die keine statische oder Lauf Zeit Reflektion erfordert.

### <a name="how-routed-events-are-implemented"></a>So werden Routingereignis implementiert

Ein Routing Ereignis ist ein CLR-Ereignis, das von einer Instanz der <xref:System.Windows.RoutedEvent> -Klasse unterstützt und beim- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ereignis System registriert wird. Die- <xref:System.Windows.RoutedEvent> Instanz, die von der Registrierung abgerufen wird, wird in der Regel als `public` `static` `readonly` Feldmember der-Klasse aufbewahrt, die das-Routing Ereignis registriert und somit "besitzt". Die Verbindung mit dem identisch benannten CLR-Ereignis (das manchmal als "Wrapper"-Ereignis bezeichnet wird) wird durch Überschreiben der `add` -und- `remove` Implementierungen für das CLR-Ereignis erreicht. Normalerweise bleiben `add` und `remove` als impliziter Standard bestehen, der die entsprechende sprachspezifische Ereignissyntax zum Hinzufügen und Entfernen von Handlern dieses Ereignisses verwendet. Der Unterstützungs-und Verbindungs Mechanismus des Routing Ereignisses ähnelt konzeptionell der Art und Weise, wie eine Abhängigkeits Eigenschaft eine CLR-Eigenschaft ist, die von der <xref:System.Windows.DependencyProperty> -Klasse unterstützt und beim- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften System registriert wird.

Das folgende Beispiel zeigt die Deklaration für ein benutzerdefiniertes Routing `Tap` Ereignis, einschließlich der Registrierung und dem verfügbar machen des <xref:System.Windows.RoutedEvent> Bezeichnerfelds und der `add` -und- `remove` Implementierungen für das `Tap` CLR-Ereignis.

[!code-csharp[RoutedEventCustom#AddRemoveHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#addremovehandler)]
[!code-vb[RoutedEventCustom#AddRemoveHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#addremovehandler)]

### <a name="routed-event-handlers-and-xaml"></a>Routingereignishandler und XAML

Um einen Handler für ein Ereignis mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hinzuzufügen, deklarieren Sie den Ereignisnamen als Attribut auf dem Element, das ein Ereignislistener ist. Der Wert des Attributs ist der Name Ihrer implementierten Handlermethode, die in der partiellen Klasse der CodeBehind-Datei vorhanden sein muss.

[!code-xaml[EventOvwSupport#SimplestSyntax](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#simplestsyntax)]

Die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Syntax zum Hinzufügen von CLR-Standard Ereignis Handlern ist für das Hinzufügen von Routing Ereignis Handlern identisch, da Sie dem CLR-Ereignis Wrapper, der über eine Routing Ereignis-Implementierung verfügt, tatsächlich Handler hinzufügen. Weitere Informationen zum Hinzufügen von Ereignishandlern in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] finden Sie unter [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).

<a name="routing_strategies"></a>

## <a name="routing-strategies"></a>Routingstrategien

Routingereignisse verwenden eine von drei Routingstrategien:

- **Bubbling:** Ereignishandler werden auf der Ereignisquelle aufgerufen. Das Routingereignis wird dann auf nachfolgenden übergeordnete Elemente weitergeleitet, bis es den Stamm der Elementstruktur erreicht. Die meisten Routingereignisse verwenden die Bubblingroutingstrategie. Bubblingroutingereignisse werden üblicherweise verwendet, um Eingabe- oder Zustandänderungen von unterschiedlichen Steuerelemente oder andere Elementen der Benutzeroberfläche zu melden.

- **Direkt:** Nur das Quellelement selbst kann als Reaktion Handler aufrufen. Dies entspricht dem Routing, das Windows Forms für Ereignisse verwendet. Anders als bei einem Standard-CLR-Ereignis unterstützen direkte Routing Ereignisse jedoch die Klassen Behandlung (die Klassen Behandlung wird in einem zukünftigen Abschnitt erläutert) und können von und verwendet werden <xref:System.Windows.EventSetter> <xref:System.Windows.EventTrigger> .

- **Tunneling:** Zunächst werden Ereignishandler am Stamm der Elementstruktur aufgerufen. Das Routingereignis bewegt sich dann über eine Route durch die nachfolgenden untergeordneten Elemente in Richtung des Knotenelements, das die Quelle des Routingereignisses ist (das Element, das das Routingereignis ausgelöst). Tunnelingroutingereignisse werden oft als Teil der Zusammensetzung eines Steuerelements verwendet oder behandelt, sodass Elemente der einzelnen Teile von Ereignissen, die für das vollständige Steuerelement spezifisch sind, bewusst unterdrückt oder ersetzt werden können. Eingabeereignisse aus [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sind oft als Tunneling/Bubbling-Paar implementiert. Tunnelingereignisse werden manchmal auch als Vorschauereignisse bezeichnet; dies liegt an einer Benennungskonvention für Paare.

<a name="why_use"></a>

## <a name="why-use-routed-events"></a>Was ist der Vorteil von Routingereignissen?

Als Anwendungsentwickler müssen Sie nicht immer wissen oder sicherstellen, dass das Ereignis, das Sie behandeln, als Routingereignis implementiert wird. Weitergeleitete Ereignisse weisen ein besonderes Verhalten auf, aber dieses Verhalten ist weitestgehend unsichtbar, wenn Sie ein Ereignisses auf dem Element behandeln, in dem es ausgelöst wurde.

Routingereignisse erweisen sich besonders dort als sehr nützlich, wo Sie eines der folgenden Szenarios verwenden: beim Definieren von gängigen Handlern am gängigen Stamm, beim Zusammensetzen eines eigenen Steuerelements oder beim Definieren Ihrer eigenen, benutzerdefinierten Steuerelementklasse.

Routingereignislistener und Routingereignisquellen müssen kein gemeinsames Ereignis in ihrer Hierarchie aufweisen. Any <xref:System.Windows.UIElement> oder <xref:System.Windows.ContentElement> kann ein Ereignislistener für ein beliebiges Routing Ereignis sein. Aus diesem Grund können Sie den vollständigen Satz von Routing Ereignissen, die im gesamten funktionierenden API-Satz verfügbar sind, als konzeptionelle "Schnittstelle" verwenden, bei der unterschiedliche Elemente in der Anwendung Ereignis Informationen austauschen können. Dieses „Schnittstellen“-Konzept für Routingereignisse kann besonders auf Eingabeereignisse angewendet werden.

Routingereignisse können auch für die Kommunikation durch die Elementstruktur verwendet werden, da die Ereignisdaten für jedes Element auf der Route aufrechterhalten werden. Ein Element könnte die Ereignisdaten ändern, und diese Änderung wäre für das nächste Element auf der Route verfügbar.

Außer dem Routing Aspekt gibt es zwei andere Gründe, warum ein bestimmtes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ereignis anstelle eines CLR-Standard Ereignisses als Routing Ereignis implementiert werden kann. Wenn Sie Ihr eigenes Ereignis implementieren, können Sie auch folgende Prinzipien berücksichtigen:

- Bestimmte Formatierungs [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -und Vorlagen Funktionen wie <xref:System.Windows.EventSetter> und <xref:System.Windows.EventTrigger> erfordern, dass das referenzierte Ereignis ein Routing Ereignis ist. Dies ist das Szenario mit einem Ereignisbezeichner, das weiter oben erwähnt wurde.

- Routingereignisse unterstützen einen Mechanismus zur Klassenbehandlung, durch den die Klasse statische Methoden angeben kann, die die Möglichkeit haben, Routingereignisse zu behandeln, bevor registrierte Instanzenhandler darauf zugreifen können. Dies ist beim Entwerfen von Steuerelementen hilfreich, da Ihre Klasse ereignisgesteuertes Klassenverhalten erzwingen kann, das nicht versehentlich durch das Behandeln eines Ereignisses auf einer Instanz unterdrückt werden kann.

Jeder der oben genannten Aspekte wird in einem separaten Abschnitt dieses Themas erläutert.

<a name="event_handing"></a>

## <a name="adding-and-implementing-an-event-handler-for-a-routed-event"></a>Hinzufügen und implementieren eines Ereignishandlers für ein Routingereignis

Zum Hinzufügen eines Ereignishandlers in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] müssen Sie einfach nur den Ereignisnamen als Attribut in ein Element einfügen und den Attributwert auf den Namen des Ereignishandlers festlegen, der einen angemessenen Delegaten implementiert, wie in folgendem Beispiel veranschaulicht.

[!code-xaml[EventOvwSupport#SimplestSyntax](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#simplestsyntax)]

`b1SetColor`der Name des implementierten Handlers, der den Code enthält, der das <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis behandelt. `b1SetColor`muss die gleiche Signatur wie der Delegat aufweisen, der der Ereignishandlerdelegat <xref:System.Windows.RoutedEventHandler> für das <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis ist. Der erste Parameter aller Delegaten von Routingereignishandlern gibt das Element an, dem der Ereignishandler hinzugefügt wird, und der zweite Parameter gibt die Daten des Ereignisses an.

[!code-csharp[EventOvwSupport#SimpleHandlerA](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#simplehandlera)]
[!code-vb[EventOvwSupport#SimpleHandlerA](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#simplehandlera)]

<xref:System.Windows.RoutedEventHandler>ist der einfache Routing Ereignishandler-Delegat. Für Routingereignisse, die auf bestimmte Steuerelemente oder Szenarien ausgelegt sind, können die für die Routingereignishandler zu verwendenden Delegaten möglicherweise so spezialisiert werden, dass sie spezialisierte Ereignisdaten übertragen können. Beispielsweise können Sie in einem allgemeinen Eingabe Szenario ein Routing Ereignis behandeln <xref:System.Windows.UIElement.DragEnter> . Der Handler muss den Delegaten implementieren <xref:System.Windows.DragEventHandler> . Mit dem spezifischsten Delegaten können Sie den <xref:System.Windows.DragEventArgs> im-Handler verarbeiten und die- <xref:System.Windows.DragEventArgs.Data%2A> Eigenschaft lesen, die die Zwischenablage Nutzlast des Zieh Vorgangs enthält.

Ein vollständiges Beispiel zum Hinzufügen eines Ereignishandlers in ein Element mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] finden Sie unter [Behandeln eines Routingereignisses](how-to-handle-a-routed-event.md).

Das Hinzufügen eines Handlers für ein Routingereignis in einer Anwendung, die im Code erstellt wird, ist einfach. Routing Ereignishandler können immer über eine Hilfsmethode hinzugefügt werden <xref:System.Windows.UIElement.AddHandler%2A> (bei der es sich um dieselbe Methode handelt, die die vorhandene Unterstützung aufruft `add` ). Vorhandene Routing [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ereignisse verfügen jedoch im Allgemeinen über Unterstützungs Implementierungen von `add` und `remove` einer Logik, mit der die Handler für Routing Ereignisse durch eine sprachspezifische Ereignis Syntax hinzugefügt werden können. Dies ist eine intuitivere Syntax als die Hilfsmethode. Im Folgenden wird die Hilfsmethode in einem Beispiel verwendet:

[!code-csharp[EventOvwSupport#AddHandlerCode](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#addhandlercode)]
[!code-vb[EventOvwSupport#AddHandlerCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#addhandlercode)]

Das nächste Beispiel zeigt die Syntax des c#-Operators (Visual Basic hat aufgrund der Behandlung der Dereferenzierung eine etwas andere Operator Syntax):

[!code-csharp[EventOvwSupport#AddHandlerPlusEquals](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#addhandlerplusequals)]
[!code-vb[EventOvwSupport#AddHandlerPlusEquals](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#addhandlerplusequals)]

Ein Beispiel für das Hinzufügen eines Ereignishandlers in Code finden Sie unter [Hinzufügen eines Ereignishandlers mithilfe von Code](how-to-add-an-event-handler-using-code.md).

Wenn Sie Visual Basic verwenden, können Sie auch das- `Handles` Schlüsselwort verwenden, um Handler als Teil der Handlerdeklarationen hinzuzufügen. Weitere Informationen finden Sie unter [Visual Basic- und WPF-Ereignisbehandlung](visual-basic-and-wpf-event-handling.md).

<a name="concept_handled"></a>

### <a name="the-concept-of-handled"></a>Das Handled-Konzept

Alle Routing Ereignisse haben eine gemeinsame Ereignisdaten-Basisklasse, <xref:System.Windows.RoutedEventArgs> . <xref:System.Windows.RoutedEventArgs>definiert die- <xref:System.Windows.RoutedEventArgs.Handled%2A> Eigenschaft, die einen booleschen Wert annimmt. Der Zweck der- <xref:System.Windows.RoutedEventArgs.Handled%2A> Eigenschaft besteht darin, jeden Ereignishandler entlang der Route zu aktivieren, um das Routing Ereignis als *behandelt*zu markieren, indem der Wert von auf festgelegt wird <xref:System.Windows.RoutedEventArgs.Handled%2A> `true` . Nachdem die freigegebenen Ereignisdaten vom Handler an einem Element auf der Route verarbeitet wurden, werden die Daten wieder jedem Listener auf der Route gemeldet.

Der Wert von <xref:System.Windows.RoutedEventArgs.Handled%2A> wirkt sich darauf aus, wie ein Routing Ereignis während der Weiterleitung entlang der Route gemeldet oder verarbeitet wird. Wenn <xref:System.Windows.RoutedEventArgs.Handled%2A> `true` in den Ereignisdaten für ein-Routing Ereignis ist, werden die Handler, die auf dieses Routing Ereignis für andere Elemente lauschen, im Allgemeinen nicht mehr für diese bestimmte Ereignis Instanz aufgerufen. Dies gilt sowohl für in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] angefügte Handler als auch für Handler, die von anderen sprachspezifischen Anfügesyntaxen für Ereignishandlern, wie z.B. `+=` oder `Handles`, hinzugefügt wurden. Bei den meisten gängigen handlerszenarios wird bei der Kennzeichnung eines Ereignisses durch Festlegen von <xref:System.Windows.RoutedEventArgs.Handled%2A> auf `true` das Routing entweder für eine tunnelungs Route oder eine bubblingerroute und auch für alle Ereignisse, die an einem Punkt in der Route von einem Klassen Handler behandelt werden, beendet.

Es gibt jedoch einen "shanddeventstoo"-Mechanismus, bei dem Listener weiterhin Handler als Antwort auf Routing Ereignisse ausführen können, in denen <xref:System.Windows.RoutedEventArgs.Handled%2A> `true` die Ereignisdaten in vorhanden sind. Das heißt, ist die Ereignisroute nicht wirklich durch Markieren der Ereignisdaten als behandelt beendet. Sie können nur den "Lenker-deventstoo"-Mechanismus im Code oder in einem verwenden <xref:System.Windows.EventSetter> :

- Anstatt eine sprachspezifische Ereignis Syntax zu verwenden, die für allgemeine CLR-Ereignisse funktioniert, müssen Sie die- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Methode verwenden, <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> um den Handler hinzuzufügen. Legen Sie den Wert von `handledEventsToo` auf `true` fest.

- <xref:System.Windows.EventSetter>Legen Sie in einem das- <xref:System.Windows.EventSetter.HandledEventsToo%2A> Attribut auf fest `true` .

Zusätzlich zu dem Verhalten, das der <xref:System.Windows.RoutedEventArgs.Handled%2A> Status in gerouteten Ereignissen erzeugt, wirkt sich das Konzept von darauf <xref:System.Windows.RoutedEventArgs.Handled%2A> aus, wie Sie Ihre Anwendung entwerfen und den Ereignishandlercode schreiben müssen. Sie können <xref:System.Windows.RoutedEventArgs.Handled%2A> als einfaches Protokoll verstanden werden, das von Routing Ereignissen verfügbar gemacht wird. Wie Sie dieses Protokoll verwenden, ist für Sie von Bedeutung, aber das konzeptionelle Design der Verwendungsweise des Werts von lautet <xref:System.Windows.RoutedEventArgs.Handled%2A> wie folgt:

- Wenn ein Routingereignis als behandelt markiert ist, muss es nicht von anderen Elementen auf dieser Route erneut verarbeitet werden.

- Wenn ein Routing Ereignis nicht als behandelt markiert ist, haben andere Listener, die sich weiter oben entlang der Route befanden, fest, dass ein Handler nicht registriert werden soll, oder die Handler, die registriert wurden, haben entschieden, die Ereignisdaten nicht zu bearbeiten und auf festzulegen <xref:System.Windows.RoutedEventArgs.Handled%2A> `true` . (Es ist natürlich auch möglich, dass der aktuelle Listener der erste Punkt in der Route ist.) Handler auf dem aktuellen Listener verfügen nun über drei mögliche Aktions Kurse:

  - Führen Sie keine Aktion durch; das Ereignis bleibt unbehandelt und wird an den nächsten Listener weitergeleitet.

  - Führen Sie Code als Reaktion auf das Ereignis aus, aber seien Sie sich im Klaren, dass die Aktion nicht umfangreich genug war, um ein Markieren des Ereignisses als „handled“ zu rechtfertigen. Das Ereignis wird an den nächsten Listener weitergeleitet.

  - Führen Sie Code als Reaktion auf das Ereignis aus. Markieren Sie das Ereignis in den an den Handler übergebenen Ereignisdaten als „handled“, weil die ausgeführte Aktion umfangreich genug war, um das Markieren als „handled“ zu rechtfertigen. Das Ereignis wird immer noch an den nächsten Listener weitergeleitet, aber mit <xref:System.Windows.RoutedEventArgs.Handled%2A> = `true` in den zugehörigen Ereignisdaten, sodass nur `handledEventsToo` die Listener weitere Handler aufrufen können.

Dieses konzeptionelle Design wird durch das zuvor erwähnte Routing Verhalten verstärkt: Es ist schwieriger (obwohl es im Code oder in Stilen immer noch möglich ist), Handler für Routing Ereignisse anzufügen, die aufgerufen werden, auch wenn ein vorheriger Handler entlang der Route bereits auf festgelegt wurde <xref:System.Windows.RoutedEventArgs.Handled%2A> `true` .

Weitere Informationen zur <xref:System.Windows.RoutedEventArgs.Handled%2A> Klassen Behandlung von Routing Ereignissen sowie Empfehlungen dazu, wann ein Routing Ereignis als markiert werden <xref:System.Windows.RoutedEventArgs.Handled%2A> kann, finden Sie unter Markieren von Routing [Ereignissen als behandelt und Klassen Behandlung](marking-routed-events-as-handled-and-class-handling.md).

In Anwendungen ist es üblich, lediglich ein Bubblingroutingereignis auf dem Objekt zu behandeln, das es ausgelöst hat, ohne die Routingmerkmale des Ereignisses zu berücksichtigen. Allerdings empfiehlt es sich immer noch, das Routingereignis in den Ereignisdaten als „handled“ zu markieren, um unvorhergesehene Nebeneffekte zu verhindern, nur für den Fall, dass ein Element, das sich weiter oben in der Elementstruktur befindet, auch einen angefügten Handler für das gleiche Routingereignis aufweist.

<a name="class_handlers"></a>

## <a name="class-handlers"></a>Klassenhandler

Wenn Sie eine Klasse definieren, die auf irgendeine Weise von abgeleitet ist <xref:System.Windows.DependencyObject> , können Sie auch einen Klassen Handler für ein Routing Ereignis definieren und anfügen, das ein deklarierter oder geerbte Ereignismember der Klasse ist. Klassenhandler werden vor Handler für Instanzlistener, die an eine Instanz dieser Klasse angefügt sind, aufgerufen, immer dann, wenn ein Routingevent eine Elementinstanz auf seiner Route erreicht.

Einige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente verfügen über inhärente Klassenbehandlung für bestimmte Routingereignisse. Dies kann nach außen den Anschein erwecken, als dass das Routingereignis nicht einmal ausgelöst wird, aber in Wirklichkeit wird es von einer Klasse behandelt, und das Routingereignis kann immer noch von Ihren Instanzhandlern behandelt werden, wenn Sie bestimmte Techniken verwenden. Außerdem machen viele Basisklassen und Steuerelemente virtuelle Methoden verfügbar, die zum Außerkraftsetzen von Klassenbehandlungsverhalten verwendet werden können. Weitere Informationen sowohl zum Umgehen unerwünschter Klassenbehandlung als auch zum Definieren Ihres eigenen Klassenverhaltens in einer benutzerdefinierten Klasse finden Sie unter [Markieren von Routingereignissen als behandelt und Klassenbehandlung](marking-routed-events-as-handled-and-class-handling.md).

<a name="attached_events"></a>

## <a name="attached-events-in-wpf"></a>Angefügte Ereignisse in WPF

Die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Sprache definiert auch eine besondere Art von Ereignissen, die als *angefügte Ereignisse* bezeichnet werden. Mit einem angefügten Ereignis können Sie einen Ereignishandler für ein bestimmtes Ereignis zu einem beliebigen Element hinzuzufügen. Das Element, das das Ereignis behandelt, muss das angefügte Ereignis weder definieren noch erben; zudem muss weder das Objekt, dass das Ereignis möglicherweise auslöst, noch die dafür zuständige Instanz dieses Ereignis als Klassenmember definieren oder „besitzen“.

Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eingabesystem verwendet angefügte Ereignisse in großem Umfang. Fast alle dieser angefügten Ereignisse werden jedoch über Basiselemente weitergeleitet. Die Eingabeereignisse erscheinen dann als äquivalente nicht angefügte Routingereignisse, die Member der Basiselementklasse sind. Beispielsweise kann das zugrunde liegende angefügte Ereignis leichter für <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> jede angegebene behandelt werden <xref:System.Windows.UIElement> , indem Sie <xref:System.Windows.UIElement.MouseDown> auf diesen anwenden, <xref:System.Windows.UIElement> anstatt mit der angefügten Ereignis Syntax entweder in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder Code umzugehen.

Weitere Informationen zu angefügten Ereignissen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Übersicht über angefügte Ereignisse](attached-events-overview.md).

<a name="Qualifying_Event_Names_in_XAML_for_Anticipated_Routing"></a>

## <a name="qualified-event-names-in-xaml"></a>Qualifizierte Ereignisnamen in XAML

Wenn Sie Handler für Routingereignisse anfügen, die von untergeordneten Elementen ausgelöst werden, ist dies so ähnlich wie der Gebrauch einer *typename*.*eventname* angefügten Ereignissyntax, obwohl es sich dabei genau genommen nicht um den Gebrauch eines angefügten Ereignisses handelt. Fügen Sie die Handler an ein gemeinsames übergeordnetes Element an, um von Ereignisrouting zu profitieren, auch wenn das gemeinsame übergeordnete Element möglicherweise das relevante Routingereignis nicht als Member enthält. Schauen Sie sich dieses Beispiel erneut an:

[!code-xaml[EventOvwSupport#GroupButton](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#groupbutton)]

Hier ist der übergeordnete Element Listener, dem der Handler hinzugefügt wird, ein <xref:System.Windows.Controls.StackPanel> . Sie fügt jedoch einen Handler für ein Routing Ereignis hinzu, das deklariert wurde und von der-Klasse ausgelöst wird <xref:System.Windows.Controls.Button> ( <xref:System.Windows.Controls.Primitives.ButtonBase> tatsächlich, aber <xref:System.Windows.Controls.Button> über Vererbung verfügbar). <xref:System.Windows.Controls.Button>"besitzt" das-Ereignis, aber das Routing Ereignis System lässt zu, dass Handler für alle Routing Ereignisse an einen beliebigen-oder-Instanzlistener angefügt werden, der <xref:System.Windows.UIElement> <xref:System.Windows.ContentElement> andernfalls Listener für ein Common Language Runtime Ereignis (CLR) anfügen kann. Der Standard-xmlns-Namespace für diese qualifizierten Attributnamen ist in der Regel der Standard-[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-xmlns-Namespace, aber Sie können auch Namespaces mit Präfix für benutzerdefinierte Routingereignisse angeben. Weitere Informationen zu xmlns finden Sie unter [XAML-Namespaces und Namespacezuordnung für WPF-XAML](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).

<a name="how_event_processing_works"></a>

## <a name="wpf-input-events"></a>Eingabeereignisse in WPF

Routingereignisse werden auf der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Plattform häufig für Eingabeereignisse verwendet. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erhalten Namen von Tunnelingroutingereignissen per Konvention das Wort „Preview“ (Vorschau) als Präfix. Eingabeereignisse treten oft paarweise auf – wobei das eine ein Bubblingereignis und das andere ein Tunnelingereignis ist. Beispielsweise haben das <xref:System.Windows.ContentElement.KeyDown> -Ereignis und das- <xref:System.Windows.ContentElement.PreviewKeyDown> Ereignis die gleiche Signatur, wobei das erste-Ereignis das bubblingangabeereignis und letzteres das tunnelingeingabeereignis ist. Manchmal haben Eingabeereignisse nur eine Bubblingversion oder nur eine direkte Routingversion. In der Dokumentation verweisen die Themen zu Routingereignissen auf ähnliche Routingereignisse mit alternativen Routingstrategien, falls derartige Routingereignisse vorhanden sind; Abschnitte auf den Seiten zu verwalteten Referenzen erläutern die Routingstrategien jedes Routingelements.

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eingabeereignisse, die paarweise auftreten, werden implementiert, damit eine einzelne Benutzereingabeaktion, wie z.B. das Drücken einer Maustaste, beide Routingereignisse des Paars in der Sequenz auslöst. Zunächst wird das Tunnelingereignis ausgelöst und durchläuft seine Route. Anschließend wird das Bubblingereignis ausgelöst und durchläuft seine Route. Die beiden Ereignisse verwenden buchstäblich dieselbe Ereignisdaten Instanz, da der <xref:System.Windows.UIElement.RaiseEvent%2A> Methodenaufrufe in der implementierenden Klasse, die das Bubblingereignis auslöst, auf die Ereignisdaten aus dem tunnelingereignis lauscht und im neuen ausgelösten Ereignis wieder verwendet wird. Listener mit Handlern für das Tunnelingereignis haben als Erstes die Möglichkeit, das Routingereignis als „handled“ zu markieren (zuerst Klassenhandler, anschließend Instanzhandler). Wenn ein Element entlang der Tunnelingroute das Routingereignis als „handled“ markiert, werden die bereits behandelten Daten des Bubblingereignisses gesendet, und typische angefügte Handler für das entsprechende Bubblingeingabeereignis werden nicht aufgerufen. Nach außen wirkt dies so, als sei das behandelte Bubblingereignis nicht einmal ausgelöst worden. Dieses Behandlungsverhalten ist beim Zusammensetzen von Steuerelementen nützlich; hier möchten Sie möglicherweise, dass alle treffertestbasierten oder fokusbasierten Eingabeereignisse von Ihrem endgültigen Steuerelement gemeldet werden, und nicht von dessen einzelnen Komponenten. Das endgültige Steuerelement ist in der Zusammensetzung näher am Stamm, weshalb es das Tunnelingereignis zunächst in einer Klasse behandeln und eventuell sogar dieses Routingereignis durch ein steuerelementspezifischeres Ereignis „ersetzen“ kann – als Teil des Codes, der die Steuerelementklasse unterstützt.

Das folgende Beispiel für ein Eingabeereignis veranschaulicht das Verarbeiten von Eingabeereignissen. In der folgenden Struktur Abbildung `leaf element #2` ist die Quelle sowohl eines-als `PreviewMouseDown` auch eines- `MouseDown` Ereignisses:

![Ereignisrouting-Diagramm](./media/routed-events-overview/input-event-routing.png)

Ein Ereignis wird in folgender Reihenfolge verarbeitet:

1. `PreviewMouseDown` (Tunnel) auf dem Stammelement (root element)

2. `PreviewMouseDown` (Tunnel) auf dem ersten Zwischenelement (intermediate element #1)

3. `PreviewMouseDown` (Tunnel) auf dem zweiten Zwischenelement (intermediate element #2)

4. `MouseDown` (Bubble) auf dem zweiten Quellelement (source element #2)

5. `MouseDown` (Bubble) auf dem ersten Zwischenelement (intermediate element #1)

6. `MouseDown` (Bubble) auf dem Stammelement (root element)

Ein Delegat eines Routingereignishandlers enthält Verweise auf zwei Objekte: auf das Objekt, das das Ereignis ausgelöst hat und das Objekt, auf dem der Handler aufgerufen wurde. Das Objekt, auf dem der Handler aufgerufen wurde, ist das Objekt, das vom `sender`-Parameter gemeldet wurde. Das Objekt, in dem das Ereignis zuerst ausgelöst wurde, wird von der- <xref:System.Windows.RoutedEventArgs.Source%2A> Eigenschaft in den Ereignisdaten gemeldet. Ein Routing Ereignis kann immer noch vom gleichen-Objekt ausgelöst und behandelt werden. in diesem `sender` Fall <xref:System.Windows.RoutedEventArgs.Source%2A> sind und identisch (Dies ist der Fall mit den Schritten 3 und 4 in der Beispielliste für die Ereignisverarbeitung).

Aufgrund von Tunnelung und bubblinden empfangen übergeordnete Elemente Eingabeereignisse, bei denen das <xref:System.Windows.RoutedEventArgs.Source%2A> eines ihrer untergeordneten Elemente ist. Wenn Sie wissen möchten, was das Quell Element ist, können Sie das Quell Element identifizieren, indem Sie auf die- <xref:System.Windows.RoutedEventArgs.Source%2A> Eigenschaft zugreifen.

Wenn das Eingabe Ereignis markiert ist, werden in der Regel <xref:System.Windows.RoutedEventArgs.Handled%2A> keine weiteren Handler aufgerufen. In der Regel sollten Sie Eingabeereignisse als „handled“ markieren, sobald ein Handler aufgerufen wird, der Ihre anwendungsspezifische logische Behandlung der Bedeutung des Eingabeereignisses angeht.

Die Ausnahme von dieser allgemeinen Anweisung über den <xref:System.Windows.RoutedEventArgs.Handled%2A> Status besteht darin, dass Eingabe Ereignishandler, die für die absichtliche Ignorierung <xref:System.Windows.RoutedEventArgs.Handled%2A> des Zustands der Ereignisdaten registriert sind, weiterhin auf einer der beiden Routen aufgerufen werden. Weitere Informationen finden Sie unter [Vorschauereignisse](preview-events.md) oder [Markieren von Routingereignissen als behandelt und Klassenbehandlung](marking-routed-events-as-handled-and-class-handling.md).

Das freigegebene Ereignisdatenmodell von Tunneling- und Bubblingereignissen und das sequenzielle Auslösen zunächst der Tunneling-und dann der Bubblingereignisse ist kein allgemein gültiges Konzept für alle Routingereignisse. Dieses Verhalten wird insbesondere davon implementiert, wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eingabegeräte Eingabeereignispaare auslösen und verbinden. Das Implementieren Ihres eigenen Eingabeereignisses ist ein erweitertes Szenario; möglicherweise entscheiden Sie sich aber dazu, dieses Modell auch für Ihre eigenen Eingabeereignisse zu nutzen.

Gewisse Klassen behandeln gewisse Eingabeereignisse in einer Klasse, meist mit dem Ziel, die Bedeutung eines bestimmten benutzergesteuerten Eingabeereignisses innerhalb dieses Steuerelements neu zu definieren und ein neues Ereignis auszulösen. Weitere Informationen finden Sie unter [Markieren von Routingereignissen als behandelt und Klassenbehandlung](marking-routed-events-as-handled-and-class-handling.md).

Weitere Informationen zur Eingabe und zur Interaktion zwischen Eingabe und Ereignissen in normalen Anwendungsszenarien finden Sie unter [Übersicht über die Eingabe](input-overview.md).

<a name="events_styles"></a>

## <a name="eventsetters-and-eventtriggers"></a>EventSetters und EventTriggers

In Stilen können Sie eine vordeklarierte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Ereignis Behandlungs Syntax in das Markup einschließen, indem Sie einen verwenden <xref:System.Windows.EventSetter> . Wenn das Format angewendet wird, wird der verwiesene Handler zur formatierten Instanz hinzugefügt. Sie können <xref:System.Windows.EventSetter> nur für ein Routing Ereignis deklarieren. Im Folgenden finden Sie ein Beispiel. Beachten Sie, dass die `b1SetColor`-Methode, auf die hier verwiesen wird, sich in einer CodeBehind-Datei befindet.

[!code-xaml[EventOvwSupport#XAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/page2.xaml#xaml2)]

Der Vorteil besteht darin, dass der Stil wahrscheinlich viele andere Informationen enthält, die auf jede Schaltfläche in der Anwendung angewendet werden können, und dass der <xref:System.Windows.EventSetter> Teil dieses Stils die Wiederverwendung von Code sogar auf Markup Ebene fördert. Außerdem <xref:System.Windows.EventSetter> abstrahiert der Methodenname für Handler einen Schritt weiter Weg von der allgemeinen Anwendung und dem Seiten Markup.

Eine weitere spezielle Syntax, die das Routing Ereignis und die Animations Funktionen von kombiniert, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist ein <xref:System.Windows.EventTrigger> . Wie bei <xref:System.Windows.EventSetter> können nur Routing Ereignisse für einen verwendet werden <xref:System.Windows.EventTrigger> . In der Regel <xref:System.Windows.EventTrigger> wird ein als Teil eines Stils deklariert, aber ein <xref:System.Windows.EventTrigger> kann auch für Elemente auf Seitenebene als Teil der Auflistung <xref:System.Windows.FrameworkElement.Triggers%2A> oder in einem deklariert werden <xref:System.Windows.Controls.ControlTemplate> . <xref:System.Windows.EventTrigger>Mit können Sie eine angeben <xref:System.Windows.Media.Animation.Storyboard> , die immer dann ausgeführt wird, wenn ein Routing Ereignis ein Element in der Route erreicht, das einen <xref:System.Windows.EventTrigger> für dieses Ereignis deklariert. Der Vorteil eines <xref:System.Windows.EventTrigger> , wenn nur das Ereignis verarbeitet und damit ein vorhandenes Storyboard gestartet wird, besteht darin, dass eine <xref:System.Windows.EventTrigger> bessere Kontrolle über das Storyboard und dessen Laufzeitverhalten bietet. Weitere Informationen finden Sie unter [Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start](../graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).

<a name="more_about"></a>

## <a name="more-about-routed-events"></a>Weitere Informationen zu Routingereignissen

In diesem Thema werden hauptsächlich die grundlegenden Konzepte von Routingereignissen erläutert; zudem bietet er Ihnen eine Orientierung, wann Sie auf Routingereignisse reagieren sollten, die bereits in den verschieden Basiselementen und -steuerelementen vorhanden sind. Allerdings können Sie eigene Routingereignis für Ihre benutzerdefinierte Klasse mit den notwendigen Hilfsmitteln, wie z. B. spezialisierte Ereignisdatenklassen und Delegaten, erstellen. Der Besitzer des Routing Ereignisses kann eine beliebige Klasse sein, aber Routing Ereignisse müssen von abgeleitet und von <xref:System.Windows.UIElement> oder <xref:System.Windows.ContentElement> abgeleiteten Klassen behandelt werden, um nützlich zu sein. Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Erstellen eines benutzerdefinierten Routingereignisses](how-to-create-a-custom-routed-event.md).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.EventManager>
- <xref:System.Windows.RoutedEvent>
- <xref:System.Windows.RoutedEventArgs>
- [Markieren von Routingereignissen als behandelt und Klassenbehandlung](marking-routed-events-as-handled-and-class-handling.md)
- [Übersicht über die Eingabe](input-overview.md)
- [Befehlsübersicht](commanding-overview.md)
- [Benutzerdefinierte Abhängigkeits Eigenschaften](custom-dependency-properties.md)
- [Strukturen in WPF](trees-in-wpf.md)
- [Schwache Ereignismuster](weak-event-patterns.md)
