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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152840"
---
# <a name="systemweb-element-web-settings"></a>\<system.web>-Element (Webeinstellungen)
Enthält Informationen dazu, wie die ASP.net-hostingschicht Prozess weites Verhalten verwaltet.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.web>**  
  
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
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|Gibt Konfigurationseinstellungen für IIS-Anwendungs Pools in einer ASPNET. config-Datei an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Gibt das Stamm Element in jeder Konfigurationsdatei an, die von den Common Language Runtime-und .NET Framework Anwendungen verwendet wird.|  
  
## <a name="remarks"></a>Bemerkungen  

Das `system.web` -Element und das zugehörige `applicationPool` untergeordnete Element wurden der .NET Framework ab .NET Framework 3,5 SP1 hinzugefügt. Wenn Sie IIS 7,0 oder höhere Versionen im integrierten Modus ausführen, können Sie mit dieser Element Kombination konfigurieren, wie ASP.NET Threads verwaltet und wie Anforderungen in die Warteschlange eingereiht werden, wenn ASP.net in einem IIS-Anwendungs Pool gehostet wird. Wenn Sie IIS 7,0 oder höhere Versionen im klassischen oder ISAPI-Modus ausführen, werden diese Einstellungen ignoriert.  
  
## <a name="example"></a>Beispiel  

Das folgende Beispiel zeigt, wie Sie das Prozess weite Verhalten von ASP.net in der Datei Aspnet. config konfigurieren, wenn ASP.net in einem IIS-Anwendungs Pool gehostet wird. Im Beispiel wird davon ausgegangen, dass IIS im integrierten Modus ausgeführt wird und die Anwendung den .NET Framework 3,5 SP1 oder eine höhere Version verwendet. Dieses Verhalten tritt nicht in früheren Versionen .NET Framework von als der .NET Framework 3,5 SP1 auf. Bei den Werten im Beispiel handelt es sich um die Standardwerte.  
  
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

- [\<applicationPool>-Element (Webeinstellungen)](applicationpool-element-web-settings.md)
