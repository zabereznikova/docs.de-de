---
title: "WPF-Architektur | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Affinitäts-Thread"
  - "Architektur"
  - "Angefügte Eigenschaften"
  - "Klassen, System.Object"
  - "Klassen, System.Threading.DispatcherObject"
  - "Klassen, System.Windows.Controls.Control"
  - "Klassen, System.Windows.DependencyObject"
  - "Klassen, System.Windows.FrameworkElement"
  - "Klassen, System.Windows.Media.Visual"
  - "Klassen, System.Windows.UIElement"
  - "CommandBindings"
  - "Komponenten, unmanaged"
  - "Control-Klasse"
  - "Datenvorlagen"
  - "DependencyObject-Klasse"
  - "DispatcherObject-Klasse"
  - "FrameworkElement-Klasse"
  - "INotifyPropertyChange-Schnittstelle"
  - "Schnittstellen, INotifyPropertyChange"
  - "milcore"
  - "Maleralgorithmus"
  - "Eigenschaften, Angefügt"
  - "Storyboards"
  - "System.Object-Klasse"
  - "System.Threading.DispatcherObject-Klasse"
  - "System.Windows.Controls.Control-Klasse"
  - "System.Windows.DependencyObject-Klasse"
  - "System.Windows.FrameworkElement-Klasse"
  - "System.Windows.Media.Visual-Klasse"
  - "System.Windows.UIElement-Klasse"
  - "Thread, Affinität"
  - "UIElement-Klasse"
  - "Nicht verwaltete Komponenten"
  - "Visuelle Klasse"
ms.assetid: 8579c10b-76ab-4c52-9691-195ce02333c8
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# WPF-Architektur
Dieses Thema enthält eine Einführung in die Klassenhierarchie von [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  Es behandelt die meisten der wichtigsten Subsysteme von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] und beschreibt deren Interaktion.  Außerdem enthält dieses Thema ausführliche Erläuterungen zu einigen Entscheidungen der Architekten von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="System_Object"></a>   
## System.Object  
 Das primäre [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Programmiermodell wird mithilfe von verwaltetem Code bereitgestellt.  Am Anfang der Entwurfsphase von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] gab es einige Diskussionen darüber, wo die Linie zwischen den im System verwalteten Komponenten und den nicht verwalteten gezogen werden sollte.  Die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] stellt eine Reihe von Features bereit, die zu einer produktiveren und robusteren Entwicklung führen \(einschließlich Speicherverwaltung, Fehlerbehandlung, allgemeines Typsystem usw.\), die jedoch auch ihren Preis haben.  
  
 Die Hauptkomponenten von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] werden in der folgenden Abbildung veranschaulicht.  Die roten Abschnitte des Diagramms \(PresentationFramework, PresentationCore und milcore\) stellen die Hauptbestandteile des Codes von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] dar.  Von den hier dargestellten Komponenten wird lediglich eine Komponente nicht verwaltet – milcore.  Milcore ist in einem nicht verwalteten Code geschrieben, um eine enge Integration mit [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] zu ermöglichen.  Alle Anzeigen in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] erfolgen durch das [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]\-Modul, um ein effizientes Hardware\- und Softwarerendering zu gewährleisten.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] erforderte außerdem eine Feinsteuerung des Speichers und der Ausführung.  Das Erstellungsmodul in milcore ist äußerst leistungsabhängig und erforderte im Sinne der Leistungsverbesserung die Aufgabe vieler [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Vorteile.  
  
 ![Die Position von WPF im .NET Framework.](../../../../docs/framework/wpf/advanced/media/wpf-architect1.png "wpf\_architect1")  
  
 Die Kommunikation zwischen den verwalteten und nicht verwalteten Bereichen in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] wird weiter unten in diesem Thema erläutert.  Das restliche verwaltete Programmiermodell wird nachfolgend beschrieben.  
  
