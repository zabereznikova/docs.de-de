---
title: "&#220;bersicht &#252;ber Routingereignisse | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Angefügte Ereignisse"
  - "Bubbling"
  - "Schatflächensatz, Gruppiert"
  - "Ereignisse, Angefügt"
  - "Ereignisse, Weitergeleitet"
  - "Gruppierter Schaltflächensatz"
  - "Routingereignisse"
  - "Routingstrategien für Ereignisse"
  - "Tunneln"
ms.assetid: 1a2189ae-13b4-45b0-b12c-8de2e49c29d2
caps.latest.revision: 29
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 28
---
# &#220;bersicht &#252;ber Routingereignisse
In diesem Thema wird das Konzept der Routingereignisse in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] beschrieben.  Das Thema enthält Definitionen zu den im Zusammenhang mit Routingereignissen verwendeten Begriffen, eine Beschreibung der Weiterleitung von Routingereignissen in einer Elementstruktur, eine Übersicht über die Behandlung von Routingereignissen sowie eine Einführung in die Erstellung benutzerdefinierter Routingereignisse.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 In diesem Thema wird vorausgesetzt, dass Sie über Grundkenntnisse in [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] und objektorientierter Programmierung verfügen und mit dem Konzept vertraut sind, nach dem die Beziehungen zwischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Elementen als Elementstruktur begriffen werden können.  Um den Beispielen in diesem Thema folgen zu können, sollten Sie zudem mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] vertraut sein und sehr einfache [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen und \-Seiten schreiben können.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erste Schritte mit WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md) und [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
<a name="routing"></a>   
## Was ist ein Routingereignis?  
 Routingereignisse können entweder aus funktionaler Perspektive oder im Hinblick auf die Implementierung betrachtet werden.  Hier werden der Vollständigkeit halber beide Definitionen erläutert.  
  
 Funktionale Definition: Ein Routingereignis ist ein Ereignistyp, der Handler für mehrere Listener in einer Elementstruktur aufrufen kann, und nicht nur für das Objekt, von dem das Ereignis ausgelöst wurde.  
  
 Implementierungsdefinition: Ein [Routingereignis](GTMT) ist ein [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Ereignis, das auf einer Instanz der <xref:System.Windows.RoutedEvent>\-Klasse basiert und vom [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Ereignissystem verarbeitet wird.  
  
 Eine typische [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung enthält viele Elemente.  Unabhängig davon, ob sie in Code erstellt oder in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] deklariert werden, stehen diese Elemente in einer Elementstruktur in Beziehung zueinander.  Die Ereignisroute kann je nach Ereignisdefinition in zwei Richtungen verlaufen, in der Regel verläuft die Route jedoch vom Quellelement aus per "Bubbling" durch die Elementstruktur hindurch nach oben, bis der Stamm der Elementstruktur erreicht ist \(normalerweise eine Seite oder ein Fenster\).  Sie sind möglicherweise bereits mit diesem Bubbling\-Konzept vertraut, wenn Sie schon einmal mit dem DHTML\-Objektmodell gearbeitet haben.  
  
 Betrachten Sie die folgende einfache Elementstruktur:  
  
 [!code-xml[EventOvwSupport#GroupButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#groupbutton)]  
  
 Diese Elementstruktur erzeugt in etwa Folgendes:  
  
 ![Schaltflächen Ja, Nein und Abbrechen](../../../../docs/framework/wpf/advanced/media/routedevent-ovw-1.png "RoutedEvent\_ovw\_1")  
  
 In dieser vereinfachten Elementstruktur ist das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis eines der <xref:System.Windows.Controls.Button>\-Elemente, und der <xref:System.Windows.Controls.Button>, auf den zuerst geklickt wird, hat die Möglichkeit, das Ereignis zu verarbeiten.  Wenn jedoch kein Handler des <xref:System.Windows.Controls.Button> auf das Ereignis angewendet wird, wird das Ereignis nach oben an den übergeordneten <xref:System.Windows.Controls.Button> in der Elementstruktur übergeben, dem <xref:System.Windows.Controls.StackPanel>.  Möglicherweise wird das Ereignis an <xref:System.Windows.Controls.Border> und dann bis an den Seitenstamm der Elementstruktur weitergeleitet \(nicht dargestellt\).  
  
 Anders ausgedrückt verläuft die Ereignisroute für dieses <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis wie folgt:  
  
 Button\-\-\>StackPanel\-\-\>Border\-\-\>...  
  
### Szenarien auf oberster Ebene für Routingereignisse  
 Im Folgenden werden die Szenarien, die das Konzept der Routingereignisse motiviert haben, kurz zusammengefasst, und es wird erläutert, warum ein herkömmliches [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Ereignis für diese Szenarien nicht geeignet war:  
  
 **Zusammensetzung und Kapselung der Steuerelemente:** Viele Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügen über ein umfangreiches Inhaltsmodell.  So können Sie z. B. ein Bild in einen <xref:System.Windows.Controls.Button> einfügen, wodurch die visuelle Struktur der Schaltfläche erweitert wird.  Das hinzugefügte Bild darf sich jedoch nicht auf das Treffertestverhalten auswirken, das eine Schaltfläche dazu veranlasst, auf einen <xref:System.Windows.Controls.Primitives.ButtonBase.Click> des Inhalts zu reagieren, auch wenn der Benutzer auf Pixel klickt, die technisch gesehen Teil des Bilds sind.  
  
 **Einzelne Handleranfügepunkte:** In [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] müssten Sie denselben Handler mehrmals anfügen, um Ereignisse zu verarbeiten, die von mehreren Elementen ausgelöst werden können.  Mit Routingereignissen haben Sie die Möglichkeit, diesen Handler nur einmal anzufügen, wie im vorherigen Beispiel gezeigt. Dann können Sie ggf. mithilfe von Handlerlogik ermitteln, woher das Ereignis stammt.  Dies könnte z. B. der Handler für das zuvor gezeigte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sein:  
  
 [!code-csharp[EventOvwSupport#GroupButtonCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#groupbuttoncodebehind)]
 [!code-vb[EventOvwSupport#GroupButtonCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#groupbuttoncodebehind)]  
  
 **Klassenbehandlung:** Routingereignisse lassen einen statischen Handler zu, der von der Klasse definiert wird.  Dieser Klassenhandler hat die Möglichkeit, ein Ereignis noch vor den angefügten Instanzhandlern zu behandeln.  
  
 **Verweisen auf ein Ereignis ohne Reflektion:** Bei manchen Code\- und Markupverfahren muss ein bestimmtes Ereignis identifiziert werden können.  Ein Routingereignis erstellt ein <xref:System.Windows.RoutedEvent>\-Feld als Bezeichner, wodurch ein robustes Verfahren der Ereignisidentifizierung bereitgestellt wird, das keine statische Reflektion oder Laufzeitreflektion erfordert.  
  
### So werden Routingereignisse implementiert  
 Ein [Routingereignis](GTMT) ist ein [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Ereignis, das auf einer Instanz der <xref:System.Windows.RoutedEvent>\-Klasse basiert und im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Ereignissystem registriert wird.  Die von der Registrierung erhaltene <xref:System.Windows.RoutedEvent>\-Instanz wird in der Regel als `public` `static` `readonly`\-Feldmember der registrierenden Klasse beibehalten, die somit "Eigentümer" des Routingereignisses ist.  Die Verbindung zu dem [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Ereignis desselben Namens \(das manchmal als "Wrapper"\-Ereignis bezeichnet wird\) wird durch Überschreiben der `add`\- und `remove`\-Implementierungen des [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Ereignisses hergestellt.  In der Regel werden `add` und `remove` als impliziter Standard belassen, der die entsprechende sprachspezifische Ereignissyntax zum Hinzufügen und Entfernen von Handlern für dieses Ereignis verwendet.  Der Mechanismus der Unterstützung und Verbindung bei Routingereignissen entspricht in etwa dem Konzept, nach dem eine [Abhängigkeitseigenschaft](GTMT) eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Eigenschaft darstellt, die auf der <xref:System.Windows.DependencyProperty>\-Klasse basiert und im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystem registriert wird.  
  
 Im folgenden Beispiel wird die Deklaration eines benutzerdefinierten `Tap`\-Routingereignisses veranschaulicht und gezeigt, wie das <xref:System.Windows.RoutedEvent>\-Bezeichnerfeld und die `add`\- und `remove`\-Implementierungen für das `Tap` [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Ereignis registriert und verfügbar gemacht werden.  
  
 [!code-csharp[RoutedEventCustom#AddRemoveHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#addremovehandler)]
 [!code-vb[RoutedEventCustom#AddRemoveHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#addremovehandler)]  
  
### Routingereignishandler und XAML  
 Um einen Handler für ein Ereignis mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hinzuzufügen, deklarieren Sie den Ereignisnamen als Attribut des Elements, das einen Ereignislistener darstellt.  Der Wert des Attributs ist der Name der implementierten Handlermethode, die in der partiellen Klasse der Code\-Behind\-Datei enthalten sein muss.  
  
 [!code-xml[EventOvwSupport#SimplestSyntax](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#simplestsyntax)]  
  
 Die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Syntax zum Hinzufügen standardmäßiger [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Ereignishandler entspricht dem Hinzufügen von Routingereignishandlern, da Sie im Grunde Handler zum [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Ereigniswrapper hinzufügen, der auf einer Routingereignisimplementierung basiert.  Weitere Informationen zum Hinzufügen von Ereignishandlern in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] finden Sie unter [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
<a name="routing_strategies"></a>   
## Routingstrategien  
 Routingereignisse verwenden eine von drei Routingstrategien:  
  
-   **Bubbling:** Es werden Ereignishandler auf der Ereignisquelle aufgerufen.  Das Routingereignis wird dann an die folgenden übergeordneten Elemente weitergeleitet, bis der Stamm der Elementstruktur erreicht ist.  Die meisten Routingereignisse verwenden die Bubbling\-Routingstrategie.  Bubbling\-Routingereignisse werden in der Regel dazu verwendet, um Eingaben oder Änderungen des Betriebszustands von verschiedenen Steuerelementen oder anderen Benutzeroberflächenelementen zu melden.  
  
-   **Direkt:** Nur das Quellelement selbst hat die Möglichkeit, durch Aufrufen von Handlern zu reagieren.  Dies entspricht dem "Routing", das von [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] für Ereignisse verwendet wird.  Im Gegensatz zu standardmäßigen [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Ereignissen unterstützen direkte Routingereignisse jedoch die Klassenbehandlung \(die Klassenbehandlung wird in einem der folgenden Abschnitte erläutert\) und können von <xref:System.Windows.EventSetter> und <xref:System.Windows.EventTrigger> verwendet werden.  
  
-   **Tunneling:** Zunächst werden Ereignishandler am Elementstrukturstamm aufgerufen.  Anschließend wird das Routingereignis über die nachfolgenden untergeordneten Elemente in der Route bis zu dem Knotenelement weitergeleitet, das die Quelle des Routingereignisses darstellt \(das Element, von dem das Routingereignis ausgelöst wurde\).  Tunneling\-Routingereignisse werden oft als Teil der Zusammensetzung für ein Steuerelement verwendet oder verarbeitet, sodass Ereignisse von zusammengesetzten Teilen gezielt unterdrückt oder durch Ereignisse ersetzt werden, die für das gesamte Steuerelement spezifisch sind.  In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bereitgestellte Eingabeereignisse werden oft als Tunneling\/Bubbling\-Paar implementiert.  Aufgrund einer Namenskonvention für die Paare werden Tunneling\-Ereignisse manchmal auch als Vorschauereignisse bezeichnet.  
  
<a name="why_use"></a>   
## Gründe für die Verwendung von Routingereignissen  
 Für Sie als Anwendungsentwickler ist es nicht immer relevant, dass das behandelte Ereignis als Routingereignis implementiert wird.  Routingereignisse verfügen zwar über ein spezielles Verhalten, dieses macht sich jedoch kaum bemerkbar, wenn Sie ein Ereignis auf dem Element behandeln, von dem es ausgelöst wird.  
  
 In den folgenden Szenarien sind Routingereignisse besonders nützlich: Definieren gemeinsamer Handler an einem gemeinsamen Stamm, Zusammensetzen eines eigenen Steuerelements oder Definieren einer eigenen benutzerdefinierten Steuerelement\-Klasse.  
  
 Routingereignislistener und Routingereignisquellen müssen nicht über ein gemeinsames Ereignis in ihrer Hierarchie verfügen.  Jedes <xref:System.Windows.UIElement> oder <xref:System.Windows.ContentElement> kann ein Ereignislistener für jedes beliebige Routingereignis sein.  Deshalb können Sie alle innerhalb des [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]\-Workingsets verfügbaren Routingereignisse als konzeptionelle "Schnittstelle" verwenden, über die unterschiedliche Elemente in der Anwendung Ereignisinformationen austauschen können.  Dieses "Schnittstellen"\-Konzept für Routingereignisse gilt vor allem für Eingabeereignisse.  
  
 Routingereignisse können auch für die Kommunikation innerhalb der Elementstruktur verwendet werden, da die Ereignisdaten für das Ereignis an jedes Element auf der Route weitergegeben werden.  Wenn ein Element z. B. eine Änderung an den Ereignisdaten vornimmt, ist diese Änderung für das nächste Element auf der Route verfügbar.  
  
 Abgesehen vom Routingaspekt gibt es zwei weitere Gründe, aus denen ein beliebiges [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Ereignis als Routingereignis anstatt als standardmäßiges [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Ereignis implementiert werden könnte.  Wenn Sie Ihre eigenen Ereignisse implementieren, könnten auch folgende Prinzipien für Sie von Interesse sein:  
  
-   Bestimmte Stil\- und Vorlagenfunktionen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], wie <xref:System.Windows.EventSetter> und <xref:System.Windows.EventTrigger>, müssen auf ein Routingereignis verweisen.  Dieses Ereignisbezeichner\-Szenario wurde bereits weiter oben beschrieben.  
  
-   Routingereignisse unterstützen einen Klassenbehandlungsmechanismus, mit dem die Klasse statische Methoden angeben kann, die Routingereignisse verarbeiten können, bevor registrierte Instanzhandler auf sie zugreifen können.  Dieser Mechanismus ist für Steuerelemententwürfe besonders nützlich, da die Klasse ereignisgesteuerte Klassenverhalten erzwingen kann, die nicht unbeabsichtigt durch Behandlung eines Ereignisses für eine Instanz unterdrückt werden können.  
  
 Jede der oben erwähnten Überlegungen wird in einem separaten Abschnitt dieses Themas erläutert.  
  
<a name="event_handing"></a>   
## Hinzufügen und Implementieren eines Ereignishandlers für ein Routingereignis  
 Zum Hinzufügen eines Ereignishandlers in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] fügen Sie einfach den Ereignisnamen als Attribut zu einem Element hinzu und legen den Attributwert als Namen des Ereignisses des Ereignishandlers fest, der einen entsprechenden Delegaten implementiert, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-xml[EventOvwSupport#SimplestSyntax](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#simplestsyntax)]  
  
 `b1SetColor` ist der Name des implementierten Handlers, der den Code zur Behandlung des <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignisses enthält.  `b1SetColor` muss über dieselbe Signatur verfügen wie der <xref:System.Windows.RoutedEventHandler>\-Delegat, bei dem es sich um das Ereignishandlerobjekt für das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis handelt.  Der erste Parameter aller Routingereignishandler\-Delegaten gibt das Element an, zu dem ein Ereignishandler hinzugefügt wird, und der zweite Parameter gibt die Daten für das Ereignis an.  
  
 [!code-csharp[EventOvwSupport#SimpleHandlerA](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#simplehandlera)]
 [!code-vb[EventOvwSupport#SimpleHandlerA](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#simplehandlera)]  
[!code-csharp[EventOvwSupport#SimpleHandlerB](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#simplehandlerb)]
[!code-vb[EventOvwSupport#SimpleHandlerB](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#simplehandlerb)]  
  
 <xref:System.Windows.RoutedEventHandler> ist der einfache Routingereignishandler\-Delegat.  Bei Routingereignissen, die speziell auf bestimmte Szenarien ausgelegt sind, können die für die Routingereignishandler zu verwendenden Delegaten auch komplexer sein, sodass sie spezialisierte Ereignisdaten übertragen können.  So könnten Sie z. B. in einem üblichen Eingabeszenario ein <xref:System.Windows.UIElement.DragEnter>\-Routingereignis behandeln.  Der Handler sollte den <xref:System.Windows.DragEventHandler>\-Delegaten implementieren.  Durch Verwendung des spezifischsten Delegaten können Sie <xref:System.Windows.DragEventArgs> im Handler verarbeiten und die <xref:System.Windows.DragEventArgs.Data%2A>\-Eigenschaft lesen, in der die Zwischenablagennutzlast des Ziehvorgangs enthalten ist.  
  
 Ein vollständiges Beispiel zum Hinzufügen eines Ereignishandlers zu einem Element mithilfe von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] finden Sie unter [Behandeln eines Routingereignisses](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md).  
  
 Das Hinzufügen eines Handlers für ein Routingereignis in einer in Code erstellten Anwendung ist nicht schwierig.  Routingereignishandler können immer mithilfe einer Hilfsmethode <xref:System.Windows.UIElement.AddHandler%2A> hinzugefügt werden \(hierbei handelt es sich um dieselbe Methode, die von der vorhandenen zugrunde liegenden Implementierung für `add` aufgerufen wird\). Vorhandene [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Routingereignisse verfügen jedoch in der Regel über zugrunde liegende Implementierungen der `add`\- und `remove`\-Logik, die das Hinzufügen der Handler für Routingereignisse über eine sprachspezifische Ereignissyntax ermöglichen, deren Syntax intuitiver ist als die Hilfsmethode.  Die Verwendung der Hilfsmethode wird im folgenden Beispiel veranschaulicht:  
  
 [!code-csharp[EventOvwSupport#AddHandlerCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#addhandlercode)]
 [!code-vb[EventOvwSupport#AddHandlerCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#addhandlercode)]  
  
 Im nächsten Beispiel ist die [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]\-Operatorsyntax dargestellt \(die Operatorsyntax von [!INCLUDE[TLA2#tla_visualb](../../../../includes/tla2sharptla-visualb-md.md)] weicht aufgrund der Dereferenzierungsbehandlung leicht davon ab\):  
  
 [!code-csharp[EventOvwSupport#AddHandlerPlusEquals](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml.cs#addhandlerplusequals)]
 [!code-vb[EventOvwSupport#AddHandlerPlusEquals](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EventOvwSupport/visualbasic/default.xaml.vb#addhandlerplusequals)]  
  
 Ein Beispiel für das Hinzufügen eines Ereignishandlers in Code finden Sie unter [Hinzufügen eines Ereignishandlers mithilfe von Code](../../../../docs/framework/wpf/advanced/how-to-add-an-event-handler-using-code.md).  
  
 Wenn Sie [!INCLUDE[TLA2#tla_visualb](../../../../includes/tla2sharptla-visualb-md.md)] verwenden, können Sie Handler auch mit dem `Handles`\-Schlüsselwort als Teil der Handlerdeklaration hinzufügen.  Weitere Informationen finden Sie unter [Visual Basic\- und WPF\-Ereignisbehandlung](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
<a name="concept_handled"></a>   
### Das Handled\-Konzept  
 Alle Routingereignisse verwenden eine gemeinsame Ereignisdaten\-Basisklasse, <xref:System.Windows.RoutedEventArgs>.  <xref:System.Windows.RoutedEventArgs> definiert die <xref:System.Windows.RoutedEventArgs.Handled%2A>\-Eigenschaft, die einen booleschen Wert annimmt.  Die <xref:System.Windows.RoutedEventArgs.Handled%2A>\-Eigenschaft soll es Ereignishandlern auf der Route ermöglichen, das Routingereignis als *behandelt* zu markieren, indem der Wert von <xref:System.Windows.RoutedEventArgs.Handled%2A> in `true` geändert wird.  Nach der Verarbeitung durch den Handler eines Elements auf der Route werden die gemeinsamen Ereignisdaten erneut jedem Listener auf der Route gemeldet.  
  
 Der Wert von <xref:System.Windows.RoutedEventArgs.Handled%2A> wirkt sich darauf aus, wie ein Routingereignis während der Weiterleitung durch die Route gemeldet oder verarbeitet wird.  Wenn <xref:System.Windows.RoutedEventArgs.Handled%2A> in den Ereignisdaten für ein Routingereignis `true` ist, werden Handler, die dieses Routingereignis auf anderen Elementen überwachen, in der Regel für diese spezifische Ereignisinstanz nicht mehr aufgerufen.  Das gilt sowohl für in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] angefügte Handler als auch für Handler, die durch eine sprachspezifische Syntax zum Hinzufügen von Routingereignissen wie `+=` oder `Handles` hinzugefügt werden.  Bei den häufigsten Handlerszenarien wird durch Festlegen von <xref:System.Windows.RoutedEventArgs.Handled%2A> auf `true` das Routing sowohl für Tunneling\- als auch für Bubbling\-Routen sowie für jedes Ereignis, das an einem Punkt auf der Route durch einen Klassenhandler behandelt wird, "gestoppt".  
  
 Es gibt jedoch einen "handledEventsToo"\-Mechanismus, der Listenern das Ausführen von Handlern als Reaktion auf Routingereignisse ermöglicht, wenn <xref:System.Windows.RoutedEventArgs.Handled%2A> in den Ereignisdaten den Wert `true` hat.  Anders ausgedrückt wird die Ereignisroute durch Markieren der Ereignisdaten als behandelt nicht wirklich gestoppt.  Sie können den handledEventsToo\-Mechanismus nur in Code oder in einem <xref:System.Windows.EventSetter> verwenden:  
  
-   Rufen Sie in Code anstelle einer für allgemeine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Ereignisse verwendbaren sprachspezifischen Ereignissyntax die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Methode <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> zum Hinzufügen des Handlers auf.  Geben Sie den Wert von `handledEventsToo` als `true` an.  
  
-   Legen Sie in einem <xref:System.Windows.EventSetter> das <xref:System.Windows.EventSetter.HandledEventsToo%2A>\-Attribut als `true` fest.  
  
 Zusätzlich zu dem Verhalten, das der <xref:System.Windows.RoutedEventArgs.Handled%2A>\-Status in Routingereignissen erzeugt, wirkt sich das Konzept von <xref:System.Windows.RoutedEventArgs.Handled%2A> auf die Art und Weise aus, wie Sie Ihre Anwendung entwerfen und den Ereignishandlercode schreiben.  <xref:System.Windows.RoutedEventArgs.Handled%2A> kann als einfaches Protokoll begriffen werden, das von Routingereignissen verfügbar gemacht wird.  Sie können selbst entscheiden, wie Sie dieses Protokoll genau verwenden, der Konzeptentwurf für die Verwendung des Werts von <xref:System.Windows.RoutedEventArgs.Handled%2A> ist jedoch auf folgende Verwendung ausgerichtet:  
  
-   Wenn ein Routingereignis als behandelt markiert ist, muss es nicht von anderen Elementen auf dieser Route erneut verarbeitet werden.  
  
-   Wenn ein Ereignis nicht als behandelt markiert ist, haben entweder frühere Listener auf der Route keinen Handler registriert, oder die registrierten Handler haben die Ereignisdaten nicht geändert und <xref:System.Windows.RoutedEventArgs.Handled%2A> nicht auf `true` festgelegt.  \(Es ist natürlich auch möglich, dass der aktuelle Listener den ersten Punkt in der Route darstellt.\) Handler auf dem aktuellen Listener verfügen jetzt über drei mögliche Vorgehensweisen:  
  
    -   Es wird überhaupt keine Aktion ausgeführt, das Ereignis wird nicht behandelt, und das Ereignis wird an den nächsten Listener weitergeleitet.  
  
    -   Code wird als Reaktion auf das Ereignis ausgeführt, die durchgeführte Aktion war jedoch nicht umfassend genug, um die Markierung des Ereignisses als behandelt zu rechtfertigen.  Das Ereignis wird zum nächsten Listener weitergeleitet.  
  
    -   Code wird als Reaktion auf das Ereignis ausgeführt.  Das Ereignis wird in den an den Handler übergebenen Ereignisdaten als behandelt markiert, da die durchgeführte Aktion ausreicht, um die Markierung des Ereignisses als behandelt zu rechtfertigen.  Das Ereignis wird dennoch an den nächsten Listener weitergeleitet, jedoch mit <xref:System.Windows.RoutedEventArgs.Handled%2A>\=`true` in den Ereignisdaten, sodass nur `handledEventsToo`\-Listener die Möglichkeit haben, weitere Handler aufzurufen.  
  
 Dieser Konzeptentwurf wird durch das oben beschriebene Routingverhalten unterstützt: Es ist schwieriger \(wenn auch in Code oder Stilen durchaus möglich\), Handler für Routingereignisse anzufügen, wenn ein vorhergehender Handler auf der Route den Wert für <xref:System.Windows.RoutedEventArgs.Handled%2A> bereits in `true` geändert hat.  
  
 Weitere Informationen zu <xref:System.Windows.RoutedEventArgs.Handled%2A>, zur Klassenbehandlung von Routingereignissen sowie zu Empfehlungen dazu, wann es angemessen ist, ein Routingereignis als <xref:System.Windows.RoutedEventArgs.Handled%2A> zu markieren, finden Sie unter [Markieren von Routingereignissen als behandelt und Klassenbehandlung](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md).  
  
 In Anwendungen ist es recht üblich, ein Bubbling\-Routingereignis nur für das Objekt zu behandeln, von dem es ausgelöst wurde, ohne die Routingeigenschaften des Ereignisses weiter zu beachten.  Es empfiehlt sich aber dennoch, das Routingereignis in den Ereignisdaten als behandelt zu markieren, um unvorhergesehene Nebeneffekte für den Fall zu verhindern, dass an ein weiter oben in der Elementstruktur befindliches Element ein Handler für dasselbe Routingereignis angefügt ist.  
  
<a name="class_handlers"></a>   
## Klassenhandler  
 Wenn Sie eine Klasse definieren, bei der auf irgendeine Weise von <xref:System.Windows.DependencyObject> abgeleitet wird, können Sie auch einen Klassenhandler für ein Routingereignis definieren und anfügen, bei dem es sich um einen deklarierten oder geerbten Ereignismember der Klasse handelt.  Klassenhandler werden noch vor den an eine Instanz dieser Klasse angefügten Instanzlistener\-Handlern aufgerufen, wenn ein Routingereignis eine Elementinstanz auf seiner Route erreicht.  
  
 Manche [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelemente verfügen über eine inhärente Klassenbehandlung für bestimmte Routingereignisse.  Hierdurch könnte der Anschein entstehen, dass das Routingereignis niemals ausgelöst wird, tatsächlich wird es jedoch durch eine Klasse behandelt, und das Routingereignis kann trotzdem von den Instanzhandlern behandelt werden, wenn Sie bestimmte Verfahrensweisen befolgen.  Zudem machen viele Basisklassen und Steuerelemente virtuelle Methoden verfügbar, mit denen das Klassenbehandlungsverhalten überschrieben werden kann.  Weitere Informationen dazu, wie eine unerwünschte Klassenbehandlung umgangen werden kann und wie Sie Ihre eigene Klassenbehandlung in einer benutzerdefinierten Klasse definieren, finden Sie unter [Markieren von Routingereignissen als behandelt und Klassenbehandlung](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="attached_events"></a>   
## Angefügte Ereignisse in WPF  
 Die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Sprache definiert auch einen speziellen Ereignistyp, der als *angefügtes Ereignis* bezeichnet wird.  Mit einem angefügten Ereignis können Sie einen Handler für ein bestimmtes Ereignis zu einem beliebigen Element hinzufügen.  Das Element, von dem das Ereignis behandelt wird, muss das angefügte Ereignis nicht definieren oder erben, und weder das Objekt, von dem das Ereignis potenziell ausgelöst wird, noch die behandelnde Zielinstanz müssen dieses Ereignis als Klassenmember definieren oder auf andere Weise "besitzen".  
  
 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eingabesystem nutzt angefügte Ereignisse in großem Umfang.  Fast alle dieser angefügten Ereignisse werden jedoch über Basiselemente weitergeleitet.  Diese Eingabeereignisse erscheinen dann als entsprechende nicht angefügte Routingereignisse, die Member der Basiselementklasse sind.  So kann beispielsweise das zugrunde liegende angefügte Ereignis <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=fullName> einfacher auf einem gegebenen <xref:System.Windows.UIElement> behandelt werden, wenn <xref:System.Windows.UIElement.MouseDown> auf diesem <xref:System.Windows.UIElement> verwendet wird, anstatt die Syntax für angefügte Ereignisse in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder im Code zu verwenden.  
  
 Weitere Informationen zu angefügten Ereignissen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Übersicht über angefügte Ereignisse](../../../../docs/framework/wpf/advanced/attached-events-overview.md).  
  
<a name="Qualifying_Event_Names_in_XAML_for_Anticipated_Routing"></a>   
## Qualifizierte Ereignisnamen in XAML  
 Eine andere Syntaxverwendung, die der *typename*.*eventname*\-Syntax für angefügte Ereignisse ähnelt, streng genommen jedoch keine angefügten Ereignisse verwendet, besteht im Hinzufügen von Handlern für Routingereignisse, die von untergeordneten Elementen ausgelöst werden.  Um das Ereignisrouting zu nutzen, fügen Sie die Handler an ein gemeinsames übergeordnetes Element an, selbst wenn das relevante Routingelement kein Member des gemeinsamen übergeordneten Elements ist.  Betrachten Sie erneut folgendes Beispiel:  
  
 [!code-xml[EventOvwSupport#GroupButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/default.xaml#groupbutton)]  
  
 Hier handelt es sich bei dem Listener des übergeordneten Elements, für das der Handler hinzugefügt wird, um ein <xref:System.Windows.Controls.StackPanel>.  Es fügt jedoch einen Handler für ein deklariertes Routingereignis hinzu und wird nicht von der <xref:System.Windows.Controls.Button>\-Klasse ausgelöst \(eigentlich <xref:System.Windows.Controls.Primitives.ButtonBase>, für <xref:System.Windows.Controls.Button> durch Vererbung verfügbar\).  <xref:System.Windows.Controls.Button> ist "Eigentümer" des Ereignisses, das Routingereignissystem lässt jedoch zu, dass Handler eines beliebigen Routingereignisses an jeden <xref:System.Windows.UIElement>\- oder <xref:System.Windows.ContentElement>\-Instanzlistener angefügt werden, die andernfalls Listener für ein [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Ereignis anfügen könnten.  Der standardmäßige xmlns\-Namespace für diese qualifizierten Ereignisattributnamen ist in der Regel der standardmäßige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-xmlns\-Namespace, Sie können jedoch auch Namespaces mit Präfix für benutzerdefinierte Routingereignisse verwenden.  Weitere Informationen zu xmlns finden Sie unter [XAML\-Namespaces und Namespacezuordnung für WPF\-XAML](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="how_event_processing_works"></a>   
## WPF\-Eingabeereignisse  
 Häufig werden Routingereignisse innerhalb der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Plattform für Eingabeereignisse verwendet. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird dem Namen von Tunnelingroutingereignissen gemäß Konvention das Wort "Preview" als Präfix vorangestellt.  Eingabeereignisse liegen in der Regel als Paar vor, das aus einem Bubbling\- und einem Tunneling\-Ereignis besteht.  So verfügen z. B. das <xref:System.Windows.ContentElement.KeyDown>\-Ereignis und das <xref:System.Windows.ContentElement.PreviewKeyDown>\-Ereignis über dieselbe Signatur, wobei ersteres das Bubbling\-Eingabeereignis und letzteres das Tunneling\-Eingabeereignis darstellt.  Manchmal haben Ereignisse nur eine Bubbling\-Version oder auch nur eine direkte Routing\-Version.  In der Dokumentation verweisen Themen, die Routingereignisse betreffen, auf ähnliche Routingereignisse mit unterschiedlichen Routingstrategien, falls solche Routingereignisse vorhanden sind, und in den Abschnitten auf den Seiten zu verwalteten Verweisen wird die Routingstrategie für jedes Routingereignis erläutert.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eingabeereignisse, die als Paar vorliegen, werden so implementiert, dass durch eine einzige Benutzereingabeaktion, wie z. B. ein Mausklick, beide Routingereignisse des Paars nacheinander ausgelöst werden.  Zuerst wird das Tunneling\-Ereignis ausgelöst und durchläuft seine Route.  Dann wird das Bubbling\-Ereignis ausgelöst und durchläuft seine Route.  Die beiden Ereignisse verwenden dieselbe Ereignisdateninstanz, da der <xref:System.Windows.UIElement.RaiseEvent%2A>\-Methodenaufruf in der implementierenden Klasse, der das Bubbling\-Ereignis auslöst, die Ereignisdaten des Tunneling\-Ereignisses überwacht und im neuen ausgelösten Ereignis verwendet.  Listener mit Handlern für das Tunneling\-Ereignis haben als erstes die Möglichkeit, das Routingereignis als behandelt zu markieren \(zuerst Klassenhandler und dann Instanzhandler\).  Wenn ein Element auf der Tunneling\-Route das Routingereignis als behandelt markiert, werden die bereits behandelten Ereignisdaten an das Bubbling\-Ereignis gesendet, und die für die entsprechenden Bubbling\-Eingabeereignisse angefügten typischen Handler werden nicht aufgerufen.  Nach außen hat es den Anschein, als ob das behandelte Bubbling\-Ereignis überhaupt nicht ausgelöst wurde.  Dieses Behandlungsverhalten ist bei der Zusammensetzung von Steuerelementen hilfreich, wenn alle auf Treffertest oder Fokus basierenden Eingabeereignisse vom endgültigen Steuerelement und nicht von dessen einzelnen Teilen gemeldet werden sollen.  Das endgültige Steuerelement befindet sich in der Zusammensetzung näher am Stamm und hat deshalb die Möglichkeit, das Tunneling\-Ereignis zuerst zu behandeln und dieses Routingereignis als Teil des Codes, auf dem die Steuerelementklasse basiert, ggf. durch ein steuerelementspezifischeres Ereignis zu "ersetzen".  
  
 Folgendes Eingabeereignisbeispiel veranschaulicht, wie die Verarbeitung von Eingabeereignissen funktioniert.  In der folgenden Strukturabbildung ist `leaf element #2` sowohl die Quelle eines `PreviewMouseDown`\- als auch eines `MouseDown`\-Ereignisses.  
  
 ![Ereignisrouting&#45;Diagramm](../../../../docs/framework/wpf/advanced/media/wcsdkcoreinputevents.png "wcsdkCoreInputEvents")  
Bubbling und Tunneling von Eingabeereignissen  
  
 Die Ereignisverarbeitung erfolgt in der folgenden Reihenfolge:  
  
1.  `PreviewMouseDown` \(Tunneling\) auf dem Stammelement.  
  
2.  `PreviewMouseDown` \(Tunneling\) auf Zwischenelement Nr. 1.  
  
3.  `PreviewMouseDown` \(Tunneling\) auf Quellelement Nr. 2.  
  
4.  `MouseDown` \(Bubbling\) auf Quellelement Nr. 2.  
  
5.  `MouseDown` \(Bubbling\) auf Zwischenelement Nr. 1.  
  
6.  `MouseDown` \(Bubbling\) auf dem Stammelement.  
  
 Ein Routingereignishandler\-Delegat stellt Verweise auf zwei Objekte bereit: das Objekt, von dem das Ereignis ausgelöst wurde, und das Objekt, von dem der Handler aufgerufen wurde.  Das Objekt, an dem der Handler aufgerufen wurde, ist das Objekt, das vom `sender`\-Parameter gemeldet wird.  Das Objekt, an dem das Ereignis erstmals ausgelöst wurde, wird von der <xref:System.Windows.RoutedEventArgs.Source%2A>\-Eigenschaft in den Ereignisdaten gemeldet.  Ein Routingereignis kann auch von demselben Objekt ausgelöst und behandelt werden, wobei `sender` und <xref:System.Windows.RoutedEventArgs.Source%2A> identisch sind \(dies ist bei Schritt 3 und 4 in der Beispielliste für die Ereignisbearbeitung der Fall\).  
  
 Aufgrund des Tunneling und Bubbling erhalten übergeordnete Elemente Eingabeereignisse, wenn die <xref:System.Windows.RoutedEventArgs.Source%2A> eines ihrer untergeordneten Elemente darstellt.  Wenn Sie wissen müssen, welches das Quellelement ist, können Sie das Quellelement durch Zugreifen auf die <xref:System.Windows.RoutedEventArgs.Source%2A>\-Eigenschaft ermitteln.  
  
 Normalerweise werden keine weiteren Handler aufgerufen, sobald das Eingabeereignis als <xref:System.Windows.RoutedEventArgs.Handled%2A> markiert wurde.  In der Regel sollten Sie Eingabeereignisse als behandelt markieren, wenn ein Handler aufgerufen wird, der sich auf die anwendungsspezifische logische Behandlung der Bedeutung des Eingabeereignisses bezieht.  
  
 Eine Ausnahme zu dieser allgemeinen Aussage zum <xref:System.Windows.RoutedEventArgs.Handled%2A>\-Status besteht darin, dass Eingabeereignishandler, die so registriert wurden, dass sie den <xref:System.Windows.RoutedEventArgs.Handled%2A>\-Status der Ereignisdaten gezielt ignorieren, auf beiden Routen dennoch ausgelöst werden.  Weitere Informationen finden Sie unter [Vorschauereignisse](../../../../docs/framework/wpf/advanced/preview-events.md) oder unter [Markieren von Routingereignissen als behandelt und Klassenbehandlung](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md).  
  
 Das Modell der gemeinsam verwendeten Ereignisdaten zwischen Tunneling\- und Bubbling\-Ereignissen sowie die sequenzielle Auslösung erst der Tunneling\- und dann der Bubbling\-Ereignisse ist kein Konzept, das für alle Routingereignisse gilt.  Die spezifische Implementierung des Verhaltens hängt davon ab, wie die Eingabeereignispaare von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eingabegeräten ausgelöst und verbunden werden.  Die Implementierung eigener Eingabeereignisse stellt ein erweitertes Szenario dar, Sie können sich jedoch auch bei eigenen Eingabeereignissen nach diesem Modell richten.  
  
 Manche Klassen wählen die Klassenbehandlung für bestimmte Eingabeereignisse, in der Regel mit dem Zweck, die Bedeutung eines bestimmten benutzergesteuerten Eingabeereignisses innerhalb dieses Steuerelements neu zu definieren und ein neues Ereignis auszulösen.  Weitere Informationen finden Sie unter [Markieren von Routingereignissen als behandelt und Klassenbehandlung](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md).  
  
 Weitere Informationen zur Eingabe und zur Interaktion zwischen Eingaben und Ereignissen in typischen Anwendungsszenarien finden Sie unter [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md).  
  
<a name="events_styles"></a>   
## EventSetters und EventTriggers  
 In Stilen können Sie manche vordeklarierte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Ereignisbehandlungssyntax mithilfe eines <xref:System.Windows.EventSetter> im Markup einschließen.  Wenn der Stil angewendet wird, wird der referenzierte Handler zur formatierten Instanz hinzugefügt.  Sie können einen <xref:System.Windows.EventSetter> nur für ein Routingereignis deklarieren.  Im Folgenden finden Sie ein Beispiel.  Beachten Sie, dass sich die hier beschriebene `b1SetColor`\-Methode in einer Code\-Behind\-Datei befindet.  
  
 [!code-xml[EventOvwSupport#XAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EventOvwSupport/CSharp/page2.xaml#xaml2)]  
  
 Der Vorteil hierbei besteht darin, dass der Stil zahlreiche andere Informationen enthält, die auf alle anderen Schaltflächen in der Anwendung angewendet werden könnten, und wenn der <xref:System.Windows.EventSetter> Teil dieses Stils ist, wird die Wiederverwendung von Code selbst auf Markupebene erleichtert.  Zudem abstrahiert ein <xref:System.Windows.EventSetter> Methodennamen für Handler, die einen Schritt von der allgemeinen Anwendung und dem Seitenmarkup entfernt sind.  
  
 Eine andere spezialisierte Syntax, in der die Routingereignis\- und Animationsfeatures von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kombiniert werden, ist ein <xref:System.Windows.EventTrigger>.  Wie bei einem <xref:System.Windows.EventSetter> dürfen für einen <xref:System.Windows.EventTrigger> nur Routingereignisse verwendet werden. In der Regel wird ein <xref:System.Windows.EventTrigger> als Teil eines Stils deklariert, ein <xref:System.Windows.EventTrigger> kann jedoch auch als Teil der <xref:System.Windows.FrameworkElement.Triggers%2A>\-Auflistung oder in einer <xref:System.Windows.Controls.ControlTemplate> für Elemente auf Seitenebene deklariert werden. Mit einem <xref:System.Windows.EventTrigger> können Sie ein <xref:System.Windows.Media.Animation.Storyboard> angeben, das immer dann ausgeführt wird, wenn ein Routingereignis ein Element auf seiner Route erreicht hat, das einen <xref:System.Windows.EventTrigger> für dieses Ereignis deklariert.  Der Vorteil eines <xref:System.Windows.EventTrigger> gegenüber der bloßen Behandlung des Ereignisses, das ein vorhandenes Storyboard startet, besteht darin, dass ein <xref:System.Windows.EventTrigger> eine bessere Steuerung des Storyboards und seines Laufzeitverhaltens ermöglicht. Weitere Informationen finden Sie unter [Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
<a name="more_about"></a>   
## Weitere Informationen zu Routingereignissen  
 In diesem Thema werden Routingereignisse vor allem durch Beschreiben der grundsätzlichen Konzepte erläutert. Außerdem erhalten Sie Hinweise dazu, wie und wann Sie auf die Routingereignisse reagieren sollten, die bereits in den verschiedenen grundlegenden Elementen und Steuerelementen enthalten sind.  Sie können jedoch ein eigenes Routingereignis für Ihre benutzerdefinierte Klasse erstellen, einschließlich der notwendigen Hilfsmittel, wie z. B. spezialisierte Ereignisdatenklassen und \-delegaten.  Jede Klasse kann Eigentümer des Routingereignisses sein, um einen echten Nutzen zu erbringen, müssen Routingereignisse jedoch von abgeleiteten <xref:System.Windows.UIElement>\- oder <xref:System.Windows.ContentElement>\-Klassen ausgelöst und behandelt werden.  Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Erstellen eines benutzerdefinierten Routingereignisses](../../../../docs/framework/wpf/advanced/how-to-create-a-custom-routed-event.md).  
  
## Siehe auch  
 <xref:System.Windows.EventManager>   
 <xref:System.Windows.RoutedEvent>   
 <xref:System.Windows.RoutedEventArgs>   
 [Markieren von Routingereignissen als behandelt und Klassenbehandlung](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)   
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md)   
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)   
 [Schwache Ereignismuster](../../../../docs/framework/wpf/advanced/weak-event-patterns.md)