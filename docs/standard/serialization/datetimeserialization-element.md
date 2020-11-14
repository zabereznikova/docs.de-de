---
title: <dateTimeSerialization>-Element
description: In diesem Artikel wird das <dateTimeSerialization>-Element beschrieben, das den Serialisierungsmodus von DateTime-Objekten bestimmt.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 90ae911c8942fef7a9e8238921990b0a52a47ca0
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93281769"
---
# <a name="datetimeserialization-element"></a>\<dateTimeSerialization>-Element
Bestimmt den Serialisierungsmodus von <xref:System.DateTime>-Objekten.  
  
 \<configuration>  
\<dateTimeSerialization>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribute|Beschreibung|  
|----------------|-----------------|  
|`mode`|Dies ist optional. Gibt den Serialisierungsmodus an. Legen Sie hierfür einen der <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>-Werte fest. Der Standardwert ist **RoundTrip**.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|system.xml.serialization|Das Element der obersten Ebene zur Steuerung der XML-Serialisierung.|  
  
## <a name="remarks"></a>Hinweise  

Wenn diese Eigenschaft auf **Local** festgelegt ist, werden <xref:System.DateTime>-Objekte stets mit der Ortszeit formatiert. Das heißt, Ortszeitzoneninformationen sind in den serialisierten Daten immer enthalten.
  
Wenn diese Eigenschaft auf **Roundtrip** festgelegt ist, werden <xref:System.DateTime>-Objekte überprüft, um zu bestimmen, ob sie sich in der lokalen, UTC- oder einer nicht angegebenen Zeitzone befinden. Die <xref:System.DateTime>-Objekte werden dann so serialisiert, dass diese Informationen beibehalten werden. Dies ist das Standardverhalten, das für alle neuen Anwendungen empfohlen wird, die nicht mit älteren Versionen des Framework kommunizieren.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [Konfigurationsdateischema](../../framework/configure-apps/file-schema/index.md)
- [\<schemaImporterExtensions>-Element](schemaimporterextensions-element.md)
- [\<add>-Element für \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md)
- [\<system.xml.serialization>-Element](system-xml-serialization-element.md)
