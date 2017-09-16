---
title: '&lt;Ereignis&gt; Element (.NET Native)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3ea3a4233ca0b01cd4b6ebd328387fea1dd189de
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="lteventgt-element-net-native"></a>&lt;Ereignis&gt; Element (.NET Native)
Wendet eine Laufzeitreflektionsrichtlinie auf ein Ereignis an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<Event Name="event_name"   
       Browse="policy_type"   
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Attributtyp|Beschreibung|  
|---------------|--------------------|-----------------|  
|`Name`|Allgemein|Erforderliches Attribut. Gibt den Ereignisnamen an.|  
|`Browse`|Spiegelung|Optionales Attribut. Steuert das Abfragen nach Informationen über das Ereignis oder das Auflisten des Ereignisses, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.|  
|`Dynamic`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf das Ereignis, um dynamische Programmierung zu ermöglichen. Diese Richtlinie stellt sicher, dass ein Ereignis dynamisch zur Laufzeit behandelt werden kann.|  
  
## <a name="name-attribute"></a>Namensattribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*method_name*|Der Name des Ereignisses. Der Typ des Ereignisses wird durch das übergeordnete [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- oder [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Element definiert.|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp für das Ereignis angewendet werden soll. Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`. Weitere Informationen finden Sie unter [Runtime Directive Policy Settings (Richtlinieneinstellungen für die Laufzeitanweisungen)](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Richtlinie eines Ereignisses nicht explizit definiert ist, erbt es die Laufzeitrichtlinie des übergeordneten Elements.  
  
## <a name="see-also"></a>Siehe auch  
 [Runtime Directives (rd.xml) Configuration File Reference (Verweis auf die Konfigurationsdatei der Laufzeitanweisungen (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Runtime Directive Elements (Elemente der Laufzeitanweisung)](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [Runtime Directive Policy Settings (Richtlinieneinstellungen für die Laufzeitanweisung)](../../../docs/framework/net-native/runtime-directive-policy-settings.md)