<a name="System_Threading_DispatcherObject"></a>   
## System.Threading.DispatcherObject  
 Die meisten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Objekte werden aus <xref:System.Windows.Threading.DispatcherObject> abgeleitet, in dem die grundlegenden Konstrukte zur Handhabung von Parallelität und Threading bereitgestellt werden.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] basiert auf einem vom Verteiler implementierten Nachrichtensystem.  Die Funktionsweise ist mit der bekannten Meldungsverteilschleife in [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] zu vergleichen. Tatsächlich verwendet der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Verteiler User32\-Meldungen zum Ausführen von threadübergreifenden Aufrufen.  
  
 Zur Behandlung des Themas Parallelität in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] müssen tatsächlich zwei Kernkonzepte erfasst werden – Verteiler und Threadaffinität.  
  
 Während der Entwurfsphase von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bestand das Ziel darin, auf einen einzelnen Ausführungsthread, jedoch unter Verwendung eines "Affinitätsmodells" ohne Thread, umzusteigen.  Eine Threadaffinität tritt auf, wenn eine Komponente die Identität des ausgeführten Threads verwendet, um irgendeinen Zustandstyp zu speichern.  Die häufigste Verwendungsform dafür ist das Speichern eines Zustands im lokalen Threadspeicher \(TLS\).  Threadaffinität erfordert, dass jeder logische Ausführungsthread nur von einem physischen Thread im Betriebssystem verwendet wird, was zu einer speicherintensiven Verarbeitung führen kann.  Letztendlich wurde eine Übereinstimmung zwischen dem Threadingmodell in WPF und dem bestehenden User32\-Threadingmodell erzielt, wonach ein einzelner Ausführungsthread mit Threadaffinität verwendet wird.  Der Hauptgrund hierfür liegt in der Interoperabilität – Systeme wie [!INCLUDE[TLA2#tla_ole2.0](../../../../includes/tla2sharptla-ole2-0-md.md)], die Zwischenablage und der Internet Explorer erfordern alle die Singlethread\-Affinitätsausführung \(STA, Single Thread Affinity\).  
  
 Wenn Sie Objekte mit STA\-Threading einsetzen, benötigen Sie eine Möglichkeit zur Kommunikation zwischen den Threads und zur Validierung des korrekten Threads.  Dies ist die Rolle des Verteilers.  Der Verteiler ist ein Basissystem zur Verteilung von Meldungen mit mehreren priorisierten Warteschlangen.  Zu den Meldungen gehören z. B. Benachrichtigungen für unformatierte Eingaben \(Mausbewegung\), Framework\-Funktionen \(Layout\) oder Benutzerbefehle \(diese Methode ausführen\).  Durch das Ableiten aus <xref:System.Windows.Threading.DispatcherObject> erstellen Sie ein [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objekt mit STA\-Verhalten, das zum Zeitpunkt der Erstellung mit einem Zeiger auf den Verteiler versehen wird.  
  
<a name="System_Windows_DependencyObject"></a>   
## System.Windows.DependencyObject  
 Eine der primären Strategien bei der Entwicklung der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Architektur war die Bevorzugung von Eigenschaften vor der Verwendung von Methoden oder Ereignissen.  Eigenschaften sind deklarativ und ermöglichen Ihnen eine einfachere Angabe von Absichten anstatt von Aktionen.  Außerdem wird dadurch ein modell\- oder datengesteuertes System für die Anzeige der Benutzerflächeninhalte unterstützt.  Diese Philosophie hatte den beabsichtigten Effekt, dass mehr Eigenschaften erstellt werden als gebunden werden können, um das Verhalten einer Anwendung besser steuern zu können.  
  
 Um mehr Systemkomponenten eigenschaftengesteuert verwenden zu können, war ein umfassenderes Eigenschaftensystem als das in der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] bereitgestellte erforderlich.  Ein einfaches Beispiel für diese Leistungsfähigkeit sind Änderungsbenachrichtigungen.  Um bidirektionale Bindungen zu ermöglichen, müssen beide Seiten der Bindung Änderungsbenachrichtigungen unterstützen.  Um das Verhalten an die Eigenschaftswerte zu binden, müssen Sie benachrichtigt werden, sobald sich der Eigenschaftswert ändert.  Das [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] verfügt über die Schnittstelle **INotifyPropertyChange**, mit der Objekte Änderungsbenachrichtigungen veröffentlichen können; die Verwendung ist jedoch optional.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] stellt ein umfangreicheres Eigenschaftensystem bereit, das vom <xref:System.Windows.DependencyObject>\-Typ abgeleitet wird.  Das Eigenschaftensystem ist insofern wirklich ein Abhängigkeitseigenschaftensystem, als es die Abhängigkeiten zwischen den Eigenschaftsausdrücken erfasst und im Falle von Abhängigkeitsänderungen die Eigenschaftswerte automatisch erneut überprüft.  Wenn Sie z. B. eine Eigenschaft verwenden, die Werte erbt \(z. B. <xref:System.Windows.Controls.Control.FontSize%2A>\), wird das System automatisch aktualisiert, wenn sich die Eigenschaft in einem übergeordneten Element des Elements ändert, das den Wert erbt.  
  
 Das [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Eigenschaftensystem basiert auf dem Konzept eines Eigenschaftsausdrucks.  In dieser ersten Version von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ist das Eigenschaftsausdrucksystem in sich geschlossen, und die Ausdrücke werden alle als Bestandteil des Frameworks bereitgestellt.  Ausdrücke sind der Grund dafür, warum das Eigenschaftensystem keine hartcodierte Datenbindung, Formatierung oder Vererbung aufweist, sondern diese in höheren Ebenen im Framework bereitstellt.  
  
 Das Eigenschaftensystem ermöglicht außerdem das Speichern von Eigenschaftswerten in einem kompakten Speicherformat.  Da Objekte über Dutzende \(wenn nicht über Hunderte\) von Eigenschaften verfügen können und sich die meisten Werte im Standardzustand \(geerbt, von Stilen festgelegt usw.\) befinden, besteht keine Notwendigkeit, die gesamten Eigenschaften für jede Instanz eines Objekts definieren zu müssen.  
  
 Als letztes neues Feature des Eigenschaftensystems sind die [angefügten Eigenschaften](GTMT) zu nennen.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Elemente sind auf dem Prinzip der Erstellung und der Wiederverwendung von Komponenten aufgebaut.  Es ist häufig der Fall, dass ein enthaltendes Element \(z. B. ein <xref:System.Windows.Controls.Grid>\-Layoutelement\) zusätzliche Daten zu untergeordneten Elementen benötigt, um sein Verhalten zu steuern \(z. B. die Zeilen\-\/Spalteninformationen\).  Anstatt alle diese Eigenschaften mit jedem einzelnen Element zu verknüpfen, ist es für jedes beliebige Objekt möglich, jedem anderen Objekt Eigenschaftendefinitionen bereitzustellen.  Dies ist mit den expando\-Features von JavaScript zu vergleichen.  
  
<a name="System_Windows_Media_Visual"></a>   
## System.Windows.Media.Visual  
 Nachdem ein System definiert ist, besteht der nächste Schritt darin, Bildelemente auf den Bildschirm zu zeichnen.  Mithilfe der <xref:System.Windows.Media.Visual>\-Klasse kann eine Struktur von visuellen Objekten erstellt werden, in der jedes Objekt optional Zeichnungsanweisungen und Metadaten zum Rendern dieser Anweisungen \(Clipping, Transformation usw.\) enthalten kann.  <xref:System.Windows.Media.Visual> wurde im Hinblick auf eine äußerst einfache und flexible Lösung entwickelt, sodass die meisten Features keine öffentliche [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]\-Verfügbarkeit aufweisen und stark von geschützten Rückruffunktionen abhängen.  
  
 <xref:System.Windows.Media.Visual> ist tatsächlich der Einstiegspunkt zum [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Erstellungssystem.  <xref:System.Windows.Media.Visual> ist der Verbindungspunkt zwischen diesen beiden Subsystemen: der verwalteten [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] und dem nicht verwalteten milcore.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] zeigt Daten an, indem die nicht verwalteten Datenstrukturen \(in milcore verwaltet\) durchlaufen werden.  Diese Strukturen werden Strukturknoten genannt und stellen eine hierarchische Anzeigestruktur mit Renderinganweisungen in jedem Knoten dar.  Auf diese Struktur \(auf der rechten Seite der folgenden Abbildung dargestellt\) kann nur über ein Nachrichtenprotokoll zugegriffen werden.  
  
 Bei der Programmierung von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] erstellen Sie <xref:System.Windows.Media.Visual>\-Elemente und abgeleitete Typen, die intern mithilfe dieses Nachrichtenprotokolls mit der zusammengesetzten Struktur kommunizieren.  Jedes <xref:System.Windows.Media.Visual>\-Element in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] kann einen, keinen oder mehrere Strukturknoten erstellen.  
  
 ![Die visuelle Struktur der Windows Presentation Foundation](../../../../docs/framework/wpf/advanced/media/wpf-architecture2.png "wpf\_architecture2")  
  
 An dieser Stelle ist ein äußerst wichtiges architektonisches Detail zu beachten: Die gesamte Struktur der visuellen Elemente und Zeichnungsanweisungen wird im Cache gespeichert.  Im Hinblick auf Grafiken verwendet [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ein Renderingsystem mit Speichermodus.  Dadurch ist es dem System möglich, Zeichnungen mit hohen Aktualisierungsraten erneut darzustellen, ohne das Erstellungssystem durch Rückrufe an den Benutzercode blockieren zu müssen.  Auf diese Weise können Sie dem Anschein einer nicht reagierenden Anwendung vorbeugen.  
  
 Ein anderes wichtiges, im Diagramm nicht wirklich erkennbares Detail, ist die Art und Weise, wie das System tatsächlich die Zusammensetzung der Komponenten ausführt.  
  
 In User32 und [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] verwendet das System ein Clippingsystem mit unmittelbarem Modus.  Wenn eine Komponente gerendert werden muss, erstellt das System eine Clippinggrenze, außerhalb derer die Komponente keine Pixel anfassen darf. Daraufhin wird die Komponente aufgefordert, die Bildelemente in dieses Feld zu zeichnen.  Das System kann sehr gut in Systemen mit eingeschränktem Speicher eingesetzt werden, da im Fall von Änderungen nur die davon betroffene Komponente zu ändern ist. Die Farbe eines einzelnen Pixels wird niemals von zwei Komponenten beeinflusst.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] verwendet ein Zeichnungsmodell mit einem Maleralgorithmus.  Dies bedeutet, dass die einzelnen Komponenten nicht geclippt werden, sondern einzeln vom Hintergrund bis hin zum Vordergrund der Anzeige gerendert werden.  Dadurch kann jede Komponente die Anzeige der vorherigen Komponente übermalen.  Der Vorteil dieses Modells ist, dass komplexe Formen verwendet werden können, die teilweise transparent sind.  Mit der heutigen modernen Grafikhardware ist dieses Modell relativ schnell \(was nicht der Fall war, als User32\/[!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] entwickelt wurde\).  
  
 Wie bereits erwähnt, sieht die Kernphilosophie von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] vor, ein eher deklaratives, eigenschaftenorientiertes Programmiermodell einzusetzen.  Im visuellen System zeigt sich dies an ein paar interessanten Stellen.  
  
 Erstens: Wenn Sie das Grafiksystem mit Speichermodus betrachten, bewegt sich dieses tatsächlich weg von einem imperativen DrawLine\/DrawLine\-Typmodell hin zu einem datenorientierten Modell – new Line\(\)\/new Line\(\).  Der Schritt hin zu einem datengesteuerten Rendering ermöglicht es, dass komplexe Vorgänge in den Zeichnungsanweisungen anhand von Eigenschaften angegeben werden können.  Die aus <xref:System.Windows.Media.Drawing> abgeleiteten Typen sind gewissermaßen das zu rendernde Objektmodell.  
  
 Zweitens: Wenn Sie das Animationssystem näher betrachten, werden Sie feststellen, dass es fast vollständig deklarativ ist.  Anstatt einen Entwickler für die Berechnung der nächsten Position oder Farbe zu benötigen, können Sie Animationen als eine Gruppe von Eigenschaften für ein Animationsobjekt angeben.  Diese Animationen geben dann die Absicht des Entwicklers oder Designers an \(diese Schaltfläche von hier nach dort in 5 Sekunden bewegen\), und das System ermittelt den effizientesten Weg zur Erreichung dieses Ziels.  
  
