---
title: LINQ to XML-Sicherheit
ms.date: 07/20/2015
ms.assetid: d99b4af2-d447-4a3b-991b-6da0231a8637
ms.openlocfilehash: 01b03dc5792981d41d16cc7b551892bd6fe2bcde
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331741"
---
# <a name="linq-to-xml-security-visual-basic"></a>LINQ to XML Sicherheit (Visual Basic)
In diesem Thema werden Sicherheitsfragen im Zusammenhang mit LINQ to XML erörtert. Darüber hinaus bietet es Anleitungen zum Minimieren von Sicherheitsrisiken.  
  
## <a name="linq-to-xml-security-overview"></a>Übersicht über die Sicherheit in LINQ to XML  
 Bei der Entwicklung von LINQ to XML standen nicht die serverseitigen Anwendungen mit strengen Sicherheitsanforderungen, sondern eher das bequeme Programmieren im Vordergrund. Die meisten XML-Szenarios beinhalten die Verarbeitung vertrauenswürdiger XML-Dokumente und nicht die Verarbeitung nicht vertrauenswürdiger XML-Dokumente, die auf einen Server hochgeladen werden. Genau für diese Szenarios ist LINQ to XML optimiert.  
  
 Wenn Sie nicht vertrauenswürdige Daten aus unbekannten Quellen verarbeiten müssen, empfiehlt Microsoft, eine Instanz der <xref:System.Xml.XmlReader>-Klasse zu verwenden, die zum Herausfiltern bekannter XML-DoS-Angriffe (Denial of Service) konfiguriert wurde.  
  
 Wenn Sie einen <xref:System.Xml.XmlReader> zur Abwehr von DoS-Angriffen konfiguriert haben, können Sie mit diesem Reader eine LINQ to XML-Struktur auffüllen und damit ebenfalls von den Produktivitätsverbesserungen profitieren, die LINQ to XML für Entwickler bietet. Bei vielen Abwehrstrategien werden Reader erstellt, die für die Minderung der Sicherheitsgefahr konfiguriert werden, und anschließend wird eine XML-Struktur durch den konfigurierten Reader instanziiert.  
  
 XML an sich ist anfällig für DoS-Angriffe, da Dokumente in Größe, Tiefe, Elementnamengröße usw. unbegrenzt sind. Egal, welche Komponenten Sie zum Verarbeiten von XML verwenden, sollten Sie immer darauf vorbereitet sein, die Anwendungsdomäne wiederherzustellen, falls übermäßig viele Ressourcen verwendet werden.  
  
## <a name="mitigation-of-xml-xsd-xpath-and-xslt-attacks"></a>Abwehr von XML-, XSD-, XPath- und XSLT-Angriffen  
 LINQ to XML basiert auf <xref:System.Xml.XmlReader> und <xref:System.Xml.XmlWriter>. LINQ to XML unterstützt durch Erweiterungsmethoden in den Namespaces <xref:System.Xml.Schema?displayProperty=nameWithType> und <xref:System.Xml.XPath?displayProperty=nameWithType> XSD und XPath. Mit den Klassen <xref:System.Xml.XmlReader>, <xref:System.Xml.XPath.XPathNavigator> und <xref:System.Xml.XmlWriter> können Sie in Verbindung mit LINQ to XML XSLT zum Transformieren von XML-Strukturen aufrufen.  
  
 In einer weniger sicheren Umgebung gibt es eine Reihe von Sicherheitsproblemen im Zusammenhang mit XML und der Verwendung der Klassen in <xref:System.Xml?displayProperty=nameWithType>, <xref:System.Xml.Schema?displayProperty=nameWithType>, <xref:System.Xml.XPath?displayProperty=nameWithType> und <xref:System.Xml.Xsl?displayProperty=nameWithType>. Dazu gehören u. a. folgende Probleme:  
  
- XSD, XPath und XSLT sind zeichenfolgenbasierte Sprachen, in denen Sie Vorgänge angeben können, die zeit- oder speicherintensiv sind. Es liegt in der Verantwortung des Anwendungsprogrammierers, der XSD-, XPath- oder XSLT-Zeichenfolgen aus nicht vertrauenswürdigen Quellen verwendet, zu validieren, dass die Zeichenfolgen nicht bösartig sind, oder zu überwachen und die Wahrscheinlichkeit zu verringern, dass die Auswertung dieser Zeichenfolgen zu einem übermäßig hohen Verbrauch der Systemressourcen führt.  
  
