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
ms.openlocfilehash: 36704d56b66de977ac7f63fd7e766c925ef9023b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974685"
---
# <a name="documents-in-wpf"></a>Dokumente in WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet eine Vielzahl von Dokument Funktionen, die die Erstellung von hochwertigen Inhalten ermöglichen, auf die einfacher zugegriffen werden kann und die besser als in früheren Generationen von Windows gelesen werden konnten. Neben erweiterten Funktionen und verbesserter Qualität bietet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] auch integrierte Dienste für Dokumentanzeige, Packen und Sicherheit. Dieses Thema enthält eine Einführung zu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Dokumenttypen und dem Packen von Dokumenten.  

<a name="types_of_documents"></a>   
## <a name="types-of-documents"></a>Dokumenttypen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] teilt Dokumente hinsichtlich ihres Verwendungszwecks in zwei große Kategorien: „fixierte Dokumente“ und „Flussdokumente“.  
  
 Fixierte Dokumente sind für Anwendungen gedacht, die eine genaue Darstellung von "was Sie sehen, was Sie sehen" (WYSIWYG), unabhängig von der verwendeten Anzeige-oder Drucker Hardware erfordern. Typische Verwendungen für fixierte Dokumente sind Desktoppublishing, Textverarbeitung und Formularlayout, bei denen die Beibehaltung des ursprünglichen Seitenentwurfs sehr wichtig ist. Ein fixiertes Dokument behält die exakte Positionierung von Inhaltselementen als Teil seines Layouts bei, unabhängig davon, welches Anzeige- oder Druckgerät verwendet wird. Beispielsweise wird die Seite eines fixierten Dokuments auf einem 96-DPI-Anzeigegerät genau gleich angezeigt wie bei einem Laserdrucker mit 600-DPI-Auflösung oder in einem 4800-DPI-Fotosatz. Das Seitenlayout bleibt in allen Fällen gleich, während die Qualität des Dokuments entsprechend der Funktionen der einzelnen Geräte maximiert wird.  
  
 Flussdokumente sollen dagegen Anzeige und Lesbarkeit optimieren und werden daher bevorzugt verwendet, wenn das Hauptaugenmerk auf der Erleichterung des Lesens liegt. Statt auf ein vordefiniertes Layout festgelegt zu werden, passen Flussdokumente ihren Inhalt basierend auf Laufzeitvariablen dynamisch an Variablen wie Fenstergröße, Geräteauflösung und optionale Benutzereinstellungen an und brechen den Inhalt dynamisch um. Ein einfaches Beispiel für ein Flussdokument ist eine Webseite, bei der der Seiteninhalt dynamisch formatiert wird, um sich dem aktuellen Fenster anzupassen. Flussdokumente optimieren Anzeige und Lesbarkeit für den Benutzer basierend auf der Laufzeitumgebung. So wird im Sinne der optimalen Lesbarkeit z.B. dasselbe Flussdokument auf einem hochauflösenden 19-Zoll-Anzeigegerät anders dynamisch umformatiert als auf einem kleinen PDA-Bildschirm mit 2x3 Zoll. Zudem verfügen Flussdokumente über eine Vielzahl integrierter Funktionen, inklusive der Suche, Anzeigemodi zur Optimierung der Lesbarkeit und der Möglichkeit zum Ändern der Größe und Darstellung von Schriftarten.  Abbildungen, Beispiele und ausführliche Informationen zu Flussdokumenten finden Sie unter [Übersicht über Flussdokumente](flow-document-overview.md).  
  
