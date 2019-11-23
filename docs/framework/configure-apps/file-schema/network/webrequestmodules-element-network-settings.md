---
title: <webRequestModules>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: e119d9ce1f8bb6f07f8050612550db459a2f065c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697460"
---
# <a name="webrequestmodules-element-network-settings"></a>\<webRequestModules >-Element (Netzwerkeinstellungen)
Gibt Module an, die zum Anfordern von Informationen von Netzwerk Hosts verwendet werden sollen.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 None.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[add](add-element-for-webrequestmodules-network-settings.md)|Fügt der Anwendung ein benutzerdefiniertes Webanforderungs Modul hinzu.|  
|[clear](clear-element-for-webrequestmodules-network-settings.md)|Entfernt alle registrierten Webanforderungs Module aus der Anwendung.|  
|[remove](remove-element-for-webrequestmodules-network-settings.md)|Entfernt ein benutzerdefiniertes Webanforderungs Modul aus der Anwendung.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[system.net](system-net-element-network-settings.md)|Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Das `webRequestModules`-Element registriert Nachfolger der <xref:System.Net.WebRequest>-Klasse, um Informationsanforderungen an Netzwerk Hosts zu verarbeiten. Webanforderungs Module müssen die <xref:System.Net.IWebRequestCreate>-Schnittstelle implementieren.  
  
 Die .NET Framework enthält Webanforderungs Module für URIs, die mit `http://`, `https://`und `file://`beginnen. Sie können die Standardmodule nur überschreiben, indem Sie ein benutzerdefiniertes Modul in der Konfigurationsdatei registrieren.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das http-Standardmodul registriert. Sie sollten die Werte für Version und PublicKeyToken durch die korrekten Werte für das angegebene Modul ersetzen.  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
