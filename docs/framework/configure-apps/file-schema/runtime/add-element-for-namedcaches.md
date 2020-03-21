---
title: <add>-Element für <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: c1345022b79df371ad9c89a39a0a8b625e26608c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154504"
---
# <a name="add-element-for-namedcaches"></a>\<Hinzufügen> \<Elements für namedCaches>
Fügt `namedCache` der `namedCaches` Auflistung einen Eintrag für einen Speichercache hinzu.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<hinzufügen>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>type  
 `None`  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|-|-|  
|`CacheMemoryLimitMegabytes`|Ein Ganzzahlwert, der die maximal zulässige Größe (in Megabyte) angibt, auf die eine Instanz eines Instance sanieren <xref:System.Runtime.Caching.MemoryCache> kann. Der Standardwert ist 0, <xref:System.Runtime.Caching.MemoryCache> was bedeutet, dass die autoisierende Heuristik der Klasse standardmäßig verwendet wird.|  
|`Name`|Der Name des Caches.|  
|`PhysicalMemoryLimitPercentage`|Ein Ganzzahlwert zwischen 0 und 100, der den maximalen Prozentsatz des physisch installierten Computerspeichers angibt, der vom Cache verbraucht werden kann. Der Standardwert ist 0, <xref:System.Runtime.Caching.MemoryCache> was bedeutet, dass die autoisierende Heuristik der Klasse standardmäßig verwendet wird.|  
|`PollingInterval`|Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind. Dieser Wert wird im Format "HH:MM:SS" eingegeben.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 `None`  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Enthält eine Auflistung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das `add` Element fügt der `namedCaches` Auflistung einen Eintrag für einen Speichercache hinzu. Sie können das [clear-Element](clear-element-for-namedcaches.md) `add` verwenden, bevor Sie das Element verwenden, um sicher zu sein, dass keine anderen benannten Caches in der Auflistung vorhanden sind. Dieses Element kann in der Datei machine.config und in der Datei Web.config verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie `namedCache` Sie Einstellungen `namedCaches` für den Standardeintrag für die Auflistung für einen Speichercache definieren.  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [\<namedCaches> Element (Cache-Einstellungen)](namedcaches-element-cache-settings.md)
