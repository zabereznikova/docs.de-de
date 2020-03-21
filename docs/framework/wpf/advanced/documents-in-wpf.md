---
title: Dokumente
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
ms.openlocfilehash: e88604c42b253b48ee605f42f24fe301e339f74b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174679"
---
# <a name="documents-in-wpf"></a>Dokumente in WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]bietet eine breite Palette von Dokumentfunktionen, die die Erstellung von High-Fidelity-Inhalten ermöglichen, die einfacher zugänglich und gelesen werden können als in früheren Windows-Generationen. Neben erweiterten Funktionen und verbesserter Qualität bietet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] auch integrierte Dienste für Dokumentanzeige, Packen und Sicherheit. Dieses Thema enthält eine Einführung zu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Dokumenttypen und dem Packen von Dokumenten.  

<a name="types_of_documents"></a>
## <a name="types-of-documents"></a>Dokumenttypen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] teilt Dokumente hinsichtlich ihres Verwendungszwecks in zwei große Kategorien: „fixierte Dokumente“ und „Flussdokumente“.  
  
 Feste Dokumente sind für Anwendungen gedacht, die eine präzise "Was Sie sehen, was Sie erhalten" (WYSIWYG) Präsentation erfordern, unabhängig von der verwendeten Display- oder Druckerhardware. Typische Verwendungen für fixierte Dokumente sind Desktoppublishing, Textverarbeitung und Formularlayout, bei denen die Beibehaltung des ursprünglichen Seitenentwurfs sehr wichtig ist. Ein fixiertes Dokument behält die exakte Positionierung von Inhaltselementen als Teil seines Layouts bei, unabhängig davon, welches Anzeige- oder Druckgerät verwendet wird. Beispielsweise wird die Seite eines fixierten Dokuments auf einem 96-DPI-Anzeigegerät genau gleich angezeigt wie bei einem Laserdrucker mit 600-DPI-Auflösung oder in einem 4800-DPI-Fotosatz. Das Seitenlayout bleibt in allen Fällen gleich, während die Qualität des Dokuments entsprechend der Funktionen der einzelnen Geräte maximiert wird.  
  
 Flussdokumente sollen dagegen Anzeige und Lesbarkeit optimieren und werden daher bevorzugt verwendet, wenn das Hauptaugenmerk auf der Erleichterung des Lesens liegt. Flussdokumente sind nicht auf ein vordefiniertes Layout festgelegt, sondern passen ihren Inhalt auf Grundlage von Laufzeitvariablen wie Fenstergröße, Geräteauflösung und optionalen Benutzereinstellungen dynamisch an und brechen ihn dynamisch um. Ein einfaches Beispiel für ein Flussdokument ist eine Webseite, bei der der Seiteninhalt dynamisch formatiert wird, um sich dem aktuellen Fenster anzupassen. Flussdokumente optimieren Anzeige und Lesbarkeit für den Benutzer basierend auf der Laufzeitumgebung. So wird im Sinne der optimalen Lesbarkeit z.B. dasselbe Flussdokument auf einem hochauflösenden 19-Zoll-Anzeigegerät anders dynamisch umformatiert als auf einem kleinen PDA-Bildschirm mit 2x3 Zoll. Zudem verfügen Flussdokumente über eine Vielzahl integrierter Funktionen, inklusive der Suche, Anzeigemodi zur Optimierung der Lesbarkeit und der Möglichkeit zum Ändern der Größe und Darstellung von Schriftarten.  Abbildungen, Beispiele und ausführliche Informationen zu Flussdokumenten finden Sie unter [Übersicht über Flussdokumente](flow-document-overview.md).  
  
