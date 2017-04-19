---
title: "&#220;bersicht &#252;ber WPF-Globalisierung und -Lokalisierung | Microsoft Docs"
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
  - "Globalisierung, Informationen über die Globalisierung"
  - "Lokalisierung, Informationen über die Lokalisierung"
ms.assetid: 56e5a5c8-6c96-4d19-b8e1-a5be1dc564af
caps.latest.revision: 39
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 34
---
# &#220;bersicht &#252;ber WPF-Globalisierung und -Lokalisierung
Wenn Sie die Verfügbarkeit des Produkts auf nur eine Sprache beschränken, reduzieren Sie Ihre potenzielle Kundenbasis auf einen Bruchteil der Weltbevölkerung von 6,5 Milliarden.  Um Anwendungen für den internationalen Markt zu entwickeln, empfiehlt sich die kostengünstige Lokalisierung des Produkts als optimale und effizienteste Methode, noch mehr Kunden anzusprechen.  
  
 In dieser Übersicht erhalten Sie eine Einführung in die Globalisierung und Lokalisierung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Unter Globalisierung versteht man das Entwerfen und Entwickeln von Anwendungen, die an verschiedenen Standorten einsetzbar sind.  Die Globalisierung unterstützt z. B. lokalisierte Benutzeroberflächen und regionale Daten für Benutzer in unterschiedlichen Kulturen.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt globalisierte Entwurfsfeatures zur Verfügung, einschließlich automatischen Layouts, Satellitenassemblys sowie lokalisierten Attributen und Kommentaren.  
  
 Als Lokalisierung bezeichnet man die Übersetzung von Anwendungsressourcen in lokalisierte Versionen für die jeweiligen Kulturen, die von der Anwendung unterstützt werden sollen.  Wenn Sie in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] lokalisieren, verwenden Sie die APIs im <xref:System.Windows.Markup.Localizer>\-Namespace. Diese APIs unterstützen das Befehlszeilentool im [Beispiel zum LocBaml\-Tool](http://go.microsoft.com/fwlink/?LinkID=160016).  Informationen zum Erstellen und Verwenden von LocBaml finden Sie unter [Lokalisieren einer Anwendung](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).  
  
   
  
## Empfohlene Vorgehensweise für die Globalisierung und Lokalisierung in WPF  
 Eine optimale Nutzung der in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] integrierten Globalisierungs\- und Lokalisierungsfunktion erzielen Sie, indem Sie die in diesem Abschnitt enthaltenen Tipps zum Entwerfen und Lokalisieren von Benutzeroberflächen befolgen.  
  
### Empfohlene Vorgehensweise für den Entwurf von WPF\-Benutzeroberflächen  
 Wenn Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-basierte [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]en entwerfen, sollten Sie die Implementierung der empfohlenen Vorgehensweisen in Erwägung ziehen:  
  
-   Schreiben Sie [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]n in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], und vermeiden Sie das Erstellen von [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]n in Code.  Wenn Sie die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erstellen, machen Sie diese durch integrierte Lokalisierungs\-APIs verfügbar.  
  
-   Vermeiden Sie beim Darstellen von Inhalt absolute Positionen und feste Größen, und verwenden Sie stattdessen die relative oder automatische Größenanpassung.  
  
    -   Verwenden Sie <xref:System.Windows.Window.SizeToContent%2A>. Breite und Höhe sollten auf `Auto` festgelegt bleiben.  
  
    -   Vermeiden Sie die Verwendung von <xref:System.Windows.Controls.Canvas>, um [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]en darzustellen.  
  
    -   Verwenden Sie <xref:System.Windows.Controls.Grid> und dessen Feature für gemeinsame Größenänderung.  
  
-   Stellen Sie zusätzlichen Abstand an den Rändern bereit, da lokalisierter Text häufig mehr Platz beansprucht.  Durch zusätzlichen Abstand entsteht Platz für mögliche überhängende Zeichen.  
  
-   Aktivieren Sie <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> für <xref:System.Windows.Controls.TextBlock>, um das Abschneiden von Daten zu vermeiden.  
  
-   Legen Sie das **xml:lang**\-Attribut fest.  Dieses Attribut beschreibt die Kultur eines bestimmten Elements und seiner untergeordneten Elemente.  Der Wert dieser Eigenschaft ändert das Verhalten mehrerer Funktionen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. So wird z. B. das Verhalten der Silbentrennung, Rechtschreibprüfung, Zahlenersetzung, komplexen Skriptgestaltung und automatischen Schriftartauswahl geändert.  Weitere Informationen zum Festlegen von [xml:lang\-Behandlung in XAML](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) finden Sie unter [Globalisierung für WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md).  
  
