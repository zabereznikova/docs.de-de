---
title: <add>-Element für <schemaImporterExtensions>
description: Das <add>-Element fügt Typen hinzu, mit denen die XmlSchemaImporter-Klasse XSD-Typen .NET-Typen zuordnet.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: b8a0775e9d33d59606b1150aa9a1b3b1026d4b0b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726443"
---
# <a name="add-element-for-schemaimporterextensions"></a>\<add>-Element für \<schemaImporterExtensions>

Fügt Typen hinzu, die von <xref:System.Xml.Serialization.XmlSchemaImporter> verwendet werden, um XSD-Typen .NET-Typen zuzuordnen. Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../framework/configure-apps/file-schema/index.md).  
  
\<configuration>  
\<system.xml.serialization>  
\<schemaImporterExtensions>  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**name**|Ein einfacher Name, der zum Suchen der Instanz verwendet wird.|  
|**Typ**|Erforderlich. Gibt die Schemaerweiterungsklasse an, die hinzugefügt werden soll. Der Wert des **type**-Attributs muss sich in einer Zeile befinden und schließt den vollständigen Typnamen enthalten. Wenn die Assembly im globalen Assemblycache (GAC) gespeichert ist, muss außerdem die Version, die Kultur und das Token des öffentlichen Schlüssels der signierten Assembly enthalten sein.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|\<schemaImporterExtensions>|Enthält die Typen, die von der <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse verwendet werden.|  
  
## <a name="example"></a>Beispiel  

 Im folgenden Codebeispiel wird ein Erweiterungstyp hinzugefügt, den XmlSchemaImporter zum Zuordnen von Typen verwenden kann.  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <schemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
       PublicKeyToken=b03f5f7f11d50a3a" />
    </schemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [\<system.xml.serialization>-Element](system-xml-serialization-element.md)
- [\<schemaImporterExtensions>-Element](schemaimporterextensions-element.md)
