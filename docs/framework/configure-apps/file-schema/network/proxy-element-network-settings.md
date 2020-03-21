---
title: <proxy>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 590ea747c2fa9e5e85e5e9d05f6fb80fe60251d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154789"
---
# <a name="proxy-element-network-settings"></a>\<Proxy-> Element (Netzwerkeinstellungen)
Definiert einen Proxyserver.  

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Proxy->**

## <a name="syntax"></a>Syntax  
  
```xml  
<proxy
  autoDetect="true|false|unspecified"
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|`autoDetect`|Gibt an, ob der Proxy automatisch erkannt wird. Standardwert: `unspecified`.|  
|`bypassonlocal`|Gibt an, ob der Proxy für lokale Ressourcen umgangen wird. Zu den lokalen Ressourcen`http://localhost` `http://loopback`gehören `http://127.0.0.1`der lokale Server (`http://webserver`, oder ) und ein URI ohne Punkt ( ). Standardwert: `unspecified`.|  
|`proxyaddress`|Gibt den zu verwendenden Proxy-URI an.|  
|`scriptLocation`|Gibt den Speicherort des Konfigurationsskripts an. Verwenden Sie `bypassonlocal` das Attribut nicht mit diesem Attribut. |  
|`usesystemdefault`|Gibt an, ob Internet Explorer-Proxyeinstellungen verwendet werden sollen. Wenn auf `true`festgelegt, überschreiben nachfolgende Attribute die Internet Explorer-Proxyeinstellungen. Standardwert: `unspecified`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).|  
  
## <a name="text-value"></a>Textwert  
  
## <a name="remarks"></a>Bemerkungen  
 Das `proxy` Element definiert einen Proxyserver für eine Anwendung. Wenn dieses Element in der Konfigurationsdatei fehlt, verwendet .NET Framework die Proxyeinstellungen in Internet Explorer.  
  
 Der Wert `proxyaddress` für das Attribut sollte ein wohlgeformter URI (Uniform Resource Indicator) sein.  
  
 Das `scriptLocation` Attribut bezieht sich auf die automatische Erkennung von Proxykonfigurationsskripten. Die <xref:System.Net.WebProxy> Klasse versucht, ein Konfigurationsskript (normalerweise Wpad.dat genannt) zu finden, wenn die Option **Automatische sendekonfigurationsskript verwenden** in Internet Explorer ausgewählt ist. Wenn `bypassonlocal` auf einen Beliebigen `scriptLocation` Wert festgelegt ist, wird ignoriert.
  
 Verwenden `usesystemdefault` Sie das Attribut für .NET Framework Version 1.1-Anwendungen, die auf Version 2.0 migrieren.  
  
 Eine Ausnahme wird `proxyaddress` ausgelöst, wenn das Attribut einen ungültigen Standardproxy angibt. Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Standardeinstellungen des Internet Explorer-Proxys verwendet, die Proxyadresse angegeben und der Proxy für den lokalen Zugriff umgangen.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Netzwerkeinstellungsschema](index.md)
