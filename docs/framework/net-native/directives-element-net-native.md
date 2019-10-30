---
title: <Directives>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: abe2e7221e0afb984a6178b12fabc36ea24deb35
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128470"
---
# <a name="directives-element-net-native"></a>\<-Direktiven > Element (.net Native)
Das Stamm Element in jeder laufzeitdirektivendatei für .net Native.  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a>Syntax  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`xmlns`|Der XML-Namespace. Der Wert ist immer **"http://schemas.microsoft.com/netfx/2013/01/metadata"** .|  
  
## <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Anwendung>](application-element-net-native.md)|Dient als Container für anwendungsweite Typen und Typmember, dessen Metadaten für die Reflektion verfügbar sind.|  
|[\<Library>](library-element-net-native.md)|Definiert die Assembly, deren untergeordneten Typen und Typmember Metadaten zur Laufzeit erfordern.|  
  
## <a name="remarks"></a>Hinweise  
 Jede Laufzeitanweisungsdatei darf nur ein `<Directives>`-Element enthalten.  
  
 Das `<Directives>`-Element kann null oder ein [\<Application>](application-element-net-native.md)-Element sowie null, ein oder mehrere [\<Library>](library-element-net-native.md)-Elemente enthalten.  
  
## <a name="see-also"></a>Siehe auch

- [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elemente der Laufzeitanweisung](runtime-directive-elements.md)
