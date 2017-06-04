---
title: "Attribute zur Steuerung der XML-Serialisierung | Microsoft Docs"
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
  - "Klassen, Serialisieren"
  - "Serialisierung, Attribute"
  - "XML-Schema, Serialisieren"
  - "XML-Serialisierung, Attribute"
  - "XmlSerializer-Klasse, Serialisieren"
ms.assetid: 414b820f-a696-4206-b576-2711d85490c7
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Attribute zur Steuerung der XML-Serialisierung
Sie können die in der folgenden Tabelle aufgeführten Attribute auf Klassen und Klassenmember anwenden, um zu steuern, wie Instanzen der Klasse durch die [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)\-Klasse serialisiert bzw. deserialisiert werden.Wie die XML\-Serialisierung mithilfe dieser Attribute gesteuert wird, wird unter [Steuern der XML\-Serialisierung mit Attributen](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md) beschrieben.  
  
 Diese Attribute können auch verwendet werden, um die durch einen XML\-Webdienst generierten literalen SOAP\-Nachrichten zu steuern.Weitere Informationen zum Anwenden dieser Attribute auf eine XML\-Webdienste\-Methode finden Sie unter [XML\-Serialisierung mit XML\-Webdiensten](../../../docs/framework/serialization/xml-serialization-with-xml-web-services.md).  
  
 Weitere Informationen zu Attributen finden Sie unter [Attribute](../../../docs/standard/attributes/index.md).  
  
|Attribute|Betrifft|Bedeutung|  
|---------------|--------------|---------------|  
|[XmlAnyAttributeAttribute](frlrfSystemXmlSerializationXmlAnyAttributeAttributeClassTopic)|Öffentliches Feld, Eigenschaft, Parameter oder Rückgabewert, wodurch ein Array von [XmlAttribute](frlrfSystemXmlXmlAttributeClassTopic)\-Objekten zurückgegeben wird.|Beim Deserialisieren wird das Array mit [XmlAttribute](frlrfSystemXmlXmlAttributeClassTopic)\-Objekten gefüllt, die für alle im Schema unbekannten XML\-Attribute stehen.|  
|[XmlAnyElementAttribute](frlrfSystemXmlSerializationXmlAnyElementAttributeClassTopic)|Öffentliches Feld, Eigenschaft, Parameter oder Rückgabewert, wodurch ein Array von [XmlElement](frlrfSystemXmlXmlElementClassTopic)\-Objekten zurückgegeben wird.|Beim Deserialisieren wird das Array mit [XmlElement](frlrfSystemXmlXmlElementClassTopic)\-Objekten gefüllt, die für alle im Schema unbekannten XML\-Elemente stehen.|  
|[XmlArrayAttribute](frlrfSystemXmlSerializationXmlArrayAttributeClassTopic)|Öffentliches Feld, Eigenschaft, Parameter oder Rückgabewert, wodurch ein Array von komplexen Objekten zurückgegeben wird.|Die Member des Arrays werden als Member eines XML\-Arrays generiert.|  
|[XmlArrayItemAttribute](frlrfSystemXmlSerializationXmlArrayItemAttributeClassTopic)|Öffentliches Feld, Eigenschaft, Parameter oder Rückgabewert, wodurch ein Array von komplexen Objekten zurückgegeben wird.|Die abgeleiteten Typen, die in ein Array eingefügt werden können.Wird in der Regel in Verbindung mit einem [XmlArrayAttribute](frlrfSystemXmlSerializationXmlArrayAttributeClassTopic)\-Objekt angewendet.|  
|[XmlAttributeAttribute](frlrfSystemXmlSerializationXmlAttributeAttributeClassTopic)|Öffentliches Feld, Eigenschaft, Parameter oder Rückgabewert.|Der Member wird als XML\-Attribut serialisiert.|  
|[XmlChoiceIdentifierAttribute](frlrfSystemXmlSerializationXmlChoiceIdentifierAttributeClassTopic)|Öffentliches Feld, Eigenschaft, Parameter oder Rückgabewert.|Der Member kann durch Verwendung einer Enumeration eindeutig bestimmt werden.|  
|[XmlElementAttribute](frlrfSystemXmlSerializationXmlElementAttributeClassTopic)|Öffentliches Feld, Eigenschaft, Parameter oder Rückgabewert.|Das Feld oder die Eigenschaft wird als XML\-Element serialisiert.|  
|[XmlEnumAttribute](frlrfSystemXmlSerializationXmlEnumAttributeClassTopic)|Öffentliches Feld, das ein Enumerationsbezeichner ist.|Der Elementname eines Enumerationsmembers.|  
|[XmlIgnoreAttribute](frlrfSystemXmlSerializationXmlIgnoreAttributeClassTopic)|Öffentliche Eigenschaften und Felder.|Die Eigenschaft oder das Feld sollte beim Serialisieren der Klasse, in dem sie bzw. es enthalten ist, ignoriert werden.|  
|[XmlIncludeAttribute](frlrfSystemXmlSerializationXmlIncludeAttributeClassTopic)|Öffentlich abgeleitete Klassendeklarationen und Rückgabewerte von öffentlichen Methoden für WSDL\-Dokumente \(Web Services Description Language\).|Diese Klasse sollte beim Generieren von Schemas enthalten sein \(und wird daher bei der Serialisierung erkannt\).|  
|[XmlRootAttribute](frlrfSystemXmlSerializationXmlRootAttributeClassTopic)|Deklarationen öffentlicher Klassen.|Steuert die XML\-Serialisierung des Attributziels als XML\-Stammelement.Mit diesem Attribut können Sie Namespace und Elementnamen genauer angeben.|  
|[XmlTextAttribute](frlrfSystemXmlSerializationXmlTextAttributeClassTopic)|Öffentliche Eigenschaften und Felder.|Die Eigenschaft oder das Feld sollte als XML\-Text serialisiert werden.|  
|[XmlTypeAttribute](frlrfSystemXmlSerializationXmlTypeAttributeClassTopic)|Deklarationen öffentlicher Klassen.|Der Name und Namespace des XML\-Typs.|  
  
 Zusätzlich zu diesen Attributen, die sich alle im [System.Xml.Serialization](frlrfSystemxmlserialization)\-Namespace befinden, können Sie auch das [System.ComponentModel.DefaultValueAttribute](frlrfSystemComponentModelDefaultValueAttributeClassTopic)\-Attribut auf ein Feld anwenden.Durch **DefaultValueAttribute** wird der Wert festgelegt, der dem Member automatisch zugewiesen wird, falls kein Wert angegeben wurde.  
  
 Informationen zur Steuerung der XML\-Serialisierung von codiertem SOAP finden Sie unter [Attribute zur Steuerung der Serialisierung von codiertem SOAP](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
## Siehe auch  
 [XML\- und SOAP\-Serialisierung](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [Steuern der XML\-Serialisierung mit Attributen](../../../docs/framework/serialization/controlling-xml-serialization-using-attributes.md)   
 [Vorgehensweise: Angeben eines alternativen Elementnamens für einen XML\-Stream](../../../docs/framework/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)   
 [Vorgehensweise: Serialisieren eines Objekts](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Vorgehensweise: Deserialisieren eines Objekts](../../../docs/framework/serialization/how-to-deserialize-an-object.md)