---
title: XML-Dokumente und XML-Daten
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: e695047f-3c0f-4045-8708-5baea91cc380
ms.openlocfilehash: a752d634141a56df1caa61eb5d375dd2a402832f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287687"
---
# <a name="xml-documents-and-data"></a>XML-Dokumente und XML-Daten

.NET Framework bietet eine umfangreiche und integrierte Gruppe von Klassen, mit denen auf einfache Weise XML-fähige Apps erstellt werden können. Die Klassen in den folgenden Namespaces unterstützen das Analysieren und Schreiben von XML, das Bearbeiten von XML-Daten im Arbeitsspeicher, die Datenvalidierung und die XSLT-Transformation.

- <xref:System.Xml>

- <xref:System.Xml.XPath>

- <xref:System.Xml.Xsl>

- <xref:System.Xml.Schema>

- <xref:System.Xml.Linq>

Suchen Sie im [.NET-API-Browser](https://docs.microsoft.com/dotnet/api/?term=system.xml) nach „System.Xml“, um eine vollständige Liste zu erhalten.

Die Klassen in diesen Namespaces unterstützen die W3C-Empfehlungen (World Wide Web Consortium). Zum Beispiel:

- Die <xref:System.Xml.XmlDocument?displayProperty=nameWithType>-Klasse implementiert die W3C-Empfehlungen [Document Object Model (DOM) Level 1 Core](https://www.w3.org/TR/REC-DOM-Level-1/) und [Document Object Model (DOM) Level 2 Core](https://www.w3.org/TR/DOM-Level-2-Core/).

- Die <xref:System.Xml.XmlReader?displayProperty=nameWithType>-Klasse und die <xref:System.Xml.XmlWriter?displayProperty=nameWithType>-Klasse unterstützen die W3C-Empfehlungen [XML 1.0](https://www.w3.org/TR/2006/REC-xml-20060816/) und [Namespaces in XML](https://www.w3.org/TR/REC-xml-names/).

- Schemas in der <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType>-Klasse unterstützen die Empfehlungen in [W3C XML Schema Part 1: Structures (XML-Schema, Teil 1: Strukturen)](https://www.w3.org/TR/xmlschema-1/) und [XML Schema Part 2: Datatypes (XML-Schema, Teil 2: Datentypen)](https://www.w3.org/TR/xmlschema-2/).

- Klassen im <xref:System.Xml.Xsl?displayProperty=nameWithType>-Namespace unterstützen XSLT-Transformationen, die der W3C-Empfehlung [XSLT 1.0](https://www.w3.org/TR/xslt) entsprechen.

Die XML-Klassen in .NET Framework bieten folgende Vorteile:

- **Produktivität** [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) und [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md) erleichtern die Programmierung mit XML und zeichnen sich durch ein Abfrageverhalten aus, das SQL ähnelt.

- **Erweiterbarkeit** Die XML-Klassen in .NET Framework können mithilfe abstrakter Basisklassen und virtueller Methoden erweitert werden. So könnten Sie z. B. eine von der <xref:System.Xml.XmlUrlResolver>-Klasse abgeleitete Klasse erstellen, durch die der Cachedatenstrom auf dem lokalen Datenträger gespeichert wird.

- **Architektur mit austauschbaren Komponenten** In der Architektur von .NET Framework können Komponenten gegenseitig voneinander Gebrauch machen und Daten zwischen Komponenten gestreamt werden. Beispielsweise kann ein Datenspeicher, z. B. ein <xref:System.Xml.XPath.XPathDocument>-Objekt oder ein <xref:System.Xml.XmlDocument>-Objekt, mit der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse transformiert werden. Anschließend kann die Ausgabe entweder in einen anderen Speicher gestreamt oder als Datenstrom von einem Webdienst zurückgegeben werden.

- **Leistung:** Zur Verbesserung der App-Leistung unterstützen einige XML-Klassen in .NET Framework ein auf Streaming basierendes Modell mit folgenden Merkmalen:

  - Minimale Zwischenspeicherung für die pullbasierte Vorwärtsanalyse (<xref:System.Xml.XmlReader>)

  - Vorwärtsvalidierung (<xref:System.Xml.XmlReader>)

  - Cursornavigation, die die Knotenerstellung auf einen einzelnen virtuellen Knoten reduziert und gleichzeitig den wahlfreien Zugriff auf das Dokument ermöglicht (<xref:System.Xml.XPath.XPathNavigator>)

  Falls XSLT-Verarbeitung erforderlich ist, können Sie die Leistung mithilfe der <xref:System.Xml.XPath.XPathDocument>-Klasse verbessern. Sie stellt einen optimierten, schreibgeschützten Speicher für XPath-Abfragen dar, der für die effiziente Zusammenarbeit mit der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse ausgelegt ist.

- **Integration in ADO.NET** Die XML-Klassen und [ADO.NET](../../../framework/data/adonet/index.md) sind nahtlos integriert und schaffen die Verbindung zwischen relationalen Daten und XML. Die <xref:System.Data.DataSet>-Klasse ist ein speicherinterner Cache für Daten, die aus einer Datenbank abgerufen wurden. Die <xref:System.Data.DataSet>-Klasse ist in der Lage, mithilfe der <xref:System.Xml.XmlReader>-Klasse und der <xref:System.Xml.XmlWriter>-Klasse XML zu lesen und zu schreiben, die zugehörige interne relationale Schemastruktur als XML-Schemas (XSD) beizubehalten und die Schemastruktur eines XML-Dokuments abzuleiten.

## <a name="in-this-section"></a>In diesem Abschnitt

[XML-Verarbeitungsoptionen](xml-processing-options.md) Erläutert die Optionen zum Verarbeiten von XML-Daten

[Verarbeiten von XML-Daten im Arbeitsspeicher](processing-xml-data-in-memory.md) Erläutert die drei Modelle für die Verarbeitung von XML-Daten im Arbeitsspeicher: [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) und [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md), die (auf dem W3C-Dokumentobjektmodell basierende) <xref:System.Xml.XmlDocument>-Klasse und die (auf dem XPath-Datenmodell) basierende <xref:System.Xml.XPath.XPathDocument>-Klasse.

[XSLT-Transformationen](xslt-transformations.md)\
In diesem Abschnitt wird die Verwendung des XSLT-Prozessors beschrieben.

[XML-Schemaobjektmodell (SOM)](xml-schema-object-model-som.md)\
In diesem Abschnitt werden die Klassen beschrieben, mit denen XML-Schemas (XSD) erstellt und bearbeitet werden, indem eine <xref:System.Xml.Schema.XmlSchema>-Klasse zum Laden und Bearbeiten eines Schemas bereitgestellt wird.

[XML-Integration mit relationalen Daten und ADO.NET](xml-integration-with-relational-data-and-adonet.md)\
In diesem Abschnitt wird beschrieben, wie .NET Framework einen synchronen Echtzeitzugriff auf die relationale und die hierarchische Darstellung von Daten über das <xref:System.Data.DataSet>-Objekt und das <xref:System.Xml.XmlDataDocument>-Objekt ermöglicht.

[Verwalten von Namespaces in einem XML-Dokument](managing-namespaces-in-an-xml-document.md)\
Beschreibt, wie die <xref:System.Xml.XmlNamespaceManager>-Klasse zum Speichern und Verwalten von Namespaceinformationen verwendet wird.

[Typenunterstützung in den System.Xml-Klassen](type-support-in-the-system-xml-classes.md)\
Beschreibt die Zuordnung von XML-Datentypen zu CLR-Typen, die Konvertierung von XML-Datentypen und andere in den <xref:System.Xml>-Klassen enthaltene Funktionen zur Unterstützung von Typen.

## <a name="related-sections"></a>Verwandte Abschnitte

[ADO.NET](../../../framework/data/adonet/index.md)\
Hier erhalten Sie Informationen über den Zugriff auf Daten mit ADO.NET.

[Sicherheit](../../security/index.md)\
Dieser Abschnitt stellt eine Übersicht über das Sicherheitssystem von .NET Framework bereit.
