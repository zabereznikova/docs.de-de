---
title: "Dokumente in WPF | Microsoft Docs"
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
  - "Im Browser darstellbare Dokumente"
  - "Dokumente, Im Browser darstellbar"
  - "Dokumente, Steuerelemente"
  - "Dokumente, Packen"
  - "Dokumente, Textlayout"
  - "Dokumente, Typen"
  - "Dokumente, XPS"
  - "Packen von Dokumenten"
  - "XPS-Dokumente"
ms.assetid: 6e8db7bc-050a-4070-aa72-bb8c46e87ff8
caps.latest.revision: 36
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 35
---
# Dokumente in WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] enthält eine Vielzahl von Dokumentfeatures, anhand derer hochwertige Inhalte erstellt werden können, auf die im Vergleich zu vorherigen Generationen von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] leichter zugegriffen werden kann, bzw. die einfacher gelesen werden können.  Außer einer verbesserten Leistungsfähigkeit und Qualität bietet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] auch integrierte Dienste für die Dokumentenanzeige, das Packen und für die Sicherheit.  Dieses Thema enthält eine Einführung in die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Dokumenttypen und in das Packen von Dokumenten.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="types_of_documents"></a>   
## Dokumenttypen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterteilt Dokumente auf der Grundlage ihrer beabsichtigten Verwendung in zwei große Kategorien. Diese Dokumentkategorien werden als "einheitlich dargestellte Dokumente" und "Flussdokumente" bezeichnet.  
  
 Einheitlich dargestellte Dokumente sind für Anwendungen geeignet, bei denen unabhängig davon, welche Hardware für das Anzeigen und Drucken von Dokumenten verwendet wird, eine präzise Präsentation im Format [!INCLUDE[TLA#tla_wys](../../../../includes/tlasharptla-wys-md.md)] erforderlich ist.  Zu den typischen Verwendungsformen von einheitlich dargestellten Dokumenten zählen Desktopveröffentlichung, Wortverarbeitung und Formularlayout, wo die Beibehaltung der ursprünglichen Seitendarstellung wichtig ist.  Ein einheitlich dargestelltes Dokument behält unabhängig vom Gerät, das zur Anzeige oder zum Ausdruck verwendet wird, die exakte Positionierung der Inhaltselemente als Teil seines Layouts bei.  Beispielsweise wird ein einheitlich dargestelltes Dokument, das mit 96 DPI \(Dots Per Inch\) auf einem Bildschirm angezeigt wird, exakt auf dieselbe Weise dargestellt, wenn es auf einem Laserdrucker mit 600 DPI oder im Fotosatz mit 4800 DPI gedruckt wird.  Das Seitenlayout bleibt in allen Fällen gleich, während sich die Qualität des Dokuments nach der maximalen Leistungsfähigkeit der einzelnen Geräte richtet.  
  
 Im Vergleich hierzu optimieren Flussdokumente die Anzeige und Lesbarkeit und eignen sich insbesondere für die Szenarien, in denen der Hauptzweck darin besteht, leicht lesbare Dokumente zu erzeugen.  Flussdokumente sind nicht auf ein vordefiniertes Layout festgelegt, sondern passen Inhalte dynamisch an und bauen sie neu auf. Dies geschieht auf der Basis von Laufzeitvariablen, wie z. B. Fenstergröße, Geräteauflösung und optionalen Benutzereinstellungen.  Eine Webseite ist ein einfaches Beispiel für ein Flussdokument. Hier wird der Seiteninhalt dynamisch formatiert und so dem aktuellen Fenster angepasst.  Flussdokumente optimieren auf der Grundlage der Laufzeitumgebung die Anzeige und die Lesbarkeit für den Benutzer.  Um z. B. sowohl auf einem hochauflösenden 19\-Zoll\-Bildschirm als auch auf einem kleinen 2x3\-Zoll\-PDA\-Bildschirm eine optimale Lesbarkeit zu erzielen, wird dasselbe Flussdokument dynamisch umformatiert.  Zusätzlich besitzen Flussdokumente eine Anzahl integrierter Features, darunter Suchfunktionen, Anzeigemodi, mit denen die Lesbarkeit verbessert wird, und die Fähigkeit, die Größe und die Darstellung von Schriftarten zu ändern.  Illustrationen, Beispiele und ausführliche Informationen über Flussdokumente finden Sie unter [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
<a name="document_viewer"></a>   
## Steuerelemente und Textlayout in Dokumenten  
 [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] enthält eine Reihe von vordefinierten Steuerelementen, die die Verwendung von einheitlich dargestellten Dokumenten, Flussdokumenten und von allgemeinem Text in Anwendungen vereinfachen.  Die Inhalte der einheitlich dargestellten Dokumente können mithilfe des Steuerelements <xref:System.Windows.Controls.DocumentViewer> angezeigt werden.  Die Anzeige der Flussdokumentinhalte wird von drei unterschiedlichen Steuerelementen unterstützt: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer> und <xref:System.Windows.Controls.FlowDocumentScrollViewer>, die verschiedenen Benutzerszenarien zugeordnet sind \(weitere Informationen finden Sie in den folgenden Abschnitten\).  Andere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelemente stellen ein vereinfachtes Layout zur Unterstützung allgemeiner Textverwendungen bereit \(weitere Informationen finden Sie unter [Text in der Benutzeroberfläche](#text_in_the_user_interface)\).  
  
### Steuerelement für einheitlich dargestellte Dokumente \- DocumentViewer  
 Das <xref:System.Windows.Controls.DocumentViewer>\-Steuerelement ist für die Anzeige von <xref:System.Windows.Documents.FixedDocument>\-Inhalten konzipiert.  Das <xref:System.Windows.Controls.DocumentViewer>\-Steuerelement stellt anhand seiner intuitiven Benutzeroberfläche eine integrierte Unterstützung für Routinevorgänge, einschließlich Druckausgabe, Kopieren in die Zwischenablage, Zoomen und Features zur Textsuche, bereit.  Das Steuerelement ermöglicht den Zugriff auf Seiteninhalte über einen vertrauten Bildlaufmechanismus.  Wie alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelemente unterstützt <xref:System.Windows.Controls.DocumentViewer> die komplette oder partielle Neuformatierung, wodurch das Steuerelement in praktisch jede Anwendung oder Umgebung visuell integriert werden kann.  
  
 <xref:System.Windows.Controls.DocumentViewer> zeigt Inhalte schreibgeschützt an. Das Bearbeiten und Ändern von Inhalten ist nicht möglich und wird nicht unterstützt.  
  
<a name="flow_document"></a>   
### Steuerelemente für Flussdokumente  
 **Hinweis:** Ausführlichere Informationen zu den Features von Flussdokumenten sowie deren Erstellung finden Sie unter [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
 Die Anzeige der Flussdokumentinhalte wird von drei Steuerelementen unterstützt: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer> und <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
#### FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> enthält Features, mit denen Benutzer dynamisch zwischen verschiedenen Anzeigemodi auswählen können. Dazu gehören ein einseitiger \(jeweils einzelne Seiten\) Anzeigemodus, ein Anzeigemodus mit zwei Seiten gleichzeitig \(Buchformat\) und ein Anzeigemodus mit fortlaufendem \(randlosem\) Bildlauf.  Weitere Informationen zu diesen Anzeigemodi finden Sie unter <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  Wenn keine dynamischen Wechsel zwischen den unterschiedlichen Anzeigemodi erforderlich sind, bieten <xref:System.Windows.Controls.FlowDocumentPageViewer> und <xref:System.Windows.Controls.FlowDocumentScrollViewer> auch weniger umfangreiche Anzeigen für fortlaufenden Inhalt, die auf einen bestimmten Anzeigemodus festgelegt sind.  
  
#### FlowDocumentPageViewer und FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> zeigt Inhalt im einseitigen Anzeigemodus an, während <xref:System.Windows.Controls.FlowDocumentScrollViewer> Inhalt im fortlaufenden Bildlaufmodus anzeigt.  Sowohl <xref:System.Windows.Controls.FlowDocumentPageViewer> als auch <xref:System.Windows.Controls.FlowDocumentScrollViewer> sind auf einen bestimmten Anzeigemodus festgelegt.  Im Gegensatz dazu bietet <xref:System.Windows.Controls.FlowDocumentReader> Features für die dynamische Auswahl verschiedener Anzeigemodi \(welche von der <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>\-Enumeration bereitgestellt werden\). Dies ist jedoch ressourcenintensiver als <xref:System.Windows.Controls.FlowDocumentPageViewer> oder <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 Standardmäßig wird immer eine vertikale Bildlaufleiste und eine horizontale Bildlaufleiste nach Bedarf angezeigt.  Die standardmäßige [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für <xref:System.Windows.Controls.FlowDocumentScrollViewer> enthält keine Symbolleiste; die <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A>\-Eigenschaft kann jedoch verwendet werden, um eine integrierte Symbolleiste zu aktivieren.  
  
<a name="text_in_the_user_interface"></a>   
### Text in der Benutzeroberfläche  
 Text kann in Dokumenten nicht nur hinzugefügt werden, sondern wird offensichtlich auch in Benutzeroberflächen von Anwendungen, z. B. in Formularen, verwendet.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält mehrere Steuerelemente, um Text auf dem Bildschirm zeichnen zu können.  Jedes Steuerelement richtet sich an ein anderes Szenario und verfügt über seine individuellen Features und Einschränkungen.  Im Allgemeinen sollte das <xref:System.Windows.Controls.TextBlock>\-Element verwendet werden, wenn eine eingeschränkte Textunterstützung erforderlich ist, z. B. ein kurzer Satz in einer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  <xref:System.Windows.Controls.Label> kann verwendet werden, wenn nur ein Minimum an Textunterstützung erforderlich ist.  Weitere Informationen finden Sie unter [Übersicht über TextBlock](../../../../docs/framework/wpf/controls/textblock-overview.md).  
  
<a name="packaging"></a>   
## Packen von Dokumenten  
 Die <xref:System.IO.Packaging>\-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] stellen ein effizientes Verfahren bereit, um Anwendungsdaten, Dokumentinhalte und zugehörige Ressourcen in einem einzelnen Container, auf den einfach zugegriffen werden kann und der portabel sowie leicht zu verteilen ist, zusammenzufassen.  Eine ZIP\-Datei ist ein Beispiel für einen <xref:System.IO.Packaging.Package>\-Typ, der mehrere Objekte in einer einzelnen Einheit enthalten kann.  Die [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] zum Packen von Dokumenten stellen eine Standard\-<xref:System.IO.Packaging.ZipPackage>\-Implementierung bereit, die einen Open Packaging Conventions\-Standard mit XML und ZIP\-Dateiarchitektur verwendet.  Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] zum Packen von Dokumenten ermöglichen eine einfache Erstellung der Pakete sowie ein einfaches Speichern und Zugreifen auf die darin enthaltenen Objekte.  Ein in einem <xref:System.IO.Packaging.Package> gespeichertes Objekt wird als <xref:System.IO.Packaging.PackagePart> \("Part"\) bezeichnet.  Pakete können auch signierte digitale Zertifikate enthalten, die verwendet werden können, um den Ersteller des Parts zu identifizieren und um zu überprüfen, ob der Paketinhalt geändert wurde.  Pakete enthalten außerdem ein <xref:System.IO.Packaging.PackageRelationship>\-Feature, das es ermöglicht, dem Paket zusätzliche Informationen hinzuzufügen oder bestimmten Parts zuzuordnen, ohne den Inhalt bereits vorhandener Parts ändern zu müssen.  Die Paketdienste unterstützen außerdem [!INCLUDE[TLA#tla_rm](../../../../includes/tlasharptla-rm-md.md)].  
  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Paketarchitektur dient als Grundlage für eine Anzahl von Schlüsseltechnologien:  
  
-   [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]\-Dokumente, die der [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] entsprechen.  
  
-   Microsoft Office "12"\-Dokumente im Open XML\-Format \(.docx\).  
  
-   Benutzerdefinierte Speicherformate für den eigenen Anwendungsentwurf.  
  
 Auf der Grundlage der zum Packen von Dokumenten verwendeten APIs ist ein <xref:System.Windows.Xps.Packaging.XpsDocument> speziell zum Speichern von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Dokumenten mit einheitlich dargestellten Inhalten konzipiert.  Ein <xref:System.Windows.Xps.Packaging.XpsDocument> ist ein eigenständiges Dokument, das in einem Viewer geöffnet, in einem <xref:System.Windows.Controls.DocumentViewer>\-Steuerelement angezeigt, an einen Druckerspooler weitergeleitet oder direkt auf einem [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]\-kompatiblen Drucker ausgegeben werden kann.  
  
 Die folgenden Abschnitte enthalten weitere Informationen zu den <xref:System.IO.Packaging.Package>\- und <xref:System.Windows.Xps.Packaging.XpsDocument>\-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], die in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthalten sind.  
  
<a name="packages"></a>   
### Paketkomponenten  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-APIs zum Packen von Dokumenten ermöglichen es, Anwendungsdaten und Dokumente in einer einzigen portablen Einheit zusammenzufassen.  Eine ZIP\-Datei ist eine der häufigsten Paketarten und ist die Standardpaketart in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  <xref:System.IO.Packaging.Package> selbst ist eine abstrakte Klasse, aus der <xref:System.IO.Packaging.ZipPackage> mithilfe einer Open Standard\-XML\- und ZIP\-Dateiarchitektur implementiert wird.  Die <xref:System.IO.Packaging.Package.Open%2A>\-Methode verwendet <xref:System.IO.Packaging.ZipPackage>, um ZIP\-Dateien zu erstellen und standardmäßig zu verwenden.  Ein Paket kann drei grundlegende Elementtypen enthalten:  
  
|||  
|-|-|  
|<xref:System.IO.Packaging.PackagePart>|Anwendungsinhalte, Daten, Dokumente und Ressourcendateien.|  
|<xref:System.IO.Packaging.PackageDigitalSignature>|[X.509\-Zertifikat](GTMT) zur Identifikation, Authentifizierung und Validierung.|  
|<xref:System.IO.Packaging.PackageRelationship>|Hinzugefügte Informationen, die sich auf das Paket oder auf einen bestimmten Part beziehen.|  
  
<a name="PackageParts"></a>   
#### PackageParts  
 Ein <xref:System.IO.Packaging.PackagePart> \("Part"\) ist eine abstrakte Klasse, die sich auf ein Objekt bezieht, das in einem <xref:System.IO.Packaging.Package> gespeichert wird.  In einer ZIP\-Datei entsprechen die Parts den einzelnen Dateien, die in der ZIP\-Datei gespeichert sind.  <xref:System.IO.Packaging.ZipPackagePart> stellt die Standardimplementierung für serialisierbare Objekte bereit, die in einem <xref:System.IO.Packaging.ZipPackage>\-Element gespeichert sind.  Die in einem Paket enthaltenen Parts werden wie in einem Dateisystem in einer hierarchisch aufgebauten Verzeichnis\- oder Ordnerstruktur gespeichert.  Mithilfe der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-APIs zum Packen von Dokumenten können Anwendungen mehrere <xref:System.IO.Packaging.PackagePart>\-Objekte unter Verwendung eines einzigen ZIP\-Dateicontainers schreiben, speichern und lesen.  
  
<a name="PackageDigitalSignatures"></a>   
#### PackageDigitalSignatures  
 Den in einem Paket enthaltenen Parts kann aus Sicherheitsgründen eine <xref:System.IO.Packaging.PackageDigitalSignature> \(digitale Signatur\) zugeordnet werden.  Eine <xref:System.IO.Packaging.PackageDigitalSignature> umfasst ein [509](GTMT), das zwei Features bereitstellt:  
  
1.  Identifiziert und authentifiziert den Ersteller des Parts.  
  
2.  Überprüft, ob das Part geändert wurde.  
  
 Die digitale Signatur verhindert nicht das Ändern von Parts, die Validierung der digitalen Signatur schlägt jedoch fehl, wenn ein Part geändert wurde.  Die Anwendung kann dann eine entsprechende Aktion ausführen, z. B. das Öffnen des Parts abblocken oder den Benutzer benachrichtigen, dass das Part geändert wurde und nicht sicher ist.  
  
<a name="PackageRelationships"></a>   
#### PackageRelationships  
 Eine <xref:System.IO.Packaging.PackageRelationship> \("Beziehung"\) stellt einen Mechanismus zum Zuordnen von zusätzlichen Informationen zum Paket oder zu einem Part im Paket bereit.  Eine Beziehung ist eine Möglichkeit auf Paketebene, um einem Part zusätzliche Informationen zuzuordnen, ohne den tatsächlichen Inhalt des Parts zu ändern.  Das direkte Einfügen von neuen Daten in den Inhalt des Parts ist in vielen Fällen nicht praktikabel:  
  
-   Der tatsächliche Parttyp und sein Inhaltsschema sind unbekannt.  
  
-   Selbst wenn das Inhaltsschema bekannt ist, bietet es evtl. keine Möglichkeit zum Hinzufügen von neuen Informationen.  
  
-   Das Part könnte digital signiert oder verschlüsselt sein und so jede Änderung ausschließen.  
  
 Paketbeziehungen bieten eine erkennbare Möglichkeit zum Hinzufügen und Zuordnen von zusätzlichen Informationen zu einzelnen Parts oder zum gesamten Paket.  Paketbeziehungen werden für zwei Hauptfunktionen verwendet:  
  
1.  Definieren von Abhängigkeitsbeziehungen von einem Part zu einem anderen Part.  
  
2.  Definieren von Informationsbeziehungen, die dem Part partsbezogene Hinweise oder andere Daten hinzufügen.  
  
 Eine <xref:System.IO.Packaging.PackageRelationship> bietet eine schnelle, erkennbare Möglichkeit zur Definition von Abhängigkeiten und zum Hinzufügen von anderen Informationen, die nur einem Paketpart oder dem gesamten Paket zugeordnet sind.  
  
<a name="Dependency_Relationships"></a>   
##### Abhängigkeitsbeziehungen  
 Abhängigkeitsbeziehungen werden zum Beschreiben von Abhängigkeiten verwendet, die zwischen einem Part und anderen Parts bestehen.  Zum Beispiel könnte ein Paket einen HTML\-Part enthalten, der einen oder mehrere Bildtags \(\<img\>\) aufweist.  Die Bildtags beziehen sich auf Bilder, die entweder andere Parts innerhalb des Pakets darstellen oder sich außerhalb des Pakets befinden \(z. B. im Internet verfügbar\).  Durch das Erstellen einer <xref:System.IO.Packaging.PackageRelationship> im Zusammenhang mit einer HTML\-Datei können die abhängigen Ressourcen schnell und leicht ermittelt und abgerufen werden.  Browser\- oder Vieweranwendungen können direkt auf die Partbeziehungen zugreifen und sofort, ohne das Schema zu kennen, mit der Zusammenstellung der abhängigen Ressourcen beginnen oder das Dokument analysieren.  
  
<a name="Information_Relationships"></a>   
##### Informationsbeziehungen  
 Wie bei einem Hinweis oder einer Anmerkung kann eine <xref:System.IO.Packaging.PackageRelationship> auch zum Speichern anderer Informationsarten verwendet werden, die dem Part zugeordnet werden sollen, ohne tatsächlich den Inhalt des Parts ändern zu müssen.  
  
<a name="XPS_Documents"></a>   
## XPS\-Dokumente  
 Ein [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]\-Dokument ist ein Paket, das ein oder mehrere einheitlich dargestellte Dokumente zusammen mit allen Ressourcen und Informationen enthält, die zum Rendern erforderlich sind.  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] ist ferner das systemeigene Druckerspoolformat in [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)].  Ein <xref:System.Windows.Xps.Packaging.XpsDocument> ist im Standard\-ZIP\-Dataset gespeichert und kann eine Kombination von XML und binären Komponenten, z. B. Bild\- und Schriftartdateien, enthalten. [PackageRelationships](#PackageRelationships) werden verwendet, um die Abhängigkeiten zwischen dem Inhalt und den Ressourcen zu definieren, die zum vollständigen Rendern des Dokuments erforderlich sind.  Das <xref:System.Windows.Xps.Packaging.XpsDocument>\-Design stellt eine individuelle, hoch zuverlässige Dokumentlösung bereit, die mehrere Verwendungen unterstützt:  
  
-   Lesen, Schreiben und Speichern der Inhalte von einheitlich dargestellten Dokumenten und Ressourcen als einzelne, portable und leicht zu verteilende Datei.  
  
-   Anzeigen von Dokumenten mit der [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]\-Vieweranwendung.  
  
-   Ausgeben von Dokumenten im Ausgabeformat des systemeigenen Druckerspoolers in [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)].  
  
-   Direktes Routing von Dokumenten zu einem [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]\-kompatiblen Drucker.  
  
## Siehe auch  
 <xref:System.Windows.Documents.FixedDocument>   
 <xref:System.Windows.Documents.FlowDocument>   
 <xref:System.Windows.Xps.Packaging.XpsDocument>   
 <xref:System.IO.Packaging.ZipPackage>   
 <xref:System.IO.Packaging.ZipPackagePart>   
 <xref:System.IO.Packaging.PackageRelationship>   
 <xref:System.Windows.Controls.DocumentViewer>   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md)   
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [Serialisierung und Speicherung von Dokumenten](../../../../docs/framework/wpf/advanced/document-serialization-and-storage.md)