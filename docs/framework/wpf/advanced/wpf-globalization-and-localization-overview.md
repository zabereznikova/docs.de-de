---
title: Übersicht über Globalisierung und Lokalisierung
description: Erfahren Sie mehr über Lokalisierung und Globalisierung für Windows Presentation Foundation, einschließlich automatischem Layout, Satellitenassemblys und lokalisierten Attributen.
ms.date: 03/30/2017
helpviewer_keywords:
- globalization [WPF], about globalization
- localization [WPF], about localization
ms.assetid: 56e5a5c8-6c96-4d19-b8e1-a5be1dc564af
ms.openlocfilehash: 9a54ce2c265b989f99383ff9cdec961c80dd655c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168298"
---
# <a name="wpf-globalization-and-localization-overview"></a>Übersicht über WPF-Globalisierung und -Lokalisierung

Wenn Sie die Verfügbarkeit Ihres Produkts auf nur eine Sprache beschränken, beschränken Sie Ihre potenzielle Kundenbasis auf einen Bruchteil der 7,5 Milliarden-Population unserer Welt. Wenn Ihre Anwendung eine globale Zielgruppe erreichen soll, ist die kostengünstige Lokalisierung Ihres Produktes eine der besten und effizientesten Möglichkeiten, mehr Kunden zu erreichen.

In dieser Übersicht wird die Globalisierung und Lokalisierung in eingeführt [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] . Unter Globalisierung versteht man den Entwurf und die Entwicklung von Anwendungen, die an verschiedenen Orten funktionieren. So unterstützt Globalisierung z.B. lokalisierte Benutzeroberflächen und regionale Daten für Benutzer in unterschiedlichen Kulturen. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet globalisierte Entwurfs Features, einschließlich automatischem Layout, Satellitenassemblys und lokalisierten Attributen und Kommentaren.

Unter Lokalisierung versteht man die Übersetzung von Anwendungsressourcen in lokalisierte Versionen für die jeweiligen von der Anwendung unterstützten Kulturen. Wenn Sie in lokalisieren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , verwenden Sie die APIs im- <xref:System.Windows.Markup.Localizer> Namespace. Diese APIs unterliegen dem Befehlszeilen Tool " [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml) ". Weitere Informationen zum Erstellen und Verwenden von LocBaml finden Sie unter [Lokalisieren einer Anwendung](how-to-localize-an-application.md).

## <a name="best-practices-for-globalization-and-localization-in-wpf"></a>Bewährte Methoden zur Globalisierung und Lokalisierung in WPF.

Sie können die in integrierten Globalisierungs-und Lokalisierungs Funktionen optimal nutzen, indem Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Design der Benutzeroberfläche und die Lokalisierungs bezogenen Tipps befolgen, die in diesem Abschnitt enthalten sind.

### <a name="best-practices-for-wpf-ui-design"></a>Bewährte Methoden für den Entwurf von WPF-Benutzeroberflächen

Wenn Sie ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] –-basiertes entwerfen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , sollten Sie die folgenden bewährten Methoden implementieren:

