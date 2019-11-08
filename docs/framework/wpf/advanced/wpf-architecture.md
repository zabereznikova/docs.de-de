---
title: WPF-Architektur
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
ms.openlocfilehash: 2ec979240b8fead10522817b77eef23e29409411
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740692"
---
# <a name="wpf-architecture"></a>WPF-Architektur
Dieses Thema enthält eine Einführung in die Windows Presentation Foundation (WPF)-Klassenhierarchie. Es behandelt die meisten der wichtigsten Subsysteme von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] und beschreibt, wie sie interagieren. Es werden auch einige der durch die Architekten von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] getroffenen Entscheidungen erläutert.  

<a name="System_Object"></a>   
## <a name="systemobject"></a>System.Object  
 Das primäre [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Programmiermodell wird mithilfe von verwaltetem Code verfügbar gemacht. In der frühen Entwurfsphase von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] gab es einige Diskussionen darüber, wo die Linie zwischen den nicht verwalteten und den verwalteten Komponenten des Systems gezogen werden soll. Die CLR bietet eine Reihe von Features, die die Entwicklung produktiver und robuster machen (einschließlich Speicherverwaltung, Fehlerbehandlung, gängiges Typsystem usw.).  
  
 Die Hauptkomponenten von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sind in der folgenden Abbildung dargestellt. Die roten Abschnitte des Diagramms (PresentationFramework, PresentationCore und Milcore) sind die wichtigsten Teile von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Von diesen ist nur eine Komponente nicht verwaltet – Milcore. Milcore ist in nicht verwaltetem Code geschrieben, um eine enge Integration in DirectX zu ermöglichen. Die gesamte Anzeige in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] wird über die DirectX-Engine durchgeführt und ermöglicht eine effiziente Hardware-und Software Rendering. Ebenso erforderte [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] genaue Kontrolle über den Speicher und die Ausführung. Die Kompositions-Engine in Milcore ist äußerst Leistungs sensibel und erfordert eine Vielzahl von Vorteilen der CLR, um die Leistung zu steigern.  
  
 ![Die Position von WPF innerhalb der .NET Framework.](./media/wpf-architect1.PNG "wpf_architect1")  
  
 Die Kommunikation zwischen den verwalteten und nicht verwalteten Teilen von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] wird weiter unten in diesem Thema behandelt. Das restliche verwaltete Programmiermodell wird nachfolgend beschrieben.  
  
<a name="System_Threading_DispatcherObject"></a>   
## <a name="systemthreadingdispatcherobject"></a>System.Threading.DispatcherObject  
 Die meisten Objekte in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] von <xref:System.Windows.Threading.DispatcherObject>abgeleitet, das die grundlegenden Konstrukte für die Handhabung von Parallelität und Threading bereitstellt. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] basiert auf einem vom Verteiler implementierten Nachrichtensystem. Dies funktioniert sehr ähnlich wie das vertraute [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-Nachrichtensystem und tatsächlich verwendet der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Verteiler User32-Nachrichten für threadübergreifende Aufrufe.  
  
 Im Grunde gibt es zwei Kernkonzepte, die man bei der Diskussion über Parallelität in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] verstehen muss: den Verteiler und Thread-Affinität.  
  
 Während der Entwurfsphase von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] war es das Ziel, den Schritt zu einem einzigen Ausführungsthread in einem Nicht-Thread „affinierten“ Modell zu schaffen. Thread-Affinität findet dann statt, wenn eine Komponente die Identität des ausgeführten Threads verwendet, um einen irgendwie gearteten Zustand zu speichern. Die häufigste Form dieser Vorgehensweise ist, den threadlokalen Speicher (TLS) zu verwenden, um einen Zustand zu speichern. Thread-Affinität erfordert, dass jeder logische Ausführungsthread im Besitz von nur einem physischen Thread im Betriebssystem ist, was speicherintensiv werden kann. Letzten Endes wurde das WPF-Threadingmodell synchron mit dem bestehenden User32-Threadingmodell einzelner Ausführungsthread mit Threadaffinität gehalten. Der Hauptgrund dafür war Interoperabilität – Systeme wie OLE 2,0, die Zwischenablage und Internet Explorer erfordern die Ausführung einer einzelnen Thread Affinität (STA).  
  
 Angesichts der Tatsache, dass Sie Objekte mit STA-Threading haben, benötigen Sie Möglichkeiten der Kommunikation zwischen Threads und der Überprüfung, dass Sie sich im richtigen Thread befinden. Genau dies ist die Aufgabe des Verteilers. Der Verteiler ist ein Basis-Nachrichtensystem mit mehreren priorisierten Warteschlangen. Zu diesen Nachrichten gehören z.B. Rohdateneingabe-Benachrichtigungen (Maus bewegt), Framework-Funktionen (Layout) oder Benutzerbefehle (diese Methode ausführen). Durch Ableiten von <xref:System.Windows.Threading.DispatcherObject>erstellen Sie ein CLR-Objekt, das STA-Verhalten hat, und erhält zum Erstellungs Zeitpunkt einen Zeiger auf einen Verteiler.  
  
