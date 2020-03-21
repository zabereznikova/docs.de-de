---
title: <namedCaches>-Element (Cacheeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: e0640ca18d386141f3c03135019eb4fe959b5bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153957"
---
# <a name="namedcaches-element-cache-settings"></a>\<namedCaches> Element (Cache-Einstellungen)
Gibt eine Auflistung von Konfigurationseinstellungen <xref:System.Runtime.Caching.MemoryCache> für die benannten Instanzen an. Die <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> Eigenschaft verweist auf die Auflistung `namedCaches` der Konfigurationseinstellungen aus einem oder mehreren Elementen der Konfigurationsdatei.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<namedCaches>  
  <add name="default"/>
</namedCaches>  
```  
  
## <a name="type"></a>type  
 `None`  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|Ein Ganzzahlwert, der die maximal zulässige Größe in Megabyte <xref:System.Runtime.Caching.MemoryCache> angibt, auf die eine Instanz eines Werts anwachsen kann. Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> autoisierende Heuristik der Klasse standardmäßig verwendet wird.|  
|`name`|Der Name des Caches.|  
|`physicalMemoryLimitPercentage`|Ein Ganzzahlwert zwischen 0 und 100, der den maximalen Prozentsatz des physisch installierten Computerspeichers angibt, der vom Cache verbraucht werden kann. Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> autoisierende Heuristik der Klasse standardmäßig verwendet wird.|  
|`pollingInterval`|Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind. Dieser Wert wird im Format "HH:MM:SS" eingegeben.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<hinzufügen>](add-element-for-namedcaches.md)|Fügt der `namedCaches`-Sammlung für einen Speichercache einen benannten Cache hinzu.|  
|[\<klare>](clear-element-for-namedcaches.md)|Löscht die `namedCaches`-Sammlung für einen Speichercache.|  
|[\<entfernen sie>](remove-element-for-namedcaches.md)|Entfernt einen benannten Cacheeintrag aus der `namedCaches`-Sammlung für einen Speichercache.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Konfiguration>](../configuration-element.md)|Gibt das Stammelement in jeder Konfigurationsdatei an, die von der Common Language Runtime und .NET Framework-Anwendungen verwendet wird.|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert.|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|Enthält Typen, mit denen Sie ausgabezwischenspeichern in Anwendungen implementieren können, die in .NET Framework integriert sind.|  
  
## <a name="remarks"></a>Bemerkungen  
 Der Speichercachekonfigurationsabschnitt der Datei Web.config `remove`kann `clear` , und `namedCaches` Attribute für die Auflistung enthalten. `add` Jeder `namedCaches` Eintrag wird durch `name` das Attribut eindeutig identifiziert.  
  
 Sie können Instanzen von Speichercacheeinträgen abrufen, indem Sie auf die Informationen in den Anwendungskonfigurationsdateien verweisen. Standardmäßig verfügt nur die Standard-Cacheinstanz über einen Eintrag in der Konfigurationsdatei. Die Standard-Cacheinstanz ist die Instanz, die von der <xref:System.Runtime.Caching.MemoryCache.Default%2A> Eigenschaft zurückgegeben wird.  
  
 Wenn Sie das Name-Attribut auf "default" festlegen, verwendet das Element die Standard-Speichercacheinstanz.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie den Namen des Caches `name` auf den Standardcacheeintragsnamen festlegen, indem Sie das Attribut auf "default" festlegen.  
  
 Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryPercentage` -Attribut werden auf 0 (Null) festgelegt. Das Festlegen dieser Attribute auf Null bedeutet, dass <xref:System.Runtime.Caching.MemoryCache> die autooptimierende Heuristik der Klasse verwendet wird. Die Cacheimplementierung vergleicht die aktuelle Speicherauslastung alle zwei Minuten mit den absoluten und prozentualen Speicherlimits.  
  
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

- [\<memoryCache> Element (Cache-Einstellungen)](memorycache-element-cache-settings.md)
