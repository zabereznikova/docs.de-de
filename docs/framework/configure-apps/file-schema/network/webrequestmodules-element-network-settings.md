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
ms.openlocfilehash: 7f2805283f89e6165d336b3e593d34054e02115d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154542"
---
# <a name="webrequestmodules-element-network-settings"></a>\<webRequestModules>-Element (Netzwerkeinstellungen)
Gibt Module an, die zum Anfordern von Informationen von Netzwerkhosts verwendet werden sollen.  
  
[**\<Konfiguration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<webRequestModules>
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[Hinzufügen](add-element-for-webrequestmodules-network-settings.md)|Fügt der Anwendung ein benutzerdefiniertes Webanforderungsmodul hinzu.|  
|[Klar](clear-element-for-webrequestmodules-network-settings.md)|Entfernt alle registrierten Webanforderungsmodule aus der Anwendung.|  
|[Entfernen](remove-element-for-webrequestmodules-network-settings.md)|Entfernt ein benutzerdefiniertes Webanforderungsmodul aus der Anwendung.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[system.net](system-net-element-network-settings.md)|Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das `webRequestModules` Element registriert abhängige <xref:System.Net.WebRequest> Elemente der Klasse, um Informationsanforderungen an Netzwerkhosts zu verarbeiten. Webanforderungsmodule müssen <xref:System.Net.IWebRequestCreate> die Schnittstelle implementieren.  
  
 .NET Framework enthält Webanforderungsmodule für URIs, `http://` `https://` `file://`die mit beginnen, und . Sie können die Standardmodule nur überschreiben, indem Sie ein benutzerdefiniertes Modul in der Konfigurationsdatei registrieren.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das Standard-HTTP-Modul registriert. Sie sollten die Werte für Version und PublicKeyToken durch die richtigen Werte für das angegebene Modul ersetzen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [Netzwerkeinstellungsschema](index.md)