<a name="System_Windows_DependencyObject"></a>   
## <a name="systemwindowsdependencyobject"></a>System.Windows.DependencyObject  
 Eine der primären Architekturstrategien bei der Konzeption von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] war die Bevorzugung von Eigenschaften über Methoden oder Ereignissen. Eigenschaften sind deklarativ und machen es einfacher, eine Absicht statt einer Aktion anzugeben. Dies bot auch Unterstützung für ein modell- oder datengesteuertes System zur Anzeige von Inhalten der Benutzeroberfläche. Diese Strategie hatte den beabsichtigten Effekt, mehr Eigenschaften zu schaffen, an die Sie anbinden können, um das Verhalten einer Anwendung besser zu steuern.  
  
 Um mehr über die Eigenschaften des Systems zu verfügen, ist ein umfangreicheres Eigenschaften System als das, was die CLR bereitstellt. Ein einfaches Beispiel für diese Vielfalt sind die Änderungsbenachrichtigungen. Um eine zwei-Wege-Bindung zu ermöglichen, müssen beide Seiten der Bindung Änderungsbenachrichtigungen unterstützen. Um an Eigenschaftswerte ein bestimmtes Verhalten zu binden, müssen Sie benachrichtigt werden, wenn sich der Eigenschaftswert ändert. Das Microsoft .NET Framework verfügt über eine Schnittstelle ( **INotifyPropertyChange**), die einem Objekt das Veröffentlichen von Änderungs Benachrichtigungen ermöglicht, aber es ist optional.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet ein umfangreicheres Eigenschaften System, das vom <xref:System.Windows.DependencyObject>-Typ abgeleitet wird. Dieses Eigenschaftensystem ist in der Tat ein Eigenschaftensystem der „Abhängigkeiten” in dem Sinne, dass es Abhängigkeiten zwischen Eigenschaftsausdrücken nachverfolgt und Eigenschaftswerte automatisch neu überprüft, wenn sich die Abhängigkeiten ändern. Wenn Sie z. b. über eine Eigenschaft verfügen, die (z. b. <xref:System.Windows.Controls.Control.FontSize%2A>) erbt, wird das System automatisch aktualisiert, wenn sich die-Eigenschaft für ein übergeordnetes Element eines Elements ändert, das den Wert erbt.  
  
 Das [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Eigenschaftensystem fußt auf dem Konzept eines Eigenschaftsausdrucks. In dieser ersten Version von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ist das Eigenschaftensystem geschlossen, und die Ausdrücke werden alle als Teil des Frameworks bereitgestellt. Ausdrücke sind der Grund, warum im Eigenschaftensystem keine Datenbindungen, Stile oder Vererbungen hartcodiert sind, sondern stattdessen von später gebildeten Ebenen innerhalb des Frameworks bereitgestellt werden.  
  
 Das Eigenschaftensystem ermöglicht auch verstreutes Speichern von Eigenschaftswerten. Da Objekte Dutzende (wenn nicht gar Hunderte) von Eigenschaften haben können, und die meisten Werte im Standardzustand sind (geerbt, von Stilen festgelegt usw.), benötigt nicht jede Instanz eines Objekts die vollständige Last aller seiner definierten Eigenschaften.  
  
 Das abschließende neue Feature des Eigenschaftensystems ist das Konzept der angefügten Eigenschaften. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Elemente basieren auf dem Prinzip der Komposition und Wiederverwendung von Komponenten aufgebaut. Häufig ist es der Fall, dass einige enthaltende Elemente (z. b. ein <xref:System.Windows.Controls.Grid> Layoutelemente) zusätzliche Daten für untergeordnete Elemente benötigen, um das Verhalten zu steuern (z. b. Zeilen-/Spalteninformationen Statt alle diese Eigenschaften jedem Element zuzuordnen, darf jedes beliebige Objekt Eigenschaftsdefinitionen für andere Objekte bereitstellen. Dies ähnelt den „Expando”-Funktionen von JavaScript.  
  
<a name="System_Windows_Media_Visual"></a>   
## <a name="systemwindowsmediavisual"></a>System.Windows.Media.Visual  
 Ist ein System einmal definiert, besteht der nächste Schritt darin, Pixel auf den Bildschirm zu zeichnen. Die <xref:System.Windows.Media.Visual>-Klasse ermöglicht das Erstellen einer Struktur von visuellen Objekten, von denen jede optional Zeichnungs Anweisungen und Metadaten zum Renderingvorgang enthält (clipping, Transformation usw.). <xref:System.Windows.Media.Visual> ist äußerst einfach und flexibel, sodass die meisten Features keine öffentliche API-Präsenz aufweisen und stark auf geschützte Rückruf Funktionen basieren.  
  
 <xref:System.Windows.Media.Visual> ist wirklich der Einstiegspunkt für das [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Kompositions System. <xref:System.Windows.Media.Visual> ist der Verbindungspunkt zwischen diesen beiden Subsystemen, der verwalteten API und der nicht verwalteten Milcore.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] zeigt Daten an, indem es die vom nicht verwalteten Milcore verwalteten Datenstrukturen durchläuft. Diese Strukturen, die man Kompositionsknoten nennt, stellen eine hierarchische Anzeige-Struktur mit Rendering-Anweisungen in jedem Knoten dar. Auf diese Struktur, die auf der rechten Seite der folgenden Abbildung dargestellt ist, kann nur über ein Nachrichtenprotokoll zugegriffen werden.  
  
 Wenn Sie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]programmieren, erstellen Sie <xref:System.Windows.Media.Visual> Elemente und abgeleitete Typen, die intern über dieses Messaging Protokoll mit der Kompositionsstruktur kommunizieren. Jede <xref:System.Windows.Media.Visual> in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] kann einen, keinen oder mehrere Kompositions Knoten erstellen.  
  
 ![Der Windows Presentation Foundation visuelle Struktur.](./media/wpf-architecture2.PNG "wpf_architecture2")  
  
 Es gibt hier ein sehr wichtiges architektonisches Detail zu beachten: die gesamte Struktur von visuellen Objekten und Zeichenanweisungen wird zwischengespeichert. Im Grafik-Vokabular heißt dies, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] verwendet ein Retained-Rendering-System, was so viel wie „zurückbehaltenes Rendering” bedeutet. Dies ermöglicht es dem System, mit hohen Aktualisierungsraten neu zu zeichnen, ohne dass das Kompositionssystem dies aufgrund von Rückrufen auf Benutzercode blockiert. Dies verhindert eine scheinbar nicht reagierende Anwendung.  
  
 Ein weiteres wichtiges Detail, das man dem Diagramm eher nicht entnehmen kann, ist wie das System die Komposition tatsächlich durchführt.  
  
 In User32 und GDI arbeitet das System mit einem Clippingsystem im unmittelbaren Modus. Wenn eine Komponente gerendert werden muss, erstellt das System eine Clippinggrenze, außerhalb derer die Komponente keine Pixel berühren darf. Danach wird die Komponente aufgefordert, Pixel in dieses Feld zu zeichnen. Dieses System funktioniert sehr gut auf Systemen mit beschränktem Arbeitsspeicher, weil man bei jeder Änderung immer nur die betroffene Komponente anfassen muss – es tragen nie zwei Komponenten zur Farbe eines einzelnen Pixels bei.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] verwendet als Zeichenmodell einen „Maleralgorithmus”. Dies bedeutet, dass, statt jede Komponente zu beschneiden, diese stattdessen aufgefordert wird, von hinten nach vorne in die Anzeige zu rendern. Dadurch kann jede Komponente die Anzeige der vorherigen Komponente übermalen. Der Vorteil dieses Modells ist, dass Sie komplexe, teilweise transparente Formen schaffen können. Mit der modernen Grafikhardware von heute ist dieses Modell relativ schnell (was bei der Erstellung von User32/GDI nicht der Fall war).  
  
 Wie bereits erwähnt, ist eine zentrale Strategie von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] der Schritt zu einem deklarativen, „eigenschaftenzentrierten” Programmiermodell. Im visuellen System zeigt sich dies an einigen interessanten Stellen.  
  
 Wenn man sich zunächst das Grafiksystem mit seinem zurückbehaltenden Modus vor Augen führt, ist dies wirklich ein großer Schritt weg von einem imperativen Modell vom Typ „DrawLine/DrawLine”, hin zu einem datenorientierten Modell: „new Line() / new Line()/”. Dieser Schritt hin zu datengesteuertem Rendering ermöglicht es, komplexe Operationen in den Zeichenanweisungen mithilfe von Eigenschaften auszudrücken. Die Typen, die von <xref:System.Windows.Media.Drawing> abgeleitet werden, sind im Grunde das Objektmodell für das Rendering.  
  
 Wenn Sie sich zum Zweiten das Animationssystem anschauen, sehen Sie, dass es fast vollständig deklarativ ist. Statt einen Entwickler zu benötigen, der die nächste Position oder Farbe berechnet, können Sie Animationen als eine Reihe von Eigenschaften für ein Animationsobjekt ausdrücken. Diese Animationen können dann die Absicht des Entwicklers oder Designers ausdrücken (bewege diese Schaltfläche innerhalb von 5 Sekunden von hier nach dort), und das System ermittelt die effizienteste Methode dieses zu bewerkstelligen.  
  
