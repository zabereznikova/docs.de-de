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
ms.openlocfilehash: c5029a7d1e53c28d0abb232efdc3e0bd2c9658d4
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088422"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a>\<DefaultHttpCachePolicy >-Element (Netzwerkeinstellungen)
Beschreibt, ob HTTP-Zwischenspeicherung aktiviert ist, und beschreibt die Standard Cache Richtlinie.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<requestCaching >** ](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<DefaultHttpCachePolicy >**

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
|`maximumAge`|Gibt das maximale Zeitintervall an, nach dem ein zwischengespeichertes Objekt als abgelaufen gekennzeichnet wird.|  
|`maximumStale`|Gibt die maximale Zeit an, die nach der berechneten Aktualität liegt, bevor ein zwischengespeichertes Objekt als abgelaufen gekennzeichnet wird.|  
|`minimumFresh`|Gibt die minimale Zeit an, für die ein zwischengespeichertes Objekt als aktuell angesehen wird.|  
|`policyLevel`|Gibt an, ob die Cachingrichtlinie automatisch erfolgt oder ob der Cache umgangen wird. Der Standardwert ist `BypassCache`sein.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[requestCaching](requestcaching-element-network-settings.md)|Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.|  
  
## <a name="remarks"></a>Hinweise  
 Der Wert für das `policyLevel`-Attribut ist entweder `BypassCache` oder `Default`.  
  
 Werte für die Elemente `maximumAge`, `maximumStale`und `minimumFresh` sind entweder ein explizites Zeitintervall mit dem Format *d*. *HH*:*mm*:*SS* (Tage, Stunden, Minuten und Sekunden) oder die Konstanten `minValue` oder `maxValue`entsprechend aus.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie eine minimale neue Zeit von sechs Stunden, eine maximale Alters Zeit von zwei Tagen und eine maximale veraltete Zeit von vier Stunden angegeben wird.  
  
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
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