- Schreiben Sie [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , und vermeiden Sie es, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Code zu erstellen. Wenn Sie das [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mithilfe von erstellen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , machen Sie es über integrierte Lokalisierungs-APIs verfügbar.

- Vermeiden Sie die Verwendung absoluter Positionen und fester Größe zum Anordnen von Inhalt. Verwenden Sie stattdessen die relative oder die automatische Größenanpassung.

  - Verwenden <xref:System.Windows.Window.SizeToContent%2A> Sie, und halten Sie breiten und Höhen auf fest `Auto` .

  - Vermeiden Sie <xref:System.Windows.Controls.Canvas> die Verwendung von für das Layout von [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] .

  - Verwenden Sie <xref:System.Windows.Controls.Grid> und dessen Größen Freigabe Feature.

- Lassen Sie an den Rändern zusätzlichen freien Platz, da lokalisierter Text häufig mehr Platz beansprucht. Zusätzlicher Leerraum kann überstehende Zeichen aufnehmen.

- Aktivieren <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> <xref:System.Windows.Controls.TextBlock> Sie auf, um Clipping zu vermeiden.

- Legen Sie das `xml:lang` -Attribut fest. Dieses Attribut beschreibt die Kultur eines bestimmten Elements und seiner untergeordneten Elemente. Der Wert dieser Eigenschaft ändert das Verhalten mehrerer Features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] . Es ändert z.B. das Verhalten von Silbentrennung, Rechtschreibprüfung, Zahlenersetzung, Formen komplexer Schriften und die Ausweich-Schriftart. Weitere Informationen zum Festlegen der [XML: lang-Behandlung in XAML](../../../desktop-wpf/xaml-services/xml-language-handling.md)finden Sie unter [Globalisierung für WPF](globalization-for-wpf.md) .

- Erstellen Sie eine angepasste zusammengesetzte Schriftart, um eine bessere Kontrolle der Schriftarten zu erhalten, die für verschiedene Sprachen verwendet werden. Standardmäßig [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet die GlobalUserInterface. Composite-Schriftart in Ihrem Windows\Fonts-Verzeichnis.

- Wenn Sie Navigationsanwendungen erstellen, die in einer Kultur lokalisiert werden können, die Text in einem Format von rechts nach Links anzeigt, legen Sie explizit <xref:System.Windows.FlowDirection> für jede Seite fest, um sicherzustellen, dass die Seite nicht von geerbt wird <xref:System.Windows.FlowDirection> <xref:System.Windows.Navigation.NavigationWindow> .

- Wenn Sie eigenständige Navigationsanwendungen erstellen, die außerhalb eines Browsers gehostet werden, legen Sie <xref:System.Windows.Application.StartupUri%2A> für die erste Anwendung auf einen <xref:System.Windows.Navigation.NavigationWindow> anstelle von auf eine Seite (z. b `<Application StartupUri="NavigationWindow.xaml">` .) fest. Dieser Entwurf ermöglicht es Ihnen, die <xref:System.Windows.FlowDirection> des Fensters und der Navigationsleiste zu ändern. Weitere Informationen und ein Beispiel finden Sie unter Beispiel für eine [Globalisierungs Homepage](https://github.com/microsoft/WPF-Samples/tree/master/Globalization%20and%20Localization/GlobalizationHomepage).

### <a name="best-practices-for-wpf-localization"></a>Bewährte Methoden für die Lokalisierung in WPF

Wenn Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] – basierte Anwendungen lokalisieren, sollten Sie die folgenden bewährten Methoden implementieren:

- Verwenden Sie Lokalisierungs Kommentare, um zusätzlichen Kontext für Lokalisierer bereitzustellen.

- Verwenden Sie Lokalisierungs Attribute, um die Lokalisierung zu steuern, anstatt Eigenschaften für Elemente selektiv zu weglassen <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> . Weitere Informationen finden Sie unter [Lokalisierungs Attribute und-Kommentare](localization-attributes-and-comments.md) .

- Verwenden Sie `msbuild -t:updateuid` und `-t:checkuid` , um <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften in Ihrem hinzuzufügen und zu überprüfen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Verwenden <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Sie Eigenschaften, um Änderungen zwischen Entwicklung und Lokalisierung zu verfolgen. <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>Eigenschaften helfen Ihnen beim Lokalisieren neuer Entwicklungsänderungen. Wenn Sie einem manuell <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften hinzufügen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , ist die Aufgabe in der Regel mühsam und weniger genau.

  - Bearbeiten oder ändern <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Sie Eigenschaften nicht, nachdem Sie mit der Lokalisierung begonnen haben.

  - Verwenden Sie keine doppelten <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften (Beachten Sie diesen Tipp, wenn Sie den Befehl "Kopieren und Einfügen" verwenden).

  - Legen `UltimateResourceFallback` Sie den Speicherort in AssemblyInfo fest \* , um die entsprechende Sprache für das Fall Back anzugeben (z `[assembly: NeutralResourcesLanguage("en-US",   UltimateResourceFallbackLocation.Satellite)]` . b.).

    Wenn Sie Ihre Quellsprache in die Hauptassembly einschließen möchten, indem Sie das- `<UICulture>` Tag in der Projektdatei weglassen, legen Sie den `UltimateResourceFallback` Speicherort als Hauptassembly anstelle des Satelliten (z `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.MainAssembly)]` . b.) fest.

## <a name="localize-a-wpf-application"></a>Lokalisieren einer WPF-Anwendung

Wenn Sie eine- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung lokalisieren, haben Sie mehrere Optionen. Beispielsweise können Sie die lokalisierbaren Ressourcen in der Anwendung an eine XML-Datei binden, lokalisierbaren Text in RESX-Tabellen speichern oder den Lokalisierer verwenden, um Dateien zu verwenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] . In diesem Abschnitt wird ein Lokalisierungs Workflow beschrieben, der die BAML-Form von XAML verwendet, die mehrere Vorteile bietet:

- Sie können lokalisieren, nachdem Sie erstellt haben.

- Sie können auf eine neuere Version der BAML-Form von XAML aktualisieren, indem Sie lokzierungen aus einer älteren Version der BAML-Form von XAML durchsetzen, sodass Sie die Lokalisierung gleichzeitig durchsetzen können.

- Sie können die ursprünglichen Quell Elemente und die Semantik zur Kompilierzeit überprüfen, da die BAML-Form von XAML die kompilierte Form von ist [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .

### <a name="localization-build-process"></a>Buildprozess für die Lokalisierung

Beim Entwickeln einer- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung lautet der Buildprozess für die Lokalisierung wie folgt:

- Der Entwickler erstellt und globalisiert die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung. Der Entwickler legt in der Projektdatei fest, `<UICulture>en-US</UICulture>` sodass bei der Kompilierung der Anwendung eine sprachneutrale Hauptassembly generiert wird. Diese Assembly verfügt über eine ausgelagerte .resources.dll-Datei, die alle lokalisierbaren Ressourcen enthält. Optional können Sie die Quellsprache in der Hauptassembly belassen, da unsere Lokalisierungs-APIs Extraktion aus der Hauptassembly unterstützen.

- Wenn die Datei in den Build kompiliert wird, wird der in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] die BAML-Form von XAML konvertiert. Die Kultur neutralen `MyDialog.exe` und Kultur abhängigen (englischen) `MyDialog.resources.dll` Dateien werden für englischsprachige Kunden freigegeben.

### <a name="localization-workflow"></a>Lokalisierungsworkflow

Der Lokalisierungsprozess beginnt, nachdem die nicht lokalisierte `MyDialog.resources.dll` Datei erstellt wurde. Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente und Eigenschaften im ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] werden mithilfe der APIs unter aus der BAML-Form von XAML in Schlüssel-Wert-Paare extrahiert <xref:System.Windows.Markup.Localizer> . Lokalisierer verwenden die Schlüssel-Wert-Paare, um die Anwendung zu lokalisieren. Sie können nach Abschluss der Lokalisierung aus den neuen Werten eine neue .resource.dll-Datei generieren.

