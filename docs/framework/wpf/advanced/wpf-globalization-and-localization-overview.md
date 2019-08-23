---
title: Übersicht über WPF-Globalisierung und -Lokalisierung
ms.date: 03/30/2017
helpviewer_keywords:
- globalization [WPF], about globalization
- localization [WPF], about localization
ms.assetid: 56e5a5c8-6c96-4d19-b8e1-a5be1dc564af
ms.openlocfilehash: e34b61e14db1e7839173658d71a70240d63c5f8a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917582"
---
# <a name="wpf-globalization-and-localization-overview"></a>Übersicht über WPF-Globalisierung und -Lokalisierung

Wenn Sie die Verfügbarkeit Ihres Produkts auf eine Sprache beschränken, beschränken Sie damit auch Ihre potentielle Kundenbasis auf einen Bruchteil der 6,5 Milliarden Einwohner unseres Planeten. Wenn Ihre Anwendung eine globale Zielgruppe erreichen soll, ist die kostengünstige Lokalisierung Ihres Produktes eine der besten und effizientesten Möglichkeiten, mehr Kunden zu erreichen.

In dieser Übersicht wird die Globalisierung und [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Lokalisierung in eingeführt. Unter Globalisierung versteht man den Entwurf und die Entwicklung von Anwendungen, die an verschiedenen Orten funktionieren. So unterstützt Globalisierung z.B. lokalisierte Benutzeroberflächen und regionale Daten für Benutzer in unterschiedlichen Kulturen. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet globalisierte Entwurfs Features, einschließlich automatischem Layout, Satellitenassemblys und lokalisierten Attributen und Kommentaren.

Unter Lokalisierung versteht man die Übersetzung von Anwendungsressourcen in lokalisierte Versionen für die jeweiligen von der Anwendung unterstützten Kulturen. Wenn Sie in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]lokalisieren, verwenden Sie die APIs <xref:System.Windows.Markup.Localizer> im-Namespace. Diese APIs unterliegen dem Befehlszeilen Tool " [LocBaml Tool Sample](https://go.microsoft.com/fwlink/?LinkID=160016) ". Weitere Informationen zum Erstellen und Verwenden von LocBaml finden Sie unter [Lokalisieren einer Anwendung](how-to-localize-an-application.md).

## <a name="best-practices-for-globalization-and-localization-in-wpf"></a>Bewährte Methoden zur Globalisierung und Lokalisierung in WPF.

Sie können die in integrierten Globalisierungs-und Lokalisierungs Funktionen optimal nutzen, indem Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Design der Benutzeroberfläche und die Lokalisierungs bezogenen Tipps befolgen, die in diesem Abschnitt enthalten sind.

### <a name="best-practices-for-wpf-ui-design"></a>Bewährte Methoden für den Entwurf von WPF-Benutzeroberflächen

Wenn Sie ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]–-basiertes [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]entwerfen, sollten Sie die folgenden bewährten Methoden implementieren:

