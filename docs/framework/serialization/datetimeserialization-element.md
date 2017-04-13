---
title: "&lt;dateTimeSerialization&gt;-Element | Microsoft Docs"
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
  - "<dateTimeSerialization>-Element"
  - "dateTimeSerialization-Element"
  - "XML-Serialisierung, Konfiguration"
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;dateTimeSerialization&gt;-Element
Bestimmt den Serialisierungsmodus von <xref:System.DateTime>\-Objekten.  
  
## Syntax  
  
```  
  
<dateTimeSerialization  
    mode = "Roundtrip" | "Local"  
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|Beschreibung|  
|---------------|------------------|  
|`mode`|Dies ist optional.  Gibt den Serialisierungsmodus an.  Legen Sie hierfür einen der <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>\-Werte fest.  Die Standardeinstellung ist **RoundTrip**.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|system.xml.serialization|Das Element der obersten Ebene zur Steuerung der XML\-Serialisierung.|  
  
## Hinweise  
 Wenn in den Versionen 1.0, 1.1, 2.0 und höheren Versionen von .NET&\#160;Framework diese Eigenschaft auf **Local** festgelegt ist, werden <xref:System.DateTime>\-Objekte immer entsprechend der Ortszeit formatiert.  Das heißt, Ortszeitzoneninformationen sind in den serialisierten Daten immer enthalten.  Legen Sie diese Eigenschaft auf **Local** fest, um die Kompatibilität mit früheren Versionen von .NET&\#160;Framework sicherzustellen.  
  
 Wenn diese Eigenschaft in .NET&\#160;Framework Version&\#160;2.0 und höher auf **Roundtrip** festgelegt ist, werden <xref:System.DateTime>\-Objekte überprüft, um zu ermitteln, ob sie entsprechend einer lokalen Zeitzone, der UTC\-Zone oder einer unbestimmten Zeitzone formatiert sind.  Die <xref:System.DateTime>\-Objekte werden dann so serialisiert, dass diese Informationen beibehalten werden.  Dies ist das Standardverhalten, das für alle neuen Anwendungen empfohlen wird, die nicht mit älteren Versionen des Framework kommunizieren.  
  
## Siehe auch  
 <xref:System.DateTime>   
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>   
 [Konfigurationsdateischema](../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<schemaImporterExtensions\>\-Element](../../../docs/framework/serialization/schemaimporterextensions-element.md)   
 [\<add\>\-Element für \<xmlSchemaImporterExtensions\>](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)   
 [\<system.xml.serialization\>\-Element](../../../docs/framework/serialization/system-xml-serialization-element.md)