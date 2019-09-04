---
title: <namedCaches>-Element (Cacheeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 4587234ad91fa3b1abbb376bd7ae517d5abea6c3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252464"
---
# <a name="namedcaches-element-cache-settings"></a>\<NamedCaches > Element (Cache Einstellungen)
Gibt eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen an. Die <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> -Eigenschaft verweist auf die Auflistung von Konfigurationseinstellungen von einem `namedCaches` oder mehreren Elementen der Konfigurationsdatei.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Runtime. Caching->** ](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<MemoryCache->** ](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<NamedCaches >**  
  
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
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|Ein ganzzahliger Wert, der die maximale zulässige Größe (in Megabyte) angibt, auf die <xref:System.Runtime.Caching.MemoryCache> eine Instanz eines anwachsen kann. Der Standardwert ist 0 (null). Dies bedeutet, dass die automatische Größenanpassung <xref:System.Runtime.Caching.MemoryCache> der-Klasse standardmäßig verwendet wird.|  
|`name`|Der Name des Caches.|  
|`physicalMemoryLimitPercentage`|Ein ganzzahliger Wert zwischen 0 und 100, der den maximalen Prozentsatz des physisch installierten Computer Arbeitsspeichers angibt, der vom Cache genutzt werden kann. Der Standardwert ist 0 (null). Dies bedeutet, dass die automatische Größenanpassung <xref:System.Runtime.Caching.MemoryCache> der-Klasse standardmäßig verwendet wird.|  
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
  
## <a name="remarks"></a>Hinweise  
 Der Konfigurations Abschnitt für den Arbeitsspeicher Cache der Datei "Web. `add`config `remove`" kann `clear` die Attribute, `namedCaches` und für die Auflistung enthalten. Jeder `namedCaches` Eintrag wird durch das `name` -Attribut eindeutig identifiziert.  
  
 Sie können Instanzen von Arbeitsspeicher-Cache Einträgen abrufen, indem Sie auf die Informationen in den Anwendungs Konfigurationsdateien verweisen. Standardmäßig verfügt nur die Standard Cache Instanz über einen Eintrag in der Konfigurationsdatei. Die Standard Cache Instanz ist die-Instanz, die von der <xref:System.Runtime.Caching.MemoryCache.Default%2A> -Eigenschaft zurückgegeben wird.  
  
 Wenn Sie das Name-Attribut auf "Default" festlegen, verwendet das-Element die Standard-Speicher Cache Instanz.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie der Name des Caches auf den standardmäßigen Cache Eintrags Namen festgelegt `name` wird, indem das-Attribut auf "Default" festgelegt wird.  
  
 Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryPercentage` -Attribut werden auf 0 (Null) festgelegt. Wenn diese Attribute auf 0 (null) festgelegt werden, wird die Heuristik für die automatische Größenänderung der <xref:System.Runtime.Caching.MemoryCache> -Klasse verwendet. Die Cache Implementierung vergleicht die aktuelle Arbeitsspeicher Last alle zwei Minuten mit den absoluten und prozentualen Arbeitsspeicher Limits.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [\<MemoryCache-> Element (Cache Einstellungen)](memorycache-element-cache-settings.md)