- Schreiben Sie [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], und vermeiden [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Sie es, Code zu erstellen. Wenn Sie das mithilfe [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]von erstellen, machen Sie es über integrierte Lokalisierungs-APIs verfügbar.

- Vermeiden Sie die Verwendung absoluter Positionen und fester Größe zum Anordnen von Inhalt. Verwenden Sie stattdessen die relative oder die automatische Größenanpassung.

  - Verwenden <xref:System.Windows.Window.SizeToContent%2A> Sie, und halten Sie breiten und `Auto`Höhen auf fest.

  - Vermeiden Sie <xref:System.Windows.Controls.Canvas> die Verwendung von [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]für das Layout von.

  - Verwenden <xref:System.Windows.Controls.Grid> Sie und dessen Größen Freigabe Feature.

- Lassen Sie an den Rändern zusätzlichen freien Platz, da lokalisierter Text häufig mehr Platz beansprucht. Zusätzlicher Leerraum kann überstehende Zeichen aufnehmen.

- Aktivieren <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> Sie <xref:System.Windows.Controls.TextBlock> auf, um Clipping zu vermeiden.

- Legen Sie das `xml:lang` -Attribut fest. Dieses Attribut beschreibt die Kultur eines bestimmten Elements und seiner untergeordneten Elemente. Der Wert dieser Eigenschaft ändert das Verhalten mehrerer Features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Es ändert z.B. das Verhalten von Silbentrennung, Rechtschreibprüfung, Zahlenersetzung, Formen komplexer Schriften und die Ausweich-Schriftart. Weitere Informationen zum Festlegen der [XML: lang-Behandlung in XAML](../../xaml-services/xml-lang-handling-in-xaml.md)finden Sie unter [Globalisierung für WPF](globalization-for-wpf.md) .

- Erstellen Sie eine angepasste zusammengesetzte Schriftart, um eine bessere Kontrolle der Schriftarten zu erhalten, die für verschiedene Sprachen verwendet werden. Standardmäßig [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet die GlobalUserInterface. Composite-Schriftart in Ihrem Windows\Fonts-Verzeichnis.

- Wenn Sie Navigationsanwendungen erstellen, die in einer Kultur lokalisiert werden können, die Text in einem Format <xref:System.Windows.FlowDirection> von rechts nach Links anzeigt, legen Sie explizit für jede Seite fest, um sicherzustellen, dass die Seite nicht von <xref:System.Windows.Navigation.NavigationWindow>geerbt <xref:System.Windows.FlowDirection> wird.

- Wenn Sie eigenständige Navigationsanwendungen erstellen, die außerhalb eines Browsers gehostet werden, legen Sie <xref:System.Windows.Application.StartupUri%2A> für die erste Anwendung auf einen <xref:System.Windows.Navigation.NavigationWindow> anstelle von auf eine `<Application StartupUri="NavigationWindow.xaml">`Seite (z. b.) fest. Dieser Entwurf ermöglicht es Ihnen, die <xref:System.Windows.FlowDirection> des Fensters und der Navigationsleiste zu ändern. Weitere Informationen und ein Beispiel finden Sie unter Beispiel für eine [Globalisierungs Homepage](https://go.microsoft.com/fwlink/?LinkID=159990).

### <a name="best-practices-for-wpf-localization"></a>Bewährte Methoden für die Lokalisierung in WPF

Wenn Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]– basierte Anwendungen lokalisieren, sollten Sie die folgenden bewährten Methoden implementieren:

- Verwenden Sie Lokalisierungs Kommentare, um zusätzlichen Kontext für Lokalisierer bereitzustellen.

- Verwenden Sie Lokalisierungs Attribute, um die Lokalisierung zu steuern, <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> anstatt Eigenschaften für Elemente selektiv zu weglassen. Weitere Informationen finden Sie unter [Lokalisierungs Attribute und-Kommentare](localization-attributes-and-comments.md) .

- Verwenden `msbuild -t:updateuid` Sie `-t:checkuid` und, um Eigenschaften <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> in Ihrem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]hinzuzufügen und zu überprüfen. Verwenden <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Sie Eigenschaften, um Änderungen zwischen Entwicklung und Lokalisierung zu verfolgen. <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>Eigenschaften helfen Ihnen beim Lokalisieren neuer Entwicklungsänderungen. Wenn Sie einem [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]manuell <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften hinzufügen, ist die Aufgabe in der Regel mühsam und weniger genau.

  - Bearbeiten oder ändern <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Sie Eigenschaften nicht, nachdem Sie mit der Lokalisierung begonnen haben.

  - Verwenden Sie keine doppelten <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften (Beachten Sie diesen Tipp, wenn Sie den Befehl "Kopieren und Einfügen" verwenden).

  - Legen Sie `UltimateResourceFallback` den Speicherort in AssemblyInfo. * fest, um die für das Fall Back geeignete Sprache `[assembly: NeutralResourcesLanguage("en-US",   UltimateResourceFallbackLocation.Satellite)]`anzugeben (z. b.).

    Wenn Sie Ihre Quellsprache in die Hauptassembly einschließen möchten, indem Sie das `<UICulture>` -Tag in der Projektdatei weglassen, legen Sie den `UltimateResourceFallback` Speicherort als Hauptassembly anstelle des `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.MainAssembly)]`Satelliten (z. b.) fest.

## <a name="localize-a-wpf-application"></a>Lokalisieren einer WPF-Anwendung

Wenn Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendung lokalisieren, haben Sie mehrere Optionen. Beispielsweise können Sie die lokalisierbaren Ressourcen in der Anwendung an eine [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] -Datei binden, lokalisierbaren Text in RESX-Tabellen speichern oder den [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Lokalisierer verwenden, um Dateien zu verwenden. In diesem Abschnitt wird ein Lokalisierungs Workflow beschrieben, der die BAML-Form von XAML verwendet, die mehrere Vorteile bietet:

- Sie können lokalisieren, nachdem Sie erstellt haben.

- Sie können auf eine neuere Version der BAML-Form von XAML aktualisieren, indem Sie lokzierungen aus einer älteren Version der BAML-Form von XAML durchsetzen, sodass Sie die Lokalisierung gleichzeitig durchsetzen können.

- Sie können die ursprünglichen Quell Elemente und die Semantik zur Kompilierzeit überprüfen, da die BAML-Form von XAML die kompilierte Form von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ist.

### <a name="localization-build-process"></a>Buildprozess für die Lokalisierung

Beim Entwickeln einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendung lautet der Buildprozess für die Lokalisierung wie folgt:

- Der Entwickler erstellt und globalisiert die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung. Der Entwickler legt `<UICulture>en-US</UICulture>` in der Projektdatei fest, sodass bei der Kompilierung der Anwendung eine sprachneutrale Hauptassembly generiert wird. Diese Assembly verfügt über eine ausgelagerte .resources.dll-Datei, die alle lokalisierbaren Ressourcen enthält. Optional können Sie die Quellsprache in der Hauptassembly belassen, da unsere Lokalisierungs-APIs Extraktion aus der Hauptassembly unterstützen.

- Wenn die Datei in den Build kompiliert wird, wird [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] der in die BAML-Form von XAML konvertiert. Die Kultur neutralen `MyDialog.exe` und Kultur abhängigen (englischen) `MyDialog.resources.dll` Dateien werden für englischsprachige Kunden freigegeben.

### <a name="localization-workflow"></a>Lokalisierungsworkflow

Der Lokalisierungsprozess beginnt, nachdem die nicht `MyDialog.resources.dll` lokalisierte Datei erstellt wurde. Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente und Eigenschaften im ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] werden mithilfe der APIs unter <xref:System.Windows.Markup.Localizer>aus der BAML-Form von XAML in Schlüssel-Wert-Paare extrahiert. Lokalisierer verwenden die Schlüssel-Wert-Paare, um die Anwendung zu lokalisieren. Sie können nach Abschluss der Lokalisierung aus den neuen Werten eine neue .resource.dll-Datei generieren.

Die Schlüssel der Schlüssel-Wert-Paare sind `x:Uid` Werte, die vom Entwickler in der ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]platziert werden. Diese `x:Uid` Werte ermöglichen der API das Nachverfolgen und Zusammenführen von Änderungen, die während der Lokalisierung zwischen dem Entwickler und dem Lokalisierer erfolgen. Wenn der Entwickler z. b. ändert [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , nachdem der Lokalisierer mit der Lokalisierung begonnen hat, können Sie die Entwicklungs Änderung mit der bereits abgeschlossenen Lokalisierungsarbeit zusammenführen, damit die minimale Übersetzungsarbeit verloren geht.

Die folgende Abbildung zeigt einen typischen auf der BAML-Form von XAML-basierenden Lokalisierungsworkflow. Dieses Diagramm setzt voraus, dass der Entwickler die Anwendung in Englisch schreibt. Der Entwickler erstellt und globalisiert die WPF-Anwendung. In der Projektdatei legt `<UICulture>en-US</UICulture>` der Entwickler fest, dass bei der Erstellung eine sprachneutrale Hauptassembly mit der Datei "Satellit. resources. dll" generiert wird, die alle lokalisierbaren Ressourcen enthält. Alternativ dazu können Sie auch Ihre Quellsprache in der Hauptassembly belassen, da unsere Lokalisierungs-APIs eine Extraktion aus der Hauptassembly unterstützen. Nach dem Buildprozess wird XAML in BAML kompiliert. Die kulturneutrale Datei „MyDialog.exe.resources.dll” wird an den englischsprachigen Kunden ausgeliefert.

![Diagramm, das den Lokalisierungs Workflow anzeigt.](./media/wpf-globalization-and-localization-overview/localization-workflow.png)

![Diagramm, das den nicht lokalisierten Workflow anzeigt.](./media/wpf-globalization-and-localization-overview/unlocalized-workflow.png)

## <a name="examples-of-wpf-localization"></a>Beispiele für WPF-Lokalisierung

Dieser Abschnitt enthält Beispiele für lokalisierte Anwendungen, die Ihnen helfen zu verstehen, wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen erstellt und lokalisiert werden.

#### <a name="run-dialog-box-example"></a>Beispiel-Dialogfeld „Ausführen”

Die folgende Grafik zeigt die Ausgabe des Beispiels für das Dialogfeld " **Ausführen** ".

**Englisch:**

![Screenshot, der ein englisches Dialogfeld "ausführen" anzeigt.](./media/wpf-globalization-and-localization-overview/run-dialog-box-english.png)

**Deutsch:**

![Screenshot, der das Dialogfeld "Deutsch ausführen" anzeigt.](./media/wpf-globalization-and-localization-overview/run-dialog-box-german.png)

**Entwerfen eines globalen Dialogfelds „Ausführen”**

In diesem Beispiel wird ein Dialogfeld **Ausführen** mithilfe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]und erstellt. Dieses Dialogfeld entspricht dem Dialogfeld **Ausführen** , das über das [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] Startmenü verfügbar ist.