<a name="System_Windows_UIElement"></a>   
## System.Windows.UIElement  
 <xref:System.Windows.UIElement> definiert Kernsubsysteme einschließlich Layouts, Eingaben und Ereignisse.  
  
 Layouts stellen ein Kernkonzept in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] dar.  Viele Systeme enthalten entweder einen festen Satz an Layoutmodellen \(HTML unterstützt drei Layoutmodelle: fortlaufende, absolute und Tabellen\) oder keine Layoutmodelle \(User32 unterstützt nur die absolute Positionierung\).  Die Vorgaben für [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] gingen von der Annahme aus, dass Entwickler und Designer ein flexibles, erweiterbares Layoutmodell benötigten, das nicht von einer imperativen Logik, sondern von Eigenschaftswerten gesteuert werden sollte.  Auf der <xref:System.Windows.UIElement>\-Ebene wird der Basisvertrag für das Layout eingeführt – ein Zweiphasenmodell mit <xref:System.Windows.UIElement.Measure%2A>\-Durchläufen und <xref:System.Windows.UIElement.Arrange%2A>\-Durchläufen.  
  
 Anhand von <xref:System.Windows.UIElement.Measure%2A> kann eine Komponente seine Größe bestimmen.  Hierbei handelt es sich um eine von <xref:System.Windows.UIElement.Arrange%2A> getrennte Phase, da viele Situationen auftreten können, in denen ein übergeordnetes Element ein untergeordnetes Element auffordert, mehrere Measures zur Ermittlung seiner optimalen Position und Größe auszuführen.  Die Tatsache, dass untergeordnete Elemente von übergeordneten Elementen zur Durchführung von Measures aufgefordert werden, verdeutlicht eine andere Schlüsselphilosophie von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] – Das Anpassen der Größe an den Inhalt.  Alle Steuerelemente in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] unterstützen die Fähigkeit, sich an die natürliche Größe ihres Inhalts anzupassen.  Dies führt zu einer einfacheren Lokalisierung und ermöglicht aufgrund der Größenanpassung ein dynamisches Elementlayout.  Anhand der <xref:System.Windows.UIElement.Arrange%2A>\-Phase kann ein übergeordnetes Element jedes untergeordnete Element positionieren und dessen endgültige Größe bestimmen.  
  
 Der Aspekt der Ausgabe in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], nämlich die Ausgabe der <xref:System.Windows.Media.Visual>\-Objekte und der verwandten Objekte, wird häufig sehr zeitintensiv besprochen.  Es gibt jedoch auch auf der Seite der Eingabe enorme Innovationen zu verzeichnen.  Eine der grundlegendsten Änderungen im Eingabemodell von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ist wahrscheinlich das einheitliche Modell, durch das Eingabeereignisse im System weitergeleitet werden.  
  
 Eingaben entstehen als ein Signal in einem Gerätetreiber im Kernelmodus und werden an den korrekten Prozess und Thread mithilfe eines komplexen Prozesses, der den Kernel von Windows und User32 einbezieht, weitergeleitet.  Nachdem für die Eingabe die entsprechende User32\-Meldung an [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] weitergeleitet wurde, wird sie in eine unformatierte [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Eingabemeldung konvertiert und an den Verteiler übermittelt.  In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] können unformatierte Eingabeereignisse in mehrere tatsächliche Ereignisse konvertiert werden, wodurch Features wie "MouseEnter" auf einer niedrigen Systemebene mit Zustellungsgewährleistung implementiert werden können.  
  
 Jedes Eingabeereignis wird in mindestens zwei Ereignisse konvertiert – in ein "Vorschauereignis" und in das tatsächliche Ereignis.  Alle [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Ereignisse können innerhalb der Elementstruktur weitergeleitet werden.  Ereignisse steigen "in Blasen" auf, wenn sie von einem Ziel entlang der Struktur nach oben bis zum Stamm traversieren. Sie arbeiten nach dem Tunnelprinzip, wenn sie vom Stamm ausgehend nach unten zu einem Ziel traversieren.  Eingabenvorschauereignisse nutzen das Tunnelprinzip, wodurch jedes in der Struktur enthaltene Element das Ereignis filtern oder eine Ereignismaßnahme ergreifen kann.  Die regulären Ereignisse \(keine Vorschauereignisse\) steigen dann vom Ziel hoch zum Stamm auf.  
  
 Diese Unterteilung zwischen der Tunnel\- und Aufstiegsphase ermöglicht eine einheitliche Implementierung von Features \(z. B. von Zugriffstasten\) in einer gemischten Umgebung.  In User32 würden Sie Zugriffstasten anhand einer einzelnen globalen Tabelle implementieren, die alle zu unterstützenden Zugriffstasten \(Strg\+N mit "Neu" verknüpft\) enthält.  In dem Verteiler Ihrer Anwendung würden Sie **TranslateAccelerator** aufrufen, der die Eingabemeldungen in User32 einliest und ermittelt, ob eine Übereinstimmung mit einer registrierten Zugriffstaste besteht.  In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] würde dies nicht funktionieren, da das System vollständig zusammensetzbar ist, d. h., jedes Element kann jede beliebige Zugriffstaste verarbeiten und verwenden.  Dieses eingabenrelevante Zweiphasenmodell ermöglicht es Komponenten, den eigenen "TranslateAccelerator" zu implementieren.  
  
 Darüber hinaus führt <xref:System.Windows.UIElement> das Konzept der CommandBindings ein.  Mithilfe des [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Befehlssystem können Entwickler Funktionalitäten in Form von Befehlsendpunkten definieren – etwas, wodurch <xref:System.Windows.Input.ICommand> implementiert wird.  Befehlsbindungen ermöglichen, dass Elemente die Zuordnung einer Eingabeaktion \(Strg\+N\) zu einem Befehl \(Neu\) definieren können.  Sowohl Eingabeaktionen als auch Befehlsdefinitionen sind erweiterbar und können zum Zeitpunkt der Verwendung miteinander verknüpft werden.  Dadurch können Endbenutzer z. B. die in einer Anwendung zu verwendenden Tastenbindungen überaus einfach anpassen.  
  
 In diesem Thema wurden bislang hauptsächlich die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Kernfeatures, d. h. die in der PresentationCore\-Assembly implementierten Features, veranschaulicht.  Das gewünschte Ergebnis beim Aufbau von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] war eine klare Trennung zwischen den grundlegenden Bestandteilen \(z. B. der Vertrag für das Layout mit **Measure** und **Arrange**\) und den Framework\-Bestandteilen \(z. B. der Implementierung eines bestimmten Layouts wie <xref:System.Windows.Controls.Grid>\).  Das Ziel bestand darin, einen Erweiterungspunkt weit unten im Stapel bereitzustellen, durch den externe Entwickler ihre eigenen Frameworks bei Bedarf erstellen könnten.  
  
