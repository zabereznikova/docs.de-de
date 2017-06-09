---
title: "Attribute zur Steuerung der Serialisierung von codiertem SOAP | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Attribute [.NET Framework], XML-Serialisierung"
  - "Serialisierung, Attribute"
  - "SOAP, XML-Serialisierung"
  - "XML-Serialisierung, Attribute"
  - "XML-Serialisierung, SOAP"
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Attribute zur Steuerung der Serialisierung von codiertem SOAP
Das vom World Wide Web Consortium \(www.w3.org\) herausgegebene Dokument mit dem Titel "Simple Object Access Protocol \(SOAP\) 1.1" enthält einen optionalen Abschnitt \(Abschnitt 5\), in dem die Codierung von SOAP\-Parametern beschrieben wird.Um Abschnitt 5 dieser Spezifikation zu entsprechen, müssen Sie spezielle Attribute verwenden, die im [System.Xml.Serialization](frlrfSystemXmlSerialization)\-Namespace enthalten sind.Wenden Sie diese Attribute auf die entsprechenden Klassen und Member der Klassen an, und verwenden Sie dann [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx), um Instanzen dieser Klasse oder Klassen zu serialisieren.  
  
 In der folgenden Tabelle sind die Attribute, ihr Anwendungsbereich und ihre Funktion aufgeführt.Weitere Informationen zum Steuern der XML\-Serialisierung mithilfe dieser Attribute finden Sie unter [Vorgehensweise: Serialisieren eines Objekts als SOAP\-codierter XML\-Stream](../../../docs/framework/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) und [Vorgehensweise: Überschreiben von codierter SOAP\-XML\-Serialisierung](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md).  
  
 Weitere Informationen zu Attributen finden Sie unter [Attribute](../../../docs/standard/attributes/index.md).  
  
|Attribut|Betrifft|Bedeutung|  
|--------------|--------------|---------------|  
|[SoapAttributeAttribute](frlrfSystemXmlSerializationSoapAttributeAttributeClassTopic)|Öffentliches Feld, Eigenschaft, Parameter oder Rückgabewert.|Der Klassenmember wird als XML\-Attribut serialisiert.|  
|[SoapElementAttribute](frlrfSystemXmlSerializationSoapElementAttributeClassTopic)|Öffentliches Feld, Eigenschaft, Parameter oder Rückgabewert.|Die Klasse wird als XML\-Element serialisiert.|  
|[SoapEnumAttribute](frlrfSystemXmlSerializationSoapEnumAttributeClassTopic)|Öffentliches Feld, das ein Enumerationsbezeichner ist.|Der Elementname eines Enumerationsmembers.|  
|[SoapIgnoreAttribute](frlrfSystemXmlSerializationSoapIgnoreAttributeClassTopic)|Öffentliche Eigenschaften und Felder.|Die Eigenschaft oder das Feld sollte beim Serialisieren der Klasse, in dem sie bzw. es enthalten ist, ignoriert werden.|  
|[SoapIncludeAttribute](frlrfSystemXmlSerializationSoapIncludeAttributeClassTopic)|Öffentliche abgeleitete Klassendeklarationen und öffentliche Methoden für WSDL\-Dokumente \(Web Services Description Language\).|Der Typ wird beim Generieren von Schemas eingeschlossen \(und daher bei der Serialisierung erkannt\).|  
|[SoapTypeAttribute](frlrfSystemXmlSerializationSoapTypeAttributeClassTopic)|Deklarationen öffentlicher Klassen.|Die Klasse sollte als XML\-Typ serialisiert werden.|  
  
## Siehe auch  
 [XML\- und SOAP\-Serialisierung](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [Vorgehensweise: Serialisieren eines Objekts als SOAP\-codierter XML\-Stream](../../../docs/framework/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)   
 [Vorgehensweise: Überschreiben von codierter SOAP\-XML\-Serialisierung](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md)   
 [Attribute](../../../docs/standard/attributes/index.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [Vorgehensweise: Serialisieren eines Objekts](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Vorgehensweise: Deserialisieren eines Objekts](../../../docs/framework/serialization/how-to-deserialize-an-object.md)