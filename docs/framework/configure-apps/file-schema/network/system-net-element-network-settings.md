---
title: '&lt;system.Net&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f9098ce379cbaf12f589270729018da399f282b0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltsystemnetgt-element-network-settings"></a>&lt;system.Net&gt; -Element (Netzwerkeinstellungen)
Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.  
  
 \<configuration>  
\<system.net>  
  
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
|[authenticationModules](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|Gibt die Module, die zum Authentifizieren von Anforderungen Internet verwendet.|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Gibt die maximale Anzahl von Verbindungen mit einem Internethost an.|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).|  
|[mailSettings](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Konfiguriert (SMTP, Simple Mail Transport Protocol) e-Mail-Sendeoptionen.|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Steuert den Zwischenspeichermechanismus für Anforderungen über das Netzwerk an.|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für Klassen in der <xref:System.Net> und zugehörigen untergeordneten Namespaces.|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Gibt die Module zu verwenden, um Informationen von Internethosts anfordern.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[Konfiguration](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Enthält Einstellungen für alle Namespaces.|  
  
## <a name="remarks"></a>Hinweise  
 Die [ \<system.net >](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) Element enthält die Einstellungen für Klassen in der <xref:System.Net> und zugehörigen untergeordneten Namespaces. Die Einstellungen konfigurieren Authentifizierungsmodule, verbindungsverwaltung, e-Mail-Einstellungen, die Proxy-Server und Internet Anforderung Module zum Empfangen von Informationen von Internethosts.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine typische Konfiguration von verwendet <xref:System.Net> Klassen.  
  
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
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
