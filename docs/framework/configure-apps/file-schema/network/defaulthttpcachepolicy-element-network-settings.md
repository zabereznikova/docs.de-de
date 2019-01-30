---
title: <defaultHttpCachePolicy>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: a48fa5e4a5768f97d3aeabebe4d594ec9f498ca2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260670"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a>\<DefaultHttpCachePolicy >-Element (Netzwerkeinstellungen)
Beschreibt, ob HTTP-Zwischenspeicherung aktiv ist und die Standardcachingrichtlinie beschreibt.  
  
 \<configuration>  
\<system.net>  
\<requestCaching>  
\<defaultHttpCachePolicy>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`maximumAge`|Gibt das maximale Zeitintervall an, bevor ein zwischengespeichertes Objekt als abgelaufen gekennzeichnet wird.|  
|`maximumStale`|Gibt die maximale Zeit nach der berechneten Aktualitätszeit, bevor ein zwischengespeichertes Objekt als abgelaufen gekennzeichnet wird.|  
|`minimumFresh`|Gibt die minimale Zeit für ein zwischengespeichertes Objekt, das als aktuell angesehen.|  
|`policyLevel`|Gibt an, ob die Cachingrichtlinie für automatische oder gibt an, ob der Cache umgangen wird. Der Standardwert ist `BypassCache`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Steuert den Zwischenspeichermechanismus für netzwerkanforderungen.|  
  
## <a name="remarks"></a>Hinweise  
 Der Wert für die `policyLevel` -Attribut ist entweder `BypassCache` oder `Default`.  
  
 Werte für die `maximumAge`, `maximumStale`, und `minimumFresh` Elemente sind ein explizites Zeitintervall im Format *d*. *Hh*:*mm*:*ss* (Tage, Stunden, Minuten und Sekunden), oder die Konstanten `minValue` oder `maxValue`je nach Bedarf.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie eine neue Zeit von sechs Stunden, ein maximales Alter zwei Tage, bis eine maximale veraltete Zeit von vier Stunden angeben.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
