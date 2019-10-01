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
ms.openlocfilehash: 94858f141e7d540454fca9c151c760c37f9ebbb0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697946"
---
# <a name="proxy-element-network-settings"></a>\<proxy >-Element (Netzwerkeinstellungen)
Definiert einen Proxyserver.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<defaultproxy >** ](defaultproxy-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<proxy >**  
  
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
|`autoDetect`|Gibt an, ob der Proxy automatisch erkannt wird. Der Standardwert ist `unspecified`sein.|  
|`bypassonlocal`|Gibt an, ob der Proxy für lokale Ressourcen umgangen wird. Lokale Ressourcen umfassen den lokalen Server (`http://localhost`, `http://loopback` oder `http://127.0.0.1`) und einen URI ohne einen Punkt (`http://webserver`). Der Standardwert ist `unspecified`sein.|  
|`proxyaddress`|Gibt den zu verwendenden Proxy-URI an.|  
|`scriptLocation`|Gibt den Speicherort des Konfigurations Skripts an. Verwenden Sie das Attribut "`bypassonlocal`" nicht mit diesem Attribut. |  
|`usesystemdefault`|Gibt an, ob Internet Explorer-Proxy Einstellungen verwendet werden sollen. Wenn `true` festgelegt ist, überschreiben nachfolgende Attribute die Internet Explorer-Proxy Einstellungen. Der Standardwert ist `unspecified`sein.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).|  
  
## <a name="text-value"></a>Textwert  
  
## <a name="remarks"></a>Hinweise  
 Das `proxy`-Element definiert einen Proxy Server für eine Anwendung. Wenn dieses Element in der Konfigurationsdatei fehlt, verwendet das .NET Framework die Proxy Einstellungen in Internet Explorer.  
  
 Der Wert für das `proxyaddress`-Attribut sollte ein wohlgeformter URI (Uniform Resource Indicator) sein.  
  
 Das Attribut "`scriptLocation`" bezieht sich auf die automatische Erkennung von Proxy Konfigurations Skripts. Die <xref:System.Net.WebProxy>-Klasse versucht, ein Konfigurationsskript (in der Regel mit dem Namen "WPAD. dat") zu suchen, wenn die Option " **Automatisches Konfigurationsskript verwenden** " in Internet Explorer ausgewählt ist. Wenn `bypassonlocal` auf einen beliebigen Wert festgelegt ist, wird `scriptLocation` ignoriert.
  
 Verwenden Sie das `usesystemdefault`-Attribut für .NET Framework Version 1,1-Anwendungen, die zu Version 2,0 migriert werden.  
  
 Eine-Ausnahme wird ausgelöst, wenn das `proxyaddress`-Attribut einen ungültigen Standard Proxy angibt. Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.  
  
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