Die Schlüssel der Schlüssel-Wert-Paare sind `x:Uid` Werte, die vom Entwickler in der ursprünglichen platziert werden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Diese `x:Uid` Werte ermöglichen der API das Nachverfolgen und Zusammenführen von Änderungen, die während der Lokalisierung zwischen dem Entwickler und dem Lokalisierer erfolgen. Wenn der Entwickler z. b. ändert, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nachdem der Lokalisierer mit der Lokalisierung begonnen hat, können Sie die Entwicklungs Änderung mit der bereits abgeschlossenen Lokalisierungsarbeit zusammenführen, damit die minimale Übersetzungsarbeit verloren geht.

Die folgende Abbildung zeigt einen typischen auf der BAML-Form von XAML-basierenden Lokalisierungsworkflow. Dieses Diagramm setzt voraus, dass der Entwickler die Anwendung in Englisch schreibt. Der Entwickler erstellt und globalisiert die WPF-Anwendung. In der Projektdatei legt der Entwickler fest, `<UICulture>en-US</UICulture>` dass bei der Erstellung eine sprachneutrale Hauptassembly mit einem Satelliten .resources.dll generiert wird, der alle lokalisierbaren Ressourcen enthält. Alternativ dazu können Sie auch Ihre Quellsprache in der Hauptassembly belassen, da unsere Lokalisierungs-APIs eine Extraktion aus der Hauptassembly unterstützen. Nach dem Buildprozess wird XAML in BAML kompiliert. Die kulturneutrale Datei „MyDialog.exe.resources.dll” wird an den englischsprachigen Kunden ausgeliefert.

