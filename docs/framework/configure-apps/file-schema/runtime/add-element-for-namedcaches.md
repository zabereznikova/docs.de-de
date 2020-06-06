---
title: <add>-Element für <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: c1345022b79df371ad9c89a39a0a8b625e26608c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154504"
---
# <a name="add-element-for-namedcaches"></a>\<add>-Element für \<namedCaches>
Fügt der-Auflistung einen `namedCache` Eintrag `namedCaches` für einen Speicher Cache hinzu.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
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
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|-|-|  
|`CacheMemoryLimitMegabytes`|Ein ganzzahliger Wert, der die maximal zulässige Größe (in Megabyte) angibt, auf die eine Instanz eines <xref:System.Runtime.Caching.MemoryCache> anwachsen kann. Der Standardwert ist 0 (null), was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> Automatisches Anpassen-Heuristik der Klasse standardmäßig verwendet wird.|  
|`Name`|Der Name des Caches.|  
|`PhysicalMemoryLimitPercentage`|Ein ganzzahliger Wert zwischen 0 und 100, der den maximalen Prozentsatz des physisch installierten Computer Arbeitsspeichers angibt, der vom Cache genutzt werden kann. Der Standardwert ist 0 (null), was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> Automatisches Anpassen-Heuristik der Klasse standardmäßig verwendet wird.|  
|`PollingInterval`|Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind. Dieser Wert wird im Format "hh: mm: SS" eingegeben.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 `None`  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Enthält eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das- `add` Element fügt der-Auflistung einen Eintrag `namedCaches` für einen Speicher Cache hinzu. Sie können das [Clear](clear-element-for-namedcaches.md) -Element verwenden, bevor Sie das- `add` Element verwenden, um sicherzustellen, dass keine anderen benannten Caches in der Auflistung vorhanden sind. Dieses Element kann in der Datei "Machine. config" und in der Datei "Web. config" verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie Einstellungen für den Standard `namedCache` Eintrag für die-Auflistung `namedCaches` für einen Speicher Cache definieren.  
  
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

- [\<namedCaches>-Element (Cache Einstellungen)](namedcaches-element-cache-settings.md)
