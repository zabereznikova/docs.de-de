---
title: "Minderung: minFreeMemoryPercentageToActiveService-Konfigurationseinstellung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a7875f26-0da8-4afe-9846-7a21778f757b
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Minderung: minFreeMemoryPercentageToActiveService-Konfigurationseinstellung
In [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] wird eine Ausnahme ausgelöst, wenn der verfügbare Arbeitsspeicher auf dem Webserver geringer ist als in der Konfigurationseinstellung [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) angegeben.  In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] wurde diese Einstellung ignoriert.  
  
## Auswirkungen  
 In den meisten Fällen ist die Beachtung der Einstellung [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) wünschenswert: Sie verbessert die Systemstabilität, indem die <xref:System.OutOfMemoryException>\-Ausnahmen verhindert werden, die auftreten können, wenn ein Windows Communication Foundation \(WCF\)\-Dienst auf einem System gestartet wird, der über eingeschränkten Arbeitsspeicher verfügt.  
  
 In einigen Fällen jedoch kann ein bisher erfolgreich gestarteter Dienst aufgrund der Einstellung möglicherweise nicht gestartet werden.  In diesem Fall wird eine ausführliche Fehlermeldung angezeigt:  
  
```Output  
  
Fehler beim Prüfen der Speichergates. Der freie Arbeitsspeicher (nnnn Byte) ist kleiner als nn % des Gesamtspeichers.  Daher ist der Dienst nicht für eingehende Anforderungen verfügbar.  Um dies zu beheben, können Sie entweder die Arbeitslast auf dem Computer reduzieren oder den Wert von "minFreeMemoryPercentageToActivateService" im Konfigurationselement "serviceHostingEnvironment" anpassen.    
```  
  
## Minderung  
 Um das vorherige Verhalten wiederherzustellen, bei dem die [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)\-Einstellung ignoriert wurde, ändern Sie die web.config\-Datei wie folgt:  
  
```  
  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"   
                           minFreeMemoryPercentageToActivateService="0">  
   <serviceActivations>  
   ...  
   </serviceActivations>  
</serviceHostingEnvironment>  
  
```  
  
## Siehe auch  
 [Änderungen zur Laufzeit](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)