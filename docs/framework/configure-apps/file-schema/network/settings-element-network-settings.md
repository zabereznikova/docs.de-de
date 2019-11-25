---
title: <settings>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: d510c445c585a36005ed415b14188efc4be03984
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089118"
---
# <a name="settings-element-network-settings"></a>\<Einstellungen > Element (Netzwerkeinstellungen)
Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net?displayProperty=nameWithType>-Namespace.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<Einstellungen >**

## <a name="syntax"></a>Syntax  
  
```xml  
<settings>  
  <httpListener>...</httpListener>  
  <httpWebRequest>...</httpWebRequest>  
  <ipv6>...</ipv6>  
  <performanceCounters>...</performanceCounters>  
  <servicePointManager>...</servicePointManager>  
  <socket>...</socket>  
  <webProxyScript>...</webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[httpListener](httplistener-element-network-settings.md)|Passt die Parameter an, die von der <xref:System.Net.HttpListener>-Klasse verwendet werden.|  
|[HttpWebRequest](httpwebrequest-element-network-settings.md)|Passt Webanforderungs Parameter an.|  
|[IPv6](ipv6-element-network-settings.md)|Aktiviert die IPv6-Unterstützung (Internet Protocol Version 6).|  
|[\<PerformanceCounter >-Element (Netzwerkeinstellungen)](performancecounter-element-network-settings.md)|Aktiviert Netzwerk Leistungsindikatoren.|  
|[ServicePointManager](servicepointmanager-element-network-settings.md)|Konfiguriert Verbindungen mit Netzwerkressourcen.|  
|[Glühbirne](socket-element-network-settings.md)|Gibt an, ob Socketvorgänge Beendigungs Ports verwenden.|  
|[\<WebProxyScript >-Element (Netzwerkeinstellungen)](webproxyscript-element-network-settings.md)|Konfiguriert die Merkmale des Skripts, das zum Ermitteln von Webproxys verwendet wird.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[system.net](system-net-element-network-settings.md)|Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Net?displayProperty=nameWithType>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