<a name="document_viewer"></a>
## <a name="document-controls-and-text-layout"></a>Dokumentsteuerelemente und Textlayout  
 .NET Framework bietet eine Reihe vorgefertigter Steuerelemente, die die Verwendung fester Dokumente, Flussdokumente und allgemeinen Textinteilen in Ihrer Anwendung vereinfachen.  Die Anzeige von Fixed Document <xref:System.Windows.Controls.DocumentViewer> Content wird über das Steuerelement unterstützt.  Die Anzeige von Flow document-Inhalten <xref:System.Windows.Controls.FlowDocumentReader>wird <xref:System.Windows.Controls.FlowDocumentPageViewer>durch <xref:System.Windows.Controls.FlowDocumentScrollViewer> drei verschiedene Steuerelemente unterstützt: , und welche Zuordnung zu verschiedenen Benutzerszenarien (siehe Abschnitte unten).  Weitere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente bieten ein vereinfachtes Layout zur Unterstützung von allgemeinem Text (siehe hierzu [Text in der Benutzeroberfläche](#text_in_the_user_interface) weiter unten).  
  
### <a name="fixed-document-control---documentviewer"></a>Steuerelement für fixierte Dokumente – DocumentViewer  
 Das <xref:System.Windows.Controls.DocumentViewer> Steuerelement ist <xref:System.Windows.Documents.FixedDocument> so konzipiert, dass Inhalte angezeigt werden. Das <xref:System.Windows.Controls.DocumentViewer> Steuerelement bietet eine intuitive Benutzeroberfläche, die integrierte Unterstützung für allgemeine Vorgänge wie Druckausgabe, Kopie in Zwischenablage, Zoom und Textsuchfunktionen bietet. Das Steuerelement ermöglicht den Zugriff auf Seiteninhalte über einen vertrauten Bildlaufmechanismus. Unterstützt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wie <xref:System.Windows.Controls.DocumentViewer> alle Steuerelemente ein komplettes oder teilweises Restyling, wodurch das Steuerelement visuell in praktisch jede Anwendung oder Umgebung integriert werden kann.  
  
 <xref:System.Windows.Controls.DocumentViewer>wurde entwickelt, um Inhalte schreibgeschützt anzuzeigen; Das Bearbeiten oder Ändern von Inhalten ist nicht verfügbar und wird nicht unterstützt.  
  
<a name="flow_document"></a>
### <a name="flow-document-controls"></a>Steuerelemente für Flussdokumente  

> [!NOTE]
> Ausführlichere Informationen zu Flow Document-Features und deren Erstellung finden Sie unter [Flussdokumentübersicht](flow-document-overview.md).  
  
 Die Anzeige des Flowdocument-Inhalts <xref:System.Windows.Controls.FlowDocumentReader>wird <xref:System.Windows.Controls.FlowDocumentPageViewer>durch <xref:System.Windows.Controls.FlowDocumentScrollViewer>drei Steuerelemente unterstützt: , , und .  
  
#### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader>enthält Funktionen, die es dem Benutzer ermöglichen, dynamisch zwischen verschiedenen Anzeigemodi zu wählen, einschließlich eines einseitigen (Seiten-zu-einer-Zeit-)Anzeigemodus, eines zweiseitigen Anzeigemodus (Buchleseformat) und eines kontinuierlichen Bildlaufs (unten ohne) Anzeigemodus.  Weitere Informationen zu diesen Anzeigemodi <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>finden Sie unter .  Wenn Sie nicht die Möglichkeit benötigen, dynamisch zwischen <xref:System.Windows.Controls.FlowDocumentPageViewer> <xref:System.Windows.Controls.FlowDocumentScrollViewer> verschiedenen Anzeigemodi zu wechseln und anzeiger für mit leichteren Flow-Inhalten zu versorgen, die in einem bestimmten Anzeigemodus festgelegt sind.  
  
#### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer und FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer>zeigt Inhalte im Page-at-a-Time-Anzeigemodus an, während <xref:System.Windows.Controls.FlowDocumentScrollViewer> Inhalte im kontinuierlichen Bildlaufmodus angezeigt werden.  Beide <xref:System.Windows.Controls.FlowDocumentPageViewer> <xref:System.Windows.Controls.FlowDocumentScrollViewer> und sind an einen bestimmten Anzeigemodus fixiert. Vergleichen <xref:System.Windows.Controls.FlowDocumentReader>Sie mit , einschließlich Features, die es dem Benutzer ermöglichen, <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> dynamisch zwischen verschiedenen Anzeigemodi (wie in <xref:System.Windows.Controls.FlowDocumentPageViewer> <xref:System.Windows.Controls.FlowDocumentScrollViewer>der Enumeration bereitgestellt) zu wählen, und das auf Kosten, dass er ressourcenintensiver ist als oder .  
  
 Standardmäßig wird eine vertikale Scrollleiste immer angezeigt, und eine horizontale Scrollleiste wird bei Bedarf angezeigt. Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Standardeinstellung für <xref:System.Windows.Controls.FlowDocumentScrollViewer> enthält keine Symbolleiste. Die <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> Eigenschaft kann jedoch verwendet werden, um eine integrierte Symbolleiste zu aktivieren.  
  
<a name="text_in_the_user_interface"></a>
### <a name="text-in-the-user-interface"></a>Text in der Benutzeroberfläche  
 Text kann nicht nur Dokumenten hinzugefügt werden, sondern wird auch in Benutzeroberflächen von Anwendungen, wie z.B. Formularen, verwendet. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält zahlreiche Steuerelemente zum Zeichnen von Text auf dem Bildschirm. Jedes Steuerelement ist einem bestimmten Szenario zugeordnet und besitzt eine eigene Liste von Funktionen und Einschränkungen. Im Allgemeinen <xref:System.Windows.Controls.TextBlock> sollte das Element verwendet werden, wenn eine eingeschränkte [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]Textunterstützung erforderlich ist, z. B. ein kurzer Satz in einem . <xref:System.Windows.Controls.Label>kann verwendet werden, wenn minimale Textunterstützung erforderlich ist. Weitere Informationen finden Sie unter [Übersicht über TextBlock](../controls/textblock-overview.md).  
  
<a name="packaging"></a>
## <a name="document-packaging"></a>Packen von Dokumenten  
 Die <xref:System.IO.Packaging> APIs bieten eine effiziente Möglichkeit, Anwendungsdaten, Dokumentinhalte und zugehörige Ressourcen in einem einzigen Container zu organisieren, der einfach zugänglich, portabel und einfach zu verteilen ist. Eine ZIP-Datei ist <xref:System.IO.Packaging.Package> ein Beispiel für einen Typ, der mehrere Objekte als eine Einheit speichern kann. Die Verpackungs-APIs <xref:System.IO.Packaging.ZipPackage> bieten eine Standardimplementierung, die mit einem Open Packaging Conventions-Standard mit XML- und ZIP-Dateiarchitektur entwickelt wurde. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Verpackungs-APIs machen es einfach, Pakete zu erstellen und objekte darin zu speichern und darauf zuzugreifen. Ein in einem <xref:System.IO.Packaging.Package> gespeichertes Objekt <xref:System.IO.Packaging.PackagePart> wird als "Teil" bezeichnet. Pakete können auch signierte digitale Zertifikate enthalten, mit denen der Ersteller eines Parts identifiziert und der Inhalt eines Pakets auf Änderungen überprüft werden kann.  Pakete enthalten <xref:System.IO.Packaging.PackageRelationship> auch eine Funktion, mit der zusätzliche Informationen zu einem Paket hinzugefügt oder bestimmten Teilen zugeordnet werden können, ohne den Inhalt vorhandener Teile tatsächlich zu ändern.  Paketdienste unterstützen auch Microsoft Windows Rights Management (RM).  
  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Paketarchitektur dient als Grundlage für eine Vielzahl von wichtigen Technologien:  
  
- XPS-Dokumente, die der XML Paper Specification (XPS) entsprechen.  
  
- Microsoft Office „12“-Dokumente im Open XML-Format (.docx)  
  
- Benutzerdefinierte Speicherformate für eigene Anwendungsentwürfe  
  
 Basierend auf den Verpackungs-APIs wurde <xref:System.Windows.Xps.Packaging.XpsDocument> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine speziell für die Speicherung von Fixed Content-Dokumenten entwickelt. Ein <xref:System.Windows.Xps.Packaging.XpsDocument> eigenständiges Dokument, das in einem Viewer geöffnet, <xref:System.Windows.Controls.DocumentViewer> in einem Steuerelement angezeigt, an eine Druckspule weitergeleitet oder direkt an einen XPS-kompatiblen Drucker ausgegeben werden kann.  
  
 Die folgenden Abschnitte enthalten zusätzliche <xref:System.IO.Packaging.Package> <xref:System.Windows.Xps.Packaging.XpsDocument> Informationen zu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]den und APIs, die mit bereitgestellt werden.  
  
<a name="packages"></a>
### <a name="package-components"></a>Paketkomponenten  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-APIs zum Packen von Dokumenten ermöglichen die Organisation von Anwendungsdaten und Dokumenten in einer einzigen portablen Einheit. Die ZIP-Datei ist einer der am häufigsten verwendeten Pakettypen und stellt auch den Standardpakettyp in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dar.  <xref:System.IO.Packaging.Package>selbst ist eine abstrakte <xref:System.IO.Packaging.ZipPackage> Klasse, von der aus eine offene XML- und ZIP-Standarddateiarchitektur implementiert wird.  Die <xref:System.IO.Packaging.Package.Open%2A> Methode <xref:System.IO.Packaging.ZipPackage> verwendet, um ZIP-Dateien standardmäßig zu erstellen und zu verwenden. Ein Paket kann drei grundlegende Arten von Elementen enthalten:  
  
|||  
|-|-|  
|<xref:System.IO.Packaging.PackagePart>|Anwendungsinhalte, Daten, Dokumente und Ressourcendateien|  
|<xref:System.IO.Packaging.PackageDigitalSignature>|[X. 509-Zertifikat] zur Identifizierung, Authentifizierung und Validierung|  
|<xref:System.IO.Packaging.PackageRelationship>|Hinzugefügte Informationen zu dem Paket oder einem bestimmten Part|  
  
<a name="PackageParts"></a>
#### <a name="packageparts"></a>PackageParts  
 A <xref:System.IO.Packaging.PackagePart> ("part") ist eine abstrakte Klasse, die <xref:System.IO.Packaging.Package>auf ein Objekt verweist, das in einem gespeichert ist. In einer ZIP-Datei entsprechen die Parts den einzelnen in der ZIP-Datei gespeicherten Dateien.  <xref:System.IO.Packaging.ZipPackagePart>stellt die Standardimplementierung für serialisierbare Objekte bereit, die in einer <xref:System.IO.Packaging.ZipPackage>gespeichert sind.  Wie in einem Dateisystem werden die im Paket enthaltenen Parts als hierarchisches Verzeichnis oder als Ordnerstruktur gespeichert.  Mithilfe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] der Paket-APIs können Anwendungen mehrere <xref:System.IO.Packaging.PackagePart> Objekte mithilfe eines einzelnen ZIP-Dateicontainers schreiben, speichern und lesen.  
  