-   Erstellen Sie eine benutzerdefinierte zusammengesetzte Schriftart, um die in unterschiedlichen Sprachen verwendeten Schriftarten besser steuern zu können.  Standardmäßig verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Schriftart GlobalUserInterface.composite im Verzeichnis Windows\\Fonts.  
  
-   Wenn Sie eine Navigationsanwendung erstellen, die möglicherweise in eine Kultur lokalisiert wird, in der Texte im Rechts\-nach\-Links\-Format wiedergegeben werden, legen Sie <xref:System.Windows.FlowDirection> von jeder Seite ausdrücklich fest, um sicherzustellen, dass <xref:System.Windows.FlowDirection> aus <xref:System.Windows.Navigation.NavigationWindow> nicht von der Seite übernommen wird.  
  
-   Wenn Sie eigenständige Navigationsanwendungen erstellen, die außerhalb eines Browsers gehostet werden, legen Sie <xref:System.Windows.Application.StartupUri%2A> für die Originalanwendung auf <xref:System.Windows.Navigation.NavigationWindow> anstatt auf eine Seite fest \(z. B. `<Application StartupUri="NavigationWindow.xaml">`\).  Dieser Entwurf ermöglicht es Ihnen, <xref:System.Windows.FlowDirection> des Fensters und der Navigationsleiste zu ändern.  Weitere Informationen und ein Beispiel finden Sie unter [Beispiel zu globalisierter Startseite](http://go.microsoft.com/fwlink/?LinkID=159990).  
  
### Empfohlene Vorgehensweisen für die WPF\-Lokalisierung  
 Wenn Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-basierte Anwendungen lokalisieren, sollten Sie die Implementierung dieser empfohlenen Vorgehensweisen erwägen:  
  
-   Verwenden Sie Lokalisierungskommentare, um zusätzlichen Kontext für Lokalisierer bereitzustellen.  
  
-   Verwenden Sie Lokalisierungsattribute zur Steuerelementlokalisierung, statt <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>\-Eigenschaften für Elemente selektiv wegzulassen.  Weitere Informationen finden Sie unter [Lokalisierungsattribute und \-kommentare](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md).  
  
-   Verwenden Sie **msbuild \/t:updateuid** und **\/t:checkuid**, um <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>\-Eigenschaften in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hinzuzufügen und zu überprüfen.  Verwenden Sie <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>\-Eigenschaften, um Änderungen zwischen Entwicklung und Lokalisierung nachzuverfolgen. Mit <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>\-Eigenschaften können Sie neue Entwicklungsänderungen lokalisieren.  Wenn Sie einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>\-Eigenschaften manuell hinzufügen, ist die Aufgabe i. d. R. zeitraubend und wenig genau.  
  
    -   Bearbeiten oder ändern Sie <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>\-Eigenschaften nicht, nachdem Sie mit der Lokalisierung begonnen haben.  
  
    -   Verwenden Sie keine doppelten <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>\-Eigenschaften \(denken Sie daran, wenn Sie die Befehle Kopieren und Einfügen verwenden\).  
  
    -   Legen Sie die `UltimateResourceFallback`\-Position in AssemblyInfo.\* fest, um die entsprechende Sprache für Fallback \(z. B. `[assembly: NeutralResourcesLanguage("en-US",   UltimateResourceFallbackLocation.Satellite)]`\) anzugeben.  
  
         Wenn Sie die Ausgangssprache in der Hauptassembly durch Auslassen des `<UICulture>`\-Tags in die Projektdatei einfügen, legen Sie die `UltimateResourceFallback`\-Position anstelle des Satelliten \(z. B. `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.MainAssembly)]`\) als Hauptassembly fest.  
  
<a name="workflow_to_localize"></a>   
## Lokalisieren einer WPF\-Anwendung  
 Wenn Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung lokalisieren, haben Sie mehrere Möglichkeiten.  Sie können z. B. lokalisierbare Ressourcen in der Anwendung an eine [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Datei binden, lokalisierbaren Text in RESX\-Tabellen speichern oder den Lokalisierungsexperten anweisen, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Dateien zu verwenden.  In diesem Abschnitt wird ein Lokalisierungsworkflow beschrieben, in dem die BAML\-Form von XAML verwendet wird. Dies bietet mehrere Vorteile:  
  
-   Sie können die Lokalisierung nach dem Buildvorgang ausführen.  
  
-   Sie können auf eine neuere Version der BAML\-Form von XAML aktualisieren und Lokalisierungen von einer älteren Version der BAML\-Form von XAML beibehalten, sodass Sie parallel zum Entwickeln auch lokalisieren können.  
  
-   Sie können ursprüngliche Quellelemente und Semantik zur Kompilierzeit überprüfen, da die BAML\-Form von XAML die kompilierte Form von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ist.  
  
### Buildprozess für die Lokalisierung  
 Wenn Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung entwickeln, verläuft der Buildprozess für die Lokalisierung folgendermaßen:  
  
-   Der Entwickler erstellt und globalisiert die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung.  In der Projektdatei legt der Entwickler `<UICulture>en-US</UICulture>` fest, sodass bei der Kompilierung einer Anwendung eine sprachneutrale Hauptassembly generiert wird. Diese Assembly enthält eine Satellitendatei ".resources.dll", die alle lokalisierbaren Ressourcen enthält. Optional können Sie die Ausgangssprache in der Hauptassembly speichern, da die Lokalisierungs\-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] die Extraktion aus der Hauptassembly unterstützen.  
  
-   Bei der Kompilierung der Datei in den Build wird [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in die BAML\-Form von XAML konvertiert.  Die kulturell neutralen `MyDialog.exe`\- und die kulturspezifischen `MyDialog.resources.dll`\-Dateien \(Englisch\) werden für den englischsprachigen Kunden freigegeben.  
  
### Lokalisierungsworkflow  
 Der Lokalisierungsprozess beginnt nach Erstellen der nicht lokalisierten `MyDialog.resources.dll`\-Datei.  Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]nelemente und \-eigenschaften im ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] werden von der BAML\-Form von XAML in Schlüssel\/Wert\-Paare extrahiert. Dazu werden die [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] unter <xref:System.Windows.Markup.Localizer> verwendet.  Lokalisierer verwenden die Schlüssel\/Wert\-Paare zum Lokalisieren der Anwendung.  Nach Abschluss der Lokalisierung können Sie anhand der neuen Werte eine neue Datei .resource.dll erstellen.  
  
 Die Schlüssel des Schlüssel\-Wert\-Paares sind `x:Uid`\-Werte, die vom Entwickler in der ursprünglichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] eingefügt werden.  Diese `x:Uid`\-Werte aktivieren die [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] zum Nachverfolgen und Zusammenführen von Änderungen, die im Verlauf der Lokalisierung zwischen dem Entwickler und dem Lokalisierer vorkommen.  Wenn der Entwickler beispielsweise die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ändert, nachdem der Lokalisierer die Lokalisierung begonnen hat, können Sie die Entwicklungsänderung mit der bereits abgeschlossenen Lokalisierung zusammenführen, um zu gewährleisten, dass nur ein Minimum der Übersetzung verloren geht.  
  
 In der folgenden Grafik wird ein typischer Lokalisierungsworkflow dargestellt, der auf der BAML\-Form von XAML basiert.  In diesem Diagramm wird davon ausgegangen, dass der Entwickler die Anwendung auf Englisch schreibt.  Der Entwickler erstellt und globalisiert die WPF\-Anwendung.  In der Projektdatei legt der Entwickler `<UICulture>en-US</UICulture>` so fest, dass im Buildvorgang eine sprachneutrale Hauptassembly mit einer Satellitendatei .resources.dll, die alle lokalisierbaren Ressourcen enthält, generiert wird.  Alternativ dazu können Sie die Ausgangssprache in der Hauptassembly speichern, da die WPF\-Lokalisierungs\-APIs  die Extraktion aus der Hauptassembly unterstützen.  Nach dem Buildprozess wird die XAML in BAML kompiliert.  Die kulturell neutrale Datei MyDialog.exe.resources.dll wird an den englischsprachigen Kunden ausgeliefert.  
  
 ![Lokalisierungsworkflow](../../../../docs/framework/wpf/advanced/media/localizationworkflow.png "LocalizationWorkflow")  
  
 ![Nicht lokalisierter Workflow](../../../../docs/framework/wpf/advanced/media/localizationworkflow2.png "LocalizationWorkflow2")  
  
