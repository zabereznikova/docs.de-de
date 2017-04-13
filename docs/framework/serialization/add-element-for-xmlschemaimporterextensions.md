---
title: "&lt;add&gt;-Element f&#252;r &lt;xmlSchemaImporterExtensions&gt; | Microsoft Docs"
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
  - "<add>-Element für <xmlSchemaImporterExtensions>"
  - "XML-Serialisierung, Konfiguration"
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;add&gt;-Element f&#252;r &lt;xmlSchemaImporterExtensions&gt;
Fügt Typen hinzu, die von <xref:System.Xml.Serialization.XmlSchemaImporter> verwendet werden, um XSD\-Typen .NET Framework\-Typen zuzuordnen.  Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateischema](../../../docs/framework/configure-apps/file-schema/index.md).  
  
 \<XmlSchemaImporterExtensions\>  
\<add\>  
  
## Syntax  
  
```  
  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|**name**|Ein einfacher Name, der zum Suchen der Instanz verwendet wird.|  
|**type**|Erforderlich.  Gibt die Schemaerweiterungsklasse an, die hinzugefügt werden soll.  Der Wert des **type**\-Attributs muss sich in einer Zeile befinden und schließt den vollständigen Typnamen enthalten.  Wenn die Assembly im globalen Assemblycache \(GAC\) gespeichert ist, muss außerdem die Version, die Kultur und das Token des öffentlichen Schlüssels der signierten Assembly enthalten sein.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|\<xmlSchemaImporterExtensions\>|Enthält die Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>\-Klasse verwendet werden.|  
  
## Beispiel  
 Im folgenden Codebeispiel wird ein Erweiterungstyp hinzugefügt, den XmlSchemaImporter zum Zuordnen von Typen verwenden kann.  
  
```  
<configuration>  
  <system.xml.serialization>  
    <xmlSchemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,   
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a" />   
    </xmlSchemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 [\<system.xml.serialization\>\-Element](../../../docs/framework/serialization/system-xml-serialization-element.md)   
 [\<schemaImporterExtensions\>\-Element](../../../docs/framework/serialization/schemaimporterextensions-element.md)