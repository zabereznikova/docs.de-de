---
title: '&lt;RequestCaching&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 9c0c8d80182931f9ac14e687a337b7be55a5a9a5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743432"
---
# <a name="ltrequestcachinggt-element-network-settings"></a>&lt;RequestCaching&gt; -Element (Netzwerkeinstellungen)
Steuert den Zwischenspeichermechanismus für Anforderungen über das Netzwerk an.  
  
 \<configuration>  
\<system.net>  
\<RequestCaching >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
      <requestCaching>  
        isPrivateCache ="true|false"  
        disableAllCaching="true|false"  
        defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
        unspecifiedMaximumAge= "d.hh.mm.ss">  
          <defaultHttpCachePolicy> … </defaultHttpCachePolicy>  
          <defaultFtpCachePolicy> … </defaultFtpCachePolicy>  
      </requestCaching>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`isPrivateCache`|Gibt an, ob der Cache Isolation zwischen den Informationen von anderen Benutzern bereitstellt. Der Standardwert ist `true`. Dieser Wert sollte `false` für Anwendungen der mittleren Ebene.|  
|`disableAllCaching`|Gibt an, dass Zwischenspeichern für alle Webantworten deaktiviert ist und kann nicht programmgesteuert überschrieben werden.|  
|`defaultPolicyLevel`|Einer der Werte in der <xref:System.Net.Cache.RequestCacheLevel>-Enumeration. Der Standardwert ist `BypassCache`.|  
|`unspecifiedMaximumAge`|Gibt die Standardzeit, die nach der Inhalt als abgelaufen gekennzeichnet wird.|  
  
## <a name="policylevel-attribute"></a>PolicyLevel-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`Default`|Gibt die zwischengespeicherte Ressource zurück, wenn die Ressource frische ist und die Inhaltslänge genau wird den Ablauf, Änderung und Content-Length-Attribute vorhanden sind.|  
|`BypassCache`|Gibt die Ressource vom Server zurück.|  
|`CacheOnly`|Gibt die zwischengespeicherte Ressource zurück, wenn die Inhaltslänge vorhanden ist und der Größe des Eintrags übereinstimmt.|  
|`CacheIfAvailable`|Gibt die zwischengespeicherte Ressource zurück, wenn die Inhaltslänge bereitgestellt werden und der Größe des Eintrags übereinstimmt. Andernfalls wird die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben wird.|  
|`Revalidate`|Gibt die zwischengespeicherte Ressource zurück, wenn der Zeitstempel der zwischengespeicherten Ressource identisch mit dem Zeitstempel der Ressource auf dem Server ist; Andernfalls wird die Ressource wird vom Server, im Cache gespeicherten heruntergeladen und an den Aufrufer zurückgegeben wird.|  
|`Reload`|Die Ressource vom Server heruntergeladen, speichert ihn im Cache und die Ressource an den Aufrufer zurückgegeben.|  
|`NoCacheNoStore`|Wenn eine zwischengespeicherte Ressource vorhanden ist, wird er gelöscht. Die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben wird.|  
|`Revalidate`|Führt eine Anforderung mithilfe die zwischengespeicherte Kopie der Ressource, wenn der Zeitstempel der Zeitstempel der Ressource auf dem Server identisch ist. Andernfalls wird die Ressource wird heruntergeladen, vom Server an den Aufrufer angezeigt und im Cache gespeichert ist,|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[defaultHttpCachePolicy](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|Optionales Element.<br /><br /> Beschreibt, ob HTTP-caching aktiv ist und beschreibt die Standardcachingrichtlinie.|  
|[\<DefaultFtpCachePolicy >-Element (Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|Optionales Element.<br /><br /> Beschreibt, ob der FTP-caching ist aktiv und beschreibt die Standardcachingrichtlinie.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[System.NET](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.|  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie das caching vollständig deaktiviert wird.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
