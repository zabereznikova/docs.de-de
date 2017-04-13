---
title: "&lt;Richtlinien&gt; Element (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# &lt;Richtlinien&gt; Element (.NET Native)
Das Stammelement in jeder Laufzeitdirektivendatei für [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
 **\<Directives xmlns\="http:\/\/schemas.microsoft.com\/netfx\/2013\/01\/metadata"\>**  
  
## Syntax  
  
```xml  
  
        <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`xmlns`|Der XML\-Namespace.  Der Wert ist immer **"http:\/\/schemas.microsoft.com\/netfx\/2013\/01\/metadata"**.|  
  
## Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Application\>](../../../docs/framework/net-native/application-element-net-native.md)|Dient als Container für anwendungsweite Typen und Typmember, dessen Metadaten für die Reflektion verfügbar sind.|  
|[\<Library\>](../../../docs/framework/net-native/library-element-net-native.md)|Definiert die Assembly, deren untergeordneten Typen und Typmember Metadaten zur Laufzeit erfordern.|  
  
## Hinweise  
 Jede Laufzeitdirektivendatei darf nur ein `<Directives>`\-Element enthalten.  
  
 Das `<Directives>`\-Element kann null oder ein [\<Application\>](../../../docs/framework/net-native/application-element-net-native.md)\-Element sowie null, ein oder mehrere [\<Library\>](../../../docs/framework/net-native/library-element-net-native.md)\-Elemente enthalten.  
  
## Siehe auch  
 [Laufzeitdirektiven\-Konfigurationsdatei \(rd.xml\) Referenz](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Elemente der Laufzeitrichtlinie](../../../docs/framework/net-native/runtime-directive-elements.md)