<a name="System_Windows_UIElement"></a>   
## <a name="systemwindowsuielement"></a>System.Windows.UIElement  
 <xref:System.Windows.UIElement> definiert Kern Subsysteme, einschließlich Layout, Eingabe und Ereignisse.  
  
 Layout ist ein Kernkonzept in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. In vielen Systemen gibt es entweder einen festen Satz von Layout-Modellen (HTML unterstützt drei Modelle für das Layout: fließend, absolut und Tabellen) oder keine (User32 unterstützt wirklich nur die absolute Positionierung). [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] begann mit der Annahme, dass Entwickler und Designer ein flexibles, erweiterbares Layout-Modell möchten, das durch Eigenschaftswerte an Stelle von imperativer Logik gesteuert werden kann. Auf <xref:System.Windows.UIElement> Ebene wird der grundlegende Vertrag für das Layout eingeführt – ein zweistufiges Modell mit <xref:System.Windows.UIElement.Measure%2A> und <xref:System.Windows.UIElement.Arrange%2A> übergibt.  
  
 mit <xref:System.Windows.UIElement.Measure%2A> kann eine Komponente ermitteln, wie viel Größe Sie benötigen. Dabei handelt es sich um eine separate Phase von <xref:System.Windows.UIElement.Arrange%2A>, da ein übergeordnetes Element ein untergeordnetes Element anfordert, mehrere Male zu messen, um die optimale Position und Größe zu ermitteln. Die Tatsache, dass übergeordnete Elemente von untergeordneten Elementen Messungen anfordern, zeigt eine andere wichtige Strategie von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] – die Größe dem Inhalt anzupassen. Alle Steuerelemente im [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] unterstützen die Fähigkeit, ihre Größe dem Inhalts entsprechend anzupassen. Dies erleichtert die Lokalisierung ungemein und lässt ein dynamische Layout von Elementen zu, die Ihre Größe ändern. In der <xref:System.Windows.UIElement.Arrange%2A> Phase kann ein übergeordnetes Element die endgültige Größe der einzelnen untergeordneten Elemente positionieren und ermitteln.  
  
 Häufig wird viel Zeit für die Ausgabe Seite von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] – <xref:System.Windows.Media.Visual> und verknüpften Objekten aufgewendet. Es gibt jedoch auch eine enorme Anzahl an Innovationen auf der Eingabeseite. Die wahrscheinlich wichtigste Änderung des Eingabemodells für [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ist das konsistente Modell, Eingabeereignisse durch das System weiterzuleiten.  
  
 Eingabedaten starten als Signal in einem Kernelmodus-Gerätetreiber und werden durch einen komplexen Prozess, der den Windows-Kernel und User32 einbezieht, an den korrekten Prozess und Thread weitergeleitet. Sobald die zur Eingabe gehörende User32-Nachricht an [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] weitergeleitet ist, wird sie in eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Rohdaten-Eingabenachricht konvertiert und an den Verteiler gesendet. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] können Rohdaten-Eingabeereignisse in mehrere tatsächliche Ereignisse konvertiert werden, was die Implementierung von Funktionen wie "MouseEnter" auf einer niedrigen Systemebene mit garantierter Übermittlung ermöglicht.  
  
 Jedes Eingabeereignis wird in mindestens zwei Ereignisse konvertiert: ein „Vorschau”-Ereignis und das tatsächliche Ereignis. Allen Ereignisse in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ist gemein, dass sie durch die Elementstruktur geleitet werden. Ereignisse werden als "Blase" bezeichnet, wenn Sie von einem Ziel nach oben in der Struktur durchlaufen und als "Tunnel" bezeichnet werden, wenn Sie am Stamm beginnen und zu einem Ziel übertragen werden. Eingabe-Vorschauereignisse tunneln, was jedem Element der Struktur die Möglichkeit gibt, etwas herauszufiltern oder eine Aktion auf das Ereignis durchzuführen. Das tatsächliche (Nicht-Vorschau-) Ereignis bubblet anschließend vom Ziel aufwärts zum Stamm.  
  
 Diese Auftrennung zwischen tunnelnder und bubblender Phase sorgt dafür, dass die Implementierung von Funktionen wie Tastenkombinationen auch in einer gemischten Umgebung konsistent funktioniert. In User32 würden Sie Zugriffstasten mithilfe einer einzelnen globalen Tabelle implementieren, die alle zu unterstützenden Zugriffstasten enthält (z.B. STRG + N für "Neu"). Sie würden im Verteiler Ihrer Anwendung **TranslateAccelerator** aufrufen, welches die eingehende Nachrichten in User32 untersuchen und bestimmen würde, welche davon registrierten Zugriffstaste entsprechen. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] würde dies nicht funktionieren, da das System vollständig "komponierbar" ist – jedes Element darf jede beliebige Zugriffstaste behandeln und verwenden. Dieses zweiphasige Eingabemodell ermöglicht es Komponenten, ihre eigene „TranslateAccelerator“-Komponente zu implementieren.  
  
 Um dies noch einen Schritt weiter zu tun, führt <xref:System.Windows.UIElement> auch das Konzept von commandbindungen ein. Das [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Befehlssystem ermöglicht Entwicklern das Definieren von Funktionen in Bezug auf einen Befehls Endpunkt – etwas, das <xref:System.Windows.Input.ICommand>implementiert. Befehlsbindungen ermöglichen es Elementen, eine Zuordnung zwischen einer Eingabegeste (STRG + N) und einem Befehl (Neu) zu definieren. Sowohl die Eingabegesten als auch die Befehlsdefinitionen sind erweiterbar und können zum Zeitpunkt der Verwendung miteinander verknüpft werden. Dies macht es für den Endbenutzer extrem einfach, z.B. die Zuordnung von Tastenkombinationen anzupassen, die innerhalb einer Anwendung verwendet werden soll.  
  
 Was dieses Thema betrifft, lag der Schwerpunkt auf den „Kern-”Features von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] – Features, die in der PresentationCore-Assembly implementiert wurden. Beim Erstellen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]war eine saubere Trennung zwischen grundlegenden Teilen (z. b. der Vertrag für das Layout mit **Measure** und **anordnen**) und frameworkez (z. b. die Implementierung eines bestimmten Layouts wie <xref:System.Windows.Controls.Grid>) das gewünschte Ergebnis. Es war das Ziel, externen Entwicklern einen Erweiterungspunkt tief im Stapel anzubieten, der ihnen erlauben würde, bei Bedarf ihre eigenen Frameworks zu erstellen.  
  