<a name="PackageDigitalSignatures"></a>
#### <a name="packagedigitalsignatures"></a>PackageDigitalSignatures  
 Aus Sicherheitsgründen <xref:System.IO.Packaging.PackageDigitalSignature> kann eine ("digitale Signatur") Mit Teilen innerhalb eines Pakets verknüpft werden. A <xref:System.IO.Packaging.PackageDigitalSignature> enthält eine [509], die zwei Funktionen bietet:  
  
1. Identifizieren und Authentifizieren des Erstellers eines Parts  
  
2. Überprüfen des Parts auf Änderungen  
  
 Die digitale Signatur schließt eine Änderung des Parts nicht aus, doch schlägt eine Validierungsüberprüfung der digitalen Signatur bei jedweder Änderung des Parts fehl. Die Anwendung kann dann entsprechende Maßnahmen ergreifen, wie z.B. das Öffnen des Parts blockieren oder den Benutzer darüber benachrichtigen, dass der Part geändert wurde und nicht sicher ist.  
  
<a name="PackageRelationships"></a>
#### <a name="packagerelationships"></a>PackageRelationships  
 A <xref:System.IO.Packaging.PackageRelationship> ("Beziehung") bietet einen Mechanismus zum Zuordnen zusätzlicher Informationen zum Paket oder einem Teil innerhalb des Pakets. Eine Beziehung ist eine Funktion auf Paketebene, die einem Part zusätzliche Informationen zuordnen kann, ohne den Inhalt des Parts selbst zu ändern. Das direkte Einfügen von neuen Daten in den Inhalt des Parts ist in den meisten Fällen nicht praktisch:  
  