- XSD-Schemas (auch Inlineschemas) sind von Natur aus anfällig für DoS-Angriffe. Sie sollten daher keine Schemas aus nicht vertrauenswürdigen Quellen akzeptieren.  
  
- XSD und XSLT können Verweise auf andere Dateien enthalten, und solche Verweise können zu zonen- und domänenübergreifenden Angriffen führen.  
  
- Externe Entitäten in DTDs können zu zonen- und domänenübergreifenden Angriffen führen.  
  
- DTDs sind anfällig für DoS-Angriffe.  
  
- Ausgesprochen tief verschachtelte XML-Dokumente bergen die Gefahr von DoS-Angriffen. Es empfiehlt sich u. U., die Tiefe von XML-Dokumenten zu beschränken.  
  
- Akzeptieren Sie keine unterstützenden Komponenten, wie <xref:System.Xml.NameTable>-Objekte, <xref:System.Xml.XmlNamespaceManager>-Objekte und <xref:System.Xml.XmlResolver>-Objekte aus nicht vertrauenswürdigen Assemblys.  
  
- Lesen Sie Daten in Ausschnitten, um große Dokumentangriffe abzuwehren.  
  
- Skriptblöcke in XSLT-Stylesheets können eine Reihe von Angriffen möglich machen.  
  
- Nehmen Sie vor dem Konstruieren dynamischer XPath-Ausdrücke eine sorgfältige Validierung vor.  
  
## <a name="linq-to-xml-security-issues"></a>Sicherheitsprobleme in LINQ to XML  
 Die Sicherheitsprobleme in diesem Thema werden nicht in einer bestimmten Reihenfolge präsentiert. Alle Probleme sind gleichermaßen wichtig und sollten entsprechend behandelt werden.  
  
 Bei einem erfolgreichen Angriff durch Rechteerhöhung erhält die bösartige Assembly mehr Kontrolle über ihre Umgebung. Ein solcher erfolgreicher Angriff durch Rechteerweiterung kann die Offenlegung von Daten, die Verweigerung des Dienstes und vieles mehr zur Folge haben.  
  
 Anwendungen sollten Benutzern, die für das Anzeigen von Daten keine Berechtigungen besitzen, keine Daten offenlegen.  
  
 DoS-Angriffe führen dazu, dass der XML-Parser oder LINQ to XML übermäßig viel Speicher oder CPU-Zeit verbraucht. Im Vergleich zu Angriffen durch Rechteerweiterung oder Angriffe, bei denen Daten offengelegt werden, gelten DoS-Angriffe als weniger schwerwiegend. In Szenarios, in denen ein Server XML-Dokumente aus nicht vertrauenswürdigen Quellen verarbeiten muss, sind sie dennoch von Bedeutung.  
  
### <a name="exceptions-and-error-messages-might-reveal-data"></a>Ausnahmen und Fehlermeldungen könnten Daten offenlegen  
 Fehlerbeschreibungen könnten für einen Angreifer wertvolle Informationen enthalten – von den zu transformierenden Daten über Dateinamen bis hin zu Implementierungsdetails. Daher sollten Aufrufer, die nicht vertrauenswürdig sind, keine Fehlermeldungen angezeigt bekommen. Sie sollten alle Fehler abfangen und für die Fehlerberichterstattung Ihre eigenen benutzerdefinierten Fehlermeldungen verwenden.  
  
### <a name="do-not-call-codeaccesspermissionsassert-in-an-event-handler"></a>Rufen Sie in einem Ereignishandler nicht "CodeAccessPermissions.Assert" auf  
 Eine Assembly kann mehr oder weniger Berechtigungen besitzen. Je mehr Berechtigungen eine Assembly besitzt, desto größer ist ihre Kontrolle über den Computer und dessen Umgebungen.  
  
 Wenn Code in einer Assembly mit mehr Berechtigungen <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=nameWithType> in einem Ereignishandler aufruft und die XML-Struktur dann an eine bösartige Assembly übergeben wird, die nur eingeschränkte Berechtigungen besitzt, kann die bösartige Assembly zur Auslösung eines Ereignisses führen. Da das Ereignis den Code ausführt, der sich in der Assembly mit den umfangreicheren Berechtigungen befindet, würde die bösartige Assembly dann mit erweiterten Rechten operieren.  
  
 Microsoft empfiehlt, <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=nameWithType> nie in einem Ereignishandler aufzurufen.  
  
