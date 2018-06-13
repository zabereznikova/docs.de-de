---
title: '&lt;Einstellungen&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3f717705a6cd4cc29fe333f5012c7fec466d350b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752477"
---
# <a name="ltsettingsgt-element-network-settings"></a>&lt;Einstellungen&gt; -Element (Netzwerkeinstellungen)
Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net?displayProperty=nameWithType>-Namespace.  
  
 \<configuration>  
\<system.net>  
\<settings>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<settings>  
  <httpListener> … </httpListener>  
  <httpWebRequest> … </httpWebRequest>  
  <ipv6> … </ipv6>  
  <performanceCounters> … </performanceCounters>  
  <servicePointManager> … </servicePointManager>  
  <socket> … </socket>  
  <webProxyScript> … </webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[HttpListener](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|Passt die vom verwendeten Parameter an die <xref:System.Net.HttpListener> Klasse.|  
|[HttpWebRequest-Anforderung](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|Passt die Anforderungsparameter werden Web an.|  
|[IPv6](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|Ermöglicht Internetprotokoll Version 6 (IPv6) unterstützen.|  
|[\<PerformanceCounter >-Element (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|Ermöglicht das Netzwerk-Leistungsindikatoren.|  
|[servicePointManager](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|Konfiguriert die Verbindungen mit Netzwerkressourcen.|  
|[Socket](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|Gibt an, ob es sich bei Socketvorgänge Abschlussports verwenden.|  
|[\<WebProxyScript >-Element (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|Konfiguriert die Eigenschaften des Skripts verwendet, um Webproxys zu ermitteln.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[System.NET](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Net?displayProperty=nameWithType>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
