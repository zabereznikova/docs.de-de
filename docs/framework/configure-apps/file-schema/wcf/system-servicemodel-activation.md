---
title: '&lt;system.serviceModel.activation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0cae85f-56cb-4030-8807-6f96edff8d2d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f15466e5ae0421f400d80f66370cb60f75c83990
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltsystemservicemodelactivationgt"></a><span data-ttu-id="f71f0-102">&lt;system.serviceModel.activation&gt;</span><span class="sxs-lookup"><span data-stu-id="f71f0-102">&lt;system.serviceModel.activation&gt;</span></span>
<span data-ttu-id="f71f0-103">Dieser Konfigurationsabschnitt stellt die Konfigurationseinstellungen für das Tool SMSvcHost.exe dar.</span><span class="sxs-lookup"><span data-stu-id="f71f0-103">This configuration section represents the configuration settings for the SMSvcHost.exe tool.</span></span> <span data-ttu-id="f71f0-104">Die Konfigurationselemente können in der SMSvcHost.exe.config-Datei konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f71f0-104">The configuration elements can be configured in the SMSvcHost.exe.config file.</span></span> <span data-ttu-id="f71f0-105">Sie enthält insbesondere alle computerweiten Einstellungen, die konfiguriert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f71f0-105">Specifically, it includes all machine-wide settings that must be configured.</span></span>  
  
## <a name="sample-configuration-file"></a><span data-ttu-id="f71f0-106">Beispielkonfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="f71f0-106">Sample Configuration File</span></span>  
 <span data-ttu-id="f71f0-107">Die folgende Beispielkonfigurationsdatei (SMSvcHost.exe.config) wird vom Listener-Vorgang SMSvcHost.exe verwendet.</span><span class="sxs-lookup"><span data-stu-id="f71f0-107">The following is a sample configuration file (SMSvcHost.exe.config), which is used by the listener process SMSvcHost.exe.</span></span>  
  
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
       </net.pipe>  
       <diagnostics performanceCountersEnabled="true" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f71f0-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f71f0-108">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration>
