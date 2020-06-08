---
title: <system.Net>-Element (Netzwerkeinstellungen)
description: Das <System.net> Network settings-Element enthält Einstellungen, die angeben, wie die .NET Framework eine Verbindung mit den Netzwerkoptionen in der .NET Framework herstellt.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 9f18c7a3586948c03391d609f437e216a91bc27f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504484"
---
# <a name="systemnet-element-network-settings"></a>\<system.Net>-Element (Netzwerkeinstellungen)
Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.net>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[authenticationModules](authenticationmodules-element-network-settings.md)|Gibt Module an, die zum Authentifizieren von Internet Anforderungen verwendet werden.|  
|[connectionManagement](connectionmanagement-element-network-settings.md)|Gibt die maximale Anzahl von Verbindungen mit einem Internet Host an.|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).|  
|[mailSettings](mailsettings-element-network-settings.md)|Konfiguriert SMTP (Simple Mail Transport Protocol)-e-Mail-Sende Optionen.|  
|[requestCaching](requestcaching-element-network-settings.md)|Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.|  
|[settings](settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für Klassen in den <xref:System.Net> zugehörigen untergeordneten Namespaces.|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|Gibt Module an, die zum Anfordern von Informationen von Internet Hosts verwendet werden sollen.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[configuration](../configuration-element.md)|Enthält Einstellungen für alle Namespaces.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das [\<system.net>](system-net-element-network-settings.md) -Element enthält Einstellungen für Klassen in den zugehörigen untergeordneten <xref:System.Net> Namespaces. Die Einstellungen konfigurieren Authentifizierungs Module, Verbindungs Verwaltung, e-Mail-Einstellungen, den Proxy Server und Internet Anforderungs Module zum Empfangen von Informationen von Internet Hosts.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine typische Konfiguration, die von-Klassen verwendet wird <xref:System.Net> .  
  
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
  
## <a name="see-also"></a>Weitere Informationen:

- [Netzwerkeinstellungsschema](index.md)