Einige Highlights beim Erstellen von globalen Dialogfeldern sind:

**Automatisches Layout**

*In der Datei Window1.xaml:*

`<Window SizeToContent="WidthAndHeight">`

Die obige Window-Eigenschaft sorgt dafür, dass sich die Fenstergröße automatisch der Inhaltsgröße entsprechend anpasst. Diese Eigenschaft verhindert, dass Inhalt, der nach der Lokalisierung an Größe zunimmt, abgeschnitten wird. Im Gegenzug wird auch unnötiger Leerraum entfernt, wenn die Größe des Inhalts nach der Lokalisierung geschrumpft ist.

`<Grid x:Uid="Grid_1">`

<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>Eigenschaften werden benötigt, damit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Lokalisierungs-APIs ordnungsgemäß funktionieren.

Sie werden von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Lokalisierungs-APIs verwendet, um Änderungen zwischen der Entwicklung und Lokalisierung [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]von zu verfolgen. <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>mithilfe von Eigenschaften können Sie eine neuere Version von [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit einer älteren Lokalisierung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]von zusammenführen. Sie fügen eine <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaft hinzu, `msbuild -t:updateuid RunDialog.csproj` indem Sie in einer Befehlsshell ausführen. Dies ist die empfohlene Methode zum hinzu <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> fügen von Eigenschaften, da Sie in der Regel zeitaufwändig und weniger genau hinzugefügt werden. Sie können überprüfen <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> , ob die Eigenschaften ordnungsgemäß `msbuild -t:checkuid RunDialog.csproj`festgelegt sind.

Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] wird mit dem <xref:System.Windows.Controls.Grid> -Steuerelement strukturiert, das ein nützliches Steuerelement ist, um das automatische Layout in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]zu nutzen. Beachten Sie, dass das Dialogfeld in drei Zeilen und fünf Spalten unterteilt ist. Nicht eine der Zeilen-und Spaltendefinitionen hat eine Größe mit fester Größe. Daher können sich [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] die in jeder Zelle positionierten Elemente bei der Lokalisierung an die Größe vergrößert und verkleinert werden.

