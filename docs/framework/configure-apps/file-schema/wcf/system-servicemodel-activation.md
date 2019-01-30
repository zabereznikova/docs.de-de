---
title: <system.serviceModel.activation>
ms.date: 03/30/2017
ms.assetid: c0cae85f-56cb-4030-8807-6f96edff8d2d
ms.openlocfilehash: ddb9c03c2d4ec17198719544fba9da989a6b0eb4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271147"
---
# <a name="systemservicemodelactivation"></a><span data-ttu-id="b6499-102">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="b6499-102">\<system.serviceModel.activation></span></span>
<span data-ttu-id="b6499-103">Dieser Konfigurationsabschnitt stellt die Konfigurationseinstellungen für das Tool SMSvcHost.exe dar.</span><span class="sxs-lookup"><span data-stu-id="b6499-103">This configuration section represents the configuration settings for the SMSvcHost.exe tool.</span></span> <span data-ttu-id="b6499-104">Die Konfigurationselemente können in der SMSvcHost.exe.config-Datei konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b6499-104">The configuration elements can be configured in the SMSvcHost.exe.config file.</span></span> <span data-ttu-id="b6499-105">Sie enthält insbesondere alle computerweiten Einstellungen, die konfiguriert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b6499-105">Specifically, it includes all machine-wide settings that must be configured.</span></span>  
  
## <a name="sample-configuration-file"></a><span data-ttu-id="b6499-106">Beispielkonfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="b6499-106">Sample Configuration File</span></span>  
 <span data-ttu-id="b6499-107">Die folgende Beispielkonfigurationsdatei (SMSvcHost.exe.config) wird vom Listener-Vorgang SMSvcHost.exe verwendet.</span><span class="sxs-lookup"><span data-stu-id="b6499-107">The following is a sample configuration file (SMSvcHost.exe.config), which is used by the listener process SMSvcHost.exe.</span></span>  
  
```xml  
<configuration>
  <runtime>
    <gcConcurrent enabled="false" />
  </runtime>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="10"
             maxPendingAccepts="2"
             maxPendingConnections="100"
             receiveTimeout="00:00:10"
             teredoEnabled="false">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
    <net.pipe maxConnectionsPendingDispatch="100"
              maxPendingAccepts="2"
              receiveTimeout="00:00:10">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
    <diagnostics performanceCountersEnabled="true" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="b6499-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6499-108">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration>