<a name="System_Windows_FrameworkElement"></a>   
## System.Windows.FrameworkElement  
 <xref:System.Windows.FrameworkElement> kann auf zwei verschiedene Weisen betrachtet werden.  Es umfasst eine Reihe von Richtlinien und Anpassungen für die Subsysteme, die in niedrigeren Ebenen von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enthalten sind.  Außerdem führt es eine Reihe neuer Subsysteme ein.  
  
 Die primäre Richtlinie in <xref:System.Windows.FrameworkElement> bezieht sich auf das Anwendungslayout.  <xref:System.Windows.FrameworkElement>baut auf dem von <xref:System.Windows.UIElement> eingeführten grundlegenden Layoutvertrag auf und fügt das Konzept eines "Layoutplatzes" hinzu, was dazu führt, dass die Layoutautoren leichter auf eine einheitliche eigenschaftengesteuerte Layoutsemantik zugreifen können.  Eigenschaften wie <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.MinWidth%2A> und <xref:System.Windows.FrameworkElement.Margin%2A> \(um nur ein paar zu nennen\) weisen allen Komponenten, die aus <xref:System.Windows.FrameworkElement> abgeleitet sind, ein einheitliches Verhalten innerhalb eines Layoutcontainers zu.  
  
 Mit <xref:System.Windows.FrameworkElement> ist es auch einfacher, eine [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] vielen der in den Kernebenen von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enthaltenen Features zur Verfügung zu stellen.  Zum Beispiel stellt das <xref:System.Windows.FrameworkElement>\-Element einen Direktzugriff auf Animationen durch die <xref:System.Windows.FrameworkElement.BeginStoryboard%2A>\-Methode bereit.  Ein <xref:System.Windows.Media.Animation.Storyboard>\-Element bietet eine Möglichkeit, mehrere Animationen in einem Skript eigenschaftsabhängig anzugeben.  
  
 Die beiden entscheidendsten Features von <xref:System.Windows.FrameworkElement> sind Datenbindung und Stile.  
  
 Das in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enthaltene Datenbindungssubsystem müsste jedem relativ bekannt sein, der eine [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] für eine Anwendung erstellt hat und dafür [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] oder [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)] verwendet hat.  In jedem dieser Systeme gibt es eine einfache Möglichkeit, um auszudrücken, dass eine oder mehrere Eigenschaften eines bestimmten Elements an bestimmte Daten gebunden werden sollen.  Eigenschaftenbindung, Transformation und Listenbindung werden in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] in vollem Umfang unterstützt.  
  
 Eines der interessantesten Features der Datenbindung in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ist die Einführung von Datenvorlagen.  Datenvorlagen ermöglichen eine deklarative Angabe darüber, wie Daten visualisiert werden sollen.  Anstatt eine benutzerdefinierte Benutzeroberfläche zu erstellen, die an Daten gebunden werden kann, können Sie das Problem von der anderen Seite angehen, indem Sie die Daten die zu erstellende Anzeige bestimmen lassen.  
  
 Das Formatieren stellt eine einfache Form der Datenbindung dar.  Anhand der Formatierung können Sie die in einer freigegebenen Definition enthaltenen Eigenschaften an eine oder mehrere Elementinstanzen binden.  Stile können auf ein Element angewendet werden, indem sie entweder explizit \(durch die Einstellung der <xref:System.Windows.FrameworkElement.Style%2A>\-Eigenschaft\) oder implizit, durch die Verknüpfung eines Stils mit dem [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Typ des Elements, angegeben werden.  
  
<a name="System_Windows_Controls_Control"></a>   
## System.Windows.Controls.Control  
 Das bedeutendste Feature von Control ist die Vorlagenverwendung.  Betrachten Sie das Erstellungssystem in WPF als Renderingsystem mit Speichermodus, in dem Steuerelemente ihr Rendering anhand von Vorlagen in einer parametrisierten, deklarativen Form darstellen können.  Eine <xref:System.Windows.Controls.ControlTemplate> ist lediglich ein Skript zur Erstellung von untergeordneten Elementen, das Bindungen zu den im Steuerelement enthaltenen Eigenschaften vorsieht.  
  
 <xref:System.Windows.Controls.Control> stellt eine Reihe von vordefinierten Eigenschaften wie <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Padding%2A> \(um nur einige zu nennen\) bereit, die von den Autoren der Vorlagen verwendet werden können, um die Anzeige eines Steuerelements anzupassen.  Die Implementierung eines Steuerelements umfasst ein Datenmodell und ein Interaktionsmodell.  Das Interaktionsmodell definiert eine Reihe von Befehlen \(z. B. für das Schließen eines Fensters\) sowie Bindungen zu Eingabeaktionen \(z. B. wenn auf das rote X der oberen Fensterecke geklickt wird\).  Das Datenmodell stellt Eigenschaften bereit, um entweder das Interaktionsmodell oder die Anzeige \(wird von der Vorlage bestimmt\) anpassen zu können.  
  
 Durch diese Unterteilung in Datenmodell \(Eigenschaften\), Interaktionsmodell \(Befehle und Ereignisse\) und Anzeigemodell \(Vorlagen\) können das Erscheinungsbild und das Verhalten eines Steuerelements vollständig angepasst werden.  
  
 Ein allgemeiner Aspekt des Datenmodells von Steuerelementen ist das Inhaltsmodell.  Wenn Sie z. B. das Steuerelement <xref:System.Windows.Controls.Button>, betrachten, stellen Sie fest, dass es über die Eigenschaft namens "Content" vom Typ <xref:System.Object> verfügt.  In [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] und [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)] würde es sich bei dieser Eigenschaft normalerweise um eine Zeichenfolge handeln, was jedoch den Typ des Inhalts einschränkt, mit dem eine Schaltfläche versehen werden kann.  Der Inhalt einer Schaltfläche kann entweder eine einfache Zeichenfolge, ein komplexes Datenobjekt oder eine komplette Elementstruktur sein.  Wenn es sich um ein Datenobjekt handelt, wird für die Erstellung der Anzeige eine Datenvorlage verwendet.  
  
