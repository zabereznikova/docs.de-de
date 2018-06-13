---
title: '&lt;System.Web&gt; Element (Webeinstellungen)'
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7527ee9e7528a0da47529bae93e8112705e03a36
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755161"
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