<a name="System_Windows_FrameworkElement"></a>   
## <a name="systemwindowsframeworkelement"></a>System.Windows.FrameworkElement  
 <xref:System.Windows.FrameworkElement> kann auf zwei verschiedene Arten betrachtet werden. Zum Einen führt es eine Reihe von Richtlinien und Anpassungen auf Subsysteme ein, die auf den unteren Ebenen von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eingeführt wurden. Zum Anderen führt es auch eine Reihe neuer Subsysteme ein.  
  
 Die von <xref:System.Windows.FrameworkElement> eingeführte primäre Richtlinie ist um das Anwendungs Layout herum. <xref:System.Windows.FrameworkElement> baut auf dem grundlegenden Layoutvertrag auf, der durch <xref:System.Windows.UIElement> eingeführt wurde, und fügt das Konzept eines Layoutslots hinzu, das es Entwicklern ermöglicht, einen konsistenten Satz von Eigenschaften orientierter Layoutsemantik zu haben. Eigenschaften wie <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.MinWidth%2A>und <xref:System.Windows.FrameworkElement.Margin%2A> (um nur einige zu nennen) weisen alle Komponenten, die von <xref:System.Windows.FrameworkElement> konsistenten Verhalten in Layoutcontainern abgeleitet sind, zu.  
  
 <xref:System.Windows.FrameworkElement> bietet außerdem eine einfachere API-Verfügbarkeit für viele Features, die in den kernschichten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]gefunden werden. <xref:System.Windows.FrameworkElement> ermöglicht beispielsweise den direkten Zugriff auf Animationen über die <xref:System.Windows.FrameworkElement.BeginStoryboard%2A>-Methode. Eine <xref:System.Windows.Media.Animation.Storyboard> bietet eine Möglichkeit, mehrere Animationen mit einem Satz von Eigenschaften zu erstellen.  
  
 Die zwei wichtigsten Dinge, die <xref:System.Windows.FrameworkElement> eingeführt, sind die Datenbindung und Stile.  
  
 Das Daten Bindungs Subsystem in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sollte allen Personen, die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] oder ASP.net zum Erstellen einer Anwendungs [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]verwendet haben, relativ vertraut sein. In jedem dieser Systeme besteht eine einfache Möglichkeit, um auszudrücken, dass Sie eine oder mehrere Eigenschaften aus einem angegebenen Element an Daten binden möchten. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] bietet vollständige Unterstützung für Eigenschaftenbindung, Transformation und Listenbindung.  
  
 Eines der interessantesten Features der Datenbindung in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ist die Einführung von Datenvorlagen. Mit Datenvorlagen können Sie deklarativ angeben, wie Daten visualisiert werden sollen. Statt eine benutzerdefinierte Benutzeroberfläche zu erzeugen, die an Daten gebunden werden kann, können Sie stattdessen das Problem umzukehren, und die Daten selbst die Anzeige bestimmen lassen, die erstellt werden soll.  
  
 Formatierung ist im Grunde eine schlanke Form der Datenbindung. Mithilfe von Formatierungen kann eine Reihe von Eigenschaften aus einer freigegebenen Definition an eine oder mehrere Instanzen eines Elements gebunden werden. Stile werden auf ein Element entweder durch einen expliziten Verweis (durch Festlegen der <xref:System.Windows.FrameworkElement.Style%2A>-Eigenschaft) oder implizit durch Zuordnen eines Stils zu einem CLR-Typ des Elements angewendet.  
  