![Diagramm, das den Lokalisierungs Workflow anzeigt.](./media/wpf-globalization-and-localization-overview/localization-workflow.png)

![Diagramm, das den nicht lokalisierten Workflow anzeigt.](./media/wpf-globalization-and-localization-overview/unlocalized-workflow.png)

## <a name="examples-of-wpf-localization"></a>Beispiele für WPF-Lokalisierung

Dieser Abschnitt enthält Beispiele für lokalisierte Anwendungen, die Ihnen helfen zu verstehen, wie Anwendungen erstellt und lokalisiert werden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .

### <a name="run-dialog-box-example"></a>Beispiel-Dialogfeld „Ausführen”

Die folgende Grafik zeigt die Ausgabe des Beispiels für das Dialogfeld " **Ausführen** ".

**Englisch:**

![Screenshot, der ein englisches Dialogfeld "ausführen" anzeigt.](./media/wpf-globalization-and-localization-overview/run-dialog-box-english.png)

**Deutsch:**

![Screenshot, der das Dialogfeld "Deutsch ausführen" anzeigt.](./media/wpf-globalization-and-localization-overview/run-dialog-box-german.png)

**Entwerfen eines globalen Dialogfelds „Ausführen”**

In diesem Beispiel wird ein Dialogfeld **Ausführen** mithilfe von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und erstellt [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Dieses Dialogfeld entspricht dem Dialogfeld **Ausführen** , das im Microsoft Windows-Startmenü verfügbar ist.

Einige Highlights beim Erstellen von globalen Dialogfeldern sind:

**Automatisches Layout**

*In der Datei Window1.xaml:*

`<Window SizeToContent="WidthAndHeight">`

Die obige Window-Eigenschaft sorgt dafür, dass sich die Fenstergröße automatisch der Inhaltsgröße entsprechend anpasst. Diese Eigenschaft verhindert, dass Inhalt, der nach der Lokalisierung an Größe zunimmt, abgeschnitten wird. Im Gegenzug wird auch unnötiger Leerraum entfernt, wenn die Größe des Inhalts nach der Lokalisierung geschrumpft ist.

`<Grid x:Uid="Grid_1">`

<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>Eigenschaften werden benötigt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , damit Lokalisierungs-APIs ordnungsgemäß funktionieren.

Sie werden von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Lokalisierungs-APIs verwendet, um Änderungen zwischen der Entwicklung und Lokalisierung von zu verfolgen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] . <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>mithilfe von Eigenschaften können Sie eine neuere Version von [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit einer älteren Lokalisierung von zusammenführen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] . Sie fügen eine <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaft hinzu, indem Sie `msbuild -t:updateuid RunDialog.csproj` in einer Befehlsshell ausführen. Dies ist die empfohlene Methode zum Hinzufügen von <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften, da Sie in der Regel zeitaufwändig und weniger genau hinzugefügt werden. Sie können überprüfen, ob die <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> Eigenschaften ordnungsgemäß festgelegt sind `msbuild -t:checkuid RunDialog.csproj` .

Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] wird mit dem-Steuerelement strukturiert <xref:System.Windows.Controls.Grid> , das ein nützliches Steuerelement ist, um das automatische Layout in zu nutzen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] . Beachten Sie, dass das Dialogfeld in drei Zeilen und fünf Spalten unterteilt ist. Nicht eine der Zeilen-und Spaltendefinitionen hat eine Größe mit fester Größe. Daher können sich die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in jeder Zelle positionierten Elemente bei der Lokalisierung an die Größe vergrößert und verkleinert werden.