### <a name="dtds-are-not-secure"></a>DTDs sind nicht sicher  
 Entitäten in DTDs sind von Natur aus nicht sicher. Ein bösartiges XML-Dokument, das eine DTD enthält, kann Ursache dafür sein, dass der Parser den gesamten Arbeitsspeicher und die gesamte CPU-Zeit nutzt, sodass es zu einem DoS-Angriff kommt. In LINQ to XML ist die DTD-Verarbeitung aus diesem Grund standardmäßig deaktiviert. Sie sollten keine DTDs von nicht vertrauenswürdigen Quellen akzeptieren.  
  
 Ein Beispiel für das Akzeptieren von DTDs aus nicht vertrauenswürdigen Quellen ist eine Internetanwendung, die es Internetbenutzern erlaubt, XML-Dateien hochzuladen, die auf eine DTD und eine DTD-Datei verweisen. Bei der Validierung der Datei könnte eine bösartige DTD einen DoS-Angriff auf Ihren Server starten. Ein anderes Beispiel für das Akzeptieren von DTDs aus nicht vertrauenswürdigen Quellen ist das Verweisen auf eine DTD auf einer Netzwerkfreigabe, die auch einen anonymen FTP-Zugriff zulässt.  
  
### <a name="avoid-excessive-buffer-allocation"></a>Vermeiden Sie übermäßige Pufferzuordnung  
 Anwendungsentwickler müssen sich bewusst sein, dass extrem große Datenquellen eine Ressourcenüberlastung und DoS-Angriffe zur Folge haben können.  
  
 Wenn ein böswilliger Benutzer ein sehr großes XML-Dokument sendet oder hochlädt, kann das dazu führen, dass LINQ to XML übermäßig viele Systemressourcen verbraucht. Dies kann die Grundlage für einen DoS-Angriff sein. Wenn Sie dies vermeiden möchten, können Sie die <xref:System.Xml.XmlReaderSettings.MaxCharactersInDocument%2A?displayProperty=nameWithType>-Eigenschaft festlegen und einen Reader erstellen, der die Größe der ladbaren Dokumente beschränkt. Anschließend erstellen Sie mit dem Reader die XML-Struktur.  
  
 Wenn Sie z. B. wissen, dass sich die maximale erwartete Größe Ihrer von einer nicht vertrauenswürdigen Quelle stammenden XML-Dokumente auf unter 50 KBytes beläuft, legen Sie für <xref:System.Xml.XmlReaderSettings.MaxCharactersInDocument%2A?displayProperty=nameWithType> den Wert "100.000" fest. Die Verarbeitung der XML-Dokumente wird davon nicht negativ beeinflusst, und gleichzeitig verringert sich das Risiko von DoS-Angriffen, bei denen Dokumente hochgeladen werden, die große Mengen des Speichers in Anspruch nehmen.  
  
### <a name="avoid-excess-entity-expansion"></a>Vermeiden Sie eine exzessive Entitätserweiterung  
 Ein bekannter DoS-Angriff mit einer DTD besteht in der Verwendung eines Dokuments, das eine exzessive Entitätserweiterung zur Folge hat. Wenn Sie solche Angriffe vermeiden möchten, können Sie die <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities%2A?displayProperty=nameWithType>-Eigenschaft festlegen und einen Reader erstellen, der die Anzahl der Zeichen beschränkt, die aus einer Entitätserweiterung resultieren. Anschließend erstellen Sie mit dem Reader die XML-Struktur.  
  