<a name="System_Windows_Controls_Control"></a>   
## <a name="systemwindowscontrolscontrol"></a>System.Windows.Controls.Control  
 Das wichtigste Feature von Control ist das Vorlagensystem. Da das Kompositionssystem von WPF ein zurückbehaltendes Renderingsystem ist, erlaubt das Vorlagensystem eine Renderingbeschreibung in einer parametrisierten, deklarativen Art und Weise. Ein <xref:System.Windows.Controls.ControlTemplate> ist wirklich nichts anderes als ein Skript zum Erstellen eines Satzes von untergeordneten Elementen, mit Bindungen zu Eigenschaften, die vom Steuerelement angeboten werden.  
  
 <xref:System.Windows.Controls.Control> bietet eine Reihe von vordefinierten Eigenschaften, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Padding%2A>, um nur einige zu benennen. diese Vorlagen Autoren können dann verwenden, um die Anzeige eines Steuer Elements anzupassen. Die Implementierung eines Steuerelements stellt ein Datenmodell und ein Interaktionsmodell bereit. Das Interaktionsmodell definiert einen Satz von Befehlen (z.B. „Schließen” für Fenster) und Bindungen an Eingabegesten (z.B. ein Klick auf das rote X in der oberen Ecke des Fensters). Das Datenmodell bietet eine Reihe von Eigenschaften, um entweder das Interaktionsmodell oder die Anzeige anzupassen (durch die Vorlage festgelegt).  
  
 Diese Auftrennung zwischen Datenmodell (Eigenschaften), Interaktionsmodell (Befehle und Ereignisse) und Anzeigemodell (Vorlagen) ermöglicht die vollständige Anpassung von Aussehen und Verhalten eines Steuerelements.  
  
 Ein allgemeiner Aspekt des Datenmodells von Steuerelementen ist das Inhaltsmodell. Wenn Sie ein Steuerelement wie <xref:System.Windows.Controls.Button>betrachten, sehen Sie, dass es über eine Eigenschaft mit dem Namen "Content" vom Typ "<xref:System.Object>" verfügt. In [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] und ASP.net wäre diese Eigenschaft normalerweise eine Zeichenfolge, die den Typ des Inhalts einschränkt, den Sie in eine Schaltfläche einfügen können. Der Inhalt einer Schaltfläche kann entweder eine einfache Zeichenfolge, ein komplexes Datenobjekt oder eine komplette Elementstruktur sein. Bei einem Datenobjekt wird die Anzeige mithilfe einer Datenvorlage erstellt.  
  
