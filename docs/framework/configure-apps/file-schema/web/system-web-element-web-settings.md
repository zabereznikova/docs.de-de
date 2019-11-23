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
ms.openlocfilehash: 5c5c857d4494b6d78b819e56bae4213abc5e2035
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699089"
---
# <a name="systemweb-element-web-settings"></a>\<System. Web >-Element (Webeinstellungen)
Enthält Informationen dazu, wie die ASP.net-hostingschicht Prozess weites Verhalten verwaltet.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp; **\<System. Web >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  

None.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|Gibt Konfigurationseinstellungen für IIS-Anwendungs Pools in einer ASPNET. config-Datei an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Gibt das Stamm Element in jeder Konfigurationsdatei an, die von den Common Language Runtime-und .NET Framework Anwendungen verwendet wird.|  
  
## <a name="remarks"></a>Hinweise  

Das `system.web`-Element und sein untergeordnetes `applicationPool` Element wurden dem .NET Framework ab .NET Framework 3,5 SP1 hinzugefügt. Wenn Sie IIS 7,0 oder höhere Versionen im integrierten Modus ausführen, können Sie mit dieser Element Kombination konfigurieren, wie ASP.NET Threads verwaltet und wie Anforderungen in die Warteschlange eingereiht werden, wenn ASP.net in einem IIS-Anwendungs Pool gehostet wird. Wenn Sie IIS 7,0 oder höhere Versionen im klassischen oder ISAPI-Modus ausführen, werden diese Einstellungen ignoriert.  
  
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
|Schemaname||  
|Validierungsdatei||  
|Kann leer sein||  
  
## <a name="see-also"></a>Siehe auch

- [\<applicationPool>-Element (Webeinstellungen)](applicationpool-element-web-settings.md)
