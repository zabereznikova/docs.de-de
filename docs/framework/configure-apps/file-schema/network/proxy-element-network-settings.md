---
title: '&lt;Proxy&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 3a6d5b080c74fbd3f6ebca9882c1667951cfcb91
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183672"
---
# <a name="ltproxygt-element-network-settings"></a>&lt;Proxy&gt; -Element (Netzwerkeinstellungen)
Definiert einen Proxyserver.  
  
 \<configuration>  
\<system.net>  
\<DefaultProxy >  
\<Proxy >  
  
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
  
### <a name="attributes"></a>Attribute  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|`autoDetect`|Gibt an, ob der Proxy automatisch erkannt wird. Der Standardwert ist `unspecified`.|  
|`bypassonlocal`|Gibt an, ob der Proxy für lokale Ressourcen umgangen wird. Lokale Ressourcen schließen Sie den lokalen Server (`http://localhost`, `http://loopback`, oder `http://127.0.0.1`) und einen URI ohne einen Punkt (`http://webserver`). Der Standardwert ist `unspecified`.|  
|`proxyaddress`|Gibt an, den Proxy-URI verwenden.|  
|`scriptLocation`|Gibt den Speicherort des Konfigurationsskripts. Verwenden Sie nicht die `bypassonlocal` Attribut mit diesem Attribut. |  
|`usesystemdefault`|Gibt an, ob Internet Explorer-Proxyeinstellungen verwendet werden soll. Wenn auf festgelegt `true`, aufeinanderfolgenden Attributen werden Internet Explorer-Proxy-Einstellungen außer Kraft setzen. Der Standardwert ist `unspecified`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).|  
  
## <a name="text-value"></a>Textwert  
  
## <a name="remarks"></a>Hinweise  
 Die `proxy` -Element definiert einen Proxyserver für eine Anwendung. Wenn dieses Element aus der Konfigurationsdatei fehlt, wird .NET Framework die Proxyeinstellungen in Internet Explorer verwenden.  
  
 Der Wert für die `proxyaddress` Attribut sollte eine wohlgeformte Uniform Resource Indicator (URI) sein.  
  
 Die `scriptLocation` -Attribut verweist auf die automatische Erkennung von Proxy-Konfigurationsskripts. Die <xref:System.Net.WebProxy> -Klasse versucht, ein Konfigurationsskript (üblicherweise Wpad.dat) beim Suchen der **Automatisches Konfigurationsskript verwenden** in Internet Explorer die Option ausgewählt ist. Wenn `bypassonlocal` festgelegt ist, auf einen beliebigen Wert, `scriptLocation` wird ignoriert.
  
 Verwenden der `usesystemdefault` -Attribut für .NET Framework Version 1.1-Anwendungen, die auf Version 2.0 migrieren.  
  
 Eine Ausnahme wird ausgelöst, wenn die `proxyaddress` -Attribut gibt einen ungültigen Standardproxy an. Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Grundursache des Fehlers enthalten.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel verwendet die Standardeinstellungen des Internet Explorer-Proxys, gibt die Proxyadresse und umgeht den Proxy für den lokalen Zugriff.  
  
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
  
## <a name="see-also"></a>Siehe auch  
- <xref:System.Net.WebProxy?displayProperty=nameWithType>  
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
