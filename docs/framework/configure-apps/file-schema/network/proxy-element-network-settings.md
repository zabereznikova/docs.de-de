---
title: '&lt;Proxy&gt; -Element (Netzwerkeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7178527f369c698b0ab53aa41cb28dd0126436b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltproxygt-element-network-settings"></a>&lt;Proxy&gt; -Element (Netzwerkeinstellungen)
Definiert einen Proxyserver.  
  
 \<configuration>  
\<System.NET >  
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
|`bypassonlocal`|Gibt an, ob der Proxy für lokale Ressourcen umgangen wird. Lokale Ressourcen umfassen den lokalen Server (http://localhost, http://loopback oder http://127.0.0.1) und einen URI ohne einen Punkt (http://webserver). Der Standardwert ist `unspecified`.|  
|`proxyaddress`|Gibt den Proxy-URI verwendet.|  
|`scriptLocation`|Gibt den Speicherort des Konfigurationsskripts.|  
|`usesystemdefault`|Gibt an, ob Internet Explorer-Proxyeinstellungen verwendet werden soll. Wenn auf festgelegt `true`, überschreiben nachfolgende Attribute die Proxyeinstellungen in Internet Explorer. Der Standardwert ist `unspecified`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).|  
  
## <a name="text-value"></a>Textwert  
  
## <a name="remarks"></a>Hinweise  
 Die `proxy` -Element definiert einen Proxyserver für eine Anwendung. Wenn dieses Element aus der Konfigurationsdatei nicht vorhanden ist, wird .NET Framework die Proxyeinstellungen in Internet Explorer verwenden.  
  
 Der Wert für die `proxyaddress` Attribut muss eine wohlgeformte Uniform Resource Indicator (URI).  
  
 Die `scriptLocation` Attribut bezieht sich auf die automatische Erkennung von Proxy-Konfigurationsskripts. Die <xref:System.Net.WebProxy> Klasse versucht, ein Konfigurationsskript (üblicherweise Wpad.dat) beim Suchen der **Automatisches Konfigurationsskript verwenden** in Internet Explorer die Option ausgewählt ist.  
  
 Verwenden der `usesystemdefault` Attribut für .NET Framework Version 1.1-Clientanwendungen, die für Version 2.0 migrieren.  
  
 Eine Ausnahme wird ausgelöst, wenn die `proxyaddress` Attribut gibt eine ungültige Standardproxy an. Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel verwendet die Standardeinstellungen des Internet Explorer-Proxys, gibt die Adresse des Proxyservers an und umgeht den Proxy für den lokalen Zugriff.  
  
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
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