- Der tatsächliche Typ des Parts und dessen Inhaltsschema sind nicht bekannt.  
  
- Selbst wenn sie bekannt sind, ermöglicht das Inhaltsschema nicht das Hinzufügen von neuen Informationen.  
  
- Der Part ist möglicherweise digital signiert oder verschlüsselt, was jede Änderung ausschließt.  
  
 Paketbeziehungen bieten eine sichtbare Möglichkeit zum Hinzufügen und Zuordnen von zusätzlichen Informationen zu einzelnen Parts oder dem gesamten Paket. Paketbeziehungen besitzen zwei Hauptaufgaben:  
  
1. Definieren von Abhängigkeitsbeziehungen zwischen einem Part und einem anderen  
  
2. Definieren von Informationsbeziehungen, durch die Hinweise oder andere Daten zum Part hinzugefügt werden  
  
 A <xref:System.IO.Packaging.PackageRelationship> bietet eine schnelle, auffindbare Möglichkeit, Abhängigkeiten zu definieren und weitere Informationen hinzuzufügen, die einem Teil des Pakets oder dem Paket als Ganzes zugeordnet sind.  
  
<a name="Dependency_Relationships"></a>
##### <a name="dependency-relationships"></a>Abhängigkeitsbeziehungen  
 Abhängigkeitsbeziehungen werden verwendet, um Abhängigkeiten zwischen einem Part und anderen Parts zu beschreiben. Ein Paket kann z.B. einen HTML-Part enthalten, der einen oder mehrere Bildtags <\<Img> einschließt. Die Bildtags verweisen auf Bilder, die sich als andere Parts innerhalb oder außerhalb des Pakets befinden (auf die z.B. über das Internet zugegriffen werden kann). Das <xref:System.IO.Packaging.PackageRelationship> Erstellen einer HTML-Datei ermöglicht das schnelle und einfache Erkennen und Zugreifen auf die abhängigen Ressourcen. Eine Browser- oder Vieweranwendung kann direkt auf die Beziehungen zwischen den Parts zugreifen und sofort die abhängigen Ressourcen zusammenstellen, ohne das Schema zu kennen oder das Dokument zu analysieren.  
  
