---
title: Übersicht über WPF-Globalisierung und -Lokalisierung
ms.date: 03/30/2017
helpviewer_keywords:
- globalization [WPF], about globalization
- localization [WPF], about localization
ms.assetid: 56e5a5c8-6c96-4d19-b8e1-a5be1dc564af
ms.openlocfilehash: 957ba16886669acdfa5501ffe02501cbe6e57198
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549616"
---
# <a name="wpf-globalization-and-localization-overview"></a>Übersicht über WPF-Globalisierung und -Lokalisierung
Wenn Sie die Verfügbarkeit Ihres Produkts auf eine Sprache beschränken, beschränken Sie damit auch Ihre potentielle Kundenbasis auf einen Bruchteil der 6,5 Milliarden Einwohner unseres Planeten. Wenn Ihre Anwendung eine globale Zielgruppe erreichen soll, ist die kostengünstige Lokalisierung Ihres Produktes eine der besten und effizientesten Möglichkeiten, mehr Kunden zu erreichen.  
  
 Diese Übersicht enthält Globalisierung und Lokalisierung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Unter Globalisierung versteht man den Entwurf und die Entwicklung von Anwendungen, die an verschiedenen Orten funktionieren. So unterstützt Globalisierung z.B. lokalisierte Benutzeroberflächen und regionale Daten für Benutzer in unterschiedlichen Kulturen. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] globalisierten Design stellt Funktionen bereit, einschließlich der automatischen Layouts, Satellitenassemblys sowie lokalisierten Attributen und kommentieren.
  
 Unter Lokalisierung versteht man die Übersetzung von Anwendungsressourcen in lokalisierte Versionen für die jeweiligen von der Anwendung unterstützten Kulturen. Wenn Sie lokalisieren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], verwenden Sie die APIs in der <xref:System.Windows.Markup.Localizer> Namespace. Diese APIs Power der [LocBaml Tool Sample](http://go.microsoft.com/fwlink/?LinkID=160016) Befehlszeilentool. Informationen zum Erstellen und Verwenden von LocBaml finden Sie unter [Lokalisieren einer Anwendung](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).    
  
## <a name="best-practices-for-globalization-and-localization-in-wpf"></a>Bewährte Methoden zur Globalisierung und Lokalisierung in WPF.  
 Sie können die meisten der Globalisierung und Lokalisierung Funktionalität, die in integrierten machen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gemäß den UI-Entwurf und die Lokalisierung bezogene Tipps, die dieser Abschnitt enthält.  
  
### <a name="best-practices-for-wpf-ui-design"></a>Bewährte Methoden für den Entwurf von WPF-Benutzeroberflächen  
 Beim Entwerfen einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]– basierten [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], erwägen Sie diese bewährten Methoden zu implementieren:  
  
-   Schreiben der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; erstellen Sie keine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] im Code. Beim Erstellen Ihrer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], ihn über integrierte Lokalisierung APIs aussetzen.  
  
-   Vermeiden Sie die Verwendung von festen Größen und absolute Positionen auf Inhaltslayout; Verwenden Sie stattdessen die relative oder eine automatische größenanpassung.
  
    -   Verwendung <xref:System.Windows.Window.SizeToContent%2A>; halten, Breite und Höhe festgelegt `Auto`.  
  
    -   Vermeiden Sie die Verwendung <xref:System.Windows.Controls.Canvas> , das Layout [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]s.  
  
    -   Verwendung <xref:System.Windows.Controls.Grid> und seine Größe sharing-Funktion.  
  
-   Lassen Sie an den Rändern zusätzlichen freien Platz, da lokalisierter Text häufig mehr Platz beansprucht. Zusätzlicher Leerraum kann überstehende Zeichen aufnehmen.  
  
-   Aktivieren Sie <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> auf <xref:System.Windows.Controls.TextBlock> um Clipping zu vermeiden.
  
-   Legen Sie die **XML: lang** Attribut. Dieses Attribut wird die Kultur der ein bestimmtes Element und seine untergeordneten Elemente beschrieben. Der Wert dieser Eigenschaft ändert das Verhalten der verschiedenen Funktionen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Es ändert z.B. das Verhalten von Silbentrennung, Rechtschreibprüfung, Zahlenersetzung, Formen komplexer Schriften und die Ausweich-Schriftart. Finden Sie unter [Globalisierung für WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md) für Weitere Informationen zum Festlegen der [XML: lang Behandlung in XAML](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md).  
  