<a name="Summary"></a>   
## Zusammenfassung  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ist für die Erstellung von dynamischen, datengesteuerten Präsentationssystemen konzipiert.  Die einzelnen Bestandteile des Systems eignen sich für die Objekterstellung anhand von Eigenschaften, die das Verhalten steuern.  Datenbindung ist ein wesentlicher und auf jeder Ebene integrierter Systembestandteil.  
  
 Herkömmliche Anwendungen erstellen eine Anzeige und daraufhin eine Bindung zu bestimmten Daten.  In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] werden sämtliche Informationen zu einem Steuerelement sowie jeder Aspekt der Anzeige durch eine bestimmte Art der Datenbindung generiert.  Der in einer Schaltfläche enthaltene Text wird angezeigt, indem in der Schaltfläche ein zusammengesetztes Steuerelement erstellt und dessen Anzeige an die Inhaltseigenschaft der Schaltfläche gebunden wird.  
  
 Wenn Sie mit der Entwicklung von Anwendungen auf der Basis von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] beginnen, wird Ihnen etliches bereits vertraut sein.  Die Verfahren zum Festlegen von Eigenschaften, zum Verwenden von Objekten und zum Binden von Daten sind in vielerlei Hinsicht den entsprechenden Verfahren in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] oder [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)] ähnlich.  Wenn Sie sich mit der Architektur von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eingehender auseinandersetzen, werden Sie die Möglichkeiten zur Erstellung von komplexeren Anwendungen entdecken, in denen Daten im Wesentlichen als Kernantrieb der Anwendung behandelt werden.  
  
## Siehe auch  
 <xref:System.Windows.Media.Visual>   
 <xref:System.Windows.UIElement>   
 <xref:System.Windows.Input.ICommand>   
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.Threading.DispatcherObject>   
 <xref:System.Windows.Input.CommandBinding>   
 <xref:System.Windows.Controls.Control>   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Layout](../../../../docs/framework/wpf/advanced/layout.md)   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)