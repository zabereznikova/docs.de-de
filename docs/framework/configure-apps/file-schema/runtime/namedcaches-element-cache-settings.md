---
title: <namedCaches>-Element (Cacheeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: ad76c01bba859934be399d73262bd974309efe98
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192398"
---
# <a name="namedcaches-element-cache-settings"></a>\<namedCaches>-Element (Cacheeinstellungen)

Gibt eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen an. Die- <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> Eigenschaft verweist auf die Auflistung von Konfigurationseinstellungen von einem oder mehreren `namedCaches` Elementen der Konfigurationsdatei.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<namedCaches>  
  <add name="default"/>
</namedCaches>  
```  
  
## <a name="type"></a>Typ  

 `None`  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|Ein ganzzahliger Wert, der die maximale zulässige Größe (in Megabyte) angibt, auf die eine Instanz eines <xref:System.Runtime.Caching.MemoryCache> anwachsen kann. Der Standardwert ist 0 (null). Dies bedeutet, dass die automatische Größenanpassung der- <xref:System.Runtime.Caching.MemoryCache> Klasse standardmäßig verwendet wird.|  
|`name`|Der Name des Caches.|  
|`physicalMemoryLimitPercentage`|Ein ganzzahliger Wert zwischen 0 und 100, der den maximalen Prozentsatz des physisch installierten Computer Arbeitsspeichers angibt, der vom Cache genutzt werden kann. Der Standardwert ist 0 (null). Dies bedeutet, dass die automatische Größenanpassung der- <xref:System.Runtime.Caching.MemoryCache> Klasse standardmäßig verwendet wird.|  
|`pollingInterval`|Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind. Dieser Wert wird im Format "hh: mm: SS" eingegeben.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<add>](add-element-for-namedcaches.md)|Fügt der `namedCaches`-Sammlung für einen Speichercache einen benannten Cache hinzu.|  
|[\<clear>](clear-element-for-namedcaches.md)|Löscht die `namedCaches`-Sammlung für einen Speichercache.|  
|[\<remove>](remove-element-for-namedcaches.md)|Entfernt einen benannten Cacheeintrag aus der `namedCaches`-Sammlung für einen Speichercache.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Gibt das Stamm Element in jeder Konfigurationsdatei an, die von den Common Language Runtime-und .NET Framework Anwendungen verwendet wird.|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert.|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|Enthält Typen, mit denen Sie die Ausgabe Zwischenspeicherung in Anwendungen implementieren können, die in die .NET Framework integriert sind.|  
  
## <a name="remarks"></a>Bemerkungen  

 Der Arbeitsspeicher-Cache Konfigurations Abschnitt der Web.config Datei kann `add` die `remove` Attribute, und für die Auflistung enthalten `clear` `namedCaches` . Jeder `namedCaches` Eintrag wird durch das-Attribut eindeutig identifiziert `name` .  
  
 Sie können Instanzen von Arbeitsspeicher-Cache Einträgen abrufen, indem Sie auf die Informationen in den Anwendungs Konfigurationsdateien verweisen. Standardmäßig verfügt nur die Standard Cache Instanz über einen Eintrag in der Konfigurationsdatei. Die Standard Cache Instanz ist die-Instanz, die von der-Eigenschaft zurückgegeben wird <xref:System.Runtime.Caching.MemoryCache.Default%2A> .  
  
 Wenn Sie das Name-Attribut auf "Default" festlegen, verwendet das-Element die Standard-Speicher Cache Instanz.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird gezeigt, wie der Name des Caches auf den standardmäßigen Cache Eintrags Namen festgelegt wird, indem das- `name` Attribut auf "Default" festgelegt wird.  
  
 Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryPercentage` -Attribut werden auf 0 (Null) festgelegt. Wenn diese Attribute auf 0 (null) festgelegt werden, wird die Heuristik für die automatische Größenänderung der- <xref:System.Runtime.Caching.MemoryCache> Klasse verwendet. Die Cache Implementierung vergleicht die aktuelle Arbeitsspeicher Last alle zwei Minuten mit den absoluten und prozentualen Arbeitsspeicher Limits.  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [\<memoryCache> -Element (Cache Einstellungen)](memorycache-element-cache-settings.md)
