---
title: Dokumente in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- documents [WPF], packaging
- documents [WPF], text layout
- documents [WPF], XPS
- 'XPS documents [WPF], , '
- documents [WPF], controls
- documents [WPF], types of
- documents [WPF], browser-viewable
ms.assetid: 6e8db7bc-050a-4070-aa72-bb8c46e87ff8
ms.openlocfilehash: b4057f54934fb5c7c9bb3d4fb97fe8e197e324ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051662"
---
# <a name="documents-in-wpf"></a>Dokumente in WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet eine große Auswahl an Dokumentfunktionen zum Erstellen von Inhalten mit hoher Wiedergabetreue, auf die im Vergleich zu früheren Generationen von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] leichter zugegriffen werden kann und die auch leichter zu lesen sind. Neben erweiterten Funktionen und verbesserter Qualität bietet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] auch integrierte Dienste für Dokumentanzeige, Packen und Sicherheit. Dieses Thema enthält eine Einführung zu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Dokumenttypen und dem Packen von Dokumenten.  

<a name="types_of_documents"></a>   
## <a name="types-of-documents"></a>Dokumenttypen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] teilt Dokumente hinsichtlich ihres Verwendungszwecks in zwei große Kategorien: „fixierte Dokumente“ und „Flussdokumente“.  
  
 Fixierte Dokumente werden für Anwendungen verwendet, die unabhängig von der verwendeten Anzeige- oder Druckerhardware eine genaue [!INCLUDE[TLA#tla_wys](../../../../includes/tlasharptla-wys-md.md)]-Darstellung erfordern. Typische Verwendungen für fixierte Dokumente sind Desktoppublishing, Textverarbeitung und Formularlayout, bei denen die Beibehaltung des ursprünglichen Seitenentwurfs sehr wichtig ist. Ein fixiertes Dokument behält die exakte Positionierung von Inhaltselementen als Teil seines Layouts bei, unabhängig davon, welches Anzeige- oder Druckgerät verwendet wird. Beispielsweise wird die Seite eines fixierten Dokuments auf einem 96-DPI-Anzeigegerät genau gleich angezeigt wie bei einem Laserdrucker mit 600-DPI-Auflösung oder in einem 4800-DPI-Fotosatz. Das Seitenlayout bleibt in allen Fällen gleich, während die Qualität des Dokuments entsprechend der Funktionen der einzelnen Geräte maximiert wird.  
  
 Flussdokumente sollen dagegen Anzeige und Lesbarkeit optimieren und werden daher bevorzugt verwendet, wenn das Hauptaugenmerk auf der Erleichterung des Lesens liegt. Flussdokumente sind nicht auf ein vordefiniertes Layout festgelegt, sondern passen ihren Inhalt auf Grundlage von Laufzeitvariablen wie Fenstergröße, Geräteauflösung und optionalen Benutzereinstellungen dynamisch an und brechen ihn dynamisch um. Ein einfaches Beispiel für ein Flussdokument ist eine Webseite, bei der der Seiteninhalt dynamisch formatiert wird, um sich dem aktuellen Fenster anzupassen. Flussdokumente optimieren Anzeige und Lesbarkeit für den Benutzer basierend auf der Laufzeitumgebung. So wird im Sinne der optimalen Lesbarkeit z.B. dasselbe Flussdokument auf einem hochauflösenden 19-Zoll-Anzeigegerät anders dynamisch umformatiert als auf einem kleinen PDA-Bildschirm mit 2x3 Zoll. Zudem besitzen Flussdokumente eine Vielzahl integrierter Funktionen, wie etwa Suche, Anzeigemodi zur Optimierung der Lesbarkeit sowie die Möglichkeit zum Ändern der Größe und der Darstellung von Schriftarten.  Abbildungen, Beispiele und ausführliche Informationen zu Flussdokumenten finden Sie unter [Übersicht über Flussdokumente](flow-document-overview.md).  
  
<a name="document_viewer"></a>   
## <a name="document-controls-and-text-layout"></a>Dokumentsteuerelemente und Textlayout  
 .NET Framework bietet eine Reihe von vorgefertigten Steuerelementen, die mithilfe von fixierten Dokumenten, Flussdokumenten und allgemeinen Text in Ihrer Anwendung zu vereinfachen.  Das Anzeigen des Inhalts von fixierten Dokuments wird unterstützt, mit der <xref:System.Windows.Controls.DocumentViewer> Steuerelement.  Anzeigen von Flussdokumentinhalten wird von drei unterschiedlichen Steuerelementen unterstützt: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, und <xref:System.Windows.Controls.FlowDocumentScrollViewer> zugeordnet sind verschiedene Szenarien (siehe unten).  Weitere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente bieten ein vereinfachtes Layout zur Unterstützung von allgemeinem Text (siehe hierzu [Text in der Benutzeroberfläche](#text_in_the_user_interface) weiter unten).  
  
### <a name="fixed-document-control---documentviewer"></a>Steuerelement für fixierte Dokumente – DocumentViewer  
 Die <xref:System.Windows.Controls.DocumentViewer> Steuerelement dient zur Anzeige <xref:System.Windows.Documents.FixedDocument> Inhalt. Die <xref:System.Windows.Controls.DocumentViewer> Steuerelement bietet eine intuitive Benutzeroberfläche, die integrierten Unterstützung allgemeiner Vorgänge, einschließlich der Druckausgabe, kopieren Sie in die Zwischenablage, Zoom und textsuchfunktionen bereitstellt. Das Steuerelement ermöglicht den Zugriff auf Seiteninhalte über einen vertrauten Bildlaufmechanismus. Wie alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente <xref:System.Windows.Controls.DocumentViewer> unterstützt vollständige oder teilweise Umformatierung, wodurch das Steuerelement visuell in nahezu jede Anwendung oder Umgebung integriert werden.  
  
 <xref:System.Windows.Controls.DocumentViewer> Dient zum Inhalt in einem schreibgeschützten Modus anzuzeigen. Bearbeiten und Ändern von Inhalt ist nicht verfügbar und wird nicht unterstützt.  
  
<a name="flow_document"></a>   
### <a name="flow-document-controls"></a>Steuerelemente für Flussdokumente  
 **Hinweis**: Ausführlichere Informationen zu den Features von und zu deren Erstellung finden Sie unter [Übersicht über Flussdokumente](flow-document-overview.md).  
  
 Anzeige von Flussdokumentinhalten wird von drei Steuerelemente unterstützt: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, und <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
#### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> enthält Features, mit die den Benutzer dynamisch zwischen verschiedenen Anzeigemodi, einschließlich einen Single-Page (Seite-an-a-Time)-Anzeigemodus, eine zwei-Seite-an-a-Time (Buch lesen Format) anzeigen, Modus und einen fortlaufenden Bildlaufmodus anzeigen (buchleseformat) von auswählen können.  Weitere Informationen zu diesen Anzeigemodi finden Sie unter <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  Wenn Sie nicht die Fähigkeit zum dynamischen Wechsel zwischen verschiedenen Anzeigemodi benötigen <xref:System.Windows.Controls.FlowDocumentPageViewer> und <xref:System.Windows.Controls.FlowDocumentScrollViewer> bieten schlankere Flow Content-Viewer, die in einem bestimmten Anzeigemodus behoben werden.  
  
#### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer und FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> Zeigt den Inhalt im Seite-an-a-Time Anzeigemodus, while <xref:System.Windows.Controls.FlowDocumentScrollViewer> zeigt den Inhalt im fortlaufenden Bildlaufmodus.  Beide <xref:System.Windows.Controls.FlowDocumentPageViewer> und <xref:System.Windows.Controls.FlowDocumentScrollViewer> wurden korrigiert, um einen bestimmten Anzeigemodus festgelegt. Vergleichen mit <xref:System.Windows.Controls.FlowDocumentReader>, darunter Features, die der Benutzer dynamisch zwischen verschiedenen Anzeigemodi wählen können (gemäß der <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> Enumeration), dabei jedoch weitere ressourcenintensiv als <xref:System.Windows.Controls.FlowDocumentPageViewer> oder <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 Eine vertikale Scrollleiste wird standardmäßig immer angezeigt, eine horizontale Scrollleiste nur nach Bedarf. Der Standardwert [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für <xref:System.Windows.Controls.FlowDocumentScrollViewer> enthält keine Symbolleiste, aber die <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> Eigenschaft kann verwendet werden, um eine integrierte Symbolleiste aktiviert.  
  
<a name="text_in_the_user_interface"></a>   
### <a name="text-in-the-user-interface"></a>Text in der Benutzeroberfläche  
 Text kann nicht nur Dokumenten hinzugefügt werden, sondern wird auch in Benutzeroberflächen von Anwendungen, wie z.B. Formularen, verwendet. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält zahlreiche Steuerelemente zum Zeichnen von Text auf dem Bildschirm. Jedes Steuerelement ist einem bestimmten Szenario zugeordnet und besitzt eine eigene Liste von Funktionen und Einschränkungen. Im Allgemeinen die <xref:System.Windows.Controls.TextBlock> Element sollte verwendet werden, wenn nur eingeschränkte Textelemente-Unterstützung erforderlich ist, z. B. einem kurzen Satz in einem [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> kann verwendet werden, wenn nur minimale textunterstützung erforderlich ist. Weitere Informationen finden Sie unter [Übersicht über TextBlock](../controls/textblock-overview.md).  
  
<a name="packaging"></a>   
## <a name="document-packaging"></a>Packen von Dokumenten  
 Die <xref:System.IO.Packaging> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] bieten eine effiziente Möglichkeit zum Organisieren von Anwendungsdaten, Dokumentinhalten und verwandten Ressourcen in einem einzelnen Container, die einfach zugegriffen werden, portable und leicht zu verteilen ist. Eine ZIP-Datei ist ein Beispiel für eine <xref:System.IO.Packaging.Package> Typ, der mehrere Objekte als einzelne Einheit. Das Verpacken [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] bieten den Standardwert <xref:System.IO.Packaging.ZipPackage> -Implementierung zur Verwendung einer Open Packaging Conventions-Standards mit XML- und ZIP-Dateiarchitektur. Mit den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] zum Packen von Dokumenten lassen sich leicht Pakete erstellen, in denen Objekte gespeichert werden und wieder leicht darauf zugegriffen werden kann. Ein Objekt, gespeichert einer <xref:System.IO.Packaging.Package> wird als bezeichnet eine <xref:System.IO.Packaging.PackagePart> ("Part"). Pakete können auch signierte digitale Zertifikate enthalten, mit denen der Ersteller eines Parts identifiziert und der Inhalt eines Pakets auf Änderungen überprüft werden kann.  Pakete enthalten außerdem eine <xref:System.IO.Packaging.PackageRelationship> -Feature, das zusätzliche Informationen zu einem Paket hinzugefügt werden, oder bestimmte Teile zugeordnet sind, ohne den Inhalt vorhandener Parts ändern zu kann.  Paketdienste unterstützen außerdem [!INCLUDE[TLA#tla_rm](../../../../includes/tlasharptla-rm-md.md)].  
  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Paketarchitektur dient als Grundlage für eine Vielzahl von wichtigen Technologien:  
  
- [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-Dokumente, die [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] entsprechen  
  
- Microsoft Office „12“-Dokumente im Open XML-Format (.docx)  
  
- Benutzerdefinierte Speicherformate für eigene Anwendungsentwürfe  
  
 Basierend auf die Paket-APIs, einer <xref:System.Windows.Xps.Packaging.XpsDocument> wurde speziell für die Speicherung von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Content Dokumente behoben. Ein <xref:System.Windows.Xps.Packaging.XpsDocument> ist ein eigenständiges Dokument, die in einem Viewer, angezeigt geöffnet werden, kann eine <xref:System.Windows.Controls.DocumentViewer> -Steuerelement, an einen Druckerspooler weitergeleitet oder Ausgabe direkt an ein [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]--kompatiblen Drucker.  
  
 Die folgenden Abschnitte enthalten zusätzliche Informationen für die <xref:System.IO.Packaging.Package> und <xref:System.Windows.Xps.Packaging.XpsDocument> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] mit bereitgestellten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="packages"></a>   
### <a name="package-components"></a>Paketkomponenten  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-APIs zum Packen von Dokumenten ermöglichen die Organisation von Anwendungsdaten und Dokumenten in einer einzigen portablen Einheit. Die ZIP-Datei ist einer der am häufigsten verwendeten Pakettypen und stellt auch den Standardpakettyp in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dar.  <xref:System.IO.Packaging.Package> selbst ist eine abstrakte Klasse, von dem <xref:System.IO.Packaging.ZipPackage> wird mithilfe einer offenen standard XML- und ZIP-Dateiarchitektur implementiert.  Die <xref:System.IO.Packaging.Package.Open%2A> -Methode verwendet <xref:System.IO.Packaging.ZipPackage> erstellen und Verwenden von ZIP-Dateien standardmäßig. Ein Paket kann drei grundlegende Arten von Elementen enthalten:  
  
|||  
|-|-|  
|<xref:System.IO.Packaging.PackagePart>|Anwendungsinhalte, Daten, Dokumente und Ressourcendateien|  
|<xref:System.IO.Packaging.PackageDigitalSignature>|[X. 509-Zertifikat] zur Identifizierung, Authentifizierung und Validierung|  
|<xref:System.IO.Packaging.PackageRelationship>|Hinzugefügte Informationen zu dem Paket oder einem bestimmten Part|  
  
<a name="PackageParts"></a>   
#### <a name="packageparts"></a>PackageParts  
 Ein <xref:System.IO.Packaging.PackagePart> ("Part") ist eine abstrakte Klasse, die auf ein in gespeichertes Objekt verweist eine <xref:System.IO.Packaging.Package>. In einer ZIP-Datei entsprechen die Parts den einzelnen in der ZIP-Datei gespeicherten Dateien.  <xref:System.IO.Packaging.ZipPackagePart> Stellt die Standardimplementierung für serialisierbare Objekte, die in gespeicherten eine <xref:System.IO.Packaging.ZipPackage>.  Wie in einem Dateisystem werden die im Paket enthaltenen Parts als hierarchisches Verzeichnis oder als Ordnerstruktur gespeichert.  Mithilfe der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -APIs zum Packen, Anwendungen, zu speichern, lesen und schreiben können mehrere <xref:System.IO.Packaging.PackagePart> -Objekte mit einem einzelnen Container der ZIP-Datei.  
  
<a name="PackageDigitalSignatures"></a>   
#### <a name="packagedigitalsignatures"></a>PackageDigitalSignatures  
 Aus Sicherheitsgründen eine <xref:System.IO.Packaging.PackageDigitalSignature> ("digitale Signatur") kann in der Teile in einem Paket zugeordnet werden. Ein <xref:System.IO.Packaging.PackageDigitalSignature> beinhaltet ein [509], die stellt zwei Funktionen bereit:  
  
1. Identifizieren und Authentifizieren des Erstellers eines Parts  
  
2. Überprüfen des Parts auf Änderungen  
  
 Die digitale Signatur schließt eine Änderung des Parts nicht aus, doch schlägt eine Validierungsüberprüfung der digitalen Signatur bei jedweder Änderung des Parts fehl. Die Anwendung kann dann entsprechende Maßnahmen ergreifen, wie z.B. das Öffnen des Parts blockieren oder den Benutzer darüber benachrichtigen, dass der Part geändert wurde und nicht sicher ist.  
  
<a name="PackageRelationships"></a>   
#### <a name="packagerelationships"></a>PackageRelationships  
 Ein <xref:System.IO.Packaging.PackageRelationship> ("Beziehung") bietet einen Mechanismus zum Zuordnen von zusätzlichen Informationen zum Paket oder ein Teil im Paket. Eine Beziehung ist eine Funktion auf Paketebene, die einem Part zusätzliche Informationen zuordnen kann, ohne den Inhalt des Parts selbst zu ändern. Das direkte Einfügen von neuen Daten in den Inhalt des Parts ist in den meisten Fällen nicht praktisch:  
  
- Der tatsächliche Typ des Parts und dessen Inhaltsschema sind nicht bekannt.  
  
- Selbst wenn sie bekannt sind, ermöglicht das Inhaltsschema nicht das Hinzufügen von neuen Informationen.  
  
- Der Part ist möglicherweise digital signiert oder verschlüsselt, was jede Änderung ausschließt.  
  
 Paketbeziehungen bieten eine sichtbare Möglichkeit zum Hinzufügen und Zuordnen von zusätzlichen Informationen zu einzelnen Parts oder dem gesamten Paket. Paketbeziehungen besitzen zwei Hauptaufgaben:  
  
1. Definieren von Abhängigkeitsbeziehungen zwischen einem Part und einem anderen  
  
2. Definieren von Informationsbeziehungen, durch die Hinweise oder andere Daten zum Part hinzugefügt werden  
  
 Ein <xref:System.IO.Packaging.PackageRelationship> bietet eine schnelle und sichtbare Möglichkeit zum Definieren der Abhängigkeiten und Hinzufügen von weiteren Informationen, die einem Part des Pakets oder das Paket als Ganzes.  
  
<a name="Dependency_Relationships"></a>   
##### <a name="dependency-relationships"></a>Abhängigkeitsbeziehungen  
 Abhängigkeitsbeziehungen werden verwendet, um Abhängigkeiten zwischen einem Part und anderen Parts zu beschreiben. Ein Paket kann z.B. einen HTML-Part enthalten, der einen oder mehrere Bildtags <\<Img> einschließt. Die Bildtags verweisen auf Bilder, die sich als andere Parts innerhalb oder außerhalb des Pakets befinden (auf die z.B. über das Internet zugegriffen werden kann). Erstellen einer <xref:System.IO.Packaging.PackageRelationship> zugeordneten HTML-Datei können ermitteln und den Zugriff auf den abhängigen Ressourcen schnell und einfach. Eine Browser- oder Vieweranwendung kann direkt auf die Beziehungen zwischen den Parts zugreifen und sofort die abhängigen Ressourcen zusammenstellen, ohne das Schema zu kennen oder das Dokument zu analysieren.  
  
<a name="Information_Relationships"></a>   
##### <a name="information-relationships"></a>Informationsbeziehungen  
 Bei einem Hinweis oder die Anmerkung, ähnlich wie eine <xref:System.IO.Packaging.PackageRelationship> kann auch verwendet werden, um andere Arten von Informationen zu einem Teil zugeordnet werden, ohne tatsächlich den Inhalt des Parts selbst ändern zu speichern.  
  
<a name="XPS_Documents"></a>   
## <a name="xps-documents"></a>XPS-Dokumente  
 Ein [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]-Dokument ist ein Paket mit einem oder mehreren fixierten Dokumenten sowie allen zum Rendern notwendigen Ressourcen und Informationen.  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] ist außerdem das native [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)]-Druckerspooler-Dateiformat.  Ein <xref:System.Windows.Xps.Packaging.XpsDocument> ist im standard-ZIP-Dataset gespeichert und kann eine Kombination aus XML- und binären Komponenten, z. B. Bild-und Schriftartdateien enthalten. [PackageRelationships](#PackageRelationships) werden zum Definieren der Abhängigkeiten zwischen Inhalt und Ressourcen verwendet, die zum vollständigen Rendern eines Dokuments erforderlich sind.  Die <xref:System.Windows.Xps.Packaging.XpsDocument> Entwurf bietet eine einzelne, High-Fidelity-Document-Projektmappe, die zahlreiche Verwendungen unterstützt:  
  
- Lesen, Schreiben und Speichern der Inhalte und Ressourcen von fixierten Dokumenten als eine einzelne, portable und leicht zu verteilende Datei  
  
- Anzeigen von Dokumenten mit der [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-Vieweranwendung  
  
- Ausgeben von Dokumenten im nativen Druckerspooler-Ausgabeformat von [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)]  
  
- Direktes Weiterleiten von Dokumenten an einen [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-kompatiblen Drucker  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Documents.FixedDocument>
- <xref:System.Windows.Documents.FlowDocument>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.IO.Packaging.ZipPackage>
- <xref:System.IO.Packaging.ZipPackagePart>
- <xref:System.IO.Packaging.PackageRelationship>
- <xref:System.Windows.Controls.DocumentViewer>
- [Text](optimizing-performance-text.md)
- [Übersicht über Flussdokumente](flow-document-overview.md)
- [Übersicht über das Drucken](printing-overview.md)
- [Serialisierung und Speicherung von Dokumenten](document-serialization-and-storage.md)