[!code-xaml[GlobalizationRunDialog#GridColumnDef](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef)]

Die ersten beiden Spalten, in denen die " **Open:** "-Bezeichnung und <xref:System.Windows.Controls.ComboBox> platziert werden, verwenden [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 10 Prozent der Gesamtbreite.

[!code-xaml[GlobalizationRunDialog#GridColumnDef2](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef2)]

Beachten Sie, dass im Beispiel das Feature für die gemeinsame <xref:System.Windows.Controls.Grid>Größenänderung von verwendet wird. Die letzten drei Spalten nutzen dies, indem Sie sich im gleichen <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A>befinden. Wie aus dem Namen der Eigenschaft zu erwarten ist, ermöglicht dies den Spalten, dieselbe Größe zu verwenden. Wenn also "Durchsuchen..." wird in die längere Zeichenfolge "Durchsuchen..." lokalisiert. alle Schaltflächen werden in der Breite vergrößert, anstatt eine kleine Schaltfläche "OK" und eine unverhältnismäßig große "Durchsuchen..." gedrückt.

**XML: lang**

`xml:lang="en-US"`

Beachten Sie, dass die [XML: lang-Behandlung in XAML](../../xaml-services/xml-lang-handling-in-xaml.md) am Stamm Element [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]von abgelegt wurde. Diese Eigenschaft beschreibt die Kultur eines bestimmten Elements und seiner untergeordneten Elemente. Dieser Wert wird von mehreren Features in verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und sollte bei der Lokalisierung entsprechend geändert werden. Dieser Wert bestimmt, welches Sprachwörterbuch für Silbentrennung und Rechtschreibprüfung verwendet wird. Es wirkt sich auch auf die Anzeige von Ziffern aus, und wie das Fallbacksystem für Schriftarten entscheidet, welche Schriftart zu benutzen ist. Schließlich beeinflusst die Eigenschaft auch, wie Zahlen formatiert und in welcher Form komplexe Schriften dargestellt werden. Der Standardwert ist „en-US”.

**Erstellen eine Satellitenressourcenassembly**

*In .csproj:*

Bearbeiten Sie `.csproj` die Datei, und fügen Sie das folgende- `<PropertyGroup>`Tag zu einem bedingungslosen hinzu:

`<UICulture>en-US</UICulture>`

Beachten Sie das Hinzufügen `UICulture` eines Werts. Wenn dies auf einen gültigen <xref:System.Globalization.CultureInfo> Wert (z. b. en-US) festgelegt ist, wird beim Erstellen des Projekts eine Satellitenassembly mit allen lokalisierbaren Ressourcen erstellt.

`<Resource Include="RunIcon.JPG">`

`<Localizable>False</Localizable>`

`</Resource>`

Der `RunIcon.JPG` muss nicht lokalisiert werden, da er für alle Kulturen identisch angezeigt werden sollte. `Localizable`ist auf `false` festgelegt, sodass Sie nicht in der Satellitenassembly, sondern in der sprach neutralen Hauptassembly verbleibt. Der Standardwert aller nicht Kompilier baren Ressourcen ist `Localizable` auf `true`festgelegt.

**Lokalisieren des Dialogfelds „Ausführen”**

**Auslesen**

Nachdem die Anwendung erstellt, ist der erste Schritt bei der Lokalisierung, die lokalisierbaren Ressourcen aus der Satellitenassembly auszulesen. Verwenden Sie für dieses Thema das Beispiel-LocBaml-Tool, das Sie unter [LocBaml Tool Sample](https://go.microsoft.com/fwlink/?LinkID=160016)finden. Beachten Sie, dass LocBaml lediglich ein Beispieltool ist, das Ihnen beim Erstellen eines Lokalisierungstools helfen soll, das Ihrem Lokalisierungsprozess entspricht. Führen Sie mithilfe von LocBaml Folgendes aus, um Folgendes zu analysieren: **LocBaml/parse RunDialog. resources. dll/out:** zum Generieren der Datei "RunDialog. resources. dll. csv".

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

Wenn sich diese Datei "Resources. dll" in einem Ordner "de-de" neben der Hauptassembly befindet, wird diese Ressource automatisch anstelle der im Ordner "en-US" geladen. Wenn Sie nicht über eine deutsche Version von Windows verfügen, um dies zu testen, legen Sie die Kultur auf eine beliebige Kultur von Fenstern fest (z `en-US`. b.), und ersetzen Sie die ursprüngliche Ressourcen-DLL.

**Laden der Satellitenressourcen**

|MyDialog.exe|en-US\MyDialog.resources.dll|de-DE\MyDialog.resources.dll|
|------------------|------------------------------------|------------------------------------|
|Code|Ursprüngliche englische BAML|Lokalisierte BAML|
|Kulturneutrale Ressourcen|Weitere Ressourcen auf Englisch|Weitere ins Deutsche lokalisierte Ressourcen|

.NET Framework wählt basierend auf den der Anwendung `Thread.CurrentThread.CurrentUICulture`automatisch aus, welche Satellitenressourcenassembly geladen werden soll. Standardmäßig wird die Kultur Ihres Windows-Betriebssystems verwendet. Wenn Sie also Deutsch Fenster verwenden, lädt de-DE\MyDialog.resources.dll, wenn Sie englische Fenster verwenden, die en-US\MyDialog.resources.dll-Auslastung. Sie können für Ihre Anwendung die endgültige Fallbackressource durch Angabe von NeutralResourcesLanguage in der AssemblyInfo.* Ihres Projekts festlegen. Wenn Sie also z.B. folgendes angeben:

`[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]`

dann wird in einem deutschen Windows die „en-US\MyDialog.resources.dll” verwendet, wenn weder „de-DE\MyDialog.resources.dll” noch „de\MyDialog.resources.dll” verfügbar sind.

### <a name="microsoft-saudi-arabia-homepage"></a>Homepage von Microsoft Saudi-Arabien

Die folgende Abbildung zeigt eine englische und eine arabische Homepage. Das gesamte Beispiel, das diese Grafiken erzeugt, finden Sie unter Beispiel für eine [Globalisierungs Homepage](https://go.microsoft.com/fwlink/?LinkID=159990).

**Englisch:**

![Screenshot, der eine englische Startseite anzeigt.](./media/wpf-globalization-and-localization-overview/english-home-page-sample.jpg)

**Arabisch:**

![Screenshot, der eine arabische Startseite zeigt.](./media/wpf-globalization-and-localization-overview/arabic-home-page-sample.jpg)

### <a name="designing-a-global-microsoft-home-page"></a>Entwerfen einer globalen Microsoft-Startseite

Dieses Modell der Microsoft Saudi-Arabien Website veranschaulicht die Globalisierungsfeatures für Sprachen in rechts-nach-links-Schreibweise. Sprachen, wie z. b. Hebräisch und Arabisch, haben eine Lesereihenfolge von rechts [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nach links, sodass das Layout von häufig anders angeordnet werden muss als in den Sprachen von links nach rechts (z. b. Englisch). Die Lokalisierung von einer links-nach-rechts-Sprache in eine rechts-nach-links-Sprache oder umgekehrt kann sehr anspruchsvoll sein. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wurde entwickelt, um solche Lokalisierungsanforderungen wesentlich zu erleichtern.

**FlowDirection**

*Homepage.xaml:*

[!code-xaml[GlobalizationHomepage#Homepage](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#homepage)]

Beachten Sie <xref:System.Windows.FrameworkElement.FlowDirection%2A> die- <xref:System.Windows.Controls.Page>Eigenschaft für. Wenn Sie diese Eigenschaft <xref:System.Windows.FlowDirection.RightToLeft> in ändern, <xref:System.Windows.FrameworkElement.FlowDirection%2A> ändert sich <xref:System.Windows.Controls.Page> die der-Elemente und der zugehörigen untergeordneten Elemente [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , sodass das Layout dieser Elemente von rechts nach links gekippt wird, wie ein arabischer Benutzer erwartet. Sie können das Vererbungs Verhalten überschreiben, indem <xref:System.Windows.FrameworkElement.FlowDirection%2A> Sie einen expliziten für jedes Element angeben. Die <xref:System.Windows.FrameworkElement.FlowDirection%2A> -Eigenschaft ist für alle <xref:System.Windows.FrameworkElement> -oder-Dokument bezogenen Elemente verfügbar und weist einen <xref:System.Windows.FlowDirection.LeftToRight>impliziten Wert von auf.

Beachten Sie, dass auch die Hintergrund Farbverlaufs Pinsel ordnungsgemäß gekippt <xref:System.Windows.FrameworkElement.FlowDirection%2A> werden, wenn der Stamm geändert wird:

**FlowDirection="LeftToRight"**

![Screenshot, der den Farbverlaufs Fluss von links nach rechts anzeigt.](./media/wpf-globalization-and-localization-overview/gradient-flow-left-right.png)

**FlowDirection="RightToLeft"**

![Screenshot, der den Farbverlauf von rechts nach Links anzeigt](./media/wpf-globalization-and-localization-overview/gradient-flow-right-left.png)

**Verwenden Sie keine feste Abmessungen für Bereiche und Steuerelemente**

Sehen Sie sich die Datei "Homepage. XAML" [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] an. Beachten Sie, dass abgesehen von der festgelegten Breite und Höhe im oberen <xref:System.Windows.Controls.DockPanel>Bereich keine anderen fixierten Dimensionen vorhanden sind. Vermeiden Sie feste Abmessungen, um zu vermeiden, dass lokalisierter Text, der länger als der Quelltext werden kann, abgeschnitten wird. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Bereiche und Steuerelemente passen ihre Größe automatisch dem ihres Inhalts an. Die meisten Steuerelemente verfügen auch über minimale und maximale Abmessungen, die Sie für mehr Kontrolle festlegen können (z. b. MinWidth = "20"). Mit <xref:System.Windows.Controls.Grid>können Sie auch relative breiten und Höhen festlegen, indem Sie "\* `Width="0.25*"`" (z. b.) verwenden oder die Freigabe Funktion für Zellen Größe verwenden.

**Lokalisierungskommentare**

Es gibt viele Fälle, in denen Inhalt mehrdeutig und schwierig zu übersetzen sein kann. Der Entwickler oder Designer verfügt über die Möglichkeit, zusätzlichen Kontext und Kommentare für Lokalisierer über Lokalisierungskommentare bereitzustellen. So verdeutlicht z.B. „Localization.Comments” im nachstehenden Beispiel die Verwendung des Zeichens '&#124'.

[!code-xaml[GlobalizationHomepage#LocalizationComment](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcomment)]

Dieser Kommentar wird dem TextBlock_1's-Inhalt zugeordnet, und im Fall des LocBaml-Tools (siehe [Lokalisieren einer Anwendung](how-to-localize-an-application.md)), kann er in der 6. Spalte der TextBlock_1-Zeile in der CSV-Ausgabedatei angezeigt werden:

|Ressourcenschlüssel|Kategorie|Lesbar|Änderbar|Kommentar|Wert|
|-|-|-|-|-|-|
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Text|TRUE|true|Dieses Zeichen wird als dekorative Abgrenzungslinie verwendet.|&#124;|

Kommentare können auf den Inhalt oder die Eigenschaften jedes Elements mithilfe der folgenden Syntax platziert werden:

[!code-xaml[GlobalizationHomepage#LocalizationCommentsProp](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcommentsprop)]

**Lokalisierungsattribute**

Häufig muss der Entwickler oder Lokalisierungsmanager Kontrolle darüber haben, was Lokalisierer lesen und ändern können. Sie möchten z.B. nicht, dass der Lokalisierer den Namen Ihres Unternehmens oder eine rechtliche Floskel übersetzt. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet Attribute, mit denen Sie die Lesbarkeit, Änderbarkeit und Kategorie des Inhalts eines Elements oder einer Eigenschaft festlegen können. Diese Attribute kann Ihr Lokalisierungstool zum Sperren, Ausblenden oder Sortieren von Elementen verwenden. Weitere Informationen finden Sie unter <xref:System.Windows.Localization.Attributes%2A>. Für die Zwecke dieses Beispiels gibt das LocBaml-Tool nur die Werte dieser Attribute aus. Alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente besitzen Standardwerte für diese Attribute, die Sie aber überschreiben können. Im folgenden Beispiel werden die Standard Lokalisierungs Attribute für `TextBlock_1` überschrieben, und der Inhalt wird so festgelegt, dass er lesbar, aber nicht änderbar für Lokalisierer ist.

[!code-xaml[LocalizationComAtt#LocalizationAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributes)]

Zusätzlich zu den Attributen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für die Lesbarkeit und Modifizierbarkeit stellt eine Enumeration allgemeiner Benutzeroberflächen Kategorien (<xref:System.Windows.LocalizationCategory>) bereit, die verwendet werden können, um Lokalisierern mehr Kontext zu geben. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Standardkategorien für Platt Form Steuerelemente können auch in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] überschrieben werden:

[!code-xaml[LocalizationComAtt#LocalizationAttributesOverridden](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributesoverridden)]

Die standardmäßigen Lokalisierungs Attribute [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , die bereitstellt, können auch durch Code überschrieben werden, sodass Sie die richtigen Standardwerte für benutzerdefinierte Steuerelemente korrekt festlegen können. Beispiel:

```csharp
[Localizability(Readability = Readability.Readable, Modifiability=Modifiability.Unmodifiable, LocalizationCategory.None)]
public class CorporateLogo : TextBlock
{
    // ...
}
```

Die in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] festgelegten Attribute pro Instanz haben Vorrang vor den Werten, die im Code für benutzerdefinierte Steuerelemente festgelegt werden. Weitere Informationen zu Attributen und Kommentaren finden Sie unter [Lokalisierungs Attribute und-Kommentare](localization-attributes-and-comments.md).

**Schriftart-Fallback und zusammengesetzte Schriftarten**

Wenn Sie eine Schriftart angeben, die einen bestimmten Code punktbereich nicht unterstützt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , wird automatisch ein Fall Back auf eine Schriftart durchführt, die mithilfe der globalen Benutzeroberfläche. compositefont, die sich in Ihrem Windows\Fonts-Verzeichnis befindet. Zusammengesetzte Schriftarten funktionieren genauso wie jede andere Schriftart und können explizit verwendet werden, `FontFamily` `FontFamily="Global User Interface"`indem die (z.) eines Elements festgelegt wird. Sie können Ihre eigene bevorzugte Ausweichschriftart angeben, indem Sie eine eigene zusammengesetzte Schriftart erstellen und angeben, welche Schriftart jeweils für bestimmte Codepunkt-Bereiche und Sprachen verwendet werden soll.

Weitere Informationen zu zusammengesetzten Schriftarten <xref:System.Windows.Media.FontFamily>finden Sie unter.

**Lokalisieren der Microsoft-Homepage**

Sie können die gleichen Schritte wie im Beispiel zum Dialogfeld „Ausführen” nutzen, um diese Anwendung zu lokalisieren. Die lokalisierte CSV-Datei für Arabisch steht Ihnen im Beispiel für die [Globalisierungs Homepage](https://go.microsoft.com/fwlink/?LinkID=159990)zur Verfügung.