<a name="Information_Relationships"></a>
##### <a name="information-relationships"></a>Informationsbeziehungen  
 Ähnlich wie bei einer Notiz <xref:System.IO.Packaging.PackageRelationship> oder Anmerkung kann a auch verwendet werden, um andere Arten von Informationen zu speichern, die einem Teil zugeordnet werden sollen, ohne den Teileinhalt selbst ändern zu müssen.  
  
<a name="XPS_Documents"></a>
## <a name="xps-documents"></a>XPS-Dokumente  
 XML Paper Specification (XPS)-Dokument ist ein Paket, das ein oder mehrere feste Dokumente zusammen mit allen Ressourcen und Informationen enthält, die zum Rendern erforderlich sind.  XPS ist auch das native Windows Vista-Druckspooldateiformat.  Ein <xref:System.Windows.Xps.Packaging.XpsDocument> wird im Standard-ZIP-Dataset gespeichert und kann eine Kombination aus XML- und Binärkomponenten wie Bild- und Schriftartdateien enthalten. [PackageRelationships](#PackageRelationships) werden zum Definieren der Abhängigkeiten zwischen Inhalt und Ressourcen verwendet, die zum vollständigen Rendern eines Dokuments erforderlich sind.  Der <xref:System.Windows.Xps.Packaging.XpsDocument> Entwurf bietet eine einzige Dokumentlösung mit hoher Genauigkeit, die mehrere Anwendungen unterstützt:  
  
- Lesen, Schreiben und Speichern der Inhalte und Ressourcen von fixierten Dokumenten als eine einzelne, portable und leicht zu verteilende Datei  
  
- Anzeigen von Dokumenten mit der XPS Viewer-Anwendung.  
  
- Ausgabe von Dokumenten im nativen Druckspoolausgabeformat von Windows Vista.  
  
- Weiterleiten von Dokumenten direkt an einen XPS-kompatiblen Drucker.  
  
## <a name="see-also"></a>Weitere Informationen

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
