---
title: '&lt;System.Web&gt; Element (Webeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 59899178fd9fc8da2334883ed62d9f8655eb335b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltsystemwebgt-element-web-settings"></a>&lt;System.Web&gt; Element (Webeinstellungen)
Enthält Informationen dazu, wie die Hostebene ASP.NET prozessübergreifende Verhalten verwaltet.  
  
 \<configuration>  
\<System.Web >-Element (Webeinstellungen)  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<applicationPool>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Gibt Konfigurationseinstellungen für IIS-Anwendungspools in aspnet.config-Datei an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Gibt das Stammelement in jeder Konfigurationsdatei an, die von der Common Language Runtime und den [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] -Anwendungen verwendet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `system.web` -Elements und seines untergeordneten `applicationPool` Element wurden hinzugefügt, um die [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] ab [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]. Bei der Ausführung [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder höheren Versionen im integrierten Modus Kombination aus diesem Element können Sie konfigurieren, wie diese Anforderungen Warteschlange, wenn ASP.NET in einem IIS-Anwendungspool gehostet wird und wie ASP.NET Threads verwaltet. Wenn das Ausführen [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder höheren Versionen im klassischen Modus oder den ISAPI-Modus, werden diese Einstellungen ignoriert.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie ASP.NET prozessübergreifende Verhalten in aspnet.config-Datei konfigurieren, wenn ASP.NET in einem IIS-Anwendungspool gehostet wird. Im Beispiel wird davon ausgegangen, dass IIS, im integrierten ausgeführt wird Modus und, dass die Anwendung verwendet die [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] oder eine höhere Version. Dieses Verhalten tritt nicht in Versionen von der [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] älter als die [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]. Die Werte im Beispiel sind die Standardwerte.  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"   
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a>Elementinformationen  
  
|||  
|-|-|  
|Namespace||  
|Schemaname||  
|Validierungsdatei||  
|Leer kann sein||  
  
## <a name="see-also"></a>Siehe auch  
 [\<applicationPool>-Element (Webeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
