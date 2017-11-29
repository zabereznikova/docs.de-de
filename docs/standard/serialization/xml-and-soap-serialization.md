---
title: XML- und SOAP-Serialisierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 809f1418d7ee0939c7e31124fbda7ef5fd8e2e5e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xml-and-soap-serialization"></a>XML- und SOAP-Serialisierung
Bei der XML-Serialisierung werden die öffentlichen Felder und Eigenschaften eines Objekts bzw. die Parameter und Rückgabewerte von Methoden in einen XML-Stream konvertiert (serialisiert), der einem bestimmtem XSD (XML Schema Definition)-Dokument entspricht. Die XML-Serialisierung führt zu stark typisierten Klassen mit öffentlichen Eigenschaften und Feldern, die in ein serielles Format (hier XML) konvertiert werden.  
  
 Weil XML ein offener Standard ist, kann der XML-Stream plattformunabhängig bei Bedarf von jeder Anwendung verarbeitet werden. Beispielsweise verwenden mit ASP.NET erstellte Webdienste die <xref:System.Xml.Serialization.XmlSerializer>-Klasse zum Erstellen von XML-Sstreams, die zur Übermittlung von Daten zwischen XML-Webdienstanwendungen über das Internet oder ein Intranet dienen. Umgekehrt wird bei der Deserialisierung das Objekt aus einem XML-Stream rekonstruiert.  
  
 Durch die XML-Serialisierung können auch Objekte in XML-Streams serialisiert werden, die der SOAP-Spezifikation entsprechen. SOAP ist ein auf XML basierendes Protokoll, das speziell für die Weitergabe von Prozeduraufrufen unter Verwendung von XML entwickelt wurde.  
  
 Sie können mithilfe der <xref:System.Xml.Serialization.XmlSerializer>-Klasse Objekte serialisieren und deserialisieren. Verwenden Sie das XML Schema Definition-Tool, um die zu serialisierenden Klassen zu erstellen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Einführung in die XML-Serialisierung](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 Enthält eine allgemeine Definition der Serialisierung, insbesondere der XML-Serialisierung.  
  
 [Vorgehensweise: Serialisieren eines Objekts](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 Stellt schrittweise Anweisungen zum Serialisieren eines Objekts bereit.  
  
 [Vorgehensweise: Deserialisieren eines Objekts](../../../docs/standard/serialization/how-to-deserialize-an-object.md)  
 Stellt schrittweise Anweisungen zum Deserialisieren eines Objekts bereit.  
  
 [Beispiele für die XML-Serialisierung](../../../docs/standard/serialization/examples-of-xml-serialization.md)  
 Enthält Beispiele, in denen die Grundlagen der XML-Serialisierung veranschaulicht werden.  
  
 [Das XML Schema Definition-Tool und die XML-Serialisierung](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)  
 Beschreibt die Verwendung des XML-Schema Definition-Tools (Xsd.exe) zum Erstellen von Klassen, die einem bestimmten XSD-Schema (XML Schema Definition Language) angehören, oder zum Generieren eines XML-Schemas aus einer DLL-Datei.  
  
 [Steuern der XML-Serialisierung mit Attributen](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)  
 Beschreibt, wie die Serialisierung durch die Verwendung von Attributen gesteuert wird.  
  
 [Attribute zur Steuerung der XML-Serialisierung](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md)  
 Listet die zur Steuerung der XML-Serialisierung verwendeten Attribute auf.  
  
 [Vorgehensweise: Angeben eines alternativen Elementnamens für einen XML-Stream](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
 Veranschaulicht anhand eines komplexen Szenarios die Generierung mehrerer XML-Streams durch außer Kraft setzen der Serialisierung.  
  
 [Vorgehensweise: Steuern der Serialisierung abgeleiteter Klassen](../../../docs/standard/serialization/how-to-control-serialization-of-derived-classes.md)  
 Zeigt anhand eines Beispiels, wie sich die Serialisierung abgeleiteter Klassen steuern läst.  
  
 [Vorgehensweise: Qualifizieren von XML-Element- und XML-Attributnamen](../../../docs/standard/serialization/how-to-qualify-xml-element-and-xml-attribute-names.md)  
 Beschreibt, wie definiert und gesteuert werden kann, wie XML-Namespaces im XML-Stream verwendet werden.  
  
 [XML-Serialisierung mit XML-Webdiensten](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)  
 Erläutert die Verwendung der XML-Serialisierung in XML-Webdiensten.  
  
 [Vorgehensweise: Serialisieren eines Objekts als SOAP-codierter XML-Stream](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
 Beschreibt die Verwendung der <xref:System.Xml.Serialization.XmlSerializer> -Klasse zur Erstellung der XML-Streams von codiertem SOAP, die Abschnitt 5 des vom World Wide Web Consortium (www.w3.org) herausgegebenen Dokuments mit dem Titel "Simple Object Access Protocol (SOAP) 1.1" entsprechen.  
  
 [Gewusst wie: Überschreiben von codierter SOAP-XML-Serialisierung](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)  
 Beschreibt, wie die XML-Serialisierung von Objekten als SOAP-Nachrichten außer Kraft gesetzt wird.  
  
 [Attribute zur Steuerung der Serialisierung von codiertem SOAP](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)  
 Listet die Attribute auf, die zur Steuerung der Serialisierung von codiertem SOAP verwendet werden.  
  
 [\<system.xml.serialization>-Element](../../../docs/standard/serialization/system-xml-serialization-element.md)  
 Das Konfigurationselement der obersten Ebene zur Steuerung der XML-Serialisierung  
  
 [\<dateTimeSerialization>-Element](../../../docs/standard/serialization/datetimeserialization-element.md)  
 Steuert den Serialisierungsmodus von <xref:System.DateTime>-Objekten.  
  
 [\<schemaImporterExtensions>-Element](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
 Enthält Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse verwendet werden.  
  
 [\<add>-Element für \<xmlSchemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)  
 Fügt Typen hinzu, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse verwendet werden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Advanced Development Technologies (Erweiterte Entwicklungstechnologien)](http://msdn.microsoft.com/en-us/c4a7e341-f0c6-4df4-a74f-223387ac6e4e)  
 Enthält Links zu weiteren Informationen über anspruchsvolle Aufgaben und Verfahren für die Entwicklung in .NET&#160;Framework.  
  
 [Mithilfe von ASP.NET und XML-Webdiensteclients erstellte XML-Webdienste](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c)  
 Stellt Themen bereit, in denen beschrieben und erklärt wird, wie XML-Webdienste mit ASP.NET programmiert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Binäre Serialisierung](../../../docs/standard/serialization/binary-serialization.md)
