---
title: Aufbau
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], attached
- attached properties [WPF]
- architecture [WPF]
- unmanaged components [WPF]
- affinity thread [WPF]
- Storyboards [WPF]
- milcore [WPF]
- components [WPF], unmanaged
- painter's algorithm
- interfaces [WPF], INotifyPropertyChange
- CommandBindings [WPF]
- data templates [WPF]
- thread [WPF], affinity
ms.assetid: 8579c10b-76ab-4c52-9691-195ce02333c8
ms.openlocfilehash: b16be8470a47f3e8e362feb0b13e10aa901baacb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187121"
---
# <a name="wpf-architecture"></a>WPF-Architektur
Dieses Thema bietet eine Führung durch die WPF-Klassenhierarchie (Windows Presentation Foundation). Es deckt die meisten der wichtigsten Subsysteme von WPF ab und beschreibt, wie sie interagieren. Es beschreibt auch einige der Entscheidungen, die von den Architekten von WPF getroffen wurden.  

<a name="System_Object"></a>
## <a name="systemobject"></a>System.Object  
 Das primäre WPF-Programmiermodell wird durch verwalteten Code verfügbar gemacht. Zu Beginn der Entwurfsphase von WPF gab es eine Reihe von Debatten darüber, wo die Linie zwischen den verwalteten Komponenten des Systems und den nicht verwalteten gezeichnet werden sollte. Die CLR bietet eine Reihe von Funktionen, die die Entwicklung produktiver und robuster machen (einschließlich Speicherverwaltung, Fehlerbehandlung, allgemeines Typsystem usw.), aber sie haben ihren Preis.  
  
 Die wichtigsten Komponenten von WPF sind in der abbildung unten dargestellt. Die roten Abschnitte des Diagramms (PresentationFramework, PresentationCore und milcore) sind die wichtigsten Codeabschnitte von WPF. Von diesen ist nur eine Komponente nicht verwaltet – Milcore. Milcore wird in nicht verwaltetem Code geschrieben, um eine enge Integration mit DirectX zu ermöglichen. Die gesamte Anzeige in WPF erfolgt über die DirectX-Engine, was ein effizientes Hardware- und Software-Rendering ermöglicht. WPF erforderte auch eine feine Kontrolle über Speicher und Ausführung. Die Kompositions-Engine in milcore ist extrem leistungsempfindlich und erforderte viele Vorteile der CLR, um Leistung zu erzielen.  
  
 ![Die Position von WPF im .NET Framework.](./media/wpf-architect1.PNG "wpf_architect1")  
  
 Die Kommunikation zwischen den verwalteten und nicht verwalteten Teilen von WPF wird weiter unten in diesem Thema erläutert. Das restliche verwaltete Programmiermodell wird nachfolgend beschrieben.  
  
