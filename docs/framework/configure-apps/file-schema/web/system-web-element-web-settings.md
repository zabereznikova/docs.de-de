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
ms.openlocfilehash: b37b05bdf90630251cbfcf86751243a3a8b77663
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152840"
---
# <a name="systemweb-element-web-settings"></a>\<system.web> Element (Webeinstellungen)
Enthält Informationen darüber, wie der ASP.NET Hosting-Layer das prozessweite Verhalten verwaltet.  
  
[**\<Konfiguration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.web>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  

Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|Gibt Konfigurationseinstellungen für IIS-Anwendungspools in einer aspnet.config-Datei an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Konfiguration>](../configuration-element.md)|Gibt das Stammelement in jeder Konfigurationsdatei an, die von der Common Language Runtime und .NET Framework-Anwendungen verwendet wird.|  
  
## <a name="remarks"></a>Bemerkungen  

Das `system.web` Element und `applicationPool` das untergeordnete Element wurden dem .NET Framework als .NET Framework 3.5 SP1 hinzugefügt. Wenn Sie IIS 7.0 oder höher im integrierten Modus ausführen, können Sie mit dieser Elementkombination konfigurieren, wie ASP.NET Threads verwaltet und wie sie Anforderungen in die Warteschlange stellen, wenn ASP.NET in einem IIS-Anwendungspool gehostet wird. Wenn Sie IIS 7.0 oder neuere Versionen im Classic- oder ISAPI-Modus ausführen, werden diese Einstellungen ignoriert.  
  
## <a name="example"></a>Beispiel  

Das folgende Beispiel zeigt, wie ASP.NET prozessweiten Verhalten in der Datei aspnet.config konfiguriert wird, wenn ASP.NET in einem IIS-Anwendungspool gehostet wird. Im Beispiel wird davon ausgegangen, dass IIS im integrierten Modus ausgeführt wird und dass die Anwendung .NET Framework 3.5 SP1 oder eine neuere Version verwendet. Dieses Verhalten tritt nicht in Versionen von .NET Framework vor .NET Framework 3.5 SP1 auf. Die Werte im Beispiel sind die Standardwerte.  
  
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
|Name des Schemas||  
|Validierungsdatei||  
|Kann leer sein||  
  
## <a name="see-also"></a>Weitere Informationen

- [\<applicationPool> Element (Webeinstellungen)](applicationpool-element-web-settings.md)