<a name="Summary"></a>   
## <a name="summary"></a>Zusammenfassung  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] wurde entworfen, um Ihnen die Erstellung dynamischer, datengesteuerter Präsentationssysteme zu ermöglichen. Jeder Teil des Systems dient zum Erstellen von Objekten über Eigenschaftensätze, die das Verhalten steuern. Datenbindungen sind ein grundlegender Teil des Systems und auf jeder Ebene integriert.  
  
 Herkömmliche Anwendungen erzeugen eine Anzeige und binden anschließend Daten an. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ist die Steuerung, ist jeder Aspekt der Anzeige, durch irgendeine Art von Datenbindung generiert. Der Text in einer Schaltfläche wird angezeigt, indem ein zusammengesetztes Steuerelement in der Schaltfläche erstellt und seine Anzeige an die Content-Eigenschaft der Schaltfläche gebunden wird.  
  
 Wenn Sie beginnen, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-basierte Anwendungen zu entwickeln, sollte Ihnen alles sehr vertraut vorkommen. Sie können Eigenschaften festlegen, Objekte und Daten Bindungen auf die gleiche Weise wie [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] oder ASP.NET verwenden. Wenn Sie dann tiefer in die Architektur von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eintauchen, werden Sie entdecken, dass es Ihnen die Möglichkeit bietet, wesentlich vielfältigere Anwendungen zu erstellen, deren grundlegende Steuerungsmechanismen über Daten stattfinden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.UIElement>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Threading.DispatcherObject>
- <xref:System.Windows.Input.CommandBinding>
- <xref:System.Windows.Controls.Control>
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Layout](layout.md)
- [Übersicht über Animationen](../graphics-multimedia/animation-overview.md)