-   Erstellen Sie eine benutzerdefinierte zusammengesetzte Schriftart, um eine bessere Steuerung des Schriftarten zu erhalten, die für verschiedene Sprachen verwendet werden. Standardmäßig [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet die Schriftart GlobalUserInterface.composite im Verzeichnis Windows\Fonts.  
  
-   Beim Erstellen von Navigation Anwendungen, die lokalisiert werden möglicherweise in einer Kultur, die Text im rechts-nach-links-Format dargestellt, explizit festlegen der <xref:System.Windows.FlowDirection> jeder Seite, um sicherzustellen, dass die Seite "erbt nicht <xref:System.Windows.FlowDirection> aus der <xref:System.Windows.Navigation.NavigationWindow>.  
  
-   Legen Sie beim Erstellen von eigenständigen Navigation Anwendungen, die außerhalb eines Browsers gehostet werden, die <xref:System.Windows.Application.StartupUri%2A> für die erste Anwendung eine <xref:System.Windows.Navigation.NavigationWindow> statt auf eine Seite (z. B. `<Application StartupUri="NavigationWindow.xaml">`). Dieser Entwurf ermöglicht es Ihnen so ändern Sie die <xref:System.Windows.FlowDirection> des Fensters und der Navigationsleiste. Weitere Informationen und ein Beispiel finden Sie unter [Globalization Homepage Sample](http://go.microsoft.com/fwlink/?LinkID=159990).  
  
### <a name="best-practices-for-wpf-localization"></a>Bewährte Methoden für die Lokalisierung in WPF  
 Wenn Sie lokalisieren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]– basierenden Anwendungen sollten Sie diese bewährten Methoden implementieren:  
  
-   Verwenden von Lokalisierungskommentaren Lokalisierungsexperten zusätzlichen Kontext bereit.  
  
-   Lokalisierungsattribute verwenden, um die Lokalisierung statt selektiv auslassen steuern <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften für Elemente. Finden Sie unter [Lokalisierungsattribute und Kommentare](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md) für Weitere Informationen.  
  
-   Verwendung **Msbuild/t: updateuid** und **/t: checkuid** hinzufügen und überprüfen Sie <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften in Ihrem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Verwendung <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften zum Nachverfolgen von Änderungen zwischen Entwicklungs- und Lokalisierung. <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften können Sie die neue entwicklungsänderungen zu lokalisieren. Wenn Sie manuell hinzufügen <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], der Vorgang ist in der Regel mühsam und weniger genau.  
  
    -   Bearbeiten oder ändern Sie nicht <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften nach dem Starten der Lokalisierung.  
  
    -   Verwenden Sie keine doppelten <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften (Denken Sie daran, wenn Sie den Befehl Kopieren und Einfügen verwenden).  
  
    -   Legen Sie die `UltimateResourceFallback` Position im AssemblyInfo an der entsprechenden Sprache für Fallback (z. B. `[assembly: NeutralResourcesLanguage("en-US",   UltimateResourceFallbackLocation.Satellite)]`).  
  
         Wenn Sie sich dazu entschließen, die Hauptassembly Source-Sprache einschließt, indem Sie auslassen der `<UICulture>` in der Projektdatei zu kennzeichnen, legen Sie die `UltimateResourceFallback` Speicherort wie die Hauptassembly anstelle der Satellit (z. B. `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.MainAssembly)]`).  
  
