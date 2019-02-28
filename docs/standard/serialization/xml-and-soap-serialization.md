---
title: XML- und SOAP-Serialisierung
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: d9dc68d8e7eced031af404aaec20784573c9930a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965617"
---
# <a name="xml-and-soap-serialization"></a>XML- und SOAP-Serialisierung

Bei der XML-Serialisierung werden die öffentlichen Felder und Eigenschaften eines Objekts bzw. die Parameter und Rückgabewerte von Methoden in einen XML-Stream konvertiert (serialisiert), der einem bestimmtem XSD (XML Schema Definition)-Dokument entspricht. Die XML-Serialisierung führt zu stark typisierten Klassen mit öffentlichen Eigenschaften und Feldern, die in ein serielles Format (hier XML) konvertiert werden.

Weil XML ein offener Standard ist, kann der XML-Stream plattformunabhängig bei Bedarf von jeder Anwendung verarbeitet werden. Beispielsweise verwenden mit ASP.NET erstellte Webdienste die <xref:System.Xml.Serialization.XmlSerializer>-Klasse zum Erstellen von XML-Sstreams, die zur Übermittlung von Daten zwischen XML-Webdienstanwendungen über das Internet oder ein Intranet dienen. Umgekehrt wird bei der Deserialisierung das Objekt aus einem XML-Stream rekonstruiert.

Durch die XML-Serialisierung können auch Objekte in XML-Streams serialisiert werden, die der SOAP-Spezifikation entsprechen. SOAP ist ein auf XML basierendes Protokoll, das speziell für die Weitergabe von Prozeduraufrufen unter Verwendung von XML entwickelt wurde.

Sie können mithilfe der <xref:System.Xml.Serialization.XmlSerializer>-Klasse Objekte serialisieren und deserialisieren. Verwenden Sie das XML Schema Definition-Tool, um die zu serialisierenden Klassen zu erstellen.

## <a name="in-this-section"></a>In diesem Abschnitt

[Einführung in die XML-Serialisierung](introducing-xml-serialization.md)  
Enthält eine allgemeine Definition der Serialisierung, insbesondere der XML-Serialisierung.

[Vorgehensweise: Serialisieren eines Objekts](how-to-serialize-an-object.md)  
Stellt schrittweise Anweisungen zum Serialisieren eines Objekts bereit.

[Vorgehensweise: Deserialisieren eines Objekts](how-to-deserialize-an-object.md)  
Stellt schrittweise Anweisungen zum Deserialisieren eines Objekts bereit.

[Beispiele für die XML-Serialisierung](examples-of-xml-serialization.md)  
Enthält Beispiele, in denen die Grundlagen der XML-Serialisierung veranschaulicht werden.

[Das XML Schema Definition-Tool und die XML-Serialisierung](the-xml-schema-definition-tool-and-xml-serialization.md)  
Beschreibt die Verwendung des XML-Schema Definition-Tools (Xsd.exe) zum Erstellen von Klassen, die einem bestimmten XSD-Schema (XML Schema Definition Language) angehören, oder zum Generieren eines XML-Schemas aus einer DLL-Datei.

[Steuern der XML-Serialisierung mit Attributen](controlling-xml-serialization-using-attributes.md)  
Beschreibt, wie die Serialisierung durch die Verwendung von Attributen gesteuert wird.

[Attribute zur Steuerung der XML-Serialisierung](attributes-that-control-xml-serialization.md)  
Listet die zur Steuerung der XML-Serialisierung verwendeten Attribute auf.

[Vorgehensweise: Angeben eines alternativen Elementnamens für einen XML-Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
Veranschaulicht anhand eines komplexen Szenarios die Generierung mehrerer XML-Streams durch außer Kraft setzen der Serialisierung.

[Vorgehensweise: Steuerung der Serialisierung abgeleiteter Klassen](how-to-control-serialization-of-derived-classes.md)  
Zeigt anhand eines Beispiels, wie sich die Serialisierung abgeleiteter Klassen steuern läst.

[Vorgehensweise: Qualifizieren von XML-Element- und XML-Attributnamen](how-to-qualify-xml-element-and-xml-attribute-names.md)  
Beschreibt, wie definiert und gesteuert werden kann, wie XML-Namespaces im XML-Stream verwendet werden.

[XML-Serialisierung mit XML-Webdiensten](xml-serialization-with-xml-web-services.md)  
Erläutert die Verwendung der XML-Serialisierung in XML-Webdiensten.

[Vorgehensweise: Serialisieren eines Objekts als ein SOAP-codierten XML-Stream](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
Beschreibt, wie die <xref:System.Xml.Serialization.XmlSerializer> Klasse codierten SOAP-XML-Streams zu erstellen, Abschnitt 5 des World Wide Web Consortium (W3C) Dokuments entsprechen [einfache Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/).

[Vorgehensweise: Überschreiben der XML-Serialisierung von codiertem SOAP](how-to-override-encoded-soap-xml-serialization.md)  
Beschreibt, wie die XML-Serialisierung von Objekten als SOAP-Nachrichten außer Kraft gesetzt wird.

[Attribute zur Steuerung der Serialisierung von codiertem SOAP](attributes-that-control-encoded-soap-serialization.md)  
Listet die Attribute auf, die zur Steuerung der Serialisierung von codiertem SOAP verwendet werden.

[\<system.xml.serialization>-Element](system-xml-serialization-element.md)  
Das Konfigurationselement der obersten Ebene zur Steuerung der XML-Serialisierung

[\<dateTimeSerialization>-Element](datetimeserialization-element.md)  
Steuert den Serialisierungsmodus von <xref:System.DateTime>-Objekten.

[\<schemaImporterExtensions>-Element](schemaimporterextensions-element.md)  
Enthält Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse verwendet werden.

[\<Hinzufügen >-Element für \<SchemaImporterExtensions >](add-element-for-schemaimporterextensions.md)  
Fügt Typen hinzu, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse verwendet werden.

## <a name="related-sections"></a>Verwandte Abschnitte

[Mit ASP.NET- und XML-Webdienstclients erstellte XML-Webdienste](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))  
Stellt Themen bereit, in denen beschrieben und erklärt wird, wie XML-Webdienste mit ASP.NET programmiert werden.

## <a name="see-also"></a>Siehe auch

- [Binäre Serialisierung](binary-serialization.md)
