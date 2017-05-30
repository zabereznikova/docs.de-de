---
title: "Entschärfung: minFreeMemoryPercentageToActiveService-Konfigurationseinstellung | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7875f26-0da8-4afe-9846-7a21778f757b
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 783dd4fb28f1590722833ce9a456b9c2c76ecd80
ms.contentlocale: de-de
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-minfreememorypercentagetoactiveservice-configuration-setting"></a>Entschärfung: minFreeMemoryPercentageToActiveService-Konfigurationseinstellung
In [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] wird eine Ausnahme ausgelöst, wenn der verfügbare Arbeitsspeicher auf dem Webserver geringer ist als in der Konfigurationseinstellung [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) angegeben. In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] wurde diese Einstellung ignoriert.  
  
## <a name="impact"></a>Auswirkungen  
 In den meisten Fällen ist die Beachtung der Einstellung [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) wünschenswert: Sie verbessert die Systemstabilität, indem die <xref:System.OutOfMemoryException>-Ausnahmen verhindert werden, die auftreten können, wenn ein Windows Communication Foundation (WCF)-Dienst auf einem System gestartet wird, das über eingeschränkten Arbeitsspeicher verfügt.  
  
 In einigen Fällen jedoch kann ein bisher erfolgreich gestarteter Dienst aufgrund der Einstellung möglicherweise nicht gestartet werden. In diesem Fall wird eine ausführliche Fehlermeldung angezeigt:  
  
```console
Memory gates checking failed because the free memory (nnnn bytes) is less than nn% of total memory. As a result, the service will not be available for incoming requests. To resolve this, either reduce the load on the machine or adjust the value of minFreeMemoryPercentageToActivateService on the serviceHostingEnvironment config element.
```
  
## <a name="mitigation"></a>Problemumgehung  
 Um das vorherige Verhalten wiederherzustellen, bei dem die [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)-Einstellung ignoriert wurde, ändern Sie die web.config-Datei wie folgt:  
  
```xml
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"   
                           minFreeMemoryPercentageToActivateService="0">  
   <serviceActivations>  
   ...  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Änderungen zur Laufzeit](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)