<a name="workflow_to_localize"></a>   
## <a name="localize-a-wpf-application"></a>Lokalisieren einer WPF-Anwendung  
 Wenn Sie Lokalisieren einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendung einsetzen möchten, stehen Ihnen mehrere Optionen. Sie können z. B. lokalisierbaren Ressourcen in der Anwendung Binden einer [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Datei, lokalisierbaren Text in Resx-Tabellen speichern oder den Lokalisierungsexperten anweisen, verwenden Sie [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Dateien. Dieser Abschnitt beschreibt einen Lokalisierungsworkflow, der die BAML-Form von XAML-Code verwendet die bietet mehrere Vorteile:  
  
-   Sie können lokalisieren, nachdem die Anwendung erstellt ist.  
  
-   Sie können mit lokalisierten Versionen einer älteren Version der BAML-Form von XAML auf eine neuere Version der BAML-Form von XAML aktualisieren, damit Sie lokalisieren können, während Sie noch entwickeln.  
  
-   Sie können überprüfen, ursprüngliche Quellelemente und Semantik zum Zeitpunkt der Kompilierung die BAML-Form von XAML ist der kompilierten Form [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
### <a name="localization-build-process"></a>Buildprozess für die Lokalisierung  
 Bei der Entwicklung einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung des Buildprozesses für die Lokalisierung lautet wie folgt:  
  
-   Der Entwickler erstellt und globalisiert die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung. Im Projekt die Datei legt der Entwickler `<UICulture>en-US</UICulture>` , wenn die Anwendung kompiliert wird, wird eine sprachneutrale Hauptassembly generiert. Diese Assembly verfügt über eine ausgelagerte .resources.dll-Datei, die alle lokalisierbaren Ressourcen enthält. Optional, Sie können die Source-Sprache in behalten die Hauptassembly da unsere Lokalisierung [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] Datenextraktion aus der Hauptassembly zu unterstützen.  
  
-   Wenn die Datei in den Build kompiliert wird die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in die BAML-Form von XAML konvertiert wird. Das kulturübergreifende `MyDialog.exe` und die jeweilige Kultur abhängigen (Englisch) `MyDialog.resources.dll` Dateien an den englischsprachigen Kunden freigegeben werden.  
  
### <a name="localization-workflow"></a>Lokalisierungsworkflow  
 Der Lokalisierungsprozess beginnt, nachdem die nicht lokalisierte `MyDialog.resources.dll` Datei basiert. Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente und Eigenschaften in Ihrem ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] werden mithilfe von die BAML-Form von XAML in Schlüssel-Wert-Paare extrahiert die [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] unter <xref:System.Windows.Markup.Localizer>. Lokalisierer verwenden die Schlüssel-Wert-Paare, um die Anwendung zu lokalisieren. Sie können nach Abschluss der Lokalisierung aus den neuen Werten eine neue .resource.dll-Datei generieren.  
  
 Die Schlüssel des Schlüssel-Wert-Paare sind `x:Uid` Werte, die vom Entwickler in der ursprünglichen platziert werden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Diese `x:Uid` Werte ermöglichen es dem [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] zum Nachverfolgen und Zusammenführen von Änderungen, die zwischen dem Entwickler und den Lokalisierungsexperten während Lokalisierung durchgeführt. Wenn der Entwickler ändert z. B. die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nach dem Beginn der Lokalisierungsexperten Lokalisieren von können Sie die Änderung der Entwicklung mit der Arbeit bereits abgeschlossenen Lokalisierung zusammenführen, sodass minimale Umwandlungen verloren geht.  
  
 Die folgende Abbildung zeigt einen typischen auf der BAML-Form von XAML-basierenden Lokalisierungsworkflow. Dieses Diagramm wird davon ausgegangen, dass der Entwickler die Anwendung in Englisch erstellt. Der Entwickler erstellt und globalisiert die WPF-Anwendung. Im Projekt die Datei legt der Entwickler `<UICulture>en-US</UICulture>` , damit beim Erstellen, eine sprachneutrale Hauptassembly mit einer Satellitenassembly generiert ruft. resources.dll, die alle lokalisierbare Ressourcen enthält. Alternativ dazu können Sie auch Ihre Quellsprache in der Hauptassembly belassen, da unsere Lokalisierungs-APIs eine Extraktion aus der Hauptassembly unterstützen. Nach dem Buildprozess wird XAML in BAML kompiliert. Die kulturneutrale Datei „MyDialog.exe.resources.dll” wird an den englischsprachigen Kunden ausgeliefert.  
  
 ![Lokalisierungsworkflow](../../../../docs/framework/wpf/advanced/media/localizationworkflow.png "LocalizationWorkflow")  
  
 ![Nicht lokalisierter Workflow](../../../../docs/framework/wpf/advanced/media/localizationworkflow2.png "LocalizationWorkflow2")  
  
<a name="examples_of_localization"></a>   
## <a name="examples-of-wpf-localization"></a>Beispiele für WPF-Lokalisierung  
 Dieser Abschnitt enthält Beispiele für lokalisierte Anwendungen, um besser zu verstehen wie erstellen und lokalisieren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen.  
  
#### <a name="run-dialog-box-example"></a>Beispiel-Dialogfeld „Ausführen”  
 In der folgenden Grafik werden die Ausgabe von der **ausführen** Beispiels Dialogfeld gezeigt.  
  
 **Englisch:**  
  
 ![Dialogfeld "Ausführen"](../../../../docs/framework/wpf/advanced/media/rundialogenglish.PNG "RunDialogEnglish")  
  
 **Deutsch:**  
  
 ![Deutsches Dialogfeld „Ausführen”](../../../../docs/framework/wpf/advanced/media/rundialoggerman.PNG "RunDialogGerman")  
  
 **Entwerfen eines globalen Dialogfelds „Ausführen”**  
  
 Dieses Beispiel erzeugt einen **ausführen** Dialogfeld mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Dieses Dialogfeld ist gleichbedeutend mit der **ausführen** (Dialogfeld), die in der [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] Startmenü.  
  
 Einige Highlights beim Erstellen von globalen Dialogfeldern sind:  
  
 **Automatisches Layout**  
  
 *In der Datei Window1.xaml:*  
  
 `<Window SizeToContent="WidthAndHeight">`  
  
 Die obige Window-Eigenschaft sorgt dafür, dass sich die Fenstergröße automatisch der Inhaltsgröße entsprechend anpasst. Diese Eigenschaft verhindert, dass Inhalt, der nach der Lokalisierung an Größe zunimmt, abgeschnitten wird. Im Gegenzug wird auch unnötiger Leerraum entfernt, wenn die Größe des Inhalts nach der Lokalisierung geschrumpft ist.  
  
 `<Grid x:Uid="Grid_1">`  
  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften werden in Reihenfolge für benötigt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Lokalisierung [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] ordnungsgemäß funktioniert.  
  
 Sie werden verwendet, indem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Lokalisierung [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] zum Nachverfolgen von Änderungen zwischen der Entwicklungs- und Lokalisierung von der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften ermöglichen es Ihnen, eine neuere Version des merge der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit einer älteren Lokalisierung von der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Sie fügen eine <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaft durch Ausführen von **Msbuild/t: updateuid RunDialog.csproj** in eine Befehlsshell. Dies ist die empfohlene Methode zum Hinzufügen von <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften, da sie manuell hinzufügen, in der Regel zeitaufwändig und weniger genau ist. Sie können überprüfen, <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften sind richtig festgelegt durch Ausführen von **Msbuild/t: checkuid RunDialog.csproj**.  
  
 Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] strukturiert ist, mithilfe der <xref:System.Windows.Controls.Grid> Steuerelement, das ist ein nützlich-Steuerelement für die Vorteile des automatischen Layouts in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Beachten Sie, dass das Dialogfeld in drei Zeilen und fünf Spalten unterteilt ist. Keiner der die Zeilen- und Spaltendefinitionen hat eine feste Größe; Daher wird die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente, die in jeder Zelle positioniert werden können, erhöht sich anpassen und Größe verkleinert, bei der Lokalisierung.  
  
 [!code-xaml[GlobalizationRunDialog#GridColumnDef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef)]  
  
 Die ersten beiden Spalten, in denen die **öffnen:** Bezeichnung und <xref:System.Windows.Controls.ComboBox> platziert werden 10 Prozent des der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Gesamtbreite.  
  
 [!code-xaml[GlobalizationRunDialog#GridColumnDef2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef2)]  
  
 Beachten Sie, die des Beispiels die shared-Sizing-Funktion von verwendet <xref:System.Windows.Controls.Grid>. Die letzten drei Spalten nutzen diesen Umstand, in der gleichen <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A>. Wie aus dem Namen der Eigenschaft zu erwarten ist, ermöglicht dies den Spalten, dieselbe Größe zu verwenden. Wenn nun also das „Browse...” zur längeren Zeichenfolge "Durchsuchen..." lokalisiert wird, werden alle Schaltflächen gleichmäßig breiter. Ohne diese Einstellung hätte man eine kleine Schaltfläche "OK" und eine unverhältnismäßig große "Durchsuchen..."- Schaltfläche.  
  
 **xml:lang**  
  
 `Xml:lang="en-US"`  
  
 Beachten Sie, dass die [XML: lang Behandlung in XAML](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) platziert das Stammelement der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Diese Eigenschaft beschreibt die Kultur eines bestimmten Elements und seiner untergeordneten Elemente. Dieser Wert wird verwendet, indem Sie mehrere Funktionen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und sollten bei der Lokalisierung entsprechend geändert werden. Dieser Wert bestimmt, welches Sprachwörterbuch für Silbentrennung und Rechtschreibprüfung verwendet wird. Es wirkt sich auch auf die Anzeige von Ziffern aus, und wie das Fallbacksystem für Schriftarten entscheidet, welche Schriftart zu benutzen ist. Schließlich beeinflusst die Eigenschaft auch, wie Zahlen formatiert und in welcher Form komplexe Schriften dargestellt werden. Der Standardwert ist „en-US”.  
  
 **Erstellen eine Satellitenressourcenassembly**  
  
 *In .csproj:*  
  
 `<UICulture>en-US</UICulture>`  
  
 Beachten Sie das Hinzufügen einer `UICulture` Wert. Wenn dies festgelegt ist auf eine gültige <xref:System.Globalization.CultureInfo> Wert z. B. En-US, beim Erstellen des Projekts eine Satellitenassembly mit alle lokalisierbaren Ressourcen bei der es generiert.  
  
 `<Resource Include="RunIcon.JPG">`  
  
 `<Localizable>False</Localizable>`  
  
 `</Resource>`  
  
 Die `RunIcon.JPG` muss nicht lokalisiert werden, da es für alle Kulturen angezeigt werden soll. `Localizable` wird festgelegt, um `false` , damit es weiterhin in der sprachneutralen Hauptassembly die Satellitenassembly ist. Der Standardwert aller nicht kompilierbaren Ressourcen ist `Localizable` festgelegt `true`.  
  
 **Lokalisieren des Dialogfelds „Ausführen”**  
  
 **Auslesen**  
  
 Nachdem die Anwendung erstellt, ist der erste Schritt bei der Lokalisierung, die lokalisierbaren Ressourcen aus der Satellitenassembly auszulesen. Verwenden Sie für die Zwecke dieses Themas, die LocBaml Beispieltool am befinden sich [LocBaml Tool Sample](http://go.microsoft.com/fwlink/?LinkID=160016). Beachten Sie, dass LocBaml lediglich ein Beispieltool ist, das Ihnen beim Erstellen eines Lokalisierungstools helfen soll, das Ihrem Lokalisierungsprozess entspricht. Mithilfe von LocBaml führen Sie Folgendes analysieren: **LocBaml/parse RunDialog.resources.dll/out:** zum Generieren einer Datei "RunDialog.resources.dll.CSV".  
  
 **Lokalisieren**  
  
 Verwenden Sie zum Bearbeiten dieser Datei Ihren bevorzugten Unicode-fähigen CSV-Editor. Filtern Sie alle Einträge mit einer Lokalisierungskategorie von „None” heraus. Sie sollten folgende Einträge sehen:  
  
|Ressourcenschlüssel|Lokalisierungskategorie|Wert|  
|-|-|-| 
|Button_1:System.Windows.Controls.Button.$Content|Schaltfläche|OK|  
|Button_2:System.Windows.Controls.Button.$Content|Schaltfläche|Abbrechen|  
|Button_3:System.Windows.Controls.Button.$Content|Schaltfläche|Durchsuchen...|  
|ComboBox_1:System.Windows.Controls.ComboBox.$Content|ComboBox||  
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Text|Geben Sie den Namen eines Programms, Ordners, Dokuments oder einer Internetressource ein, damit Windows das entsprechende Objekt öffnet.|  
|TextBlock_2:System.Windows.Controls.TextBlock.$Content|Text|Öffnen:|  
|Window_1:System.Windows.Window.Title|Titel|Run|  
  
 Um die Anwendung auf Deutsch zu lokalisieren, sind die folgenden Übersetzungen erforderlich:  
  
|Ressourcenschlüssel|Lokalisierungskategorie|Wert|  
|-|-|-| 
|Button_1:System.Windows.Controls.Button.$Content|Schaltfläche|OK|  
|Button_2:System.Windows.Controls.Button.$Content|Schaltfläche|Abbrechen|  
|Button_3:System.Windows.Controls.Button.$Content|Schaltfläche|Durchsuchen…|  
|ComboBox_1:System.Windows.Controls.ComboBox.$Content|ComboBox||  
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Text|Geben Sie den Namen eines Programms, Ordners, Dokuments oder einer Internetressource an.|  
|TextBlock_2:System.Windows.Controls.TextBlock.$Content|Text|Öffnen:|  
|Window_1:System.Windows.Window.Title|Titel|Ausführen|  
  
 **Generieren**  
  
 Der letzte Schritt der Lokalisierung umfasst das Erstellen der neu lokalisierten Satellitenassembly. Dies kann mithilfe des folgenden LocBaml-Befehls erreicht werden:  
  
 **LocBaml.exe /generate RunDialog.resources.dll /trans:RunDialog.resources.dll.CSV /out: . /cul:de-DE**  
  
 Auf Deutsch [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], wenn diese Datei resources.dll in einem Ordner de-DE neben der Hauptassembly platziert wird, wird diese Ressource automatisch nicht die im Ordner "En-US" geladen. Wenn Sie eine deutsche Version eines keine [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] um dies zu testen, legen Sie die Kultur auf die Kultur des [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Sie verwenden (z. B. En-US), und Ersetzen Sie den ursprünglichen resources.dll.  
  
 **Laden der Satellitenressourcen**  
  
|MyDialog.exe|en-US\MyDialog.resources.dll|de-DE\MyDialog.resources.dll|  
|------------------|------------------------------------|------------------------------------|  
|Code|Ursprüngliche englische BAML|Lokalisierte BAML|  
|Kulturneutrale Ressourcen|Weitere Ressourcen auf Englisch|Weitere ins Deutsche lokalisierte Ressourcen|  
  
 .NET Framework wählt automatisch basierend auf der Anwendungsverzeichnis laden Satellitenressourcenassembly `Thread.CurrentThread.CurrentUICulture`. Die Kultur der wird standardmäßig die [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] OS. Dies der Fall ist bei Verwendung von Deutsch [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], die de-DE\MyDialog.resources.dll geladen wird, bei Verwendung von Englisch [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], lädt die en-US\MyDialog.resources.dll. Sie können für Ihre Anwendung die endgültige Fallbackressource durch Angabe von NeutralResourcesLanguage in der AssemblyInfo.* Ihres Projekts festlegen. Wenn Sie also z.B. folgendes angeben:  
  
 `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]`  
  
 dann wird in einem deutschen Windows die „en-US\MyDialog.resources.dll” verwendet, wenn weder „de-DE\MyDialog.resources.dll” noch „de\MyDialog.resources.dll” verfügbar sind.  
  
### <a name="microsoft-saudi-arabia-homepage"></a>Homepage von Microsoft Saudi-Arabien  
 Die folgende Abbildung zeigt eine englische und eine arabische Homepage. Das vollständige Beispiel, das diese Grafiken erzeugt finden Sie unter [Globalization Homepage Sample](http://go.microsoft.com/fwlink/?LinkID=159990).  
  
 **Englisch:**  
  
 ![Englische Seite](../../../../docs/framework/wpf/advanced/media/englishhomepage.jpg "EnglishHomepage")  
  
 **Arabisch:**  
  
 ![Arabische Seite](../../../../docs/framework/wpf/advanced/media/arabichomepage.jpg "ArabicHomepage")  
  
### <a name="designing-a-global-microsoft-homepage"></a>Entwerfen einer globalen Microsoft-Homepage  
 Dieses Modell der Microsoft Saudi-Arabien Website veranschaulicht die Globalisierungsfeatures für Sprachen in rechts-nach-links-Schreibweise. Sprachen wie z. B. Hebräisch und Arabisch haben eine rechts-nach-Links-Lesefolge, sodass das Layout der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] müssen häufig angelegt werden hingegen anders, als wäre in links-nach-rechts-Sprachen wie Englisch. Die Lokalisierung von einer links-nach-rechts-Sprache in eine rechts-nach-links-Sprache oder umgekehrt kann sehr anspruchsvoll sein. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wurde entwickelt, um solche Lokalisierungsanforderungen wesentlich zu erleichtern.  
  
 **FlowDirection**  
  
 *Homepage.xaml:*  
  
 [!code-xaml[GlobalizationHomepage#Homepage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#homepage)]  
  
 Beachten Sie, dass die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft <xref:System.Windows.Controls.Page>. Ändern diese Eigenschaft auf <xref:System.Windows.FlowDirection.RightToLeft> ändert sich die <xref:System.Windows.FrameworkElement.FlowDirection%2A> von der <xref:System.Windows.Controls.Page> und seine untergeordneten Elemente, damit das Layout dieses [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] rechts-nach-links dahingehend, wie ein Arabische Benutzer erwarten gekippt wird. Eine Indizierungsoperationen kann der Vererbungsverhalten explizites <xref:System.Windows.FrameworkElement.FlowDirection%2A> auf ein beliebiges Element. Die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft steht auf jedem <xref:System.Windows.FrameworkElement> oder dokumentbezogenen Element und hat einen impliziten Wert von <xref:System.Windows.FlowDirection.LeftToRight>.  
  
 Beachten Sie, dass sogar die Farbverlaufspinsel Hintergrund ordnungsgemäß, wenn gekippt werden der Stamm <xref:System.Windows.FrameworkElement.FlowDirection%2A> geändert wird:  
  
 **FlowDirection="LeftToRight"**  
  
 ![Lesefluss von links nach rechts](../../../../docs/framework/wpf/advanced/media/lefttoright.PNG "LeftToRight")  
  
 **FlowDirection="RightToLeft"**  
  
 ![Lesefluss von rechts nach links](../../../../docs/framework/wpf/advanced/media/righttoleft.PNG "RightToLeft")  
  
 **Verwenden Sie keine feste Abmessungen für Bereiche und Steuerelemente**  
  
 Betrachten Sie Homepage.xaml, beachten Sie, dass abgesehen von der feste Breite und Höhe angegeben wird, für die gesamte [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] am oberen Rand <xref:System.Windows.Controls.DockPanel>, keine anderen festen Dimensionen vorhanden sind. Vermeiden Sie feste Abmessungen, um zu vermeiden, dass lokalisierter Text, der länger als der Quelltext werden kann, abgeschnitten wird. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Bereiche und Steuerelemente passen ihre Größe automatisch dem ihres Inhalts an. Die meisten Steuerelemente haben außerdem Mindest- und Höchstmaße, die Sie für mehr Kontrolle angeben können (z.B. MinWidth="20"). Mit <xref:System.Windows.Controls.Grid>, Sie können auch die relative Breite und Höhe festlegen, mit "*" (z. B. Width = "0,25\*"), oder verwenden Sie die Größe der Zelle freigeben.  
  
 **Lokalisierungskommentare**  
  
 Es gibt viele Fälle, in denen Inhalt mehrdeutig und schwierig zu übersetzen sein kann. Der Entwickler oder Designer verfügt über die Möglichkeit, zusätzlichen Kontext und Kommentare für Lokalisierer über Lokalisierungskommentare bereitzustellen. So verdeutlicht z.B. „Localization.Comments” im nachstehenden Beispiel die Verwendung des Zeichens '&#124'.  
  
 [!code-xaml[GlobalizationHomepage#LocalizationComment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcomment)]  
  
 Dieser Kommentar TextBlock_1 Inhalt und im Falle des LocBaml-Tools zugeordnet wird (finden Sie unter [Lokalisieren einer Anwendung](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)), kann in der Spalte 6. der TextBlock_1 Zeile in der Ausgabe CSV-Datei angezeigt werden:  
  
|Ressourcenschlüssel|Kategorie|Lesbar|Änderbar|Kommentar|Wert|  
|-|-|-|-|-|-|  
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Text|TRUE|true|Dieses Zeichen wird als dekorative Abgrenzungslinie verwendet.|&#124;|  
  
 Kommentare können auf den Inhalt oder die Eigenschaften jedes Elements mithilfe der folgenden Syntax platziert werden:  
  
 [!code-xaml[GlobalizationHomepage#LocalizationCommentsProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcommentsprop)]  
  
 **Lokalisierungsattribute**  
  
 Häufig muss der Entwickler oder Lokalisierungsmanager Kontrolle darüber haben, was Lokalisierer lesen und ändern können. Sie möchten z.B. nicht, dass der Lokalisierer den Namen Ihres Unternehmens oder eine rechtliche Floskel übersetzt. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet Attribute, mit denen Sie die Lesbarkeit, Änderbarkeit und Kategorie des Inhalts eines Elements oder einer Eigenschaft festlegen können. Diese Attribute kann Ihr Lokalisierungstool zum Sperren, Ausblenden oder Sortieren von Elementen verwenden. Weitere Informationen finden Sie unter <xref:System.Windows.Localization.Attributes%2A>. Für die Zwecke dieses Beispiels gibt das LocBaml-Tool nur die Werte dieser Attribute aus. Alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente besitzen Standardwerte für diese Attribute, die Sie aber überschreiben können. Im folgende Beispiel überschreibt z. B. die Lokalisierung Standardattribute für `TextBlock_1` und der Inhalt lesbar sein für Lokalisierungsexperten jedoch als nicht änderbar festgelegt.  
  
 [!code-xaml[LocalizationComAtt#LocalizationAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributes)]  
  
 Zusätzlich zu der Lesbarkeit und die Attribute der Änderbarkeit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine Enumeration von allgemeinen UI Kategorien (<xref:System.Windows.LocalizationCategory>), die verwendet werden kann, um Lokalisierungsexperten mehr Kontext zu gewähren. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Standardkategorien für Plattformsteuerelemente können überschrieben werden, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ebenfalls:  
  
 [!code-xaml[LocalizationComAtt#LocalizationAttributesOverridden](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributesoverridden)]  
  
 Die Standard-Lokalisierung Attribute, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet kann auch mithilfe von Code überschrieben werden, sodass Sie die richtigen Standardwerte für benutzerdefinierte Steuerelemente ordnungsgemäß einrichten können. Zum Beispiel:  
  
 `[Localizability(Readability = Readability.Readable, Modifiability=Modifiability.Unmodifiable, LocalizationCategory.None)]`  
  
 `public class CorporateLogo: TextBlock`  
  
 `{`  
  
 `…`  
  
 `..`  
  
 `.`  
  
 `}`  
  
 Den pro Instanz Attributsatz [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Vorrang vor der Werte im Code für benutzerdefinierte Steuerelemente. Weitere Informationen zu Attributen und Kommentaren finden Sie unter [Lokalisierungsattribute und Kommentare](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md).  
  
 **Schriftart-Fallback und zusammengesetzte Schriftarten**  
  
 Wenn Sie eine Schriftart angeben, die nicht über einen gegebenen Bereich unterstützt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird automatisch fallback auf einen, die mithilfe der globalen Interface.compositefont Benutzer, die im Verzeichnis Windows\Fonts befindet. Zusammengesetzte Schriftarten funktionieren wie jede andere Schriftart und können durch explizites Festlegen der FontFamily-Eigenschaft eines Elements verwendet werden (z.B. FontFamily = "Global User Interface"). Sie können Ihre eigene bevorzugte Ausweichschriftart angeben, indem Sie eine eigene zusammengesetzte Schriftart erstellen und angeben, welche Schriftart jeweils für bestimmte Codepunkt-Bereiche und Sprachen verwendet werden soll.  
  
 Weitere Informationen zu zusammengesetzten Schriftarten finden Sie unter <xref:System.Windows.Media.FontFamily>.  
  
 **Lokalisieren der Microsoft-Homepage**  
  
 Sie können die gleichen Schritte wie im Beispiel zum Dialogfeld „Ausführen” nutzen, um diese Anwendung zu lokalisieren. Die lokalisierte CSV-Datei für Arabisch steht für Sie in der [Globalization Homepage Sample](http://go.microsoft.com/fwlink/?LinkID=159990).
