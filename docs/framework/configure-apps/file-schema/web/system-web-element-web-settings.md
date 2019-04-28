---
title: <system.web>-Element (Webeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: 50566422c5e28585e93171c991144cf12a6866eb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698498"
---
# <a name="systemweb-element-web-settings"></a>\<System.Web >-Element (Webeinstellungen)
Enthält Informationen dazu, wie die hostingebene von ASP.NET prozessübergreifende Verhalten verwaltet.  
  
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
|[\<applicationPool>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Gibt Konfigurationseinstellungen für die IIS-Anwendungspools in eine Datei "aspnet.config" an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Gibt das Stammelement in jeder Konfigurationsdatei an, die von der Common Language Runtime und den [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] -Anwendungen verwendet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `system.web` Element und dessen untergeordnete `applicationPool` Element wurden hinzugefügt, um die [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] als [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]. Beim Ausführen von [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder höher im integrierten Modus, diese Kombination von Element ermöglicht das Konfigurieren, wie ASP.NET Threads verwaltet, und wie diese Anforderungen Warteschlangen, wenn ASP.NET in einem IIS-Anwendungspool gehostet wird. Wenn das Ausführen [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder höhere Versionen im klassischen Bereitstellungsmodell oder ISAPI-Modus werden diese Einstellungen ignoriert.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie ASP.NET prozessübergreifende Verhalten in der Datei "aspnet.config" konfigurieren, wenn ASP.NET in einem IIS-Anwendungspool gehostet wird. Im Beispiel wird davon ausgegangen, dass IIS, im integrierten ausgeführt wird Modus und dass die Anwendung verwendet die [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] oder eine höhere Version. Dieses Verhalten tritt nicht in Versionen von der [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] älter als die [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]. Die Werte im Beispiel werden die Standardwerte.  
  
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

- [\<applicationPool>-Element (Webeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
