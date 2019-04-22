---
title: Übersicht über WPF-Globalisierung und -Lokalisierung
ms.date: 03/30/2017
helpviewer_keywords:
- globalization [WPF], about globalization
- localization [WPF], about localization
ms.assetid: 56e5a5c8-6c96-4d19-b8e1-a5be1dc564af
ms.openlocfilehash: c97ae4f277395a75fb7522ffb74061001c10e07d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819579"
---
# <a name="wpf-globalization-and-localization-overview"></a>Übersicht über WPF-Globalisierung und -Lokalisierung

Wenn Sie die Verfügbarkeit Ihres Produkts auf eine Sprache beschränken, beschränken Sie damit auch Ihre potentielle Kundenbasis auf einen Bruchteil der 6,5 Milliarden Einwohner unseres Planeten. Wenn Ihre Anwendung eine globale Zielgruppe erreichen soll, ist die kostengünstige Lokalisierung Ihres Produktes eine der besten und effizientesten Möglichkeiten, mehr Kunden zu erreichen.  
  
 Diese Übersicht enthält, Globalisierung und Lokalisierung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Unter Globalisierung versteht man den Entwurf und die Entwicklung von Anwendungen, die an verschiedenen Orten funktionieren. So unterstützt Globalisierung z.B. lokalisierte Benutzeroberflächen und regionale Daten für Benutzer in unterschiedlichen Kulturen. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt globalisierte Designfeatures zur, darunter Automatisches Layout, Satellitenassemblys sowie lokalisierte Attribute und Kommentare.
  
 Unter Lokalisierung versteht man die Übersetzung von Anwendungsressourcen in lokalisierte Versionen für die jeweiligen von der Anwendung unterstützten Kulturen. Bei der Lokalisierung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], verwenden Sie die APIs in der <xref:System.Windows.Markup.Localizer> Namespace. Diese APIs Power der [Beispieltool LocBaml](https://go.microsoft.com/fwlink/?LinkID=160016) -Befehlszeilentool. Informationen zum Erstellen und Verwenden von LocBaml finden Sie unter [Lokalisieren einer Anwendung](how-to-localize-an-application.md).
  
## <a name="best-practices-for-globalization-and-localization-in-wpf"></a>Bewährte Methoden zur Globalisierung und Lokalisierung in WPF.

 Sie können die meisten der Globalisierung und Lokalisierung Funktionen, die in integrierten machen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] anhand der UI-Entwurf und die Lokalisierungs-bezogene Tipps, die dieser Abschnitt enthält.  
  
### <a name="best-practices-for-wpf-ui-design"></a>Bewährte Methoden für den Entwurf von WPF-Benutzeroberflächen

 Beim Entwerfen einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]– basierten [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], sollten Sie diese bewährten Methoden halten:  
  
-   Schreiben Ihrer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; erstellen Sie keine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] im Code. Bei der Erstellung Ihrer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], machen Sie es über den integrierten Lokalisierungs-APIs.  
  
-   Vermeiden Sie die Verwendung absoluter Positionierung und Dimensionierung zum Setzen von Inhaltselementen; Verwenden Sie stattdessen relative oder automatische größenanpassung.
  
    -   Verwendung <xref:System.Windows.Window.SizeToContent%2A> und halten Sie Breiten und Höhen festlegen, um `Auto`.  
  
    -   Verwenden Sie <xref:System.Windows.Controls.Canvas> für das Layout [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]s.  
  
    -   Verwendung <xref:System.Windows.Controls.Grid> und das Feature Größeninformationen.  
  
-   Lassen Sie an den Rändern zusätzlichen freien Platz, da lokalisierter Text häufig mehr Platz beansprucht. Zusätzlicher Leerraum kann überstehende Zeichen aufnehmen.  
  
-   Aktivieren Sie <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> auf <xref:System.Windows.Controls.TextBlock> , dies zu vermeiden.
  
