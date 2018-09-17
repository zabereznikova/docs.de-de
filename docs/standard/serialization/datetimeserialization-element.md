---
title: '&lt;dateTimeSerialization&gt;-Element'
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: cd275cdbc51c86b1d774058db839c38349b319a6
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45963839"
---
# <a name="ltdatetimeserializationgt-element"></a>&lt;dateTimeSerialization&gt;-Element
Bestimmt den Serialisierungsmodus von <xref:System.DateTime>-Objekten.  
  
 \<configuration>  
\<dateTimeSerialization>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip" | "Local"  
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
 Wenn in den Versionen 1.0, 1.1, 2.0 und höheren Versionen von .NET Framework diese Eigenschaft auf **Local** festgelegt ist, werden <xref:System.DateTime>-Objekte immer entsprechend der Ortszeit formatiert. Das heißt, Ortszeitzoneninformationen sind in den serialisierten Daten immer enthalten. Legen Sie diese Eigenschaft auf **Local** fest, um die Kompatibilität mit früheren Versionen von .NET Framework sicherzustellen.  
  
 Wenn diese Eigenschaft in .NET Framework Version 2.0 und höher auf **Roundtrip** festgelegt ist, werden <xref:System.DateTime>-Objekte überprüft, um zu ermitteln, ob sie entsprechend einer lokalen Zeitzone, der UTC-Zone oder einer unbestimmten Zeitzone formatiert sind. Die <xref:System.DateTime>-Objekte werden dann so serialisiert, dass diese Informationen beibehalten werden. Dies ist das Standardverhalten, das für alle neuen Anwendungen empfohlen wird, die nicht mit älteren Versionen des Framework kommunizieren.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.DateTime>  
- <xref:System.Xml.Serialization.XmlSchemaImporter>  
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
- [Konfigurationsdateischema](../../../docs/framework/configure-apps/file-schema/index.md)  
- [\<schemaImporterExtensions>-Element](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
- [\<Hinzufügen >-Element für \<SchemaImporterExtensions >](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)  
- [\<system.xml.serialization>-Element](../../../docs/standard/serialization/system-xml-serialization-element.md)