[!code-xaml[GlobalizationRunDialog#GridColumnDef](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef)]

Die ersten beiden Spalten, in denen die " **Open:** "-Bezeichnung und <xref:System.Windows.Controls.ComboBox> platziert werden, verwenden 10 Prozent der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Gesamtbreite.

[!code-xaml[GlobalizationRunDialog#GridColumnDef2](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef2)]

Beachten Sie, dass im Beispiel das Feature für die gemeinsame Größenänderung von verwendet wird <xref:System.Windows.Controls.Grid> . Die letzten drei Spalten nutzen dies, indem Sie sich im gleichen befinden <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> . Wie aus dem Namen der Eigenschaft zu erwarten ist, ermöglicht dies den Spalten, dieselbe Größe zu verwenden. Wenn also "Durchsuchen..." wird in die längere Zeichenfolge "Durchsuchen..." lokalisiert. alle Schaltflächen werden in der Breite vergrößert, anstatt eine kleine Schaltfläche "OK" und eine unverhältnismäßig große "Durchsuchen..." gedrückt.

**xml:lang**

`xml:lang="en-US"`

Beachten Sie, dass die [XML: lang-Behandlung in XAML](../../../desktop-wpf/xaml-services/xml-language-handling.md) am Stamm Element von abgelegt wurde [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] . Diese Eigenschaft beschreibt die Kultur eines bestimmten Elements und seiner untergeordneten Elemente. Dieser Wert wird von mehreren Features in verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und sollte bei der Lokalisierung entsprechend geändert werden. Dieser Wert bestimmt, welches Sprachwörterbuch für Silbentrennung und Rechtschreibprüfung verwendet wird. Es wirkt sich auch auf die Anzeige von Ziffern aus, und wie das Fallbacksystem für Schriftarten entscheidet, welche Schriftart zu benutzen ist. Schließlich beeinflusst die Eigenschaft auch, wie Zahlen formatiert und in welcher Form komplexe Schriften dargestellt werden. Der Standardwert ist „en-US”.

**Erstellen eine Satellitenressourcenassembly**

*In .csproj:*

Bearbeiten `.csproj` Sie die Datei, und fügen Sie das folgende-Tag zu einem bedingungslosen hinzu `<PropertyGroup>` :

`<UICulture>en-US</UICulture>`

Beachten Sie das Hinzufügen eines `UICulture` Werts. Wenn dies auf einen gültigen Wert ( <xref:System.Globalization.CultureInfo> z. b. en-US) festgelegt ist, wird beim Erstellen des Projekts eine Satellitenassembly mit allen lokalisierbaren Ressourcen erstellt.

`<Resource Include="RunIcon.JPG">`

`<Localizable>False</Localizable>`

`</Resource>`

Der `RunIcon.JPG` muss nicht lokalisiert werden, da er für alle Kulturen identisch angezeigt werden sollte. `Localizable`ist auf festgelegt, `false` sodass Sie nicht in der Satellitenassembly, sondern in der sprach neutralen Hauptassembly verbleibt. Der Standardwert aller nicht Kompilier baren Ressourcen ist `Localizable` auf festgelegt `true` .

**Lokalisieren des Dialogfelds „Ausführen”**

**Parse**

Nachdem die Anwendung erstellt, ist der erste Schritt bei der Lokalisierung, die lokalisierbaren Ressourcen aus der Satellitenassembly auszulesen. Verwenden Sie für dieses Thema das Beispiel-LocBaml-Tool, das Sie unter [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml)finden. Beachten Sie, dass LocBaml lediglich ein Beispieltool ist, das Ihnen beim Erstellen eines Lokalisierungstools helfen soll, das Ihrem Lokalisierungsprozess entspricht. Führen Sie mithilfe von LocBaml Folgendes aus, um Folgendes zu analysieren: **LocBaml/parse RunDialog.resources.dll/out:** , um eine "RunDialog.resources.dll.CSV"-Datei zu generieren.

**Lokalisieren**

Verwenden Sie zum Bearbeiten dieser Datei Ihren bevorzugten Unicode-fähigen CSV-Editor. Filtern Sie alle Einträge mit einer Lokalisierungskategorie von „None” heraus. Sie sollten folgende Einträge sehen:

|Ressourcenschlüssel|Lokalisierungskategorie|Wert|
|-|-|-|
|Button_1:System.Windows.Controls.Button.$Content|Schaltfläche|OK|
|Button_2:System.Windows.Controls.Button.$Content|Schaltfläche|Abbrechen|
|Button_3:System.Windows.Controls.Button.$Content|Schaltfläche|Durchsuchen...|
|ComboBox_1:System.Windows.Controls.ComboBox.$Content|ComboBox||
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Text|Geben Sie den Namen eines Programms, Ordners, Dokuments oder einer Internetressource ein, damit Windows das entsprechende Objekt öffnet.|
|TextBlock_2:System.Windows.Controls.TextBlock.$Content|Text|Offen:|
|Window_1:System.Windows.Window.Title|Titel|Ausführen|

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

**Generate**

Der letzte Schritt der Lokalisierung umfasst das Erstellen der neu lokalisierten Satellitenassembly. Dies kann mithilfe des folgenden LocBaml-Befehls erreicht werden:

**LocBaml.exe /generate RunDialog.resources.dll /trans:RunDialog.resources.dll.CSV /out: . /cul:de-DE**

Wenn diese resources.dll in deutschen Fenstern in einem Ordner "de-de" neben der Hauptassembly abgelegt wird, wird diese Ressource automatisch anstelle der im Ordner "en-US" geladen. Wenn Sie nicht über eine deutsche Version von Windows verfügen, um dies zu testen, legen Sie die Kultur auf eine beliebige Kultur von Fenstern fest (z. b. `en-US` ), und ersetzen Sie die ursprüngliche Ressourcen-DLL.

**Laden der Satellitenressourcen**

|MyDialog.exe|en-US\MyDialog.resources.dll|de-DE\MyDialog.resources.dll|
|------------------|------------------------------------|------------------------------------|
|Code|Ursprüngliche englische BAML|Lokalisierte BAML|
|Kulturneutrale Ressourcen|Weitere Ressourcen auf Englisch|Weitere ins Deutsche lokalisierte Ressourcen|

.Net wählt basierend auf den der Anwendung automatisch aus, welche Satellitenressourcenassembly geladen werden soll <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> . Standardmäßig wird die Kultur Ihres Windows-Betriebssystems verwendet. Wenn Sie deutsche Fenster verwenden, lädt die *de-DE\MyDialog.resources.dll* Datei. Wenn Sie englische Fenster verwenden, lädt die *en-US\MyDialog.resources.dll* Datei. Sie können die endgültige Fall Back Ressource für Ihre Anwendung festlegen, indem Sie das `NeutralResourcesLanguage` -Attribut in der *AssemblyInfo* -Datei Ihres Projekts angeben. Wenn Sie z. b. Folgendes angeben:

`[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]`

Anschließend wird die *en-US\MyDialog.resources.dll* -Datei mit deutschen Fenstern verwendet, wenn keine der folgenden Dateien verfügbar ist: *de-DE\MyDialog.resources.dll* oder *de\MyDialog.resources.dll*.

### <a name="microsoft-saudi-arabia-homepage"></a>Homepage von Microsoft Saudi-Arabien

Die folgende Abbildung zeigt eine englische und eine arabische Homepage. Das gesamte Beispiel, das diese Grafiken erzeugt, finden Sie unter Beispiel für eine [Globalisierungs Homepage](https://github.com/microsoft/WPF-Samples/tree/master/Globalization%20and%20Localization/GlobalizationHomepage).

**Englisch:**

![Screenshot, der eine englische Startseite anzeigt.](./media/wpf-globalization-and-localization-overview/english-home-page-sample.jpg)

**Arabisch:**

![Screenshot, der eine arabische Startseite zeigt.](./media/wpf-globalization-and-localization-overview/arabic-home-page-sample.jpg)

### <a name="designing-a-global-microsoft-home-page"></a>Entwerfen einer globalen Microsoft-Startseite

Dieses Modell der Microsoft Saudi-Arabien Website veranschaulicht die Globalisierungsfeatures für Sprachen in rechts-nach-links-Schreibweise. Sprachen, wie z. b. Hebräisch und Arabisch, haben eine Lesereihenfolge von rechts nach links, sodass das Layout von [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] häufig anders angeordnet werden muss als in den Sprachen von links nach rechts (z. b. Englisch). Die Lokalisierung von einer links-nach-rechts-Sprache in eine rechts-nach-links-Sprache oder umgekehrt kann sehr anspruchsvoll sein. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wurde entwickelt, um solche Lokalisierungsanforderungen wesentlich zu erleichtern.

**FlowDirection**

*Homepage.xaml:*

[!code-xaml[GlobalizationHomepage#Homepage](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#homepage)]

Beachten Sie die- <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft für <xref:System.Windows.Controls.Page> . Wenn Sie diese Eigenschaft in ändern, <xref:System.Windows.FlowDirection.RightToLeft> ändert sich die <xref:System.Windows.FrameworkElement.FlowDirection%2A> der-Elemente und der zugehörigen untergeordneten <xref:System.Windows.Controls.Page> Elemente, sodass das Layout dieser Elemente von [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] rechts nach links gekippt wird, wie ein arabischer Benutzer erwartet. Sie können das Vererbungs Verhalten überschreiben, indem Sie einen expliziten <xref:System.Windows.FrameworkElement.FlowDirection%2A> für jedes Element angeben. Die <xref:System.Windows.FrameworkElement.FlowDirection%2A> -Eigenschaft ist für alle <xref:System.Windows.FrameworkElement> -oder-Dokument bezogenen Elemente verfügbar und weist einen impliziten Wert von auf <xref:System.Windows.FlowDirection.LeftToRight> .

Beachten Sie, dass auch die Hintergrund Farbverlaufs Pinsel ordnungsgemäß gekippt werden, wenn der Stamm <xref:System.Windows.FrameworkElement.FlowDirection%2A> geändert wird:

**FlowDirection="LeftToRight"**

![Screenshot, der den Farbverlaufs Fluss von links nach rechts anzeigt.](./media/wpf-globalization-and-localization-overview/gradient-flow-left-right.png)

**FlowDirection="RightToLeft"**

![Screenshot, der den Farbverlauf von rechts nach Links anzeigt](./media/wpf-globalization-and-localization-overview/gradient-flow-right-left.png)

**Verwenden Sie keine feste Abmessungen für Bereiche und Steuerelemente**

Sehen Sie sich die Datei "Homepage. XAML" an. Beachten Sie, dass abgesehen von der festgelegten Breite und Höhe [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] im oberen Bereich <xref:System.Windows.Controls.DockPanel> keine anderen fixierten Dimensionen vorhanden sind. Vermeiden Sie feste Abmessungen, um zu vermeiden, dass lokalisierter Text, der länger als der Quelltext werden kann, abgeschnitten wird. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Bereiche und Steuerelemente passen ihre Größe automatisch dem ihres Inhalts an. Die meisten Steuerelemente verfügen auch über minimale und maximale Abmessungen, die Sie für mehr Kontrolle festlegen können (z. b. MinWidth = "20"). Mit <xref:System.Windows.Controls.Grid> können Sie auch relative breiten und Höhen festlegen, indem Sie " \* " (z. b `Width="0.25*"` .) verwenden oder die Freigabe Funktion für Zellen Größe verwenden.

**Lokalisierungskommentare**

Es gibt viele Fälle, in denen Inhalt mehrdeutig und schwierig zu übersetzen sein kann. Der Entwickler oder Designer verfügt über die Möglichkeit, zusätzlichen Kontext und Kommentare für Lokalisierer über Lokalisierungskommentare bereitzustellen. Beispielsweise verdeutlicht die unten angegebene Lokalisierung. comments die Verwendung des Zeichens "&#124;".

[!code-xaml[GlobalizationHomepage#LocalizationComment](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcomment)]

Dieser Kommentar wird dem Inhalt von TextBlock_1 zugeordnet, und im Fall des LocBaml-Tools (siehe [Lokalisieren einer Anwendung](how-to-localize-an-application.md)) kann er in der 6. Spalte der TextBlock_1 Zeile in der CSV-Ausgabedatei angezeigt werden:

|Ressourcenschlüssel|Category|Lesbar|Änderbar|Comment|Wert|
|-|-|-|-|-|-|
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Text|TRUE|TRUE|Dieses Zeichen wird als dekorative Abgrenzungslinie verwendet.|&#124;|

Kommentare können auf den Inhalt oder die Eigenschaften jedes Elements mithilfe der folgenden Syntax platziert werden:

[!code-xaml[GlobalizationHomepage#LocalizationCommentsProp](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcommentsprop)]

**Lokalisierungsattribute**

Häufig muss der Entwickler oder Lokalisierungsmanager Kontrolle darüber haben, was Lokalisierer lesen und ändern können. Sie möchten z.B. nicht, dass der Lokalisierer den Namen Ihres Unternehmens oder eine rechtliche Floskel übersetzt. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]stellt Attribute bereit, mit denen Sie die Lesbarkeit, die Änderbarkeit und die Kategorie des Inhalts oder der Eigenschaft eines Elements festlegen können, das von Ihrem Lokalisierungs Tool zum Sperren, ausblenden oder Sortieren von Elementen verwendet werden kann. Weitere Informationen finden Sie unter <xref:System.Windows.Localization.Attributes%2A>. Für die Zwecke dieses Beispiels gibt das LocBaml-Tool nur die Werte dieser Attribute aus. Alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente besitzen Standardwerte für diese Attribute, die Sie aber überschreiben können. Im folgenden Beispiel werden die Standard Lokalisierungs Attribute für überschrieben, `TextBlock_1` und der Inhalt wird so festgelegt, dass er lesbar, aber nicht änderbar für Lokalisierer ist.

[!code-xaml[LocalizationComAtt#LocalizationAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributes)]

Zusätzlich zu den Attributen für die Lesbarkeit und Modifizierbarkeit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine Enumeration allgemeiner Benutzeroberflächen Kategorien ( <xref:System.Windows.LocalizationCategory> ) bereit, die verwendet werden können, um Lokalisierern mehr Kontext zu geben. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Standardkategorien für Platt Form Steuerelemente können auch in überschrieben werden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] :

[!code-xaml[LocalizationComAtt#LocalizationAttributesOverridden](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributesoverridden)]

Die standardmäßigen Lokalisierungs Attribute, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bereitstellt, können auch durch Code überschrieben werden, sodass Sie die richtigen Standardwerte für benutzerdefinierte Steuerelemente korrekt festlegen können. Beispiel:

```csharp
[Localizability(Readability = Readability.Readable, Modifiability=Modifiability.Unmodifiable, LocalizationCategory.None)]
public class CorporateLogo : TextBlock
{
    // ...
}
```

Die in festgelegten Attribute pro Instanz haben [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Vorrang vor den Werten, die im Code für benutzerdefinierte Steuerelemente festgelegt werden. Weitere Informationen zu Attributen und Kommentaren finden Sie unter [Lokalisierungs Attribute und-Kommentare](localization-attributes-and-comments.md).

**Schriftart-Fallback und zusammengesetzte Schriftarten**

Wenn Sie eine Schriftart angeben, die einen bestimmten Code punktbereich nicht unterstützt, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird automatisch ein Fall Back auf eine Schriftart durchführt, die mithilfe der globalen Benutzeroberfläche. compositefont, die sich in Ihrem Windows\Fonts-Verzeichnis befindet. Zusammengesetzte Schriftarten funktionieren genauso wie jede andere Schriftart und können explizit verwendet werden, indem die `FontFamily` (z.) eines Elements festgelegt wird `FontFamily="Global User Interface"` . Sie können Ihre eigene bevorzugte Ausweichschriftart angeben, indem Sie eine eigene zusammengesetzte Schriftart erstellen und angeben, welche Schriftart jeweils für bestimmte Codepunkt-Bereiche und Sprachen verwendet werden soll.

Weitere Informationen zu zusammengesetzten Schriftarten finden Sie unter <xref:System.Windows.Media.FontFamily> .

**Lokalisieren der Microsoft-Homepage**

Sie können die gleichen Schritte wie im Beispiel zum Dialogfeld „Ausführen” nutzen, um diese Anwendung zu lokalisieren. Die lokalisierte CSV-Datei für Arabisch steht Ihnen im Beispiel für die [Globalisierungs Homepage](https://github.com/microsoft/WPF-Samples/tree/master/Globalization%20and%20Localization/GlobalizationHomepage)zur Verfügung.
