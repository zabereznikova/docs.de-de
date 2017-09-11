---
title: "Entschärfung: minFreeMemoryPercentageToActiveService-Konfigurationseinstellung"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f7f228890476d45517a21bc09806538139c5e389
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-minfreememorypercentagetoactiveservice-configuration-setting"></a><span data-ttu-id="854df-102">Entschärfung: minFreeMemoryPercentageToActiveService-Konfigurationseinstellung</span><span class="sxs-lookup"><span data-stu-id="854df-102">Mitigation: minFreeMemoryPercentageToActiveService Configuration Setting</span></span>
<span data-ttu-id="854df-103">In [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] wird eine Ausnahme ausgelöst, wenn der verfügbare Arbeitsspeicher auf dem Webserver geringer ist als in der Konfigurationseinstellung [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) angegeben.</span><span class="sxs-lookup"><span data-stu-id="854df-103">In the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], an exception is thrown if the available memory on the web server is less than the percentage specified by the [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) configuration setting.</span></span> <span data-ttu-id="854df-104">In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] wurde diese Einstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="854df-104">In the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], this setting was ignored.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="854df-105">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="854df-105">Impact</span></span>  
 <span data-ttu-id="854df-106">In den meisten Fällen ist die Beachtung der Einstellung [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) wünschenswert: Sie verbessert die Systemstabilität, indem die <xref:System.OutOfMemoryException>-Ausnahmen verhindert werden, die auftreten können, wenn ein Windows Communication Foundation (WCF)-Dienst auf einem System gestartet wird, das über eingeschränkten Arbeitsspeicher verfügt.</span><span class="sxs-lookup"><span data-stu-id="854df-106">In most cases, the impact of observing the [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) setting is desirable: It improves system stability by preventing the <xref:System.OutOfMemoryException> exceptions that can occur when a Windows Communication Foundation (WCF) service is started on a system that has constrained memory.</span></span>  
  
 <span data-ttu-id="854df-107">In einigen Fällen jedoch kann ein bisher erfolgreich gestarteter Dienst aufgrund der Einstellung möglicherweise nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="854df-107">However, in some cases, a service that previously started successfully may be unable to start.</span></span> <span data-ttu-id="854df-108">In diesem Fall wird eine ausführliche Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="854df-108">In that case, a detailed error message appears:</span></span>  
  
```console
Memory gates checking failed because the free memory (nnnn bytes) is less than nn% of total memory. As a result, the service will not be available for incoming requests. To resolve this, either reduce the load on the machine or adjust the value of minFreeMemoryPercentageToActivateService on the serviceHostingEnvironment config element.
```
  
## <a name="mitigation"></a><span data-ttu-id="854df-109">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="854df-109">Mitigation</span></span>  
 <span data-ttu-id="854df-110">Um das vorherige Verhalten wiederherzustellen, bei dem die [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)-Einstellung ignoriert wurde, ändern Sie die web.config-Datei wie folgt:</span><span class="sxs-lookup"><span data-stu-id="854df-110">To revert to the previous behavior where the [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) setting was ignored, modify the web.config file as follows:</span></span>  
  
```xml
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"   
                           minFreeMemoryPercentageToActivateService="0">  
   <serviceActivations>  
   ...  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="see-also"></a><span data-ttu-id="854df-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="854df-111">See Also</span></span>  
 [<span data-ttu-id="854df-112">Änderungen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="854df-112">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)

