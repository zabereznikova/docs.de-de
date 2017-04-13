---
title: "&lt;schemaImporterExtensions&gt;-Element | Microsoft Docs"
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
  - "<schemaImporterExtensions>-Element"
  - "schemaImporterExtensions-Element"
  - "XML-Serialisierung, Konfiguration"
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;schemaImporterExtensions&gt;-Element
Enthält Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>\-Klasse zum Zuordnen von XSD\-Typen zu .NET Framework\-Typen verwendet werden.  Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateischema](../../../docs/framework/configure-apps/file-schema/index.md).  
  
## Syntax  
  
```  
  
<schemaImporterExtensions>  
    <!-- Add types -->  
</SchemaImporterExtension>  
```  
  
## Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<add\>\-Element für \<xmlSchemaImporterExtensions\>](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)|Fügt Typen hinzu, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>\-Klasse verwendet werden, um Zuordnungen zu erstellen.|  
  
## Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<system.xml.serialization\>\-Element](../../../docs/framework/serialization/system-xml-serialization-element.md)|Das Element der obersten Ebene zur Steuerung der XML\-Serialisierung.|  
  
## Beispiel  
 Das folgende Codebeispiel veranschaulicht, wie Typen hinzugefügt werden, die von <xref:System.Xml.Serialization.XmlSchemaImporter> beim Zuordnen von XSD\-Typen zu .NET Framework\-Typen verwendet werden.  
  
```  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =   
        "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
/system.sxml.serializaiton>  
```  
  
## Siehe auch  
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>   
 [Konfigurationsdateischema](../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<dateTimeSerialization\>\-Element](../../../docs/framework/serialization/datetimeserialization-element.md)   
 [\<add\>\-Element für \<xmlSchemaImporterExtensions\>](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)   
 [\<system.xml.serialization\>\-Element](../../../docs/framework/serialization/system-xml-serialization-element.md)