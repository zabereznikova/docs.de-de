---
title: "&lt;system.xml.serialization&gt;-Element | Microsoft Docs"
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
  - "<system.xml.serialization>-Element"
  - "system.xml.serialization-Element"
  - "XML-Serialisierung, Konfiguration"
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;system.xml.serialization&gt;-Element
Das Element der obersten Ebene zur Steuerung der XML\-Serialisierung.  Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateischema](../../../docs/framework/configure-apps/file-schema/index.md).  
  
## Syntax  
  
```  
  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<dateTimeSerialization\>\-Element](../../../docs/framework/serialization/datetimeserialization-element.md)|Bestimmt den Serialisierungsmodus von <xref:System.DateTime>\-Objekten.|  
|[\<schemaImporterExtensions\>\-Element](../../../docs/framework/serialization/schemaimporterextensions-element.md)|Enthält Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>\-Klasse zum Zuordnen von XSD\-Typen zu .NET Framework\-Typen verwendet werden.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<configuration\>\-Element](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Das Stammelement in jeder Konfigurationsdatei, die von der Common Language Runtime und den .NET Framework\-Anwendungen verwendet wird.|  
  
## Beispiel  
 Das folgende Codebeispiel veranschaulicht, wie der Serialisierungsmodus eines <xref:System.DateTime>\-Objekts und das Hinzufügen von Typen, die von <xref:System.Xml.Serialization.XmlSchemaImporter> verwendet werden, beim Zuordnen von XSD\-Typen zu .NET Framework\-Typen festgelegt werden.  
  
```  
<system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
    <dateTimeSerialization mode = "Local" />  
    <schemaImporterExtensions>  
        <add   
        name = "MobileCapabilities"   
        type = "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neuutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.sxml.serialization>  
```  
  
## Siehe auch  
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>   
 [Konfigurationsdateischema](../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<dateTimeSerialization\>\-Element](../../../docs/framework/serialization/datetimeserialization-element.md)   
 [\<schemaImporterExtensions\>\-Element](../../../docs/framework/serialization/schemaimporterextensions-element.md)   
 [\<add\>\-Element für \<xmlSchemaImporterExtensions\>](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)