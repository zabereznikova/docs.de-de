---
title: '&lt;Richtlinien&gt; Element (.NET Native)'
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd571255f924c9f3878c00a2bc01397d63e6d777
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33394445"
---
# <a name="ltdirectivesgt-element-net-native"></a>&lt;Richtlinien&gt; Element (.NET Native)
Das Stammelement in jeder Laufzeitdirektivendatei für [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
 **\<Direktiven Xmlns = "http://schemas.microsoft.com/netfx/2013/01/metadata" >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
      <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`xmlns`|Der XML-Namespace. Der Wert ist immer **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.|  
  
## <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Application>](../../../docs/framework/net-native/application-element-net-native.md)|Dient als Container für anwendungsweite Typen und Typmember, dessen Metadaten für die Reflektion verfügbar sind.|  
|[\<Library>](../../../docs/framework/net-native/library-element-net-native.md)|Definiert die Assembly, deren untergeordneten Typen und Typmember Metadaten zur Laufzeit erfordern.|  
  
## <a name="remarks"></a>Hinweise  
 Jede Laufzeitdirektivendatei darf nur ein `<Directives>`-Element enthalten.  
  
 Das `<Directives>`-Element kann null oder ein [\<Application>](../../../docs/framework/net-native/application-element-net-native.md)-Element sowie null, ein oder mehrere [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)-Elemente enthalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [Elemente der Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-elements.md)
