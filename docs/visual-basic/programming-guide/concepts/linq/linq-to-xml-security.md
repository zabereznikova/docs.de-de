---
title: LINQ to XML-Sicherheit (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: d99b4af2-d447-4a3b-991b-6da0231a8637
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 559bf330640840a310ff947cac118953d1df1a13
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-security-visual-basic"></a>LINQ to XML-Sicherheit (Visual Basic)
In diesem Thema werden Sicherheitsfragen im Zusammenhang mit LINQ to XML erörtert. Darüber hinaus finden Sie hier einige Empfehlungen zur Minderung der Sicherheitsrisiken.  
  
## <a name="linq-to-xml-security-overview"></a>Übersicht über die Sicherheit in LINQ to XML  
 Bei der Entwicklung von LINQ to XML standen nicht die serverseitigen Anwendungen mit strengen Sicherheitsanforderungen, sondern eher das bequeme Programmieren im Vordergrund. Die meisten XML-Szenarios beinhalten die Verarbeitung vertrauenswürdiger XML-Dokumente und nicht die Verarbeitung nicht vertrauenswürdiger XML-Dokumente, die auf einen Server hochgeladen werden. Genau für diese Szenarios ist LINQ to XML optimiert.  
  
 Wenn Sie nicht vertrauenswürdige Daten aus unbekannten Quellen verarbeiten müssen, empfiehlt Microsoft die Verwendung einer Instanz der <xref:System.Xml.XmlReader>-Klasse, die zum Herausfiltern bekannten XML-DOS DOS Angriffe (DoS) konfiguriert wurde.</xref:System.Xml.XmlReader>  
  
 Wenn Sie konfiguriert haben eine <xref:System.Xml.XmlReader>um DOS-Angriffe zu verringern, können Sie diesem Reader eine LINQ to XML-Struktur auffüllen und dennoch von der Programmierer Produktivitätssteigerungen von LINQ to XML profitieren.</xref:System.Xml.XmlReader> Bei vielen Abwehrstrategien werden Reader erstellt, die für die Minderung der Sicherheitsgefahr konfiguriert werden, und anschließend wird eine XML-Struktur durch den konfigurierten Reader instanziiert.  
  
 XML an sich ist anfällig für DoS-Angriffe, da Dokumente in Größe, Tiefe, Elementnamengröße usw. unbegrenzt sind. Egal, welche Komponenten Sie zum Verarbeiten von XML verwenden, sollten Sie immer darauf vorbereitet sein, die Anwendungsdomäne wiederherzustellen, falls übermäßig viele Ressourcen verwendet werden.  
  
## <a name="mitigation-of-xml-xsd-xpath-and-xslt-attacks"></a>Abwehr von XML-, XSD-, XPath- und XSLT-Angriffen  
 LINQ to XML basiert auf <xref:System.Xml.XmlReader>und <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> LINQ to XML unterstützt XSD und XPath durch Erweiterungsmethoden in den <xref:System.Xml.Schema?displayProperty=fullName>und <xref:System.Xml.XPath?displayProperty=fullName>Namespaces.</xref:System.Xml.XPath?displayProperty=fullName> </xref:System.Xml.Schema?displayProperty=fullName> Mithilfe der <xref:System.Xml.XmlReader>, <xref:System.Xml.XPath.XPathNavigator>, und <xref:System.Xml.XmlWriter>Klassen im Zusammenhang mit LINQ to XML können Sie XSLT zum Transformieren von XML-Strukturen aufrufen.</xref:System.Xml.XmlWriter> </xref:System.Xml.XPath.XPathNavigator> </xref:System.Xml.XmlReader>  
  
 Wenn Sie in einer weniger sicheren Umgebung befinden, es gibt eine Reihe von Sicherheitsproblemen, die mit XML verknüpft sind und die Verwendung der Klassen in <xref:System.Xml?displayProperty=fullName>, <xref:System.Xml.Schema?displayProperty=fullName>, <xref:System.Xml.XPath?displayProperty=fullName>, und <xref:System.Xml.Xsl?displayProperty=fullName>.</xref:System.Xml.Xsl?displayProperty=fullName> </xref:System.Xml.XPath?displayProperty=fullName> </xref:System.Xml.Schema?displayProperty=fullName> </xref:System.Xml?displayProperty=fullName> Dazu gehören u. a. folgende Probleme:  
  
-   XSD, XPath und XSLT sind zeichenfolgenbasierte Sprachen, in denen Sie Vorgänge angeben können, die zeit- oder speicherintensiv sind. Es liegt in der Verantwortung des Anwendungsprogrammierers, der XSD-, XPath- oder XSLT-Zeichenfolgen aus nicht vertrauenswürdigen Quellen verwendet, zu validieren, dass die Zeichenfolgen nicht bösartig sind, oder zu überwachen und die Wahrscheinlichkeit zu verringern, dass die Auswertung dieser Zeichenfolgen zu einem übermäßig hohen Verbrauch der Systemressourcen führt.  
  
-   XSD-Schemas (auch Inlineschemas) sind von Natur aus anfällig für DoS-Angriffe. Sie sollten daher keine Schemas aus nicht vertrauenswürdigen Quellen akzeptieren.  
  
-   XSD und XSLT können Verweise auf andere Dateien enthalten, und solche Verweise können zu zonen- und domänenübergreifenden Angriffen führen.  
  
-   Externe Entitäten in DTDs können zu zonen- und domänenübergreifenden Angriffen führen.  
  
-   DTDs sind anfällig für DoS-Angriffe.  
  
-   Ausgesprochen tief verschachtelte XML-Dokumente bergen die Gefahr von DoS-Angriffen. Es empfiehlt sich u. U., die Tiefe von XML-Dokumenten zu beschränken.  
  
-   Akzeptieren Sie keine unterstützende Komponenten, wie z. B. <xref:System.Xml.NameTable>, <xref:System.Xml.XmlNamespaceManager>, und <xref:System.Xml.XmlResolver>-Objekte aus nicht vertrauenswürdigen Assemblys.</xref:System.Xml.XmlResolver> </xref:System.Xml.XmlNamespaceManager> </xref:System.Xml.NameTable>  
  
-   Lesen Sie Daten in Ausschnitten, um große Dokumentangriffe abzuwehren.  
  
-   Skriptblöcke in XSLT-Stylesheets können eine Reihe von Angriffen möglich machen.  
  
-   Nehmen Sie vor dem Konstruieren dynamischer XPath-Ausdrücke eine sorgfältige Validierung vor.  
  
## <a name="linq-to-xml-security-issues"></a>Sicherheitsprobleme in LINQ to XML  
 Die Aufzählung der in diesem Thema genannten Sicherheitsprobleme folgt keiner bestimmten Reihenfolge. Alle Probleme sind gleichermaßen wichtig und sollten entsprechend behandelt werden.  
  
 Bei einem erfolgreichen Angriff durch Rechteerhöhung erhält die bösartige Assembly mehr Kontrolle über ihre Umgebung. Ein solcher erfolgreicher Angriff durch Rechteerweiterung kann die Offenlegung von Daten, die Verweigerung des Dienstes und vieles mehr zur Folge haben.  
  
 Anwendungen sollten Benutzern, die für das Anzeigen von Daten keine Berechtigungen besitzen, keine Daten offenlegen.  
  
 DoS-Angriffe führen dazu, dass der XML-Parser oder LINQ to XML übermäßig viel Speicher oder CPU-Zeit verbraucht. Im Vergleich zu Angriffen durch Rechteerweiterung oder Angriffe, bei denen Daten offengelegt werden, gelten DoS-Angriffe als weniger schwerwiegend. In Szenarios, in denen ein Server XML-Dokumente aus nicht vertrauenswürdigen Quellen verarbeiten muss, sind sie dennoch von Bedeutung.  
  
### <a name="exceptions-and-error-messages-might-reveal-data"></a>Ausnahmen und Fehlermeldungen könnten Daten offenlegen  
 Fehlerbeschreibungen könnten für einen Angreifer wertvolle Informationen enthalten – von den zu transformierenden Daten über Dateinamen bis hin zu Implementierungsdetails. Daher sollten Aufrufer, die nicht vertrauenswürdig sind, keine Fehlermeldungen angezeigt bekommen. Sie sollten alle Fehler abfangen und für die Fehlerberichterstattung Ihre eigenen benutzerdefinierten Fehlermeldungen verwenden.  
  
### <a name="do-not-call-codeaccesspermissionsassert-in-an-event-handler"></a>Rufen Sie in einem Ereignishandler nicht "CodeAccessPermissions.Assert" auf  
 Eine Assembly kann mehr oder weniger Berechtigungen besitzen. Je mehr Berechtigungen eine Assembly besitzt, desto größer ist ihre Kontrolle über den Computer und dessen Umgebungen.  
  
 Wenn Code in einer Assembly mit mehr Berechtigungen erfordert <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>in einem Ereignishandler und dann die XML-Struktur an eine bösartige Assembly übergeben sind, eingeschränkte Berechtigungen besitzt, kann die bösartige Assembly führen ein Ereignis ausgelöst werden.</xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName> Da das Ereignis den Code ausführt, der sich in der Assembly mit den umfangreicheren Berechtigungen befindet, würde die bösartige Assembly dann mit erweiterten Rechten operieren.  
  
 Microsoft empfiehlt, dass Sie niemals aufrufen, <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>in einem Ereignishandler.</xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>  
  
### <a name="dtds-are-not-secure"></a>DTDs sind nicht sicher  
 Entitäten in DTDs sind von Natur aus nicht sicher. Ein bösartiges XML-Dokument, das eine DTD enthält, kann Ursache dafür sein, dass der Parser den gesamten Arbeitsspeicher und die gesamte CPU-Zeit nutzt, sodass es zu einem DoS-Angriff kommt. In LINQ to XML ist die DTD-Verarbeitung aus diesem Grund standardmäßig deaktiviert. Sie sollten keine DTDs von nicht vertrauenswürdigen Quellen akzeptieren.  
  
 Ein Beispiel für das Akzeptieren von DTDs aus nicht vertrauenswürdigen Quellen ist eine Internetanwendung, die es Internetbenutzern erlaubt, XML-Dateien hochzuladen, die auf eine DTD und eine DTD-Datei verweisen. Bei der Validierung der Datei könnte eine bösartige DTD einen DoS-Angriff auf Ihren Server starten. Ein anderes Beispiel für das Akzeptieren von DTDs aus nicht vertrauenswürdigen Quellen ist das Verweisen auf eine DTD auf einer Netzwerkfreigabe, die auch einen anonymen FTP-Zugriff zulässt.  
  
### <a name="avoid-excessive-buffer-allocation"></a>Vermeiden Sie übermäßige Pufferzuordnung  
 Anwendungsentwickler müssen sich bewusst sein, dass extrem große Datenquellen eine Ressourcenüberlastung und DoS-Angriffe zur Folge haben können.  
  
 Wenn ein böswilliger Benutzer ein sehr großes XML-Dokument sendet oder hochlädt, kann das dazu führen, dass LINQ to XML übermäßig viele Systemressourcen verbraucht. Dies kann die Grundlage für einen DoS-Angriff sein. Um dies zu verhindern, legen Sie die <xref:System.Xml.XmlReaderSettings.MaxCharactersInDocument%2A?displayProperty=fullName>-Eigenschaft und einen Reader erstellen, beschränkt die Größe des Dokuments, die geladen werden können.</xref:System.Xml.XmlReaderSettings.MaxCharactersInDocument%2A?displayProperty=fullName> Anschließend erstellen Sie mit dem Reader die XML-Struktur.  
  
 Z. B. Wenn Sie wissen, dass die maximale erwartete Größe Ihrer von einer nicht vertrauenswürdigen Quelle stammenden XML-Dokumente wird weniger als 50 KBytes beläuft, legen <xref:System.Xml.XmlReaderSettings.MaxCharactersInDocument%2A?displayProperty=fullName>und 100.000.</xref:System.Xml.XmlReaderSettings.MaxCharactersInDocument%2A?displayProperty=fullName> Die Verarbeitung der XML-Dokumente wird davon nicht negativ beeinflusst, und gleichzeitig verringert sich das Risiko von DoS-Angriffen, bei denen Dokumente hochgeladen werden, die große Mengen des Speichers in Anspruch nehmen.  
  
### <a name="avoid-excess-entity-expansion"></a>Vermeiden Sie eine exzessive Entitätserweiterung  
 Ein bekannter DoS-Angriff mit einer DTD besteht in der Verwendung eines Dokuments, das eine exzessive Entitätserweiterung zur Folge hat. Um dies zu verhindern, legen Sie die <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities%2A?displayProperty=fullName>-Eigenschaft und einen Reader erstellen, beschränkt die Anzahl der Zeichen, die aus einer entitätserweiterung resultieren.</xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities%2A?displayProperty=fullName> Anschließend erstellen Sie mit dem Reader die XML-Struktur.  
  
### <a name="limit-the-depth-of-the-xml-hierarchy"></a>Schränken Sie die Tiefe der XML-Hierarchie ein  
 Ein möglicher DoS-Angriff besteht darin, ein Dokument zu senden, dass eine außerordentlich große Hierarchietiefe besitzt. Um dies zu verhindern, können Sie umschließen einer <xref:System.Xml.XmlReader>in Ihrer eigenen Klasse, die die Tiefe der Elemente zählt.</xref:System.Xml.XmlReader> Wenn die Tiefe ein vorher festgelegtes vernünftiges Maß übersteigt, können Sie die Verarbeitung des bösartigen Dokuments beenden.  
  
### <a name="protect-against-untrusted-xmlreader-or-xmlwriter-implementations"></a>Schützen Sie sich vor nicht vertrauenswürdigen "XmlReader"- oder "XmlWriter"-Implementierungen  
 Administratoren müssen sicherstellen, dass alle extern bereitgestellten <xref:System.Xml.XmlReader>oder <xref:System.Xml.XmlWriter>Implementierungen einen starken Namen aufweisen und in der Computerkonfiguration registriert.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> Auf diese Weise wird verhindert, dass bösartiger Code geladen wird, der sich als Reader oder Writer maskiert.  
  
### <a name="periodically-free-objects-that-reference-xname"></a>Geben Sie regelmäßig Objekte frei, die auf "XName" verweisen  
 Zum Schutz vor bestimmten Arten von Angriffen, sollten Anwendungsprogrammierer freigeben, alle Objekte, die auf ein <xref:System.Xml.Linq.XName>Objekt in der Anwendungsdomäne in regelmäßigen Abständen.</xref:System.Xml.Linq.XName>  
  
### <a name="protect-against-random-xml-names"></a>Schützen Sie sich vor zufälligen XML-Namen  
 Anwendungen, die Daten aus nicht vertrauenswürdigen Quellen nehmen sollten mit einer <xref:System.Xml.XmlReader>, eingeschlossen in benutzerdefiniertem Code die Möglichkeit einer zufälligen XML-Namen und -Namespaces sucht.</xref:System.Xml.XmlReader> Wenn solche zufälligen XML-Namen und -Namespaces entdeckt werden, kann die Anwendung die Verarbeitung des bösartigen Dokuments abbrechen.  
  
 Sie können die Anzahl der Namen in einem Namespace (einschließlich von Namen, die sich nicht in einem Namespace befinden) auf ein vernünftiges Maß beschränken.  
  
### <a name="annotations-are-accessible-by-software-components-that-share-a-linq-to-xml-tree"></a>Auf Anmerkungen kann von Softwarekomponenten aus zugegriffen werden, die gemeinsam eine LINQ to XML-Struktur nutzen  
 Mit LINQ to XML könnten Verarbeitungspipelines erstellt werden, in denen verschiedene Anwendungskomponenten geladen, validiert, abgefragt, transformiert, aktualisiert und XML-Daten gespeichert werden, die zwischen Komponenten als XML-Strukturen übergeben werden. Dies kann zur Optimierung der Leistung beitragen, weil der Mehraufwand für das Laden und Serialisieren von Objekten in XML-Text nur an den Enden der Pipeline entsteht. Entwickler müssen sich aber bewusst sein, dass alle Anmerkungen und Ereignishandler, die von einer Komponente erstellt werden, auch für andere Komponenten verfügbar sind. Wenn die Komponenten ein unterschiedliches Maß an Vertrauenswürdigkeit besitzen, kann dies zu einer Reihe von Sicherheitsrisiken führen. Wenn Sie sichere Pipelines auch mit weniger vertrauenswürdigen Komponenten erstellen möchten, müssen sie LINQ to XML-Objekte in XML-Text serialisieren, bevor die Daten an eine nicht vertrauenswürdige Komponente übergeben werden.  
  
 Ein gewisses Maß an Sicherheit wird durch die CLR (Common Language Runtime) bereitgestellt. So kann z. B. eine Komponente, die keine private Klasse enthält, auch nicht auf Anmerkungen zugreifen, die von dieser Klasse verschlüsselt wurden. Es ist aber möglich, dass Komponenten Anmerkungen löschen können, die sie gar nicht lesen können. Dieses Verhalten könnte für einen Manipulationsangriff missbraucht werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Programmierhandbuch (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