<a name="System_Threading_DispatcherObject"></a>
## <a name="systemthreadingdispatcherobject"></a>System.Threading.DispatcherObject  
 Die meisten Objekte in <xref:System.Windows.Threading.DispatcherObject>WPF leiten sich von ab, was die grundlegenden Konstrukte für den Umgang mit Parallelität und Threading bereitstellt. WPF basiert auf einem Messagingsystem, das vom Dispatcher implementiert wurde. Dies funktioniert ähnlich wie die vertraute Win32-Nachrichtenpumpe; Tatsächlich verwendet der WPF-Dispatcher User32-Nachrichten zum Ausführen von Crossthreadaufrufen.  
  
 Es gibt wirklich zwei Kernkonzepte zu verstehen, wenn Parallelität in WPF diskutiert wird – der Dispatcher und die Threadaffinität.  
  
 Während der Entwurfsphase von WPF bestand das Ziel darin, zu einem einzelnen Ausführungsthread zu wechseln, aber zu einem nicht-thread"affinisierten" Modell. Thread-Affinität findet dann statt, wenn eine Komponente die Identität des ausgeführten Threads verwendet, um einen irgendwie gearteten Zustand zu speichern. Die häufigste Form dieser Vorgehensweise ist, den threadlokalen Speicher (TLS) zu verwenden, um einen Zustand zu speichern. Thread-Affinität erfordert, dass jeder logische Ausführungsthread im Besitz von nur einem physischen Thread im Betriebssystem ist, was speicherintensiv werden kann. Letzten Endes wurde das WPF-Threadingmodell synchron mit dem bestehenden User32-Threadingmodell einzelner Ausführungsthread mit Threadaffinität gehalten. Der Hauptgrund dafür war die Interoperabilität – Systeme wie OLE 2.0, die Zwischenablage und Internet Explorer erfordern alle die Ausführung einer Single Thread-Affinität (Single Thread-Affinität (SINGLE Thread Affinity, STA).  
  
 Angesichts der Tatsache, dass Sie Objekte mit STA-Threading haben, benötigen Sie Möglichkeiten der Kommunikation zwischen Threads und der Überprüfung, dass Sie sich im richtigen Thread befinden. Genau dies ist die Aufgabe des Verteilers. Der Verteiler ist ein Basis-Nachrichtensystem mit mehreren priorisierten Warteschlangen. Zu diesen Nachrichten gehören z.B. Rohdateneingabe-Benachrichtigungen (Maus bewegt), Framework-Funktionen (Layout) oder Benutzerbefehle (diese Methode ausführen). Indem Sie von <xref:System.Windows.Threading.DispatcherObject>ableiten, erstellen Sie ein CLR-Objekt mit STA-Verhalten und erhalten bei der Erstellung einen Zeiger auf einen Dispatcher.  
  
<a name="System_Windows_DependencyObject"></a>
## <a name="systemwindowsdependencyobject"></a>System.Windows.DependencyObject  
 Eine der wichtigsten Architekturphilosophien, die beim Erstellen von WPF verwendet wurden, war die Vorliebe für Eigenschaften gegenüber Methoden oder Ereignissen. Eigenschaften sind deklarativ und machen es einfacher, eine Absicht statt einer Aktion anzugeben. Dies bot auch Unterstützung für ein modell- oder datengesteuertes System zur Anzeige von Inhalten der Benutzeroberfläche. Diese Strategie hatte den beabsichtigten Effekt, mehr Eigenschaften zu schaffen, an die Sie anbinden können, um das Verhalten einer Anwendung besser zu steuern.  
  
 Um mehr vom System durch Eigenschaften gesteuert zu haben, wurde ein reicheres Eigenschaftensystem benötigt, als die CLR bereitstellt. Ein einfaches Beispiel für diese Vielfalt sind die Änderungsbenachrichtigungen. Um eine zwei-Wege-Bindung zu ermöglichen, müssen beide Seiten der Bindung Änderungsbenachrichtigungen unterstützen. Um an Eigenschaftswerte ein bestimmtes Verhalten zu binden, müssen Sie benachrichtigt werden, wenn sich der Eigenschaftswert ändert. Microsoft .NET Framework verfügt über eine Schnittstelle, **INotifyPropertyChange**, die es einem Objekt ermöglicht, Änderungsbenachrichtigungen zu veröffentlichen, obwohl es optional ist.  
  
 WPF stellt ein umfangreicheres Eigenschaftensystem bereit, das <xref:System.Windows.DependencyObject> vom Typ abgeleitet ist. Dieses Eigenschaftensystem ist in der Tat ein Eigenschaftensystem der „Abhängigkeiten” in dem Sinne, dass es Abhängigkeiten zwischen Eigenschaftsausdrücken nachverfolgt und Eigenschaftswerte automatisch neu überprüft, wenn sich die Abhängigkeiten ändern. Wenn Sie z. B. über eine <xref:System.Windows.Controls.Control.FontSize%2A>Eigenschaft verfügen, die erbt (z. B.), wird das System automatisch aktualisiert, wenn sich die Eigenschaft auf einem übergeordneten Element eines Elements ändert, das den Wert erbt.  
  
 Die Grundlage des WPF-Eigenschaftssystems ist das Konzept eines Eigenschaftsausdrucks. In dieser ersten Version von WPF wird das Eigenschaftenausdruckssystem geschlossen, und die Ausdrücke werden alle als Teil des Frameworks bereitgestellt. Ausdrücke sind der Grund, warum im Eigenschaftensystem keine Datenbindungen, Stile oder Vererbungen hartcodiert sind, sondern stattdessen von später gebildeten Ebenen innerhalb des Frameworks bereitgestellt werden.  
  
 Das Eigenschaftensystem ermöglicht auch verstreutes Speichern von Eigenschaftswerten. Da Objekte Dutzende (wenn nicht gar Hunderte) von Eigenschaften haben können, und die meisten Werte im Standardzustand sind (geerbt, von Stilen festgelegt usw.), benötigt nicht jede Instanz eines Objekts die vollständige Last aller seiner definierten Eigenschaften.  
  
 Das abschließende neue Feature des Eigenschaftensystems ist das Konzept der angefügten Eigenschaften. WPF-Elemente basieren auf dem Prinzip der Zusammensetzung und wiederverwendung von Komponenten. Es ist häufig der Fall, dass <xref:System.Windows.Controls.Grid> einige enthaltende Elemente (z. B. ein Layoutelement) zusätzliche Daten zu untergeordneten Elementen benötigen, um ihr Verhalten zu steuern (wie die Zeilen-/Spalteninformationen). Statt alle diese Eigenschaften jedem Element zuzuordnen, darf jedes beliebige Objekt Eigenschaftsdefinitionen für andere Objekte bereitstellen. Dies ähnelt den „Expando”-Funktionen von JavaScript.  
  
<a name="System_Windows_Media_Visual"></a>
## <a name="systemwindowsmediavisual"></a>System.Windows.Media.Visual  
 Ist ein System einmal definiert, besteht der nächste Schritt darin, Pixel auf den Bildschirm zu zeichnen. Die <xref:System.Windows.Media.Visual> Klasse sieht das Erstellen einer Struktur visueller Objekte vor, die optional Zeichnungsanweisungen und Metadaten zum Rendern dieser Anweisungen (Clipping, Transformation usw.) enthalten. <xref:System.Windows.Media.Visual>ist extrem leicht und flexibel, sodass die meisten Funktionen keine öffentliche API-Belichtung aufweisen und stark auf geschützte Rückruffunktionen angewiesen sind.  
  
 <xref:System.Windows.Media.Visual>ist wirklich der Einstiegspunkt zum WPF-Kompositionssystem. <xref:System.Windows.Media.Visual>ist der Verbindungspunkt zwischen diesen beiden Subsystemen, der verwalteten API und dem nicht verwalteten milcore.  
  
 WPF zeigt Daten an, indem die nicht verwalteten Datenstrukturen durchlaufen werden, die vom milcore verwaltet werden. Diese Strukturen, die man Kompositionsknoten nennt, stellen eine hierarchische Anzeige-Struktur mit Rendering-Anweisungen in jedem Knoten dar. Auf diese Struktur, die auf der rechten Seite der folgenden Abbildung dargestellt ist, kann nur über ein Nachrichtenprotokoll zugegriffen werden.  
  
 Beim Programmieren von <xref:System.Windows.Media.Visual> WPF erstellen Sie Elemente und abgeleitete Typen, die intern über dieses Messagingprotokoll mit der Kompositionsstruktur kommunizieren. Jeder <xref:System.Windows.Media.Visual> in WPF kann einen, keinen oder mehrere Kompositionsknoten erstellen.  
  
 ![Die visuelle Struktur der Windows Presentation Foundation](./media/wpf-architecture2.PNG "wpf_architecture2")  
  
 Es gibt hier ein sehr wichtiges architektonisches Detail zu beachten: die gesamte Struktur von visuellen Objekten und Zeichenanweisungen wird zwischengespeichert. In grafischer Hinsicht verwendet WPF ein beibehaltenes Renderingsystem. Dies ermöglicht es dem System, mit hohen Aktualisierungsraten neu zu zeichnen, ohne dass das Kompositionssystem dies aufgrund von Rückrufen auf Benutzercode blockiert. Dies verhindert eine scheinbar nicht reagierende Anwendung.  
  
 Ein weiteres wichtiges Detail, das man dem Diagramm eher nicht entnehmen kann, ist wie das System die Komposition tatsächlich durchführt.  
  
 In User32 und GDI arbeitet das System auf einem Sofortmodus-Clipping-System. Wenn eine Komponente gerendert werden muss, erstellt das System eine Clippinggrenze, außerhalb derer die Komponente keine Pixel berühren darf. Danach wird die Komponente aufgefordert, Pixel in dieses Feld zu zeichnen. Dieses System funktioniert sehr gut auf Systemen mit beschränktem Arbeitsspeicher, weil man bei jeder Änderung immer nur die betroffene Komponente anfassen muss – es tragen nie zwei Komponenten zur Farbe eines einzelnen Pixels bei.  
  
 WPF verwendet ein "Maleralgorithmus"-Malmodell. Dies bedeutet, dass, statt jede Komponente zu beschneiden, diese stattdessen aufgefordert wird, von hinten nach vorne in die Anzeige zu rendern. Dadurch kann jede Komponente die Anzeige der vorherigen Komponente übermalen. Der Vorteil dieses Modells ist, dass Sie komplexe, teilweise transparente Formen schaffen können. Mit der heutigen modernen Grafikhardware ist dieses Modell relativ schnell (was bei der Erstellung von User32/ GDI nicht der Fall war).  
  
 Wie bereits erwähnt, besteht eine Kernphilosophie von WPF darin, zu einem deklarativeren, "eigenschaftszentrierten" Programmiermodell überzugehen. Im visuellen System zeigt sich dies an einigen interessanten Stellen.  
  
 Wenn man sich zunächst das Grafiksystem mit seinem zurückbehaltenden Modus vor Augen führt, ist dies wirklich ein großer Schritt weg von einem imperativen Modell vom Typ „DrawLine/DrawLine”, hin zu einem datenorientierten Modell: „new Line() / new Line()/”. Dieser Schritt hin zu datengesteuertem Rendering ermöglicht es, komplexe Operationen in den Zeichenanweisungen mithilfe von Eigenschaften auszudrücken. Die Typen, von <xref:System.Windows.Media.Drawing> denen sie stammen, sind effektiv das Objektmodell für das Rendern.  
  
 Wenn Sie sich zum Zweiten das Animationssystem anschauen, sehen Sie, dass es fast vollständig deklarativ ist. Statt einen Entwickler zu benötigen, der die nächste Position oder Farbe berechnet, können Sie Animationen als eine Reihe von Eigenschaften für ein Animationsobjekt ausdrücken. Diese Animationen können dann die Absicht des Entwicklers oder Designers ausdrücken (bewege diese Schaltfläche innerhalb von 5 Sekunden von hier nach dort), und das System ermittelt die effizienteste Methode dieses zu bewerkstelligen.  
  
<a name="System_Windows_UIElement"></a>
## <a name="systemwindowsuielement"></a>System.Windows.UIElement  
 <xref:System.Windows.UIElement>definiert Kernsubsysteme wie Layout, Eingabe und Ereignisse.  
  
 Layout ist ein Kernkonzept in WPF. In vielen Systemen gibt es entweder einen festen Satz von Layout-Modellen (HTML unterstützt drei Modelle für das Layout: fließend, absolut und Tabellen) oder keine (User32 unterstützt wirklich nur die absolute Positionierung). WPF begann mit der Annahme, dass Entwickler und Designer ein flexibles, erweiterbares Layoutmodell wollten, das von Eigenschaftswerten und nicht von imperativer Logik gesteuert werden könnte. Auf <xref:System.Windows.UIElement> der Ebene wird der Grundvertrag für Layout <xref:System.Windows.UIElement.Measure%2A> eingeführt <xref:System.Windows.UIElement.Arrange%2A> – ein Zweiphasenmodell mit und durchläuft.  
  
 <xref:System.Windows.UIElement.Measure%2A>ermöglicht es einer Komponente zu bestimmen, wie viel Größe sie annehmen möchte. Dies ist eine <xref:System.Windows.UIElement.Arrange%2A> separate Phase von, da es viele Situationen gibt, in denen ein übergeordnetes Element ein untergeordnetes Element mehrmals bitten wird, zu messen, um seine optimale Position und Größe zu bestimmen. Die Tatsache, dass übergeordnete Elemente untergeordnete Elemente zum Messen auffordern, zeigt eine weitere Schlüsselphilosophie von WPF – Größe zu Inhalt. Alle Steuerelemente in WPF unterstützen die Möglichkeit, die Größe auf die natürliche Größe ihres Inhalts zu vergrößern. Dies erleichtert die Lokalisierung ungemein und lässt ein dynamische Layout von Elementen zu, die Ihre Größe ändern. Die <xref:System.Windows.UIElement.Arrange%2A> Phase ermöglicht es einem Elternteil, die endgültige Größe jedes untergeordneten Elements zu positionieren und zu bestimmen.  
  
 Oft wird viel Zeit damit verbracht, über die <xref:System.Windows.Media.Visual> Ausgabeseite von WPF zu sprechen – und verwandte Objekte. Es gibt jedoch auch eine enorme Anzahl an Innovationen auf der Eingabeseite. Die wahrscheinlich grundlegendste Änderung im Eingabemodell für WPF ist das konsistente Modell, mit dem Eingabeereignisse durch das System geleitet werden.  
  
 Eingabedaten starten als Signal in einem Kernelmodus-Gerätetreiber und werden durch einen komplexen Prozess, der den Windows-Kernel und User32 einbezieht, an den korrekten Prozess und Thread weitergeleitet. Sobald die der Eingabe entsprechende User32-Nachricht an WPF weitergeleitet wird, wird sie in eine WPF-Roheingabenachricht konvertiert und an den Dispatcher gesendet. WPF ermöglicht die Konvertierung von Roheingabeereignissen in mehrere tatsächliche Ereignisse, sodass Funktionen wie "MouseEnter" auf einer niedrigen Ebene des Systems mit garantierter Lieferung implementiert werden können.  
  
 Jedes Eingabeereignis wird in mindestens zwei Ereignisse konvertiert: ein „Vorschau”-Ereignis und das tatsächliche Ereignis. Alle Ereignisse in WPF haben eine Vorstellung vom Routing durch die Elementstruktur. Ereignisse werden als "Blase" bezeichnet, wenn sie sich von einem Ziel bis zur Wurzel durchqueren, und es wird gesagt, dass sie "tunneln", wenn sie an der Wurzel beginnen und zu einem Ziel hinablaufen. Eingabe-Vorschauereignisse tunneln, was jedem Element der Struktur die Möglichkeit gibt, etwas herauszufiltern oder eine Aktion auf das Ereignis durchzuführen. Das tatsächliche (Nicht-Vorschau-) Ereignis bubblet anschließend vom Ziel aufwärts zum Stamm.  
  
 Diese Auftrennung zwischen tunnelnder und bubblender Phase sorgt dafür, dass die Implementierung von Funktionen wie Tastenkombinationen auch in einer gemischten Umgebung konsistent funktioniert. In User32 würden Sie Zugriffstasten mithilfe einer einzelnen globalen Tabelle implementieren, die alle zu unterstützenden Zugriffstasten enthält (z.B. STRG + N für "Neu"). Sie würden im Verteiler Ihrer Anwendung **TranslateAccelerator** aufrufen, welches die eingehende Nachrichten in User32 untersuchen und bestimmen würde, welche davon registrierten Zugriffstaste entsprechen. In WPF würde dies nicht funktionieren, da das System vollständig "komposierbar" ist – jedes Element kann jeden Tastaturbeschleuniger verarbeiten und verwenden. Dieses zweiphasige Eingabemodell ermöglicht es Komponenten, ihre eigene „TranslateAccelerator“-Komponente zu implementieren.  
  
 Um dies einen <xref:System.Windows.UIElement> Schritt weiter zu gehen, wird auch der Begriff CommandBindings eingeführt. Das WPF-Befehlssystem ermöglicht es Entwicklern, Funktionen in Bezug <xref:System.Windows.Input.ICommand>auf einen Befehlsendpunkt zu definieren – etwas, das implementiert. Befehlsbindungen ermöglichen es Elementen, eine Zuordnung zwischen einer Eingabegeste (STRG + N) und einem Befehl (Neu) zu definieren. Sowohl die Eingabegesten als auch die Befehlsdefinitionen sind erweiterbar und können zum Zeitpunkt der Verwendung miteinander verknüpft werden. Dies macht es für den Endbenutzer extrem einfach, z.B. die Zuordnung von Tastenkombinationen anzupassen, die innerhalb einer Anwendung verwendet werden soll.  
  
 Bis zu diesem Punkt im Thema standen "Kern"-Features von WPF – Features, die in der PresentationCore-Assembly implementiert wurden – im Mittelpunkt. Beim Bau von WPF war eine saubere Trennung zwischen Fundamentteilen (wie dem Vertrag für Layout mit <xref:System.Windows.Controls.Grid> **Measure** and **Arrange)** und Rahmenteilen (wie die Implementierung eines bestimmten Layouts wie ) das gewünschte Ergebnis. Es war das Ziel, externen Entwicklern einen Erweiterungspunkt tief im Stapel anzubieten, der ihnen erlauben würde, bei Bedarf ihre eigenen Frameworks zu erstellen.  
  
<a name="System_Windows_FrameworkElement"></a>
## <a name="systemwindowsframeworkelement"></a>System.Windows.FrameworkElement  
 <xref:System.Windows.FrameworkElement>kann auf zwei verschiedene Arten betrachtet werden. Es führt eine Reihe von Richtlinien und Anpassungen auf den Subsystemen ein, die in niedrigeren Ebenen von WPF eingeführt wurden. Zum Anderen führt es auch eine Reihe neuer Subsysteme ein.  
  
 Die primäre Richtlinie, die von <xref:System.Windows.FrameworkElement> eingeführt wird, dreht sich um das Anwendungslayout. <xref:System.Windows.FrameworkElement>baut auf dem grundlegenden <xref:System.Windows.UIElement> Layoutvertrag auf, der von Layout-Verträgen eingeführt wurde, und fügt den Begriff eines Layout-"Slots" hinzu, der es Layoutautoren erleichtert, einen konsistenten Satz von eigenschaftengesteuerter Layoutsemantik zu verwenden. Eigenschaften <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>wie <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> , und (um nur einige <xref:System.Windows.FrameworkElement> zu nennen) geben alle Komponenten an, die von einem konsistenten Verhalten innerhalb von Layoutcontainern abgeleitet sind.  
  
 <xref:System.Windows.FrameworkElement>bietet außerdem eine einfachere API-Belichtung vieler Funktionen, die in den Kernebenen von WPF zu finden sind. <xref:System.Windows.FrameworkElement> Bietet beispielsweise direkten Zugriff auf <xref:System.Windows.FrameworkElement.BeginStoryboard%2A> Animationen über die Methode. A <xref:System.Windows.Media.Animation.Storyboard> bietet eine Möglichkeit, mehrere Animationen anhand einer Reihe von Eigenschaften zu skripten.  
  
 Die beiden wichtigsten <xref:System.Windows.FrameworkElement> Dinge, die eingeführt werden, sind Datenbindung und Stile.  
  
 Das Datenbindungssubsystem in WPF sollte jedem, der Windows Forms oder [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]ASP.NET zum Erstellen einer Anwendung verwendet hat, relativ vertraut sein. In jedem dieser Systeme besteht eine einfache Möglichkeit, um auszudrücken, dass Sie eine oder mehrere Eigenschaften aus einem angegebenen Element an Daten binden möchten. WPF bietet volle Unterstützung für die Eigenschaftenbindung, Transformation und Listenbindung.  
  
 Eines der interessantesten Merkmale der Datenbindung in WPF ist die Einführung von Datenvorlagen. Mit Datenvorlagen können Sie deklarativ angeben, wie Daten visualisiert werden sollen. Statt eine benutzerdefinierte Benutzeroberfläche zu erzeugen, die an Daten gebunden werden kann, können Sie stattdessen das Problem umzukehren, und die Daten selbst die Anzeige bestimmen lassen, die erstellt werden soll.  
  
 Formatierung ist im Grunde eine schlanke Form der Datenbindung. Mithilfe von Formatierungen kann eine Reihe von Eigenschaften aus einer freigegebenen Definition an eine oder mehrere Instanzen eines Elements gebunden werden. Stile werden entweder durch explizite Verweise (durch Festlegen der <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft) oder implizit durch Zuordnen eines Stils zum CLR-Typ des Elements auf ein Element angewendet.  
  
<a name="System_Windows_Controls_Control"></a>
## <a name="systemwindowscontrolscontrol"></a>System.Windows.Controls.Control  
 Das wichtigste Feature von Control ist das Vorlagensystem. Da das Kompositionssystem von WPF ein zurückbehaltendes Renderingsystem ist, erlaubt das Vorlagensystem eine Renderingbeschreibung in einer parametrisierten, deklarativen Art und Weise. A <xref:System.Windows.Controls.ControlTemplate> ist wirklich nichts anderes als ein Skript, um einen Satz von untergeordneten Elementen zu erstellen, mit Bindungen an Eigenschaften, die vom Steuerelement angeboten werden.  
  
 <xref:System.Windows.Controls.Control>stellt eine Reihe von <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.Background%2A>Bestandseigenschaften , , <xref:System.Windows.Controls.Control.Padding%2A>, um nur einige zu nennen, die Vorlagenautoren dann verwenden können, um die Anzeige eines Steuerelements anzupassen. Die Implementierung eines Steuerelements stellt ein Datenmodell und ein Interaktionsmodell bereit. Das Interaktionsmodell definiert einen Satz von Befehlen (z.B. „Schließen” für Fenster) und Bindungen an Eingabegesten (z.B. ein Klick auf das rote X in der oberen Ecke des Fensters). Das Datenmodell bietet eine Reihe von Eigenschaften, um entweder das Interaktionsmodell oder die Anzeige anzupassen (durch die Vorlage festgelegt).  
  
 Diese Auftrennung zwischen Datenmodell (Eigenschaften), Interaktionsmodell (Befehle und Ereignisse) und Anzeigemodell (Vorlagen) ermöglicht die vollständige Anpassung von Aussehen und Verhalten eines Steuerelements.  
  
 Ein allgemeiner Aspekt des Datenmodells von Steuerelementen ist das Inhaltsmodell. Wenn Sie sich ein <xref:System.Windows.Controls.Button>Steuerelement wie sehen, werden Sie sehen, <xref:System.Object>dass es eine Eigenschaft mit dem Namen "Inhalt" vom Typ hat. In Windows Forms und ASP.NET wäre diese Eigenschaft in der Regel eine Zeichenfolge – dies schränkt jedoch den Inhaltstyp ein, den Sie in eine Schaltfläche eingeben können. Der Inhalt einer Schaltfläche kann entweder eine einfache Zeichenfolge, ein komplexes Datenobjekt oder eine komplette Elementstruktur sein. Bei einem Datenobjekt wird die Anzeige mithilfe einer Datenvorlage erstellt.  
  
<a name="Summary"></a>
## <a name="summary"></a>Zusammenfassung  
 WPF wurde entwickelt, um dynamische, datengesteuerte Präsentationssysteme zu erstellen. Jeder Teil des Systems dient zum Erstellen von Objekten über Eigenschaftensätze, die das Verhalten steuern. Datenbindungen sind ein grundlegender Teil des Systems und auf jeder Ebene integriert.  
  
 Herkömmliche Anwendungen erzeugen eine Anzeige und binden anschließend Daten an. In WPF wird alles über das Steuerelement, jeden Aspekt der Anzeige, durch eine Art von Datenbindung generiert. Der Text in einer Schaltfläche wird angezeigt, indem ein zusammengesetztes Steuerelement in der Schaltfläche erstellt und seine Anzeige an die Content-Eigenschaft der Schaltfläche gebunden wird.  
  
 Wenn Sie mit der Entwicklung von WPF-basierten Anwendungen beginnen, sollte es sich sehr vertraut anfühlen. Sie können Eigenschaften festlegen, Objekte und Datenbindungen auf die gleiche Weise festlegen wie windows Forms oder ASP.NET. Bei einer tieferen Untersuchung der WPF-Architektur werden Sie feststellen, dass die Möglichkeit besteht, viel umfangreichere Anwendungen zu erstellen, die Daten grundsätzlich als Haupttreiber der Anwendung behandeln.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.UIElement>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Threading.DispatcherObject>
- <xref:System.Windows.Input.CommandBinding>
- <xref:System.Windows.Controls.Control>
- [Datenbindung sübersicht](../../../desktop-wpf/data/data-binding-overview.md)
- [Layout](layout.md)
- [Übersicht über Animationen](../graphics-multimedia/animation-overview.md)
