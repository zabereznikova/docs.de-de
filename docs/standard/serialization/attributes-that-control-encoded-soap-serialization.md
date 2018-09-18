---
title: Attribute zur Steuerung der Serialisierung von codiertem SOAP
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- serialization, attributes
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
ms.openlocfilehash: 7b5a48003ff9bfb398c05c8d70a9076d49ad83d6
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46003242"
---
# <a name="attributes-that-control-encoded-soap-serialization"></a>Attribute zur Steuerung der Serialisierung von codiertem SOAP

Das World Wide Web Consortium (W3C)-Dokument mit dem Namen [einfache Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/) enthält einen optionalen Abschnitt (Abschnitt 5), die SOAP-Codierung von Parametern beschrieben werden können. Um dem Abschnitt 5 dieser Spezifikation zu entsprechen, müssen Sie spezielle Attribute verwenden, die im <xref:System.Xml.Serialization>-Namespace enthalten sind. Wenden Sie diese Attribute auf die entsprechenden Klassen und Member der Klassen an, und verwenden Sie dann <xref:System.Xml.Serialization.XmlSerializer>, um Instanzen dieser Klasse oder Klassen zu serialisieren.

In der folgenden Tabelle sind die Attribute, ihr Anwendungsbereich und ihre Funktion aufgeführt. Weitere Informationen zum Einsatz dieser Attribute zur Steuerung der XML-Serialisierung finden Sie unter [Vorgehensweise: Serialisieren eines Objekts als SOAP-codierter XML-Stream](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) und [Vorgehensweise: Überschreiben von codierter SOAP-XML-Serialisierung](how-to-override-encoded-soap-xml-serialization.md).

Weitere Informationen zu Attributen finden Sie unter [Attribute](../../../docs/standard/attributes/index.md).

|Attribut|Betrifft|Bedeutung|
|---------------|----------------|---------------|
|<xref:System.Xml.Serialization.SoapAttributeAttribute>|Öffentliches Feld, Eigenschaft, Parameter oder Rückgabewert.|Der Klassenmember wird als XML-Attribut serialisiert.|
|<xref:System.Xml.Serialization.SoapElementAttribute>|Öffentliches Feld, Eigenschaft, Parameter oder Rückgabewert.|Die Klasse wird als XML-Element serialisiert.|
|<xref:System.Xml.Serialization.SoapEnumAttribute>|Öffentliches Feld, das ein Enumerationsbezeichner ist.|Der Elementname eines Enumerationsmembers.|
|<xref:System.Xml.Serialization.SoapIgnoreAttribute>|Öffentliche Eigenschaften und Felder.|Die Eigenschaft oder das Feld wird beim Serialisieren der Klasse, in dem sie bzw. es enthalten ist, ignoriert.|
|<xref:System.Xml.Serialization.SoapIncludeAttribute>|Öffentliche abgeleitete Klassendeklarationen und öffentliche Methoden für WSDL-Dokumente (Web Services Description Language).|Der Typ wird beim Generieren von Schemas eingeschlossen (und daher bei der Serialisierung erkannt).|
|<xref:System.Xml.Serialization.SoapTypeAttribute>|Deklarationen öffentlicher Klassen.|Die Klasse wird als XML-Typ serialisiert.|

## <a name="see-also"></a>Siehe auch

- [XML- und SOAP-Serialisierung](xml-and-soap-serialization.md)  
- [Vorgehensweise: Serialisieren eines Objekts als SOAP-codierter XML-Stream](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
- [Gewusst wie: Überschreiben von codierter SOAP-XML-Serialisierung](how-to-override-encoded-soap-xml-serialization.md)  
- [Attribute](../../../docs/standard/attributes/index.md)  
- <xref:System.Xml.Serialization.XmlSerializer>  
- [Vorgehensweise: Serialisieren eines Objekts](how-to-serialize-an-object.md)  
- [Vorgehensweise: Deserialisieren eines Objekts](how-to-deserialize-an-object.md)
