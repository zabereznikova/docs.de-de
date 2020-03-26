---
title: <xmlSerializer>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: b83ecda30bba8af1f3175eb6ad08593b07a80e6c
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249538"
---
# <a name="xmlserializer-element"></a>\<xmlSerializer> Element
Gibt an, ob eine zusätzliche Zustandsüberprüfung für <xref:System.Xml.Serialization.XmlSerializer> durchgeführt wird.  
  
 \<configuration>  
\<system.xml.serialization>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**checkDeserializeAdvances**|Gibt an, ob der Zustand von <xref:System.Xml.Serialization.XmlSerializer> überprüft wird. Legen Sie das Attribut auf "true" oder "false" fest. Der Standardwert ist "true".|  
|**useLegacySerializationGeneration**|Gibt an, ob <xref:System.Xml.Serialization.XmlSerializer> eine Vorgänger-Serialisierungsgenerierung verwendet, die Assemblys generiert, indem C#-Code in eine Datei geschrieben und anschließend in eine Assembly kompiliert wird. Der Standardwert ist **false**.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.xml.serialization> Element](../../../docs/standard/serialization/system-xml-serialization-element.md)|Enthält Konfigurationseinstellungen für die <xref:System.Xml.Serialization.XmlSerializer>-Klasse und die <xref:System.Xml.Serialization.XmlSchemaImporter>-Klasse.|  
  
## <a name="remarks"></a>Bemerkungen  
 Standardmäßig bietet <xref:System.Xml.Serialization.XmlSerializer> eine zusätzliche Sicherheitsebene, um mögliche Denial-of-Service-Angriffe beim Serialisieren nicht vertrauenswürdiger Daten zu verhindern. Hierzu wird während der Deserialisierung versucht, Endlosschleifen zu erkennen. Wenn eine solche Bedingung erkannt wird, wird eine Ausnahme ausgelöst und folgende Meldung ausgegeben: "Interner Fehler: Deserialisierung des zugrunde liegenden Streams konnte nicht fortgesetzt werden."  
  
 Diese Meldung bedeutet nicht unbedingt, dass gerade ein Denial-of-Service-Angriff ausgeführt wird. In einigen seltenen Fällen erzeugt der Erkennungsmechanismus für Endlosschleifen einen falschen positiven Wert und die Ausnahme wird aufgrund einer zulässigen eingehenden Meldung ausgelöst. Wenn in Ihrer Anwendung zulässige Meldungen durch diese zusätzliche Sicherheitsebene verweigert werden, legen Sie das **checkDeserializeAdvances**-Attribut auf FALSE fest.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird das **checkDeserializeAdvances**-Attribut auf FALSE festgelegt.  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Serialization.XmlSerializer>
- [\<system.xml.serialization> Element](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [XML- und SOAP-Serialisierung](../../../docs/standard/serialization/xml-and-soap-serialization.md)
