---
title: <system.Net>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 810e942394c75c192e4423afe4c674ef3a2b9900
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697510"
---
# <a name="systemnet-element-network-settings"></a>\<system.Net>-Element (Netzwerkeinstellungen)
Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp; **\<System. net >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 None.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[authenticationModules](authenticationmodules-element-network-settings.md)|Gibt Module an, die zum Authentifizieren von Internet Anforderungen verwendet werden.|  
|[connectionManagement](connectionmanagement-element-network-settings.md)|Gibt die maximale Anzahl von Verbindungen mit einem Internet Host an.|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).|  
|[mailSettings](mailsettings-element-network-settings.md)|Konfiguriert SMTP (Simple Mail Transport Protocol)-e-Mail-Sende Optionen.|  
|[requestCaching](requestcaching-element-network-settings.md)|Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.|  
|[settings](settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für Klassen in den <xref:System.Net> und verwandten untergeordneten Namespaces.|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|Gibt Module an, die zum Anfordern von Informationen von Internet Hosts verwendet werden sollen.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[configuration](../configuration-element.md)|Enthält Einstellungen für alle Namespaces.|  
  
## <a name="remarks"></a>Hinweise  
 Das [\<System. net >](system-net-element-network-settings.md) -Element enthält Einstellungen für Klassen im <xref:System.Net> und verwandten untergeordneten Namespaces. Die Einstellungen konfigurieren Authentifizierungs Module, Verbindungs Verwaltung, e-Mail-Einstellungen, den Proxy Server und Internet Anforderungs Module zum Empfangen von Informationen von Internet Hosts.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine typische Konfiguration, die von <xref:System.Net>-Klassen verwendet wird.  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