### <a name="limit-the-depth-of-the-xml-hierarchy"></a>Begrenzen der Tiefe der XML-Hierarchie  
 Eine Möglichkeit eines Denial-of-Service-Angriff ist gegeben, wenn ein Dokument mit einer übermäßigen Hierarchietiefe gesendet wird. Wenn Sie solche Angriffe verhindern möchten, können Sie in Ihrer eigenen Klasse einen <xref:System.Xml.XmlReader> umschließen, der die Tiefe der Elemente zählt. Wenn die Tiefe ein vorher festgelegtes vernünftiges Maß übersteigt, können Sie die Verarbeitung des bösartigen Dokuments beenden.  
  
### <a name="protect-against-untrusted-xmlreader-or-xmlwriter-implementations"></a>Schützen Sie sich vor nicht vertrauenswürdigen "XmlReader"- oder "XmlWriter"-Implementierungen  
 Administratoren müssen sicherstellen, dass alle extern bereitgestellten <xref:System.Xml.XmlReader>-Implementierungen oder <xref:System.Xml.XmlWriter>-Implementierungen starke Namen besitzen und in der Computerkonfiguration registriert sind. Auf diese Weise wird verhindert, dass bösartiger Code geladen wird, der sich als Reader oder Writer maskiert.  
  
### <a name="periodically-free-objects-that-reference-xname"></a>Geben Sie regelmäßig Objekte frei, die auf "XName" verweisen  
 Um sich vor bestimmten Arten von Angriffen zu schützen, sollten Anwendungsprogrammierer in regelmäßigen Abständen alle Objekte freigeben, die auf ein <xref:System.Xml.Linq.XName>-Objekt in der Anwendungsdomäne verweisen.  
  
### <a name="protect-against-random-xml-names"></a>Schützen Sie sich vor zufälligen XML-Namen  
 Für Anwendungen, die Daten aus nicht vertrauenswürdigen Quellen nehmen, sollte die Verwendung eines <xref:System.Xml.XmlReader> in Erwägung gezogen werden, der von benutzerdefiniertem Code umschlossen wird und nach möglichen zufälligen XML-Namen und -Namespaces sucht. Wenn solche zufälligen XML-Namen und -Namespaces entdeckt werden, kann die Anwendung die Verarbeitung des bösartigen Dokuments abbrechen.  
  
 Sie können die Anzahl der Namen in einem Namespace (einschließlich von Namen, die sich nicht in einem Namespace befinden) auf ein vernünftiges Maß beschränken.  
  
### <a name="annotations-are-accessible-by-software-components-that-share-a-linq-to-xml-tree"></a>Auf Anmerkungen kann von Softwarekomponenten aus zugegriffen werden, die gemeinsam eine LINQ to XML-Struktur nutzen  
 Mit LINQ to XML könnten Verarbeitungspipelines erstellt werden, in denen verschiedene Anwendungskomponenten geladen, validiert, abgefragt, transformiert, aktualisiert und XML-Daten gespeichert werden, die zwischen Komponenten als XML-Strukturen übergeben werden. Dies kann zur Optimierung der Leistung beitragen, weil der Mehraufwand für das Laden und Serialisieren von Objekten in XML-Text nur an den Enden der Pipeline entsteht. Entwickler müssen sich aber bewusst sein, dass alle Anmerkungen und Ereignishandler, die von einer Komponente erstellt werden, auch für andere Komponenten verfügbar sind. Wenn die Komponenten ein unterschiedliches Maß an Vertrauenswürdigkeit besitzen, kann dies zu einer Reihe von Sicherheitsrisiken führen. Wenn Sie sichere Pipelines auch mit weniger vertrauenswürdigen Komponenten erstellen möchten, müssen sie LINQ to XML-Objekte in XML-Text serialisieren, bevor die Daten an eine nicht vertrauenswürdige Komponente übergeben werden.  
  
 Ein gewisses Maß an Sicherheit wird durch die CLR (Common Language Runtime) bereitgestellt. So kann z. B. eine Komponente, die keine private Klasse enthält, auch nicht auf Anmerkungen zugreifen, die von dieser Klasse verschlüsselt wurden. Es ist aber möglich, dass Komponenten Anmerkungen löschen können, die sie gar nicht lesen können. Dieses Verhalten könnte für einen Manipulationsangriff missbraucht werden.  
  
## <a name="see-also"></a>Siehe auch

- [Programmier Handbuch (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
