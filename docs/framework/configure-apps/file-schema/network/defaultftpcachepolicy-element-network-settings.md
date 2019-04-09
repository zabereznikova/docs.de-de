---
title: <defaultFtpCachePolicy> -Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
ms.openlocfilehash: 36d174beea58ff96674bd873bfbcb8be89591669
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132534"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a>\<DefaultFtpCachePolicy >-Element (Netzwerkeinstellungen)
Beschreibt, ob der FTP-caching ist aktiv und wird beschrieben, die Standardcachingrichtlinie.  
  
 \<configuration>  
\<system.net>  
\<requestCaching>  
\<defaultFtpCachePolicy>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`policyLevel`|Gibt die FTP-Cachingrichtlinie an. Der Standardwert ist `Default`.|  
  
## <a name="policylevel-attribute"></a>PolicyLevel-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`Default`|Gibt die zwischengespeicherte Ressource zurück, wenn die Ressource aktuell ist, die Inhaltslänge genau ist und den Ablauf, Änderungen und Content-Length-Attribute vorhanden sind.|  
|`BypassCache`|Gibt die Ressource vom Server zurück.|  
|`CacheOnly`|Gibt die zwischengespeicherte Ressource zurück, wenn die Inhaltslänge vorhanden ist und der Größe des Eintrags übereinstimmt.|  
|`CacheIfAvailable`|Gibt die zwischengespeicherte Ressource zurück, wenn die Inhaltslänge bereitgestellt wird und der Größe des Eintrags übereinstimmt. Andernfalls wird die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben wird.|  
|`Revalidate`|Gibt die zwischengespeicherte Ressource zurück, wenn es sich bei der Timestamp der zwischengespeicherten Ressource dem Timestamp der Ressource auf dem Server identisch ist; Andernfalls wird die Ressource vom Server heruntergeladen, im Cache gespeichert und an den Aufrufer zurückgegeben.|  
|`Reload`|Lädt die Ressource vom Server herunter, speichert sie in den Cache und die Ressource an den Aufrufer zurückgegeben.|  
|`NoCacheNoStore`|Wenn eine zwischengespeicherte Ressource vorhanden ist, wird sie gelöscht. Die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben wird.|  
|`Revalidate`|Führt eine Anforderung mithilfe die zwischengespeicherte Kopie der Ressource, wenn der Zeitstempel der Zeitstempel der Ressource auf dem Server identisch ist. Andernfalls ist die Ressource vom Server heruntergeladen, an den Aufrufer angezeigt und im Cache gespeichert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Steuert den Zwischenspeichermechanismus für netzwerkanforderungen.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie eine FTP-Cachingrichtlinie angeben `NoCacheNoStore`.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        policyLevel="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