-   Legen Sie das `xml:lang` -Attribut fest. Dieses Attribut beschreibt die Kultur eines bestimmten Elements und seiner untergeordneten Elemente. Der Wert dieser Eigenschaft ändert das Verhalten mehrerer Features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Es ändert z.B. das Verhalten von Silbentrennung, Rechtschreibprüfung, Zahlenersetzung, Formen komplexer Schriften und die Ausweich-Schriftart. Finden Sie unter [Globalisierung für WPF](globalization-for-wpf.md) für Weitere Informationen zum Festlegen der [XML: lang Handling in XAML](../../xaml-services/xml-lang-handling-in-xaml.md).  
  
-   Erstellen Sie eine benutzerdefinierte zusammengesetzte Schriftart, um eine bessere Kontrolle über Schriftarten zu erhalten, die für verschiedene Sprachen verwendet werden. In der Standardeinstellung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet die Schriftart GlobalUserInterface.composite im Verzeichnis Windows\Fonts.  
  
-   Beim Erstellen von Navigations-Anwendungen, die lokalisiert werden kann, in einer Kultur, die Text im rechts-nach-links-Format dargestellt, explizit festlegen der <xref:System.Windows.FlowDirection> jeder Seite, um sicherzustellen, dass die Seite erbt nicht <xref:System.Windows.FlowDirection> aus der <xref:System.Windows.Navigation.NavigationWindow>.  
  
-   Legen Sie beim Erstellen von eigenständigen Navigations-Anwendungen, die außerhalb eines Browsers gehostet werden die <xref:System.Windows.Application.StartupUri%2A> für die erste Anwendung auf eine <xref:System.Windows.Navigation.NavigationWindow> statt auf eine Seite (z. B. `<Application StartupUri="NavigationWindow.xaml">`). Dieser Entwurf ermöglicht es Ihnen so ändern Sie die <xref:System.Windows.FlowDirection> des Fensters und in der Navigationsleiste auf. Weitere Informationen und ein Beispiel finden Sie unter [Beispiel für eine globalisierte Homepage](https://go.microsoft.com/fwlink/?LinkID=159990).  
  
### <a name="best-practices-for-wpf-localization"></a>Bewährte Methoden für die Lokalisierung in WPF

 Bei der Lokalisierung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]– basierenden Anwendungen, sollten Sie diese bewährten Methoden halten:  
  
-   Verwenden Sie Lokalisierungskommentare, um zusätzlichen Kontext für Lokalisierer bereitzustellen.  
  
-   Verwenden Sie Lokalisierungsattribute, Lokalisierung, statt selektiv steuern <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften für Elemente. Finden Sie unter [Lokalisierungsattribute und-Kommentare](localization-attributes-and-comments.md) für Weitere Informationen.  
  
-   Verwendung `msbuild -t:updateuid` und `-t:checkuid` zum Hinzufügen und prüfen <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften in Ihrem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Verwendung <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften zum Nachverfolgen von Änderungen zwischen Entwicklung und Lokalisierung. <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften können Sie die Lokalisierung neuer entwicklungsänderungen. Wenn Sie manuell hinzufügen <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften, die eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], die Aufgabe besteht in der Regel aufwendig und weniger genau.  
  
    -   Bearbeiten oder ändern Sie nicht <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften, die nach Beginn der Lokalisierung.  
  
    -   Verwenden Sie keine doppelten <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> -Eigenschaften (Denken Sie daran, wenn Sie den Befehl Kopieren und Einfügen verwenden).  
  
    -   Legen Sie die `UltimateResourceFallback` Position in der AssemblyInfo, um die entsprechende Ausweichsprache anzugeben (z. B. `[assembly: NeutralResourcesLanguage("en-US",   UltimateResourceFallbackLocation.Satellite)]`).  
  
         Wenn Sie sich entscheiden sollen Ihre Quellsprache in der Hauptassembly durch Auslassen der `<UICulture>` markieren Sie in Ihrer Projektdatei hinzu, legen Sie die `UltimateResourceFallback` Speicherort wie die Hauptassembly statt des Satelliten (z. B. `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.MainAssembly)]`).  
  
