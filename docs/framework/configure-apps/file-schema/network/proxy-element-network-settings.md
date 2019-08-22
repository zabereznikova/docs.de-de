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
ms.openlocfilehash: a183c4160c4cd55b05c5c23f7a10e3a1d1c74ea4
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659291"
---
# <a name="proxy-element-network-settings"></a>\<Proxy > Element (Netzwerkeinstellungen)
Definiert einen Proxyserver.  
  
 \<configuration>  
\<system.net>  
\<defaultProxy>  
\<proxy>  
  
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
|`bypassonlocal`|Gibt an, ob der Proxy für lokale Ressourcen umgangen wird. Lokale Ressourcen umfassen den lokalen Server (`http://localhost`, `http://loopback`oder `http://127.0.0.1`) und einen URI ohne einen Punkt (`http://webserver`). Der Standardwert ist `unspecified`.|  
|`proxyaddress`|Gibt den zu verwendenden Proxy-URI an.|  
|`scriptLocation`|Gibt den Speicherort des Konfigurations Skripts an. Verwenden Sie das `bypassonlocal` -Attribut nicht mit diesem Attribut. |  
|`usesystemdefault`|Gibt an, ob Internet Explorer-Proxy Einstellungen verwendet werden sollen. Wenn diese Einstellung `true`auf festgelegt ist, überschreiben nachfolgende Attribute Internet Explorer-Proxy Einstellungen. Der Standardwert ist `unspecified`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).|  
  
## <a name="text-value"></a>Textwert  
  
## <a name="remarks"></a>Hinweise  
 Das `proxy` -Element definiert einen Proxy Server für eine Anwendung. Wenn dieses Element in der Konfigurationsdatei fehlt, verwendet das .NET Framework die Proxy Einstellungen in Internet Explorer.  
  
 Der Wert für das `proxyaddress` -Attribut muss ein wohlgeformter URI (Uniform Resource Indicator) sein.  
  
 Das `scriptLocation` -Attribut verweist auf die automatische Erkennung von Proxy Konfigurations Skripts. Die <xref:System.Net.WebProxy> Klasse versucht, ein Konfigurationsskript (in der Regel mit dem Namen "WPAD. dat") zu suchen, wenn die Option " **Automatisches Konfigurationsskript verwenden** " in Internet Explorer ausgewählt ist. Wenn `bypassonlocal` auf einen beliebigen Wert festgelegt `scriptLocation` ist, wird ignoriert.
  
 Verwenden Sie `usesystemdefault` das-Attribut für .NET Framework Anwendungen der Version 1,1, die zu Version 2,0 migrieren.  
  
 Eine-Ausnahme wird ausgelöst, `proxyaddress` wenn das-Attribut einen ungültigen Standard Proxy angibt. Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Standardwerte aus dem Internet Explorer-Proxy verwendet, die Proxy Adresse angegeben und der Proxy für den lokalen Zugriff umgangen.  
  
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
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