<a name="document_viewer"></a>   
## <a name="document-controls-and-text-layout"></a>Dokumentsteuerelemente und Textlayout  
 Der .NET Framework stellt eine Reihe vorkonfigurierten Steuerelemente bereit, die die Verwendung fester Dokumente, Fluss Dokumente und allgemeinen Texts in der Anwendung vereinfachen.  Die Anzeige von festem Dokumentinhalt wird mithilfe des <xref:System.Windows.Controls.DocumentViewer>-Steuer Elements unterstützt.  Die Anzeige von Inhalt von Fluss Dokumenten wird von drei verschiedenen Steuerelementen unterstützt: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>und <xref:System.Windows.Controls.FlowDocumentScrollViewer>, die verschiedenen Benutzer Szenarien zugeordnet sind (siehe nachfolgende Abschnitte).  Weitere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente bieten ein vereinfachtes Layout zur Unterstützung von allgemeinem Text (siehe hierzu [Text in der Benutzeroberfläche](#text_in_the_user_interface) weiter unten).  
  
### <a name="fixed-document-control---documentviewer"></a>Steuerelement für fixierte Dokumente – DocumentViewer  
 Das <xref:System.Windows.Controls.DocumentViewer> Steuerelement ist so konzipiert, dass <xref:System.Windows.Documents.FixedDocument> Inhalt angezeigt wird. Das <xref:System.Windows.Controls.DocumentViewer>-Steuerelement stellt eine intuitive Benutzeroberfläche bereit, die integrierte Unterstützung für häufige Vorgänge bereitstellt, einschließlich Druckausgabe, in Zwischenablage kopieren, Zoom und Textsuchfunktionen. Das Steuerelement ermöglicht den Zugriff auf Seiteninhalte über einen vertrauten Bildlaufmechanismus. Wie alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente unterstützt <xref:System.Windows.Controls.DocumentViewer> vollständige oder partielle Neuformatierung, wodurch das Steuerelement visuell in praktisch jede Anwendung oder Umgebung integriert werden kann.  
  
 <xref:System.Windows.Controls.DocumentViewer> ist so konzipiert, dass Inhalte schreibgeschützt angezeigt werden. das Bearbeiten oder Ändern von Inhalten ist nicht verfügbar und wird nicht unterstützt.  
  
<a name="flow_document"></a>   
### <a name="flow-document-controls"></a>Steuerelemente für Flussdokumente  

> [!NOTE]
> Ausführlichere Informationen zu den Funktionen von Fluss Dokumenten und deren Erstellung finden Sie unter [Übersicht über Fluss Dokumente](flow-document-overview.md).  
  
 Die Anzeige von Inhalt von Fluss Dokumenten wird von drei Steuerelementen unterstützt: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>und <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
#### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> enthält Funktionen, die es dem Benutzer ermöglichen, dynamisch zwischen verschiedenen Anzeigemodi zu wählen, z. b. einem einseitigen Anzeigemodus (seitenweise), einem zwei-Seite-mal (Buch lese Format) und einem kontinuierlichen Bildlauf (in der untersten). Anzeigemodus.  Weitere Informationen zu diesen Anzeigemodi finden Sie unter <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  Wenn Sie nicht in der Lage sein müssen, dynamisch zwischen verschiedenen Anzeigemodi zu wechseln, können <xref:System.Windows.Controls.FlowDocumentPageViewer> und <xref:System.Windows.Controls.FlowDocumentScrollViewer> hellere fortlaufende Inhalts-Viewer bereitstellen, die in einem bestimmten Anzeigemodus korrigiert sind.  
  
#### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer und FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> zeigt den Inhalt im Seiten-zu-Uhrzeit-Anzeigemodus an, während <xref:System.Windows.Controls.FlowDocumentScrollViewer> den Inhalt im fortlaufenden Bild Lauf Modus anzeigt.  Sowohl <xref:System.Windows.Controls.FlowDocumentPageViewer> als auch <xref:System.Windows.Controls.FlowDocumentScrollViewer> werden in einem bestimmten Anzeigemodus korrigiert. Vergleichen Sie <xref:System.Windows.Controls.FlowDocumentReader>mit Features, die es dem Benutzer ermöglichen, sich dynamisch zwischen verschiedenen Anzeigemodi (wie von der <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>-Enumeration bereitgestellt) zu entscheiden. Dies ist kostengünstiger als <xref:System.Windows.Controls.FlowDocumentPageViewer> oder <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 Standardmäßig wird eine vertikale Scrollleiste immer angezeigt, und eine horizontale Scrollleiste wird bei Bedarf angezeigt. Der Standard [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für <xref:System.Windows.Controls.FlowDocumentScrollViewer> enthält keine Symbolleiste. die <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A>-Eigenschaft kann jedoch verwendet werden, um eine integrierte Symbolleiste zu aktivieren.  
  
<a name="text_in_the_user_interface"></a>   
### <a name="text-in-the-user-interface"></a>Text in der Benutzeroberfläche  
 Text kann nicht nur Dokumenten hinzugefügt werden, sondern wird auch in Benutzeroberflächen von Anwendungen, wie z.B. Formularen, verwendet. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält zahlreiche Steuerelemente für das Zeichnen von Text auf dem Bildschirm. Jedes Steuerelement dient einem anderen Szenario und verfügt über eine eigene Liste von Funktionen und Einschränkungen. Im Allgemeinen sollte das <xref:System.Windows.Controls.TextBlock>-Element verwendet werden, wenn eingeschränkte Textunterstützung erforderlich ist, z. b. ein kurzer Satz in einer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> kann verwendet werden, wenn nur minimale Textunterstützung erforderlich ist. Weitere Informationen finden Sie unter [Übersicht über TextBlock](../controls/textblock-overview.md).  
  
<a name="packaging"></a>   
## <a name="document-packaging"></a>Packen von Dokumenten  
 Die <xref:System.IO.Packaging>-APIs bieten eine effiziente Möglichkeit zum Organisieren von Anwendungsdaten, Dokument Inhalten und zugehörigen Ressourcen in einem einzelnen Container, der einfach zugänglich und portabel und leicht zu verteilen ist. Eine ZIP-Datei ist ein Beispiel für einen <xref:System.IO.Packaging.Package> Typ, der mehrere-Objekte als eine Einheit aufnehmen kann. Die Paket-APIs bieten eine standardmäßige <xref:System.IO.Packaging.ZipPackage> Implementierung, die mit einem Open Packaging Conventions-Standard mit XML-und ZIP-Datei Architektur entworfen wurde. Mit den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Paket-APIs können Sie problemlos Pakete erstellen und darin Objekte speichern und darauf zugreifen. Ein Objekt, das in einem <xref:System.IO.Packaging.Package> gespeichert wird, wird als <xref:System.IO.Packaging.PackagePart> ("Part") bezeichnet. Pakete können auch signierte digitale Zertifikate enthalten, mit denen der Ersteller eines Parts identifiziert und der Inhalt eines Pakets auf Änderungen überprüft werden kann.  Pakete enthalten außerdem ein <xref:System.IO.Packaging.PackageRelationship> Feature, das es ermöglicht, dass zusätzliche Informationen einem Paket hinzugefügt oder bestimmten Teilen zugeordnet werden, ohne den Inhalt vorhandener Teile tatsächlich zu ändern.  Paketdienste unterstützen auch Microsoft Windows Rights Management (RM).  
  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Paketarchitektur dient als Grundlage für eine Vielzahl von wichtigen Technologien:  
  
- XPS-Dokumente, die der XML Paper Specification (XPS) entsprechen.  
  
- Microsoft Office „12“-Dokumente im Open XML-Format (.docx)  
  
- Benutzerdefinierte Speicherformate für eigene Anwendungsentwürfe  
  
 Basierend auf den Paket-APIs ist ein-<xref:System.Windows.Xps.Packaging.XpsDocument> speziell für die Speicherung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fester Inhalts Dokumente konzipiert. Ein <xref:System.Windows.Xps.Packaging.XpsDocument> ist ein eigenständiges Dokument, das in einem Viewer geöffnet, in einem <xref:System.Windows.Controls.DocumentViewer>-Steuerelement angezeigt, an einen Druck Spoolvorgang weitergeleitet oder direkt an einen mit XPS kompatiblen Drucker ausgegeben werden kann.  
  
 Die folgenden Abschnitte enthalten zusätzliche Informationen zu den <xref:System.IO.Packaging.Package>-und <xref:System.Windows.Xps.Packaging.XpsDocument>-APIs, die mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bereitgestellt werden.  
  
<a name="packages"></a>   
### <a name="package-components"></a>Paketkomponenten  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-APIs zum Packen von Dokumenten ermöglichen die Organisation von Anwendungsdaten und Dokumenten in einer einzigen portablen Einheit. Die ZIP-Datei ist einer der am häufigsten verwendeten Pakettypen und stellt auch den Standardpakettyp in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dar.  <xref:System.IO.Packaging.Package> selbst ist eine abstrakte Klasse, von der <xref:System.IO.Packaging.ZipPackage> mithilfe einer offenen Standard-XML-und ZIP-Datei Architektur implementiert wird.  Die <xref:System.IO.Packaging.Package.Open%2A>-Methode verwendet <xref:System.IO.Packaging.ZipPackage>, um Zip-Dateien standardmäßig zu erstellen und zu verwenden. Ein Paket kann drei grundlegende Arten von Elementen enthalten:  
  
|||  
|-|-|  
|<xref:System.IO.Packaging.PackagePart>|Anwendungsinhalte, Daten, Dokumente und Ressourcendateien|  
|<xref:System.IO.Packaging.PackageDigitalSignature>|[X. 509-Zertifikat] zur Identifizierung, Authentifizierung und Validierung|  
|<xref:System.IO.Packaging.PackageRelationship>|Hinzugefügte Informationen zu dem Paket oder einem bestimmten Part|  
  
<a name="PackageParts"></a>   
#### <a name="packageparts"></a>PackageParts  
 Eine <xref:System.IO.Packaging.PackagePart> ("Part") ist eine abstrakte Klasse, die auf ein Objekt verweist, das in einem <xref:System.IO.Packaging.Package>gespeichert ist. In einer ZIP-Datei entsprechen die Parts den einzelnen in der ZIP-Datei gespeicherten Dateien.  <xref:System.IO.Packaging.ZipPackagePart> stellt die Standard Implementierung für serialisierbare Objekte bereit, die in einem <xref:System.IO.Packaging.ZipPackage>gespeichert sind.  Wie in einem Dateisystem werden die im Paket enthaltenen Parts als hierarchisches Verzeichnis oder als Ordnerstruktur gespeichert.  Mithilfe der APIs zum [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verpacken können Anwendungen mehrere <xref:System.IO.Packaging.PackagePart> Objekte mithilfe eines einzelnen ZIP-Datei Containers schreiben, speichern und lesen.  
  
<a name="PackageDigitalSignatures"></a>   
#### <a name="packagedigitalsignatures"></a>PackageDigitalSignatures  
 Aus Sicherheitsgründen kann eine <xref:System.IO.Packaging.PackageDigitalSignature> ("digitale Signatur") Teilen innerhalb eines Pakets zugeordnet werden. Ein <xref:System.IO.Packaging.PackageDigitalSignature> enthält einen [509], der zwei Funktionen bereitstellt:  
  
1. Identifizieren und Authentifizieren des Erstellers eines Parts  
  
2. Überprüfen des Parts auf Änderungen  
  
 Die digitale Signatur schließt eine Änderung des Parts nicht aus, doch schlägt eine Validierungsüberprüfung der digitalen Signatur bei jedweder Änderung des Parts fehl. Die Anwendung kann dann entsprechende Maßnahmen ergreifen, wie z.B. das Öffnen des Parts blockieren oder den Benutzer darüber benachrichtigen, dass der Part geändert wurde und nicht sicher ist.  
  
<a name="PackageRelationships"></a>   
#### <a name="packagerelationships"></a>PackageRelationships  
 Eine <xref:System.IO.Packaging.PackageRelationship> ("Beziehung") bietet einen Mechanismus zum Zuordnen zusätzlicher Informationen zum Paket oder zu einem Teil innerhalb des Pakets. Eine Beziehung ist eine Funktion auf Paketebene, die einem Part zusätzliche Informationen zuordnen kann, ohne den Inhalt des Parts selbst zu ändern. Das direkte Einfügen von neuen Daten in den Inhalt des Parts ist in den meisten Fällen nicht praktisch:  
  
- Der tatsächliche Typ des Parts und dessen Inhaltsschema sind nicht bekannt.  
  
- Selbst wenn sie bekannt sind, ermöglicht das Inhaltsschema nicht das Hinzufügen von neuen Informationen.  
  
- Der Part ist möglicherweise digital signiert oder verschlüsselt, was jede Änderung ausschließt.  
  
 Paketbeziehungen bieten eine sichtbare Möglichkeit zum Hinzufügen und Zuordnen von zusätzlichen Informationen zu einzelnen Parts oder dem gesamten Paket. Paketbeziehungen besitzen zwei Hauptaufgaben:  
  
1. Definieren von Abhängigkeitsbeziehungen zwischen einem Part und einem anderen  
  
2. Definieren von Informationsbeziehungen, durch die Hinweise oder andere Daten zum Part hinzugefügt werden  
  
 Eine <xref:System.IO.Packaging.PackageRelationship> bietet eine schnelle, erkennbare Möglichkeit zum Definieren von Abhängigkeiten und zum Hinzufügen weiterer Informationen, die einem Teil des Pakets oder dem Paket als Ganzes zugeordnet sind.  
  
<a name="Dependency_Relationships"></a>   
##### <a name="dependency-relationships"></a>Abhängigkeitsbeziehungen  
 Abhängigkeitsbeziehungen werden verwendet, um Abhängigkeiten zwischen einem Part und anderen Parts zu beschreiben. Ein Paket kann z.B. einen HTML-Part enthalten, der einen oder mehrere Bildtags <\<Img> einschließt. Die Bildtags verweisen auf Bilder, die sich als andere Parts innerhalb oder außerhalb des Pakets befinden (auf die z.B. über das Internet zugegriffen werden kann). Durch das Erstellen einer <xref:System.IO.Packaging.PackageRelationship>, die der HTML-Datei zugeordnet ist, werden die abhängigen Ressourcen schnell und einfach ermittelt und darauf zugegriffen Eine Browser- oder Vieweranwendung kann direkt auf die Beziehungen zwischen den Parts zugreifen und sofort die abhängigen Ressourcen zusammenstellen, ohne das Schema zu kennen oder das Dokument zu analysieren.  
  
<a name="Information_Relationships"></a>   
##### <a name="information-relationships"></a>Informationsbeziehungen  
 Ähnlich wie bei einem Hinweis oder einer Anmerkung kann ein <xref:System.IO.Packaging.PackageRelationship> auch verwendet werden, um andere Arten von Informationen zu speichern, die einem Teil zugeordnet werden sollen, ohne dass der Teil Inhalt tatsächlich geändert werden muss.  
  
<a name="XPS_Documents"></a>   
## <a name="xps-documents"></a>XPS-Dokumente  
 Das XML Paper Specification-Dokument (XPS) ist ein Paket, das ein oder mehrere fixierte Dokumente sowie alle für das Rendering erforderlichen Ressourcen und Informationen enthält.  XPS ist auch das Native Windows Vista-druckspooldateiformat.  Ein <xref:System.Windows.Xps.Packaging.XpsDocument> wird im ZIP-Standard Dataset gespeichert und kann eine Kombination aus XML-und Binär Komponenten enthalten, wie z. b. Bild-und Schriftart Dateien. [PackageRelationships](#PackageRelationships) werden zum Definieren der Abhängigkeiten zwischen Inhalt und Ressourcen verwendet, die zum vollständigen Rendern eines Dokuments erforderlich sind.  Der <xref:System.Windows.Xps.Packaging.XpsDocument> Entwurf bietet eine einzige, hochwertige Dokument Lösung, die mehrere Verwendungsmöglichkeiten unterstützt:  
  
- Lesen, Schreiben und Speichern der Inhalte und Ressourcen von fixierten Dokumenten als eine einzelne, portable und leicht zu verteilende Datei  
  
- Anzeigen von Dokumenten mit der XPS-Viewer-Anwendung.  
  
- Ausgabe von Dokumenten im nativen druckspoolausgabeformat von Windows Vista.  
  
- Direktes Weiterleiten von Dokumenten an einen XPS-kompatiblen Drucker.  
  
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