## <a name="localize-a-wpf-application"></a>Lokalisieren einer WPF-Anwendung

Bei der Lokalisierung einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendung haben Sie mehrere Optionen. Sie können z. B. lokalisierbaren Ressourcen in Ihrer Anwendung zum Binden einer [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Datei, lokalisierbaren Text in Resx-Tabellen speichern oder Ihren Lokalisierungsexperten anweisen verwenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Dateien. Dieser Abschnitt beschreibt einen Lokalisierungsworkflow, der die BAML-Form von XAML, verwendet die mehrere Vorteile bietet:  
  
-   Sie können lokalisieren, nachdem Sie erstellt haben.  
  
-   Sie können auf eine neuere Version der BAML-Form von XAML mit lokalisierten Versionen von einer älteren Version der BAML-Form von XAML aktualisieren, damit Sie gleichzeitig auch lokalisieren können, die Sie entwickeln.  
  
-   Sie können überprüfen, originalen Quellelemente und Semantik zum Zeitpunkt der Kompilierung, weil die BAML-Form von XAML die kompilierte Form von ist [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
### <a name="localization-build-process"></a>Buildprozess für die Lokalisierung  

Bei der Entwicklung einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung des Buildprozesses für die Lokalisierung lautet wie folgt:  
  
-   Der Entwickler erstellt und globalisiert die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung. Im Projekt die Datei der Entwickler legt `<UICulture>en-US</UICulture>` , wenn die Anwendung kompiliert wird, wird eine sprachneutrale Hauptassembly generiert. Diese Assembly verfügt über eine ausgelagerte .resources.dll-Datei, die alle lokalisierbaren Ressourcen enthält. Optional, Sie können Anzeigen der Source-Sprache in der Hauptassembly da unsere Lokalisierungs- [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] Extraktion aus der Hauptassembly unterstützen.  
  
-   Wenn die Datei in den Build kompiliert wird die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in BAML-Form von XAML konvertiert wird. Die kulturneutrale `MyDialog.exe` und die kulturspezifische (in englischer Sprache) `MyDialog.resources.dll` Dateien für die englischsprachige Kunden freigegeben werden.  
  
### <a name="localization-workflow"></a>Lokalisierungsworkflow

Der Lokalisierungsprozess beginnt nach der nicht lokalisierte `MyDialog.resources.dll` -Datei erstellt wird. Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente und Eigenschaften in Ihrem ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] werden mithilfe von BAML-Form von XAML in Schlüssel-Wert-Paare extrahiert die [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] unter <xref:System.Windows.Markup.Localizer>. Lokalisierer verwenden die Schlüssel-Wert-Paare, um die Anwendung zu lokalisieren. Sie können nach Abschluss der Lokalisierung aus den neuen Werten eine neue .resource.dll-Datei generieren.
  
 Die Schlüssel des Schlüssel-Wert-Paare sind `x:Uid` Werte, die vom Entwickler in der ursprünglichen platziert werden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Diese `x:Uid` Werte ermöglichen die [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] nachverfolgen und Änderungen, die zwischen dem Entwickler und der Lokalisierer, bei der Lokalisierung auftreten zusammenführen. Wenn der Entwickler ändert z. B. die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , nachdem der Lokalisierer hat begonnen, können Sie die Änderung der Entwicklung mit der Arbeit bereits abgeschlossenen Lokalisierung zusammenführen, so, dass Arbeit verloren geht.  
  
 Die folgende Abbildung zeigt einen typischen auf der BAML-Form von XAML-basierenden Lokalisierungsworkflow. In diesem Diagramm wird davon ausgegangen, dass der Entwickler die Anwendung schreibt, in englischer Sprache. Der Entwickler erstellt und globalisiert die WPF-Anwendung. Im Projekt die Datei der Entwickler legt `<UICulture>en-US</UICulture>` , damit beim Buildvorgang eine sprachneutrale Hauptassembly generiert wird, eine. resources.dll, die alle lokalisierbare Ressourcen enthält. Alternativ dazu können Sie auch Ihre Quellsprache in der Hauptassembly belassen, da unsere Lokalisierungs-APIs eine Extraktion aus der Hauptassembly unterstützen. Nach dem Buildprozess wird XAML in BAML kompiliert. Die kulturneutrale Datei „MyDialog.exe.resources.dll” wird an den englischsprachigen Kunden ausgeliefert.  
  
 ![Das Diagramm zeigt den Workflow für die Lokalisierung.](./media/wpf-globalization-and-localization-overview/localization-workflow.png)  
  
 ![Das Diagramm zeigt den nicht lokalisierten Workflow.](./media/wpf-globalization-and-localization-overview/unlocalized-workflow.png)  
  
## <a name="examples-of-wpf-localization"></a>Beispiele für WPF-Lokalisierung

 Dieser Abschnitt enthält Beispiele von lokalisierten Anwendungen, die besser zu verstehen, wie Sie erstellen und Lokalisieren von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen.  
  
#### <a name="run-dialog-box-example"></a>Beispiel-Dialogfeld „Ausführen”

 Die folgende Abbildung zeigt die Ausgabe der **ausführen** Beispiel für ein Dialogfeld.  
  
 **Englisch:**  
  
 ![Der Screenshot zeigt ein Dialogfeld Englisch ausführen.](./media/wpf-globalization-and-localization-overview/run-dialog-box-english.png)  
  
 **Deutsch:**  
  
 ![Der Screenshot zeigt ein deutsches Dialogfeld Ausführen.](./media/wpf-globalization-and-localization-overview/run-dialog-box-german.png)  
  
 **Entwerfen eines globalen Dialogfelds „Ausführen”**  
  
 Dieses Beispiel erzeugt eine **ausführen** Dialogfeld mithilfe von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Dieses Dialogfeld entspricht dem der **ausführen** Dialogfeld, das in der [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] Menü "Start".  
  
 Einige Highlights beim Erstellen von globalen Dialogfeldern sind:  
  
 **Automatisches Layout**  
  
 *In der Datei Window1.xaml:*  
  
 `<Window SizeToContent="WidthAndHeight">`  
  
 Die obige Window-Eigenschaft sorgt dafür, dass sich die Fenstergröße automatisch der Inhaltsgröße entsprechend anpasst. Diese Eigenschaft verhindert, dass Inhalt, der nach der Lokalisierung an Größe zunimmt, abgeschnitten wird. Im Gegenzug wird auch unnötiger Leerraum entfernt, wenn die Größe des Inhalts nach der Lokalisierung geschrumpft ist.  
  
 `<Grid x:Uid="Grid_1">`  
  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften sind erforderlich, in der Reihenfolge für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Lokalisierung [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] ordnungsgemäß funktioniert.  
  
 Sie werden verwendet, indem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Lokalisierung [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] zum Nachverfolgen von Änderungen zwischen der Entwicklung und Lokalisierung der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften können Sie eine neuere Version von Zusammenführen der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit einer älteren Lokalisierung der der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Sie fügen eine <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaft, indem Sie Ausführung `msbuild -t:updateuid RunDialog.csproj` in einer Befehlsshell. Dies ist die empfohlene Methode zum Hinzufügen von <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften da Manuelles Hinzufügen normalerweise sehr zeitaufwändig und weniger genau ist. Sie können überprüfen, die <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften werden durch die Ausführung ordnungsgemäß festgelegt `msbuild -t:checkuid RunDialog.csproj`.
  
 Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] strukturiert ist, mithilfe der <xref:System.Windows.Controls.Grid> -Steuerelement, das ein Steuerelement nützlich, für die Ausnutzung des automatischen Layouts ist in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Beachten Sie, dass das Dialogfeld in drei Zeilen und fünf Spalten unterteilt ist. Keiner der Zeilen- und Spaltendefinitionen hat eine feste Größe; daher die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente, die in jeder Zelle positioniert werden können, erhöht sich anpassen, dass bei der Lokalisierung vergrößern oder verkleinern.  
  
 [!code-xaml[GlobalizationRunDialog#GridColumnDef](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef)]  
  
 Die ersten beiden Spalten, in denen die **öffnen:** Bezeichnung und <xref:System.Windows.Controls.ComboBox> platziert werden 10 Prozent der der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Gesamtbreite.  
  
 [!code-xaml[GlobalizationRunDialog#GridColumnDef2](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef2)]  
  
 Beachten Sie, die der im Beispiel die größenteilungs-Funktion von verwendet <xref:System.Windows.Controls.Grid>. Die letzten drei Spalten nutzen diesen Umstand, in der gleichen <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A>. Wie aus dem Namen der Eigenschaft zu erwarten ist, ermöglicht dies den Spalten, dieselbe Größe zu verwenden. Wenn Sie "Durchsuchen..." zur längeren Zeichenfolge "Durchsuchen..." lokalisiert wird, wachsen alle Schaltflächen im breiter. ohne eine kleine Schaltfläche "OK" und eine unverhältnismäßig große "Durchsuchen..."-Schaltfläche.  
  
 **xml:lang**
  
 `xml:lang="en-US"`  
  
 Beachten Sie, dass die [XML: lang Handling in XAML](../../xaml-services/xml-lang-handling-in-xaml.md) platziert das Stammelement der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Diese Eigenschaft beschreibt die Kultur eines bestimmten Elements und seiner untergeordneten Elemente. Dieser Wert wird verwendet, von mehreren Features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und sollte bei der Lokalisierung entsprechend geändert werden. Dieser Wert bestimmt, welches Sprachwörterbuch für Silbentrennung und Rechtschreibprüfung verwendet wird. Es wirkt sich auch auf die Anzeige von Ziffern aus, und wie das Fallbacksystem für Schriftarten entscheidet, welche Schriftart zu benutzen ist. Schließlich beeinflusst die Eigenschaft auch, wie Zahlen formatiert und in welcher Form komplexe Schriften dargestellt werden. Der Standardwert ist „en-US”.  
  
 **Erstellen eine Satellitenressourcenassembly**  
  
 *In .csproj:*  

 Bearbeiten der `.csproj` Datei, und fügen Sie das folgende Tag, eine unbedingte `<PropertyGroup>`:
 
 `<UICulture>en-US</UICulture>`  
  
 Beachten Sie, dass das Hinzufügen einer `UICulture` Wert. Dies ist bei Festlegung auf einen gültigen <xref:System.Globalization.CultureInfo> Wert wie z. B. En-US, beim Erstellen des Projekts eine Satellitenassembly alle lokalisierbaren Ressourcen bei der es generiert.  
  
 `<Resource Include="RunIcon.JPG">`  
  
 `<Localizable>False</Localizable>`  
  
 `</Resource>`  
  
 Die `RunIcon.JPG` muss nicht lokalisiert werden, da sie für alle Kulturen identisch angezeigt werden soll. `Localizable` nastaven NA hodnotu `false` , damit es in der sprachneutralen Hauptassembly statt der Satellitenassembly verbleibt. Der Standardwert aller nicht kompilierbaren Ressourcen ist `Localizable` festgelegt `true`.  
  
 **Lokalisieren des Dialogfelds „Ausführen”**  
  
 **Auslesen**  
  
 Nachdem die Anwendung erstellt, ist der erste Schritt bei der Lokalisierung, die lokalisierbaren Ressourcen aus der Satellitenassembly auszulesen. Für die Zwecke dieses Themas, verwenden Sie das Beispieltool LocBaml die finden Sie unter [Beispieltool LocBaml](https://go.microsoft.com/fwlink/?LinkID=160016). Beachten Sie, dass LocBaml lediglich ein Beispieltool ist, das Ihnen beim Erstellen eines Lokalisierungstools helfen soll, das Ihrem Lokalisierungsprozess entspricht. Verwenden von LocBaml, führen Sie Folgendes analysieren: **LocBaml/parse RunDialog.resources.dll/out:** um eine "RunDialog.resources.dll.CSV"-Datei zu generieren.  
  
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
  
 Auf Deutsch [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], wenn diese "Resources.dll"-Datei in einen Ordner "de-DE" neben der Hauptassembly platziert wird, wird diese Ressource automatisch statt der im Ordner "En-US" geladen. Wenn Sie nicht über eine deutsche Version von verfügen [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] um dies zu testen, legen Sie die Kultur auf die Kultur des [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Sie verwenden (z. B. `en-US`), und Ersetzen Sie die ursprünglichen Ressourcen-DLL.  
  
 **Laden der Satellitenressourcen**  
  
|MyDialog.exe|en-US\MyDialog.resources.dll|de-DE\MyDialog.resources.dll|  
|------------------|------------------------------------|------------------------------------|  
|Code|Ursprüngliche englische BAML|Lokalisierte BAML|  
|Kulturneutrale Ressourcen|Weitere Ressourcen auf Englisch|Weitere ins Deutsche lokalisierte Ressourcen|  
  
 .NET Framework wählt automatisch die Satellitenressourcenassembly basierend auf der Anwendung laden `Thread.CurrentThread.CurrentUICulture`. Dies ist standardmäßig auf die Kultur des Ihre [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] OS. Dies der Fall ist bei Verwendung der deutschen [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], die de-DE\MyDialog.resources.dll geladen wird, wenn Sie Englisch verwenden [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], lädt die en-US\MyDialog.resources.dll. Sie können für Ihre Anwendung die endgültige Fallbackressource durch Angabe von NeutralResourcesLanguage in der AssemblyInfo.* Ihres Projekts festlegen. Wenn Sie also z.B. folgendes angeben:  
  
 `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]`  
  
 dann wird in einem deutschen Windows die „en-US\MyDialog.resources.dll” verwendet, wenn weder „de-DE\MyDialog.resources.dll” noch „de\MyDialog.resources.dll” verfügbar sind.  
  
### <a name="microsoft-saudi-arabia-homepage"></a>Homepage von Microsoft Saudi-Arabien  
 Die folgende Abbildung zeigt eine englische und eine arabische Homepage. Das vollständige Beispiel, das diese Abbildungen erzeugt finden Sie unter [Beispiel für eine globalisierte Homepage](https://go.microsoft.com/fwlink/?LinkID=159990).  
  
 **Englisch:**  
  
 ![Screenshot mit einer englischen-Homepage.](./media/wpf-globalization-and-localization-overview/english-home-page-sample.jpg)  
  
 **Arabisch:**  
  
 ![Der Screenshot zeigt eine arabische Homepage.](./media/wpf-globalization-and-localization-overview/arabic-home-page-sample.jpg)  
  
### <a name="designing-a-global-microsoft-home-page"></a>Entwerfen einer globalen Microsoft-Startseite  
 Dieses Modell der Microsoft Saudi-Arabien Website veranschaulicht die Globalisierungsfeatures für Sprachen in rechts-nach-links-Schreibweise. Sprachen wie Hebräisch und Arabisch haben eine rechts-nach-Links-Lesefolge, sodass das Layout der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] müssen häufig angeordnet werden etwas anders, als wäre es in links-nach-rechts-Sprachen wie Englisch. Die Lokalisierung von einer links-nach-rechts-Sprache in eine rechts-nach-links-Sprache oder umgekehrt kann sehr anspruchsvoll sein. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wurde entwickelt, um solche Lokalisierungsanforderungen wesentlich zu erleichtern.  
  
 **FlowDirection**  
  
 *Homepage.xaml:*  
  
 [!code-xaml[GlobalizationHomepage#Homepage](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#homepage)]  
  
 Beachten Sie, dass die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft <xref:System.Windows.Controls.Page>. Ändern diese Eigenschaft auf <xref:System.Windows.FlowDirection.RightToLeft> ändert sich die <xref:System.Windows.FrameworkElement.FlowDirection%2A> von der <xref:System.Windows.Controls.Page> und seiner untergeordneten Elemente, damit das Layout der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] rechts-nach-links ein Arabischer Benutzer dies erwarten würde steigender gekippt wird. Das Vererbungsverhalten lässt sich durch Angabe einer expliziten überschreiben <xref:System.Windows.FrameworkElement.FlowDirection%2A> auf ein beliebiges Element. Die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft steht auf jedem <xref:System.Windows.FrameworkElement> oder dokumentbezogenes Element und hat den impliziten Wert <xref:System.Windows.FlowDirection.LeftToRight>.  
  
 Beachten Sie, dass sogar die Hintergrund-Farbverlaufspinsel ordnungsgemäß, wenn gekippt werden der Stamm <xref:System.Windows.FrameworkElement.FlowDirection%2A> geändert wird:  
  
 **FlowDirection="LeftToRight"**  
  
 ![Screenshot, der den Farbverlauf Fluss von links nach rechts zeigt.](./media/wpf-globalization-and-localization-overview/gradient-flow-left-right.png)  
  
 **FlowDirection="RightToLeft"**  
  
 ![Screenshot, der den Farbverlauf Fluss von rechts nach links zeigt.](./media/wpf-globalization-and-localization-overview/gradient-flow-right-left.png)  
  
 **Verwenden Sie keine feste Abmessungen für Bereiche und Steuerelemente**  
  
 Nehmen Sie sich Homepage.XAML anschauen, beachten Sie, dass abgesehen von der feste Breite und Höhe angegeben, für die gesamte [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] am oberen Rand <xref:System.Windows.Controls.DockPanel>, es gibt keine anderen festen Abmessungen. Vermeiden Sie feste Abmessungen, um zu vermeiden, dass lokalisierter Text, der länger als der Quelltext werden kann, abgeschnitten wird. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Bereiche und Steuerelemente passen ihre Größe automatisch dem ihres Inhalts an. Die meisten Steuerelemente haben außerdem Mindest- und höchstmaße, die Sie für mehr Kontrolle angeben können (z.B. MinWidth = "20"). Mit <xref:System.Windows.Controls.Grid>, Sie können auch die relative Breiten und Höhen festlegen, indem Sie mit "\*" (z. B. `Width="0.25*"`) oder das größenteilungsfeature der Zelle verwenden.  
  
 **Lokalisierungskommentare**  
  
 Es gibt viele Fälle, in denen Inhalt mehrdeutig und schwierig zu übersetzen sein kann. Der Entwickler oder Designer verfügt über die Möglichkeit, zusätzlichen Kontext und Kommentare für Lokalisierer über Lokalisierungskommentare bereitzustellen. So verdeutlicht z.B. „Localization.Comments” im nachstehenden Beispiel die Verwendung des Zeichens '&#124'.  
  
 [!code-xaml[GlobalizationHomepage#LocalizationComment](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcomment)]  
  
 Dieser Kommentar wird im Fall des LocBaml-Tools und Inhalt von TextBlock_1 zugeordnet (finden Sie unter [Lokalisieren einer Anwendung](how-to-localize-an-application.md)), kann in der 6. Spalte der Zeile TextBlock_1 in der ausgegebenen CSV-Datei angezeigt werden:  
  
|Ressourcenschlüssel|Kategorie|Lesbar|Änderbar|Kommentar|Wert|  
|-|-|-|-|-|-|  
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Text|TRUE|true|Dieses Zeichen wird als dekorative Abgrenzungslinie verwendet.|&#124;|  
  
 Kommentare können auf den Inhalt oder die Eigenschaften jedes Elements mithilfe der folgenden Syntax platziert werden:  
  
 [!code-xaml[GlobalizationHomepage#LocalizationCommentsProp](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcommentsprop)]  
  
 **Lokalisierungsattribute**  
  
 Häufig muss der Entwickler oder Lokalisierungsmanager Kontrolle darüber haben, was Lokalisierer lesen und ändern können. Sie möchten z.B. nicht, dass der Lokalisierer den Namen Ihres Unternehmens oder eine rechtliche Floskel übersetzt. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet Attribute, mit denen Sie die Lesbarkeit, Änderbarkeit und Kategorie des Inhalts eines Elements oder einer Eigenschaft festlegen können. Diese Attribute kann Ihr Lokalisierungstool zum Sperren, Ausblenden oder Sortieren von Elementen verwenden. Weitere Informationen finden Sie unter <xref:System.Windows.Localization.Attributes%2A>. Für die Zwecke dieses Beispiels gibt das LocBaml-Tool nur die Werte dieser Attribute aus. Alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente besitzen Standardwerte für diese Attribute, die Sie aber überschreiben können. Im folgende Beispiel überschreibt z. B. die standardmäßigen Lokalisierungsattribute für `TextBlock_1` und der Inhalt lesbar sein für Lokalisierer aber nicht änderbar festgelegt.  
  
 [!code-xaml[LocalizationComAtt#LocalizationAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributes)]  
  
 Zusätzlich zu den Lesbarkeit und Änderbarkeit Attribute [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine Enumeration von allgemeinen Kategorien der Benutzeroberfläche (<xref:System.Windows.LocalizationCategory>), die verwendet werden kann, um Lokalisierern mehr Kontext bereitgestellt. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Standardkategorien für Plattformsteuerelemente können überschrieben werden, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ebenfalls:  
  
 [!code-xaml[LocalizationComAtt#LocalizationAttributesOverridden](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributesoverridden)]  
  
 Die standardmäßigen Lokalisierungsattribute, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet kann auch über Code überschrieben werden, damit Sie die richtigen Standardwerte für benutzerdefinierte Steuerelemente ordnungsgemäß festlegen können. Zum Beispiel:  

```csharp 
[Localizability(Readability = Readability.Readable, Modifiability=Modifiability.Unmodifiable, LocalizationCategory.None)] 
public class CorporateLogo : TextBlock
{
    // ...
}
``` 
 
 Der im festgelegten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Vorrang vor den Werten, die im Code für benutzerdefinierte Steuerelemente festgelegt. Weitere Informationen zu Attributen und Kommentaren finden Sie unter [Lokalisierungsattribute und-Kommentare](localization-attributes-and-comments.md).  
  
 **Schriftart-Fallback und zusammengesetzte Schriftarten**  
  
 Wenn Sie eine Schriftart angeben, die nicht über einen bestimmten Bereich unterstützt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] führen ein automatisches fallback auf eine, die mit die globale User-Codepunkten, die im Verzeichnis Windows\Fonts befindet. Zusammengesetzte Schriftarten funktionieren wie jede andere Schriftart und explizit durch Festlegen eines Elements verwendet werden können `FontFamily` (z. B. `FontFamily="Global User Interface"`). Sie können Ihre eigene bevorzugte Ausweichschriftart angeben, indem Sie eine eigene zusammengesetzte Schriftart erstellen und angeben, welche Schriftart jeweils für bestimmte Codepunkt-Bereiche und Sprachen verwendet werden soll.  
  
 Weitere Informationen zu zusammengesetzte Schriftarten finden Sie unter <xref:System.Windows.Media.FontFamily>.  
  
 **Lokalisieren der Microsoft-Homepage**  
  
 Sie können die gleichen Schritte wie im Beispiel zum Dialogfeld „Ausführen” nutzen, um diese Anwendung zu lokalisieren. Die lokalisierte CSV-Datei für Arabisch steht für Sie in der [Beispiel für eine globalisierte Homepage](https://go.microsoft.com/fwlink/?LinkID=159990).
