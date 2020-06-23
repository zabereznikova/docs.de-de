---
title: <proxy>-Element (Netzwerkeinstellungen)
description: Das <proxy> Netzwerk Einstellungs Element definiert die Proxy Serveroptionen in der .NET Framework. Dieser Artikel enthält ein Beispiel.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 8ae30b8c29dcf3aaa183ff295c7ee8592322797f
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141780"
---
# <a name="proxy-element-network-settings"></a>\<proxy>-Element (Netzwerkeinstellungen)
Definiert einen Proxyserver.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

## <a name="syntax"></a>Syntax  
  
```xml  
<proxy
  autoDetect="True|False|Unspecified"
  bypassonlocal="True|False|Unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="True|False|Unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|`autoDetect`|Gibt an, ob der Proxy automatisch erkannt wird. Der Standardwert ist `Unspecified`.|  
|`bypassonlocal`|Gibt an, ob der Proxy für lokale Ressourcen umgangen wird. Lokale Ressourcen umfassen den lokalen Server ( `http://localhost` , `http://loopback` oder `http://127.0.0.1` ) und einen URI ohne einen Punkt ( `http://webserver` ). Der Standardwert ist `Unspecified`.|  
|`proxyaddress`|Gibt den zu verwendenden Proxy-URI an.|  
|`scriptLocation`|Gibt den Speicherort des Konfigurations Skripts an. Verwenden Sie das- `bypassonlocal` Attribut nicht mit diesem Attribut. |  
|`usesystemdefault`|Gibt an, ob Internet Explorer-Proxy Einstellungen verwendet werden sollen. Wenn diese Einstellung auf festgelegt `True` ist, überschreiben nachfolgende Attribute Internet Explorer-Proxy Einstellungen. Der Standardwert ist `Unspecified`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).|  
  
## <a name="text-value"></a>Textwert  
  
## <a name="remarks"></a>Hinweise  
 Das- `proxy` Element definiert einen Proxy Server für eine Anwendung. Wenn dieses Element in der Konfigurationsdatei fehlt, verwendet das .NET Framework die Proxy Einstellungen in Internet Explorer.  
  
 Der Wert für das- `proxyaddress` Attribut muss ein wohlgeformter URI (Uniform Resource Indicator) sein.  
  
 Das- `scriptLocation` Attribut verweist auf die automatische Erkennung von Proxy Konfigurations Skripts. Die <xref:System.Net.WebProxy> Klasse versucht, ein Konfigurationsskript (in der Regel mit dem Namen "WPAD. dat") zu suchen, wenn die Option " **Automatisches Konfigurationsskript verwenden** " in Internet Explorer ausgewählt ist. Wenn `bypassonlocal` auf einen beliebigen Wert festgelegt ist, `scriptLocation` wird ignoriert.
  
 Verwenden Sie das- `usesystemdefault` Attribut für .NET Framework Anwendungen der Version 1,1, die zu Version 2,0 migrieren.  
  
 Eine-Ausnahme wird ausgelöst, wenn das- `proxyaddress` Attribut einen ungültigen Standard Proxy angibt. Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Standardwerte aus dem Internet Explorer-Proxy verwendet, die Proxy Adresse angegeben und der Proxy für den lokalen Zugriff umgangen.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="True"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="True"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Netzwerkeinstellungsschema](index.md)
