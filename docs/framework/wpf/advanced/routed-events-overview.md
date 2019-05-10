---
title: Übersicht über Routingereignisse
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
ms.openlocfilehash: 7712ed02d20d692842267464a645bfc93ca8fd73
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063895"
---
# <a name="routed-events-overview"></a>Übersicht über Routingereignisse
Dieses Thema beschreibt das Konzept von Routingereignissen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Das Thema definiert die Terminologie von Routingereignissen, beschreibt, wie Routingereignisse anhand einer Struktur von Elementen weitergeleitet werden und führt Sie in das Erstellen Ihrer eigenen, benutzerdefinierten Routingereignisse ein.
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Vorraussetzungen  
 In diesem Thema wird davon ausgegangen, dass Sie über grundlegende Kenntnisse zu [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] und objektorientiertem Programmieren sowie zur Konzeptualisierung der Beziehungen zwischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Elementen als Struktur verfügen. Um den Beispielen in diesem Thema zu folgen, sollten Sie zudem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] verstehen und wissen, wie sehr einfache [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen oder -Seiten geschrieben werden. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md) und [XAML Overview (WPF)](xaml-overview-wpf.md).  
  
<a name="routing"></a>   
## <a name="what-is-a-routed-event"></a>Was ist ein Routingereignis?  
 Stellen Sie sich Routingereignisse entweder aus Sicht der Funktion oder der Implementierung vor. Beide Definitionen werden hier vorgestellt, da Benutzer die Definitionen unterschiedlich hilfreich finden.  
  
 Funktionale Definition: Ein Routingereignis ist ein Ereignistyp, der Handler kann auf mehreren Listenern in einer Elementstruktur und nicht nur auf das Objekt, das das Ereignis ausgelöst hat.  
  
 Implementierungsdefinition: Ein Routingereignis ist ein [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] -Ereignis, das von einer Instanz von gesichert wird die <xref:System.Windows.RoutedEvent> Klasse und wird verarbeitet, indem die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Ereignissystem.  
  
 Eine typische [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung enthält viele Elemente. Egal ob im Code erstellt oder in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] deklariert, stehen diese Elemente in einer Beziehung einer Elementstruktur zueinander. Die Ereignisroute kann sich abhängig von der Ereignisdefinition in eine von zwei Richtungen bewegen; im Allgemeinen bewegt sie sich vom Quellelement aus und „steigt“ in der Elementstruktur auf, bis sie den Stamm der Elementstruktur erreicht (normalerweise eine Seite oder ein Fenster). Dieses Bubblingkonzept kommt Ihnen möglicherweise bekannt vor, wenn Sie schon einmal mit dem DHTML-Objektmodell gearbeitet haben.  
  
 Betrachten Sie die folgende einfache Elementstruktur:  
  
 [!code-xaml[EventOvwSupport#GroupButton](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#groupbutton)]  
  
 Diese Elementstruktur erzeugt in etwa Folgendes:  
  
 ![Die Schaltflächen „Ja“, „Nein“ und „Abbrechen“](./media/routedevent-ovw-1.gif "RoutedEvent_ovw_1")  
  
 In dieser vereinfachten Elementstruktur ist die Quelle des eine <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis ist eines von der <xref:System.Windows.Controls.Button> Elemente, und der <xref:System.Windows.Controls.Button> geklickt wurde ist das erste Element, das die Möglichkeit zum Behandeln des Ereignisses hat. Aber wenn keine Ereignishandler angefügt der <xref:System.Windows.Controls.Button> fungiert für das Ereignis, und klicken Sie dann nach oben an das Ereignis übergeben werden die <xref:System.Windows.Controls.Button> übergeordnete Element in der Elementstruktur, handelt es sich die <xref:System.Windows.Controls.StackPanel>. Potenziell das Ereignis wird weitergeleitet, <xref:System.Windows.Controls.Border>, und dann bis zum Seitenstamm der Elementstruktur (nicht dargestellt).  
  
 Das heißt, die Ereignisroute für dieses <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis ist:  
  
 Button-->StackPanel-->Border-->...  
  
### <a name="top-level-scenarios-for-routed-events"></a>Szenarios auf oberster Ebene für Routingereignisse  
 Im folgenden wird eine kurze Zusammenfassung der Szenarios dargestellt, die das Konzept der Routingereignisse motiviert haben; außerdem wird erläutert, warum ein herkömmliches [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Ereignis für die folgenden Szenarios nicht ausreichend ist:  
  
 **Zusammensetzung und Kapselung:** Verschiedene Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügen über ein umfangreiches Inhaltsmodell. Sie können z. B. ein Bild innerhalb des Platzieren einer <xref:System.Windows.Controls.Button>, effektiv die visuelle Struktur der Schaltfläche Erweitert. Das hinzugefügte Bild muss jedoch nicht unterbrechen die Treffertest-Verhalten, das bewirkt, eine Schaltfläche dass, um auf Antworten einer <xref:System.Windows.Controls.Primitives.ButtonBase.Click> seines Inhalts, selbst wenn der Benutzer auf Pixel klickt, die technisch Teil des Bilds sind.  
  
 **Einzelne Anfügepunkte für Handleranfügepunkte:** In [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], Sie müssten den gleichen Handler mehrmals zur Verarbeitung der Ereignisse anfügen, die aus mehreren Elementen ausgelöst werden können. Routingereignisse ermöglichen es Ihnen, diesen Handler nur einmal anzufügen, wie im vorherigen Beispiel gezeigt wurde, und verwenden Handlerlogik, um ggf. zu bestimmen, woher das Ereignis stammt. Dies kann z.B. der Handler für die zuvor gezeigte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sein:  
  
 [!code-csharp[EventOvwSupport#GroupButtonCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#groupbuttoncodebehind)]
 [!code-vb[EventOvwSupport#GroupButtonCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#groupbuttoncodebehind)]  
  
 **Klassenbehandlung:** Routingereignisse lassen einen statischen Handler, die von der Klasse definiert ist. Dieser Klassenhandler hat die Möglichkeit, ein Ereignis vor angefügten Instanzhandlern zu behandeln.  
  
 **Verweisen auf ein Ereignis ohne Reflektion:** Bestimmte Code und markuptechniken erfordern eine Möglichkeit, ein bestimmtes Ereignis zu identifizieren. Ein Routingereignis erstellt ein <xref:System.Windows.RoutedEvent> -Feld als Bezeichner, der eine stabile ereignisidentifikationstechnik bietet, die keine statischen oder Laufzeit Reflektion erforderlich ist.  
  
### <a name="how-routed-events-are-implemented"></a>So werden Routingereignis implementiert  
 Ein Routingereignis ist ein [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] -Ereignis, das von einer Instanz von gestützt wird der <xref:System.Windows.RoutedEvent> Klasse und registriert die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ereignissystem. Die <xref:System.Windows.RoutedEvent> Instanz abgerufen, die von der Registrierung bleibt in der Regel als eine `public` `static` `readonly` Feldmember der Klasse, die registriert und somit "besitzt" das Routingereignis. Die Verbindung mit dem identisch benannten [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Ereignis (das manchmal auch als „Wrapper“-Ereignis bezeichnet wird) erfolgt durch das Außerkraftsetzen der `add`- und `remove`-Implementierungen für das [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Ereignis. Normalerweise bleiben `add` und `remove` als impliziter Standard bestehen, der die entsprechende sprachspezifische Ereignissyntax zum Hinzufügen und Entfernen von Handlern dieses Ereignisses verwendet. Das Routingereignis unterstützungs- und Verbindungsmechanismus ähnelt im Prinzip wie eine Abhängigkeitseigenschaft ist eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] -Eigenschaft, die von unterstützt wird die <xref:System.Windows.DependencyProperty> Klasse und registriert die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaftensystem.  
  
 Das folgende Beispiel zeigt die Deklaration für eine benutzerdefinierte `Tap` Routingereignis, einschließlich der Registrierung und der Offenlegung von der <xref:System.Windows.RoutedEvent> Feld "ID" und die `add` und `remove` Implementierungen für die `Tap` [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Ereignis.  
  
 [!code-csharp[RoutedEventCustom#AddRemoveHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#addremovehandler)]
 [!code-vb[RoutedEventCustom#AddRemoveHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#addremovehandler)]  
  
### <a name="routed-event-handlers-and-xaml"></a>Routingereignishandler und XAML  
 Um einen Handler für ein Ereignis mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hinzuzufügen, deklarieren Sie den Ereignisnamen als Attribut auf dem Element, das ein Ereignislistener ist. Der Wert des Attributs ist der Name Ihrer implementierten Handlermethode, die in der partiellen Klasse der CodeBehind-Datei vorhanden sein muss.  
  
 [!code-xaml[EventOvwSupport#SimplestSyntax](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#simplestsyntax)]  
  
 Die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Syntax zum Hinzufügen von Standard-[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Ereignishandlern ist die gleiche wie für das Hinzufügen von Routingereignishandlern, da Sie genauso Handler in den [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Ereigniswrapper einfügen, dem eine Routingereignisimplementierung zu Grunde liegt . Weitere Informationen zum Hinzufügen von Ereignishandlern in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] finden Sie unter [Übersicht über XAML (WPF)](xaml-overview-wpf.md).  
  
<a name="routing_strategies"></a>   
## <a name="routing-strategies"></a>Routingstrategien  
 Routingereignisse verwenden eine von drei Routingstrategien:  
  
- **Bubbling:** Die Ereignisquelle Ereignishandler werden aufgerufen. Das Routingereignis wird dann auf nachfolgenden übergeordnete Elemente weitergeleitet, bis es den Stamm der Elementstruktur erreicht. Die meisten Routingereignisse verwenden die Bubblingroutingstrategie. Bubblingroutingereignisse werden üblicherweise verwendet, um Eingabe- oder Zustandänderungen von unterschiedlichen Steuerelemente oder andere Elementen der Benutzeroberfläche zu melden.  
  
- **Direkt:** Nur das Quellelement selbst erhält die Gelegenheit, Reaktion Handler aufrufen. Dies entspricht dem „Routing“, das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] für Ereignisse verwendet. Anders als bei einer Standard [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] -Ereignis unterstützen direkte Routingereignisse Klassenbehandlung (die Klassenbehandlung wird in einem späteren Abschnitt erläutert) und kann verwendet werden, indem <xref:System.Windows.EventSetter> und <xref:System.Windows.EventTrigger>.  
  
- **Tunneling:** Zunächst werden Ereignishandler am Stamm Elementstruktur aufgerufen. Das Routingereignis bewegt sich dann über eine Route durch die nachfolgenden untergeordneten Elemente in Richtung des Knotenelements, das die Quelle des Routingereignisses ist (das Element, das das Routingereignis ausgelöst). Tunnelingroutingereignisse werden oft als Teil der Zusammensetzung eines Steuerelements verwendet oder behandelt, sodass Elemente der einzelnen Teile von Ereignissen, die für das vollständige Steuerelement spezifisch sind, bewusst unterdrückt oder ersetzt werden können. Eingabeereignisse aus [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sind oft als Tunneling/Bubbling-Paar implementiert. Tunnelingereignisse werden manchmal auch als Vorschauereignisse bezeichnet; dies liegt an einer Benennungskonvention für Paare.  
  
<a name="why_use"></a>   
## <a name="why-use-routed-events"></a>Was ist der Vorteil von Routingereignissen?  
 Als Anwendungsentwickler müssen Sie nicht immer wissen oder sicherstellen, dass das Ereignis, das Sie behandeln, als Routingereignis implementiert wird. Weitergeleitete Ereignisse weisen ein besonderes Verhalten auf, aber dieses Verhalten ist weitestgehend unsichtbar, wenn Sie ein Ereignisses auf dem Element behandeln, in dem es ausgelöst wurde.  
  
 Routingereignisse erweisen sich besonders dort als sehr nützlich, wo Sie eines der folgenden Szenarios verwenden: beim Definieren von gängigen Handlern am gängigen Stamm, beim Zusammensetzen eines eigenen Steuerelements oder beim Definieren Ihrer eigenen, benutzerdefinierten Steuerelementklasse.  
  
 Routingereignislistener und Routingereignisquellen müssen kein gemeinsames Ereignis in ihrer Hierarchie aufweisen. Alle <xref:System.Windows.UIElement> oder <xref:System.Windows.ContentElement> kann ein Ereignislistener für jedes beliebige Routingereignis sein. Daher können Sie den kompletten Satz an Routingereignissen, die durch die Arbeits-[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] zur Verfügung stehen, als konzeptionelle „Schnittstelle“ verwenden, über die unterschiedliche Elemente in der Anwendung Ereignisinformationen austauschen können. Dieses „Schnittstellen“-Konzept für Routingereignisse kann besonders auf Eingabeereignisse angewendet werden.  
  
 Routingereignisse können auch für die Kommunikation durch die Elementstruktur verwendet werden, da die Ereignisdaten für jedes Element auf der Route aufrechterhalten werden. Ein Element könnte die Ereignisdaten ändern, und diese Änderung wäre für das nächste Element auf der Route verfügbar.  
  
 Neben dem Routingaspekt gibt es zwei andere Gründe, aus denen ein beliebiges [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignis möglicherweise als Routingereignis statt als [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Standardereignis implementiert wird. Wenn Sie Ihr eigenes Ereignis implementieren, können Sie auch folgende Prinzipien berücksichtigen:  
  
- Bestimmte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Stile und Vorlagen Features wie z. B. <xref:System.Windows.EventSetter> und <xref:System.Windows.EventTrigger> erfordern das verwiesene Ereignis ein Routingereignis ist. Dies ist das Szenario mit einem Ereignisbezeichner, das weiter oben erwähnt wurde.  
  
- Routingereignisse unterstützen einen Mechanismus zur Klassenbehandlung, durch den die Klasse statische Methoden angeben kann, die die Möglichkeit haben, Routingereignisse zu behandeln, bevor registrierte Instanzenhandler darauf zugreifen können. Dies ist beim Entwerfen von Steuerelementen hilfreich, da Ihre Klasse ereignisgesteuertes Klassenverhalten erzwingen kann, das nicht versehentlich durch das Behandeln eines Ereignisses auf einer Instanz unterdrückt werden kann.  
  
 Jeder der oben genannten Aspekte wird in einem separaten Abschnitt dieses Themas erläutert.  
  
<a name="event_handing"></a>   
## <a name="adding-and-implementing-an-event-handler-for-a-routed-event"></a>Hinzufügen und implementieren eines Ereignishandlers für ein Routingereignis  
 Zum Hinzufügen eines Ereignishandlers in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] müssen Sie einfach nur den Ereignisnamen als Attribut in ein Element einfügen und den Attributwert auf den Namen des Ereignishandlers festlegen, der einen angemessenen Delegaten implementiert, wie in folgendem Beispiel veranschaulicht.  
  
 [!code-xaml[EventOvwSupport#SimplestSyntax](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#simplestsyntax)]  
  
 `b1SetColor` Der Name des implementierten Handlers, der Code enthält, die behandelt, die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis. `b1SetColor` müssen die gleiche Signatur wie der <xref:System.Windows.RoutedEventHandler> -Delegaten, der den Ereignishandlerdelegaten ist für die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis. Der erste Parameter aller Delegaten von Routingereignishandlern gibt das Element an, dem der Ereignishandler hinzugefügt wird, und der zweite Parameter gibt die Daten des Ereignisses an.  
  
[!code-csharp[EventOvwSupport#SimpleHandlerA](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#simplehandlera)]
[!code-vb[EventOvwSupport#SimpleHandlerA](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#simplehandlera)]  
  
 <xref:System.Windows.RoutedEventHandler> ist die grundlegende Delegat für Routingereignishandler. Für Routingereignisse, die auf bestimmte Steuerelemente oder Szenarien ausgelegt sind, können die für die Routingereignishandler zu verwendenden Delegaten möglicherweise so spezialisiert werden, dass sie spezialisierte Ereignisdaten übertragen können. Z. B. in einem gängigen Eingabeszenario Sie möglicherweise behandeln eine <xref:System.Windows.UIElement.DragEnter> Routingereignis. Der Handler implementieren sollte die <xref:System.Windows.DragEventHandler> delegieren. Mithilfe des spezifischsten Delegaten können Sie verarbeiten die <xref:System.Windows.DragEventArgs> im Handler und lesen die <xref:System.Windows.DragEventArgs.Data%2A> Eigenschaft, die die zwischenablagenutzlast des Ziehvorgangs enthält.  
  
 Ein vollständiges Beispiel zum Hinzufügen eines Ereignishandlers in ein Element mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] finden Sie unter [Behandeln eines Routingereignisses](how-to-handle-a-routed-event.md).  
  
 Das Hinzufügen eines Handlers für ein Routingereignis in einer Anwendung, die im Code erstellt wird, ist einfach. Routingereignishandler können immer hinzugefügt werden, über eine Hilfsmethode <xref:System.Windows.UIElement.AddHandler%2A> (Dies ist dieselbe Methode, die die vorhandene Unterstützung für ruft `add`.) Allerdings haben vorhandene [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Routingereignisse für gewöhnlich Unterstützungsimplementierungen mit `add`- und `remove`-Logik, die es ermöglichen, dass die Handler für die Routingereignisse von einer sprachspezifischen Ereignissyntax hinzugefügt werden können; diese Syntax ist viel intuitiver als die Hilfsmethode. Im Folgenden wird die Hilfsmethode in einem Beispiel verwendet:  
  
 [!code-csharp[EventOvwSupport#AddHandlerCode](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#addhandlercode)]
 [!code-vb[EventOvwSupport#AddHandlerCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#addhandlercode)]  
  
 Das folgende Beispiel zeigt die C# -Operatorsyntax (Visual Basic hat geringfügig andere Operatorsyntax aufgrund seiner Behandlung von Dereferenzierung):  
  
 [!code-csharp[EventOvwSupport#AddHandlerPlusEquals](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#addhandlerplusequals)]
 [!code-vb[EventOvwSupport#AddHandlerPlusEquals](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#addhandlerplusequals)]  
  
 Ein Beispiel für das Hinzufügen eines Ereignishandlers in Code finden Sie unter [Hinzufügen eines Ereignishandlers mithilfe von Code](how-to-add-an-event-handler-using-code.md).  
  
 Wenn Sie Visual Basic verwenden, können Sie auch die `Handles` Schlüsselwort, um Handler als Teil der Handlerdeklarationen hinzufügen. Weitere Informationen finden Sie unter [Visual Basic- und WPF-Ereignisbehandlung](visual-basic-and-wpf-event-handling.md).  
  
<a name="concept_handled"></a>   
### <a name="the-concept-of-handled"></a>Das Handled-Konzept  
 Alle Routingereignisse verwenden eine gemeinsame Ereignisdaten-Basisklasse, <xref:System.Windows.RoutedEventArgs>. <xref:System.Windows.RoutedEventArgs> definiert die <xref:System.Windows.RoutedEventArgs.Handled%2A> -Eigenschaft, die einen booleschen Wert akzeptiert. Der Zweck der <xref:System.Windows.RoutedEventArgs.Handled%2A> Eigenschaft ist die Aktivierung von allen Ereignishandler entlang der Route, die das Routingereignis als markieren *behandelt*, durch Festlegen des Werts der <xref:System.Windows.RoutedEventArgs.Handled%2A> zu `true`. Nachdem die freigegebenen Ereignisdaten vom Handler an einem Element auf der Route verarbeitet wurden, werden die Daten wieder jedem Listener auf der Route gemeldet.  
  
 Der Wert des <xref:System.Windows.RoutedEventArgs.Handled%2A> wirkt sich auf wie ein Ereignis gemeldet oder verarbeitet werden, bei der Übertragung weiter entlang der Route. Wenn <xref:System.Windows.RoutedEventArgs.Handled%2A> ist `true` im Ereignis für ein Routingereignis, Ereignishandler, die für das Routingereignis auf anderen Elementen Lauschen sind in der Regel nicht mehr aufgerufen für diese bestimmte Ereignisinstanz. Dies gilt sowohl für in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] angefügte Handler als auch für Handler, die von anderen sprachspezifischen Anfügesyntaxen für Ereignishandlern, wie z.B. `+=` oder `Handles`, hinzugefügt wurden. Für die meisten gängigen handlerszenarios, markieren Sie ein Ereignis als behandelt, indem <xref:System.Windows.RoutedEventArgs.Handled%2A> zu `true` wird "stop" routing für entweder eine Tunneling- oder bubbling-Route sowie für alle Ereignisse, die zu einem Zeitpunkt in der Route, die von einem Klassenhandler behandelt wird.  
  
 Es ist jedoch bei dem Listener weiterhin Handler als Reaktion auf Routingereignisse ausgeführt können Mechanismus "HandledEventsToo", in denen <xref:System.Windows.RoutedEventArgs.Handled%2A> ist `true` in den Ereignisdaten. Das heißt, ist die Ereignisroute nicht wirklich durch Markieren der Ereignisdaten als behandelt beendet. Sie können den HandledEventsToo-Mechanismus nur verwenden, im Code oder in einem <xref:System.Windows.EventSetter>:  
  
- Im Code anstelle einer sprachspezifischen Ereignissyntax, das funktioniert für allgemeine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Aufrufen von Ereignissen, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Methode <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> um Ihren Handler hinzuzufügen. Legen Sie den Wert von `handledEventsToo` auf `true` fest.  
  
- In einer <xref:System.Windows.EventSetter>legen die <xref:System.Windows.EventSetter.HandledEventsToo%2A> Attribut `true`.  
  
 Zusätzlich zu dem Verhalten, <xref:System.Windows.RoutedEventArgs.Handled%2A> Zustand erzeugt in Routingereignisse das Konzept der <xref:System.Windows.RoutedEventArgs.Handled%2A> hat Auswirkungen, wie Sie Ihre Anwendung entwerfen und den Ereignishandlercode schreiben sollten. Sie können konzipieren <xref:System.Windows.RoutedEventArgs.Handled%2A> als ein einfaches Protokoll, das von Routingereignissen verfügbar gemacht wird. Wie Sie dieses Protokoll genau verwenden liegt bei Sie, aber der konzeptuelle Entwurf, wie der Wert des <xref:System.Windows.RoutedEventArgs.Handled%2A> soll verwendet werden, lautet wie folgt:  
  
- Wenn ein Routingereignis als behandelt markiert ist, muss es nicht von anderen Elementen auf dieser Route erneut verarbeitet werden.  
  
- Wenn ein Routingereignis nicht als behandelt markiert ist, haben andere Listener, die zuvor entlang der Route ausgewählt, entweder nicht registriert einen Handler, oder der Handler, die registrierten ausgewählt haben, nicht zum Bearbeiten von Daten für das Ereignis aus, und legen Sie <xref:System.Windows.RoutedEventArgs.Handled%2A> zu `true`. (Es ist selbstverständlich auch möglich, dass der aktuelle Listener der erste Punkt auf der Route ist.) Handler auf dem aktuellen Listener verfügen jetzt über drei mögliche Vorgehensweisen:  
  
    - Führen Sie keine Aktion durch; das Ereignis bleibt unbehandelt und wird an den nächsten Listener weitergeleitet.  
  
    - Führen Sie Code als Reaktion auf das Ereignis aus, aber seien Sie sich im Klaren, dass die Aktion nicht umfangreich genug war, um ein Markieren des Ereignisses als „handled“ zu rechtfertigen. Das Ereignis wird an den nächsten Listener weitergeleitet.  
  
    - Führen Sie Code als Reaktion auf das Ereignis aus. Markieren Sie das Ereignis in den an den Handler übergebenen Ereignisdaten als „handled“, weil die ausgeführte Aktion umfangreich genug war, um das Markieren als „handled“ zu rechtfertigen. Das Ereignis weiterhin weitergeleitet werden können, an den nächsten Listener, jedoch mit <xref:System.Windows.RoutedEventArgs.Handled%2A> = `true` in seinen Ereignisdaten, sodass nur `handledEventsToo` Listener haben die Möglichkeit, weitere Handler aufzurufen.  
  
 Dieser konzeptuelle Entwurf wird durch die oben genannten Routingverhalten bestätigt: Es ist schwieriger (aber immer noch in Code und Formaten möglich), um Handler für Routingereignisse anzufügen, die aufgerufen werden, auch wenn ein vorheriger Handler entlang der Route bereitseingerichtethat<xref:System.Windows.RoutedEventArgs.Handled%2A>zu `true`.  
  
 Weitere Informationen zu <xref:System.Windows.RoutedEventArgs.Handled%2A>Klassenbehandlung von Routingereignissen und Empfehlungen, wenn es sich um ein Routingereignis als markieren geeignete <xref:System.Windows.RoutedEventArgs.Handled%2A>, finden Sie unter [Markieren von Routingereignissen als behandelt und Klassenbehandlung](marking-routed-events-as-handled-and-class-handling.md).  
  
 In Anwendungen ist es üblich, lediglich ein Bubblingroutingereignis auf dem Objekt zu behandeln, das es ausgelöst hat, ohne die Routingmerkmale des Ereignisses zu berücksichtigen. Allerdings empfiehlt es sich immer noch, das Routingereignis in den Ereignisdaten als „handled“ zu markieren, um unvorhergesehene Nebeneffekte zu verhindern, nur für den Fall, dass ein Element, das sich weiter oben in der Elementstruktur befindet, auch einen angefügten Handler für das gleiche Routingereignis aufweist.  
  
<a name="class_handlers"></a>   
## <a name="class-handlers"></a>Klassenhandler  
 Wenn Sie eine abgeleitete Klasse definieren, in irgendeiner Art von <xref:System.Windows.DependencyObject>, Sie können auch definieren, und fügen Sie einen Klassenhandler für ein Routingereignis, das ein deklarierter oder geerbter Ereignismember Ihrer Klasse ist. Klassenhandler werden vor Handler für Instanzlistener, die an eine Instanz dieser Klasse angefügt sind, aufgerufen, immer dann, wenn ein Routingevent eine Elementinstanz auf seiner Route erreicht.  
  
 Einige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente verfügen über inhärente Klassenbehandlung für bestimmte Routingereignisse. Dies kann nach außen den Anschein erwecken, als dass das Routingereignis nicht einmal ausgelöst wird, aber in Wirklichkeit wird es von einer Klasse behandelt, und das Routingereignis kann immer noch von Ihren Instanzhandlern behandelt werden, wenn Sie bestimmte Techniken verwenden. Außerdem machen viele Basisklassen und Steuerelemente virtuelle Methoden verfügbar, die zum Außerkraftsetzen von Klassenbehandlungsverhalten verwendet werden können. Weitere Informationen sowohl zum Umgehen unerwünschter Klassenbehandlung als auch zum Definieren Ihres eigenen Klassenverhaltens in einer benutzerdefinierten Klasse finden Sie unter [Markieren von Routingereignissen als behandelt und Klassenbehandlung](marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="attached_events"></a>   
## <a name="attached-events-in-wpf"></a>Angefügte Ereignisse in WPF  
 Die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Sprache definiert auch eine besondere Art von Ereignissen, die als *angefügte Ereignisse* bezeichnet werden. Mit einem angefügten Ereignis können Sie einen Ereignishandler für ein bestimmtes Ereignis zu einem beliebigen Element hinzuzufügen. Das Element, das das Ereignis behandelt, muss das angefügte Ereignis weder definieren noch erben; zudem muss weder das Objekt, dass das Ereignis möglicherweise auslöst, noch die dafür zuständige Instanz dieses Ereignis als Klassenmember definieren oder „besitzen“.  
  
 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eingabesystem verwendet angefügte Ereignisse in großem Umfang. Fast alle dieser angefügten Ereignisse werden jedoch über Basiselemente weitergeleitet. Die Eingabeereignisse erscheinen dann als äquivalente nicht angefügte Routingereignisse, die Member der Basiselementklasse sind. Z. B. die zugrunde liegende angefügte Ereignis <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> mehr problemlos verarbeitet werden können auf ein beliebiges <xref:System.Windows.UIElement> mit <xref:System.Windows.UIElement.MouseDown> , <xref:System.Windows.UIElement> statt Umgang mit Syntax für angefügte Ereignisse entweder in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder Code.  
  
 Weitere Informationen zu angefügten Ereignissen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Übersicht über angefügte Ereignisse](attached-events-overview.md).  
  
<a name="Qualifying_Event_Names_in_XAML_for_Anticipated_Routing"></a>   
## <a name="qualified-event-names-in-xaml"></a>Qualifizierte Ereignisnamen in XAML  
 Wenn Sie Handler für Routingereignisse anfügen, die von untergeordneten Elementen ausgelöst werden, ist dies so ähnlich wie der Gebrauch einer *typename*.*eventname* angefügten Ereignissyntax, obwohl es sich dabei genau genommen nicht um den Gebrauch eines angefügten Ereignisses handelt. Fügen Sie die Handler an ein gemeinsames übergeordnetes Element an, um von Ereignisrouting zu profitieren, auch wenn das gemeinsame übergeordnete Element möglicherweise das relevante Routingereignis nicht als Member enthält. Schauen Sie sich dieses Beispiel erneut an:  
  
 [!code-xaml[EventOvwSupport#GroupButton](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#groupbutton)]  
  
 Der Listener des übergeordneten Elements, in dem der Handler hinzugefügt wird, wird eine <xref:System.Windows.Controls.StackPanel>. Allerdings wird einen Handler für ein Routingereignis, der deklariert wurde und es wird ausgelöst durch Hinzufügen der <xref:System.Windows.Controls.Button> Klasse (<xref:System.Windows.Controls.Primitives.ButtonBase> tatsächlich jedoch zur <xref:System.Windows.Controls.Button> durch Vererbung). <xref:System.Windows.Controls.Button> "besitzt" das Ereignis, aber das System lässt Routingereignishandler für jedes beliebige Routingereignis an alle angefügt werden <xref:System.Windows.UIElement> oder <xref:System.Windows.ContentElement> Instanzlistener, der andernfalls Listener für Anhängen könnte eine [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Ereignis. Der Standard-xmlns-Namespace für diese qualifizierten Attributnamen ist in der Regel der Standard-[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-xmlns-Namespace, aber Sie können auch Namespaces mit Präfix für benutzerdefinierte Routingereignisse angeben. Weitere Informationen zu xmlns finden Sie unter [XAML-Namespaces und Namespacezuordnung für WPF-XAML](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="how_event_processing_works"></a>   
## <a name="wpf-input-events"></a>Eingabeereignisse in WPF  
 Routingereignisse werden auf der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Plattform häufig für Eingabeereignisse verwendet. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erhalten Namen von Tunnelingroutingereignissen per Konvention das Wort „Preview“ (Vorschau) als Präfix. Eingabeereignisse treten oft paarweise auf – wobei das eine ein Bubblingereignis und das andere ein Tunnelingereignis ist. Z. B. die <xref:System.Windows.ContentElement.KeyDown> Ereignis und die <xref:System.Windows.ContentElement.PreviewKeyDown> Ereignis haben die gleiche Signatur, wobei ersteres das Bubbling- und letzteres das tunneling von Eingabeereignissen. Manchmal haben Eingabeereignisse nur eine Bubblingversion oder nur eine direkte Routingversion. In der Dokumentation verweisen die Themen zu Routingereignissen auf ähnliche Routingereignisse mit alternativen Routingstrategien, falls derartige Routingereignisse vorhanden sind; Abschnitte auf den Seiten zu verwalteten Referenzen erläutern die Routingstrategien jedes Routingelements.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eingabeereignisse, die paarweise auftreten, werden implementiert, damit eine einzelne Benutzereingabeaktion, wie z.B. das Drücken einer Maustaste, beide Routingereignisse des Paars in der Sequenz auslöst. Zunächst wird das Tunnelingereignis ausgelöst und durchläuft seine Route. Anschließend wird das Bubblingereignis ausgelöst und durchläuft seine Route. Die beiden Ereignisse verwenden die gleiche Instanz der Ereignisdaten, da die <xref:System.Windows.UIElement.RaiseEvent%2A> Methodenaufruf in der implementierenden Klasse, die das Bubblingereignis auslöst überwacht für die Ereignisdaten des tunnelingereignisses und in neuen, ausgelösten Ereignis. Listener mit Handlern für das Tunnelingereignis haben als Erstes die Möglichkeit, das Routingereignis als „handled“ zu markieren (zuerst Klassenhandler, anschließend Instanzhandler). Wenn ein Element entlang der Tunnelingroute das Routingereignis als „handled“ markiert, werden die bereits behandelten Daten des Bubblingereignisses gesendet, und typische angefügte Handler für das entsprechende Bubblingeingabeereignis werden nicht aufgerufen. Nach außen wirkt dies so, als sei das behandelte Bubblingereignis nicht einmal ausgelöst worden. Dieses Behandlungsverhalten ist beim Zusammensetzen von Steuerelementen nützlich; hier möchten Sie möglicherweise, dass alle treffertestbasierten oder fokusbasierten Eingabeereignisse von Ihrem endgültigen Steuerelement gemeldet werden, und nicht von dessen einzelnen Komponenten. Das endgültige Steuerelement ist in der Zusammensetzung näher am Stamm, weshalb es das Tunnelingereignis zunächst in einer Klasse behandeln und eventuell sogar dieses Routingereignis durch ein steuerelementspezifischeres Ereignis „ersetzen“ kann – als Teil des Codes, der die Steuerelementklasse unterstützt.  
  
 Das folgende Beispiel für ein Eingabeereignis veranschaulicht das Verarbeiten von Eingabeereignissen. In der folgenden Baumdiagramm ist `leaf element #2` ist die Quelle der sowohl eine `PreviewMouseDown` und dann eine `MouseDown` Ereignis:  
  
 ![Ereignisrouting-Diagramm](./media/routed-events-overview/input-event-routing.png)  
  
 Ein Ereignis wird in folgender Reihenfolge verarbeitet:  
  
1. `PreviewMouseDown` (Tunnel) auf dem Stammelement (root element)  
  
2. `PreviewMouseDown` (Tunnel) auf dem ersten Zwischenelement (intermediate element #1)  
  
3. `PreviewMouseDown` (Tunnel) auf dem zweiten Zwischenelement (intermediate element #2)  
  
4. `MouseDown` (Bubble) auf dem zweiten Quellelement (source element #2)  
  
5. `MouseDown` (Bubble) auf dem ersten Zwischenelement (intermediate element #1)  
  
6. `MouseDown` (Bubble) auf dem Stammelement (root element)  
  
 Ein Delegat eines Routingereignishandlers enthält Verweise auf zwei Objekte: auf das Objekt, das das Ereignis ausgelöst hat und das Objekt, auf dem der Handler aufgerufen wurde. Das Objekt, auf dem der Handler aufgerufen wurde, ist das Objekt, das vom `sender`-Parameter gemeldet wurde. Das Objekt, in dem das Ereignis erstmals ausgelöst, wird gemeldet, durch die <xref:System.Windows.RoutedEventArgs.Source%2A> Eigenschaft in den Ereignisdaten. Ein Ereignis dennoch ausgelöst und verarbeitet werden kann durch das gleiche Objekt in diesem Fall `sender` und <xref:System.Windows.RoutedEventArgs.Source%2A> identisch sind (Dies ist der Fall mit Schritt 3 und 4, die Verarbeitung in dieser Liste mit Beispielen).  
  
 Aufgrund von tunneling und bubbling erhalten übergeordnete Elemente Eingabeereignisse, in denen die <xref:System.Windows.RoutedEventArgs.Source%2A> ist eines der untergeordneten Elemente. Wenn es wichtig ist zu wissen, was das Quellelement ist, können Sie das Quellelement identifizieren, indem Sie den Zugriff auf die <xref:System.Windows.RoutedEventArgs.Source%2A> Eigenschaft.  
  
 In der Regel, sobald das Eingabeereignis gekennzeichnet ist <xref:System.Windows.RoutedEventArgs.Handled%2A>, weitere Handler nicht aufgerufen werden. In der Regel sollten Sie Eingabeereignisse als „handled“ markieren, sobald ein Handler aufgerufen wird, der Ihre anwendungsspezifische logische Behandlung der Bedeutung des Eingabeereignisses angeht.  
  
 Die Ausnahme von dieser allgemeinen Aussage zum <xref:System.Windows.RoutedEventArgs.Handled%2A> Zustand ist, dass die Ereignishandler, die registriert werden, dass ignorieren Eingabe <xref:System.Windows.RoutedEventArgs.Handled%2A> Zustand der Daten für das Ereignis wird weiterhin auf beiden Routen aufgerufen werden. Weitere Informationen finden Sie unter [Vorschauereignisse](preview-events.md) oder [Markieren von Routingereignissen als behandelt und Klassenbehandlung](marking-routed-events-as-handled-and-class-handling.md).  
  
 Das freigegebene Ereignisdatenmodell von Tunneling- und Bubblingereignissen und das sequenzielle Auslösen zunächst der Tunneling-und dann der Bubblingereignisse ist kein allgemein gültiges Konzept für alle Routingereignisse. Dieses Verhalten wird insbesondere davon implementiert, wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eingabegeräte Eingabeereignispaare auslösen und verbinden. Das Implementieren Ihres eigenen Eingabeereignisses ist ein erweitertes Szenario; möglicherweise entscheiden Sie sich aber dazu, dieses Modell auch für Ihre eigenen Eingabeereignisse zu nutzen.  
  
 Gewisse Klassen behandeln gewisse Eingabeereignisse in einer Klasse, meist mit dem Ziel, die Bedeutung eines bestimmten benutzergesteuerten Eingabeereignisses innerhalb dieses Steuerelements neu zu definieren und ein neues Ereignis auszulösen. Weitere Informationen finden Sie unter [Markieren von Routingereignissen als behandelt und Klassenbehandlung](marking-routed-events-as-handled-and-class-handling.md).  
  
 Weitere Informationen zur Eingabe und zur Interaktion zwischen Eingabe und Ereignissen in normalen Anwendungsszenarien finden Sie unter [Übersicht über die Eingabe](input-overview.md).  
  
<a name="events_styles"></a>   
## <a name="eventsetters-and-eventtriggers"></a>EventSetters und EventTriggers  
 In Stilen, Sie können vordeklarierte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Ereignisbehandlungssyntax in das Markup mit einem <xref:System.Windows.EventSetter>. Wenn das Format angewendet wird, wird der verwiesene Handler zur formatierten Instanz hinzugefügt. Sie können deklarieren, ein <xref:System.Windows.EventSetter> nur für ein Routingereignis. Nachfolgend finden Sie ein Beispiel: Beachten Sie, dass die `b1SetColor`-Methode, auf die hier verwiesen wird, sich in einer CodeBehind-Datei befindet.  
  
 [!code-xaml[EventOvwSupport#XAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/page2.xaml#xaml2)]  
  
 Der Vorteil hierbei ist, dass das Format wahrscheinlich viel andere Informationen enthält, die auf eine beliebige Schaltfläche in der Anwendung angewendet werden können und dass die <xref:System.Windows.EventSetter> Teil dieser Art fördert die Wiederverwendung von Code sogar auf Markupebene. Darüber hinaus eine <xref:System.Windows.EventSetter> Methodennamen für Handler, die einen Schritt weg von der allgemeinen Anwendung und dem Seitenmarkup abstrahiert.  
  
 Weitere spezialisierte Syntax, die die geroutete Ereignis und Animation von kombiniert [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist ein <xref:System.Windows.EventTrigger>. Wie bei <xref:System.Windows.EventSetter>, nur Routingereignisse verwendet werden können, für eine <xref:System.Windows.EventTrigger>. In der Regel ein <xref:System.Windows.EventTrigger> ist als Teil eines Stils, deklariert jedoch <xref:System.Windows.EventTrigger> können auch auf Seitenebene als Teil des deklariert werden die <xref:System.Windows.FrameworkElement.Triggers%2A> -Auflistung, oder in einer <xref:System.Windows.Controls.ControlTemplate>. Ein <xref:System.Windows.EventTrigger> ermöglicht Ihnen die Angabe einer <xref:System.Windows.Media.Animation.Storyboard> , ausgeführt wird, wenn ein Routingereignis ein Element in der Route erreicht deklariert eine <xref:System.Windows.EventTrigger> für dieses Ereignis. Der Vorteil des ein <xref:System.Windows.EventTrigger> über nur behandeln des Ereignisses und, startet ein vorhandenes Storyboard ist, eine <xref:System.Windows.EventTrigger> bietet bessere Kontrolle über das Storyboard und dessen Laufzeitverhalten. Weitere Informationen finden Sie unter [Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start](../graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
<a name="more_about"></a>   
## <a name="more-about-routed-events"></a>Weitere Informationen zu Routingereignissen  
 In diesem Thema werden hauptsächlich die grundlegenden Konzepte von Routingereignissen erläutert; zudem bietet er Ihnen eine Orientierung, wann Sie auf Routingereignisse reagieren sollten, die bereits in den verschieden Basiselementen und -steuerelementen vorhanden sind. Allerdings können Sie eigene Routingereignis für Ihre benutzerdefinierte Klasse mit den notwendigen Hilfsmitteln, wie z. B. spezialisierte Ereignisdatenklassen und Delegaten, erstellen. Eigentümer des Routingereignisses kann jede Klasse sein, aber die Routingereignisse müssen ausgelöst und behandelt, indem <xref:System.Windows.UIElement> oder <xref:System.Windows.ContentElement> abgeleiteten Klassen, damit Sie nützlich ist. Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Erstellen eines benutzerdefinierten Routingereignisses](how-to-create-a-custom-routed-event.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.EventManager>
- <xref:System.Windows.RoutedEvent>
- <xref:System.Windows.RoutedEventArgs>
- [Markieren von Routingereignissen als behandelt und Klassenbehandlung](marking-routed-events-as-handled-and-class-handling.md)
- [Übersicht über die Eingabe](input-overview.md)
- [Befehlsübersicht](commanding-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Strukturen in WPF](trees-in-wpf.md)
- [Schwache Ereignismuster](weak-event-patterns.md)