<a name="examples_of_localization"></a>   
## Beispiele für die WPF\-Lokalisierung  
 In diesem Abschnitt werden Beispiele für lokalisierte Anwendungen behandelt, die Ihr Verständnis für das Erstellen und Lokalisieren von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen fördern sollen.  
  
#### Beispiel für das Dialogfeld Ausführen  
 In der folgenden Grafik wird die Ausgabe des Beispiels für das Dialogfeld **Ausführen** gezeigt.  
  
 **Englisch:**  
  
 ![Dialogfeld Ausführen](../../../../docs/framework/wpf/advanced/media/rundialogenglish.png "RunDialogEnglish")  
  
 **Deutsch:**  
  
 ![Deutsches Dialogfeld Ausführen](../../../../docs/framework/wpf/advanced/media/rundialoggerman.png "RunDialogGerman")  
  
 **Entwerfen eines globalen Dialogfelds Ausführen**  
  
 In diesem Beispiel wird das Dialogfeld **Ausführen** mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erzeugt.  Dieses Dialogfeld ist identisch mit dem Dialogfeld **Ausführen**, das im [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]\-Startmenü zur Verfügung steht.  
  
 Beim Erstellen von globalen Dialogfeldern ist Folgendes zu betonen:  
  
 **Automatic Layout**  
  
 *In Window1.xaml:*  
  
 `<Window SizeToContent="WidthAndHeight">`  
  
 Die vorherige Window\-Eigenschaft passt die Größe des Fensters automatisch an die Größe des Inhalts an.  Durch diese Eigenschaft wird verhindert, dass Inhalt, der nach der Lokalisierung an Größe zunimmt, abgeschnitten wird. Sollte der Inhalt nach der Lokalisierung an Größe abnehmen, wird nicht benötigter Platz außerdem entfernt.  
  
 `<Grid x:Uid="Grid_1">`  
  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>\-Eigenschaften werden benötigt, damit die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Lokalisierungs\-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] ordnungsgemäß ausgeführt werden.  
  
 Diese werden von den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Lokalisierungs\-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] zum Nachverfolgen von Änderungen zwischen der Entwicklung und der Lokalisierung der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] verwendet.  Mit <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>\-Eigenschaften können Sie eine neuere Version der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit einer älteren Lokalisierung der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] zusammenführen.  <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>\-Eigenschaften werden durch Ausführen von **msbuild \/t:updateuid RunDialog.csproj** in einer Befehlsshell hinzugefügt.  Hierbei handelt es sich um die empfohlene Methode zum Hinzufügen von <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>\-Eigenschaften, da manuelles Hinzufügen normalerweise sehr zeitaufwändig und wenig präzise ist.  Sie können überprüfen, ob <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>\-Eigenschaften ordnungsgemäß festgelegt sind, indem Sie **msbuild \/t:checkuid RunDialog.csproj** ausführen.  
  
 Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] wird mithilfe des <xref:System.Windows.Controls.Grid>\-Steuerelements strukturiert. Dieses Steuerelement eignet sich für automatische Layouts in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Beachten Sie, dass das Dialogfeld in drei Zeilen und fünf Spalten geteilt wird.  Keine der Zeilen\- oder Spaltendefinitionen hat eine feste Größe. Daher können sich die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Elemente, die sich in jeder Zelle befinden, während der Lokalisierung an jede Größenänderung anpassen.  
  
 [!code-xml[GlobalizationRunDialog#GridColumnDef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef)]  
  
 Die ersten beiden Spalten, in die die Bezeichnungen **Öffnen:** und <xref:System.Windows.Controls.ComboBox> eingefügt sind, nehmen 10 Prozent der Gesamtbreite der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ein.  
  
 [!code-xml[GlobalizationRunDialog#GridColumnDef2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef2)]  
  
 Beachten Sie, dass im Beispiel das Feature für die gemeinsame Größenänderung von <xref:System.Windows.Controls.Grid> verwendet wird.  Die letzten drei Spalten nutzen diesen Umstand, indem sie in derselben <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> eingefügt werden.  Wie aufgrund des Eigenschaftennamens zu erwarten ist, ermöglicht dies den Spalten, dieselbe Größe zu verwenden.  Wenn also "Browse…" in die längere Zeichenfolge "Durchsuchen…" lokalisiert wird, nimmt die Breite aller Schaltflächen zu, anstatt eine kleine Schaltfläche "OK" und eine unverhältnismäßig große Schaltfläche "Durchsuchen…" anzuzeigen.  
  
 **Xml:lang**  
  
 `Xml:lang="en-US"`  
  
 Beachten Sie, dass [xml:lang\-Behandlung in XAML](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md) am Stammelement der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] platziert ist.  Diese Eigenschaft beschreibt die Kultur eines bestimmten Elements und seiner untergeordneten Elemente.  Dieser Wert wird von mehreren Features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet und sollte im Rahmen der Lokalisierung entsprechend geändert werden.  Dieser Wert bestimmt, welches Sprachwörterbuch zur Silbentrennung und Rechtschreibprüfung verwendet wird.  Außerdem wirkt er sich auf die Anzeige von Ziffern aus und bestimmt, welche Schriftart durch die automatische Schriftartauswahl ausgewählt wird.  Schließlich beeinflusst diese Eigenschaft die Anzeige von Nummern und die Gestaltung von Text in komplexen Skripts.  Der Standardwert ist "en\-US".  
  
 **Building a Satellite Resource Assembly**  
  
 *In .csproj:*  
  
 `<UICulture>en-US</UICulture>`  
  
 Beachten Sie den zusätzlichen `UICulture`\-Wert.  Wird diese auf einen gültigen <xref:System.Globalization.CultureInfo>\-Wert festgelegt, z. B. en\-US, wird durch das Erstellen des Projekts eine Satellitenassembly mit sämtlichen lokalisierbaren Ressourcen erzeugt.  
  
 `<Resource Include="RunIcon.JPG">`  
  
 `<Localizable>False</Localizable>`  
  
 `</Resource>`  
  
 Die Datei `RunIcon.JPG` muss nicht lokalisiert werden, da sie für alle Kulturen identisch angezeigt werden sollte.  `Localizable` ist auf `false` festgelegt, damit es in der sprachneutralen Hauptassembly verbleibt anstatt in der Satellitenassembly.  Für den Standardwert aller nicht kompilierbaren Ressourcen wird `Localizable` auf `true` festgelegt.  
  
 **Lokalisieren des Dialogfelds Ausführen**  
  
 **Parse**  
  
 Die Analyse der lokalisierbaren Ressourcen aus der Satellitenassembly ist der erste Schritt der Lokalisierung, nachdem die Anwendung erstellt wurde.  Verwenden Sie für dieses Thema das LocBaml\-Beispieltool, das sich unter [Beispiel zum LocBaml\-Tool](http://go.microsoft.com/fwlink/?LinkID=160016) befindet.  Bedenken Sie, dass LocBaml lediglich ein Beispieltool und dafür konzipiert ist, Ihnen den Einstieg in das Erstellen eines Lokalisierungstools zu erleichtern, das sich dem Lokalisierungsprozess anpasst.  Analysieren Sie mithilfe von LocBaml Folgendes: **LocBaml \/parse RunDialog.resources.dll \/out:**, um die Datei "RunDialog.resources.dll.CSV" zu generieren.  
  
 **Localize**  
  
 Verwenden Sie Ihren bevorzugten CSV\-Editor, der Unicode unterstützt, um diese Datei zu bearbeiten.  Filtern Sie alle Einträge mit der Lokalisierungskategorie "None" heraus.  Folgende Einträge sollten angezeigt werden:  
  
||||  
|-|-|-|  
|Ressourcenschlüssel|Lokalisierungskategorie|Wert|  
|Button\_1:System.Windows.Controls.Button.$Content|Button|OK|  
|Button\_2:System.Windows.Controls.Button.$Content|Button|Abbrechen|  
|Button\_3:System.Windows.Controls.Button.$Content|Button|Browse...|  
|ComboBox\_1:System.Windows.Controls.ComboBox.$Content|ComboBox||  
|TextBlock\_1:System.Windows.Controls.TextBlock.$Content|Text|Geben Sie den Namen eines Programms, Ordners, Dokuments oder einer Internetressource ein, die daraufhin von Windows für Sie geöffnet wird.|  
|TextBlock\_2:System.Windows.Controls.TextBlock.$Content|Text|Open:|  
|Window\_1:System.Windows.Window.Title|Titel|Run|  
  
 Eine Lokalisierung der Anwendung ins Deutsche macht folgende Übersetzungen erforderlich:  
  
||||  
|-|-|-|  
|Ressourcenschlüssel|Lokalisierungskategorie|Wert|  
|Button\_1:System.Windows.Controls.Button.$Content|Button|OK|  
|Button\_2:System.Windows.Controls.Button.$Content|Button|Abbrechen|  
|Button\_3:System.Windows.Controls.Button.$Content|Button|Durchsuchen…|  
|ComboBox\_1:System.Windows.Controls.ComboBox.$Content|ComboBox||  
|TextBlock\_1:System.Windows.Controls.TextBlock.$Content|Text|Geben Sie den Namen eines Programms, Ordners, Dokuments oder einer Internetressource an.|  
|TextBlock\_2:System.Windows.Controls.TextBlock.$Content|Text|Öffnen:|  
|Window\_1:System.Windows.Window.Title|Titel|Run|  
  
 **Generate**  
  
 Der letzte Lokalisierungsschritt umfasst das Erstellen der neu lokalisierten Satellitenassembly.  Dies kann mit dem folgenden LocBaml\-Befehl ausgeführt werden:  
  
 **LocBaml.exe \/generate RunDialog.resources.dll \/trans:RunDialog.resources.dll.CSV \/out: .  \/cul:de\-DE**  
  
 Wenn diese Datei resources.dll im deutschen [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] in den Ordner de\-DE neben der Hauptassembly platziert wird, dann wird automatisch diese Ressource anstelle der Ressource im Ordner es\-US geladen.  Wenn Sie keine deutsche Version von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] besitzen, um das zu testen, legen Sie die Kultur auf eine beliebige Kultur des verwendeten [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] fest \(z. B.  en\-US\). Ersetzen Sie anschließend die ursprüngliche resources.dll\-Datei.  
  
 **Satellite Resource Loading**  
  
|MyDialog.exe|en\-US\\MyDialog.resources.dll|de\-DE\\MyDialog.resources.dll|  
|------------------|------------------------------------|------------------------------------|  
|Code|Ursprüngliche englische BAML|Lokalisierte BAML|  
|Kulturell neutrale Ressourcen|Weitere Ressourcen auf Englisch|Weitere ins Deutsche lokalisierte Ressourcen|  
  
 Basierend auf der `Thread.CurrentThread.CurrentUICulture` der Anwendung wählt .NET Framework die zu ladende Satellitenressourcenassembly automatisch aus.  Dies wird die Standardkultur des [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]\-Betriebssystems.  Wenn Sie also das deutsche [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] verwenden, wird de\-DE\\MyDialog.resources.dll geladen und beim englischen [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] wird en\-US\\MyDialog.resources.dll geladen.  Sie können für die Anwendung die endgültige Fallbackressource festlegen, indem Sie NeutralResourcesLanguage in der Datei AssemblyInfo.\* des Projekts angeben.  Wenn Sie beispielsweise Folgendes angeben:  
  
 `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]`  
  
 wird die en\-US\\MyDialog.resources.dll mit der deutschen Windows\-Version verwendet, falls weder de\-DE\\MyDialog.resources.dll noch de\\MyDialog.resources.dll verfügbar sind.  
  
### Microsoft\-Hompage für Saudi\-Arabien  
 In der folgenden Grafik wird eine englische und eine arabische Homepage angezeigt.  Das vollständige Beispiel, das in dieser Grafik dargestellt wird, finden Sie unter [Beispiel zu globalisierter Startseite](http://go.microsoft.com/fwlink/?LinkID=159990).  
  
 **Englisch:**  
  
 ![Englische Seite](../../../../docs/framework/wpf/advanced/media/englishhomepage.png "EnglishHomepage")  
  
 **Arabisch:**  
  
 ![Arabische Seite](../../../../docs/framework/wpf/advanced/media/arabichomepage.png "ArabicHomepage")  
  
### Entwerfen einer globalen Microsoft\-Homepage  
 Mit der Simulierung der Microsoft\-Website für Saudi\-Arabien werden die Globalisierungsfeatures veranschaulicht, die für Sprachen mit Schreibrichtung von rechts nach links zur Verfügung gestellt werden.  Sprachen wie Hebräisch und Arabisch haben eine Leserichtung von rechts nach links, sodass das Layout der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]s oftmals ganz anders ausgerichtet werden muss, als das in Sprachen mit einer Schreibrichtung von links nach rechts \(z. B. Englisch\) der Fall wäre.  Das Lokalisieren einer von links nach rechts geschriebenen Sprache in eine von rechts nach links geschriebene Sprache oder umgekehrt kann sich als recht schwierig erweisen.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wurde entwickelt, um solche Lokalisierungen erheblich zu erleichtern.  
  
 **FlowDirection**  
  
 *Homepage.xaml:*  
  
 [!code-xml[GlobalizationHomepage#Homepage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#homepage)]  
  
 Beachten Sie die <xref:System.Windows.FrameworkElement.FlowDirection%2A>\-Eigenschaft bei <xref:System.Windows.Controls.Page>.  Eine Änderung dieser Eigenschaft in <xref:System.Windows.FlowDirection> zieht eine Änderung der <xref:System.Windows.FrameworkElement.FlowDirection%2A> der <xref:System.Windows.Controls.Page> und deren untergeordneter Elemente nach sich, sodass das Layout der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] gekippt wird, um entsprechend der Erwartung eines arabischen Benutzers von rechts nach links ausgerichtet zu sein.  Das Vererbungsverhalten lässt sich überschreiben, indem Sie eine explizite <xref:System.Windows.FrameworkElement.FlowDirection%2A> für jedes Element angeben.  Die <xref:System.Windows.FrameworkElement.FlowDirection%2A>\-Eigenschaft steht jedem <xref:System.Windows.FrameworkElement> oder dokumentbezogenen Element zur Verfügung und hat den impliziten Wert <xref:System.Windows.FlowDirection>.  
  
 Beachten Sie, dass sogar der Farbverlaufhintergrund ordnungsgemäß gekippt wird, wenn die <xref:System.Windows.FrameworkElement.FlowDirection%2A> des Stamms geändert wird:  
  
 **FlowDirection\="LeftToRight"**  
  
 ![Fluss von links nach rechts](../../../../docs/framework/wpf/advanced/media/lefttoright.png "LeftToRight")  
  
 **FlowDirection\="RightToLeft"**  
  
 ![Fluss von rechts nach links](../../../../docs/framework/wpf/advanced/media/righttoleft.png "RightToLeft")  
  
 **Vermeiden der Verwendung fester Abmessungen für Bereiche und Steuerelemente**  
  
 Wenn Sie sich Homepage.xaml anschauen, wird Ihnen neben der festen Breite und Höhe, die für die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] im oberen <xref:System.Windows.Controls.DockPanel> angegeben wurde, auffallen, dass es keine weiteren festen Abmessungen gibt.  Vermeiden Sie die Verwendung von festen Abmessungen, um das Abschneiden von lokalisiertem Text zu verhindern, der u. U. länger als der Ausgangstext ist.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Bereiche und \-Steuerelemente werden basierend auf dem enthaltenen Inhalt automatisch angepasst.  Außerdem enthalten die meisten Steuerelemente minimale und maximale Abmessungen, die Sie für weitere Steuerelemente festlegen können \(z. B.  MinWidth\= "20"\).  Mit <xref:System.Windows.Controls.Grid> können Sie auch relative Breiten und Höhen festlegen, indem Sie ‘\*’ \(z. B.  Width\= "0.25\*"\) oder die Funktion für gemeinsame Zellengrößen verwenden.  
  
 **Lokalisierungskommentare**  
  
 In vielen Fällen ist der Inhalt mehrdeutig und schwierig zu übersetzen.  Der Entwickler oder Designer kann dem Lokalisierer über Lokalisierungskommentare zusätzlichen Kontext und entsprechende Kommentare zur Verfügung zu stellen.  Im Folgenden wird durch Localization.Comments die Verwendung des Zeichens ‘&#124;’ erläutert.  
  
 [!code-xml[GlobalizationHomepage#LocalizationComment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcomment)]  
  
 Dieser Kommentar wird dem Inhalt von TextBlock\_1 zugeordnet. Im Fall des LocBaml\-Tools \(siehe [Lokalisieren einer Anwendung](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)\) wird er in der sechsten Spalte der Zeile TextBlock\_1 in der CSV\-Ausgabedatei angezeigt:  
  
|||||||  
|-|-|-|-|-|-|  
|Ressourcenschlüssel|Kategorie|Lesbar|Änderbar|Kommentar|Wert|  
|TextBlock\_1:System.Windows.Controls.TextBlock.$Content|Text|TRUE|TRUE|Dieses Zeichen wird als dekorative Regel verwendet.|&#124;|  
  
 Kommentare können für den Inhalt oder die Eigenschaft eines beliebigen Elements mit folgender Syntax eingefügt werden:  
  
 [!code-xml[GlobalizationHomepage#LocalizationCommentsProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcommentsprop)]  
  
 **Lokalisierungsattribute**  
  
 Häufig müssen Entwickler oder Lokalisierungsmanager einschränken, was Lokalisierer lesen und ändern dürfen.  Wenn Sie beispielsweise nicht möchten, dass der Lokalisierer den Namen Ihres Unternehmens oder Rechtstexte übersetzt, stellt  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Attribute bereit, mit deren Hilfe Sie die Lesbarkeit, Änderbarkeit und Kategorie von Elementinhalt und \-eigenschaften festlegen können, die Ihr Lokalisierungstool zum Sperren, Ausblenden oder Sortieren von Elementen verwenden kann.  Weitere Informationen hierzu finden Sie unter <xref:System.Windows.Localization.Attributes%2A>.  In diesem Beispiel gibt das LocBaml\-Tool lediglich die Werte dieser Attribute aus.  Alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelemente besitzen Standardwerte für diese Attribute, die Sie jedoch überschreiben können.  Im Folgenden werden beispielsweise die standardmäßigen Lokalisierungsattribute für `TextBlock_1` überschrieben. Der Inhalt bleibt für Lokalisierer lesbar, kann aber nicht von ihnen bearbeitet werden.  
  
 [!code-xml[LocalizationComAtt#LocalizationAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributes)]  
  
 Neben den Lesbarkeits\- und Änderbarkeitsattributen stellt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Enumeration allgemeiner Benutzeroberflächenkategorien zur Verfügung \(<xref:System.Windows.LocalizationCategory>\), mit deren Hilfe Lokalisierern mehr Kontext bereitgestellt wird.  Die standardmäßigen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Kategorien für Plattformsteuerelemente können in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ebenfalls überschrieben werden:  
  
 [!code-xml[LocalizationComAtt#LocalizationAttributesOverridden](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributesoverridden)]  
  
 Mithilfe von Code können auch die von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zur Verfügung gestellten standardmäßigen Lokalisierungsattribute überschrieben werden. Anschließend können Sie die richtigen Standardwerte für benutzerdefinierte Steuerelemente ordnungsgemäß festlegen.  Beispiele:  
  
 `[Localizability(Readability = Readability.Readable, Modifiability=Modifiability.Unmodifiable, LocalizationCategory.None)]`  
  
 `public class CorporateLogo: TextBlock`  
  
 `{`  
  
 `…`  
  
 `..`  
  
 `.`  
  
 `}`  
  
 Die in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] festgelegten Beispielattribute haben Vorrang gegenüber Werten, die im Code für benutzerdefinierte Steuerelemente festgelegt wurden.  Weitere Informationen zu Attributen und Kommentaren finden Sie unter [Lokalisierungsattribute und \-kommentare](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md).  
  
 **Automatische Schriftartauswahl und zusammengesetzte Schriftarten**  
  
 Wenn Sie eine Schriftart angeben, die einen gegebenen Codepunktbereich nicht unterstützt, sucht [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] automatisch eine Schriftart aus, die dies erfüllt. Hierzu wird Global User Interface.compositefont im Verzeichnis Windows\\Fonts verwendet.  Zusammengesetzte Schriftarten funktionieren wie jede andere Schriftart. Sie können durch Festlegen der FontFamily \(z. B.  FontFamily\= "Global User Interface"\) eines Elements explizit verwendet werden.  Sie können Ihre eigenen Einstellungen für die automatische Schriftartauswahl angeben, indem Sie eine eigene zusammengesetzte Schriftart erstellen und die Schriftart angeben, die für spezielle Codepunktbereiche und Sprachen verwendet werden soll.  
  
 Weitere Informationen zu zusammengesetzten Schriftarten finden Sie unter <xref:System.Windows.Media.FontFamily>.  
  
 **Lokalisieren der Microsoft\-Homepage**  
  
 Führen Sie zum Lokalisieren dieser Anwendung dieselben Schritte aus wie für das Beispieldialogfeld Ausführen.  Die lokalisierte CSV\-Datei für Arabisch steht Ihnen unter [Beispiel zu globalisierter Startseite](http://go.microsoft.com/fwlink/?LinkID=159990) zur Verfügung.