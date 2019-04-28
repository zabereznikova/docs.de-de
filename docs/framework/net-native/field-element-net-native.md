---
title: <Field> (Element (.NET Native)
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c58be27334bcb862367464475a4eade5e01bdbb2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61868539"
---
# <a name="field-element-net-native"></a>\<Feld > (Element (.NET Native)
Wendet eine Laufzeitreflektionrichtlinie auf ein Feld an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Attributtyp|Beschreibung|  
|---------------|--------------------|-----------------|  
|`Name`|Allgemein|Erforderliches Attribut. Gibt den Feldnamen an.|  
|`Browse`|Spiegelung|Optionales Attribut. Steuert das Abfragen nach Informationen über das Feld oder das Auflisten des Felds, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.|  
|`Dynamic`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf das Feld, um dynamische Programmierung zu ermöglichen. Diese Richtlinie stellt sicher, dass ein Feld zur Laufzeit dynamisch festgelegt oder abgerufen werden kann.|  
|`Serialize`|Serialisierung|Optionales Attribut. Steuert den Laufzeitzugriff auf ein Feld, damit Typinstanzen von Bibliotheken wie dem Newtonsoft JSON-Serialisierungsprogramm serialisiert werden können oder für die Datenbindung verwendet werden können.|  
  
## <a name="name-attribute"></a>Namensattribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*method_name*|Der Feldname. Der Typ des Felds wird durch das übergeordnete [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- oder [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Element definiert.|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp für das Feld angewendet werden soll. Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`. Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Richtlinie eines Felds nicht explizit definiert ist, erbt es die Laufzeitrichtlinie des übergeordneten Elements.  
  
## <a name="see-also"></a>Siehe auch

- [Elemente der Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-elements.md)
- [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
