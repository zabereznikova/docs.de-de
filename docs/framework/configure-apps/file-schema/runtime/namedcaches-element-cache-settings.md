---
title: <namedCaches>-Element (Cacheeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 36920a5e585c0c7581fbc4f84043d68550fbdac1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704868"
---
# <a name="namedcaches-element-cache-settings"></a>\<NamedCaches >-Element (Cacheeinstellungen)
Gibt eine Auflistung von Konfigurationseinstellungen für den benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen. Die <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> -Eigenschaft verweist auf die Auflistung der Konfigurationseinstellungen von einer oder mehreren `namedCaches` Elemente der Konfigurationsdatei.  
  
 \<configuration>  
\< system.runtime.caching>  
\<memoryCache>  
\<namedCaches>  
  
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
|`cacheMemoryLimitMegabytes`|Ein ganzzahliger Wert, der angibt, die maximale zulässige Größe in Megabyte, die eine Instanz von einem <xref:System.Runtime.Caching.MemoryCache> anwachsen kann. Der Standardwert ist 0 (null) und das bedeutet, die-Heuristik von dass der <xref:System.Runtime.Caching.MemoryCache> Klasse standardmäßig verwendet werden.|  
|`name`|Der Name des Caches.|  
|`physicalMemoryLimitPercentage`|Ein ganzzahliger Wert zwischen 0 und 100, der den maximalen Prozentsatz der physisch installierten Arbeitsspeichers angibt, die vom Cache genutzt werden können. Der Standardwert ist 0 (null) und das bedeutet, die-Heuristik von dass der <xref:System.Runtime.Caching.MemoryCache> Klasse standardmäßig verwendet werden.|  
|`pollingInterval`|Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind. Dieser Wert wird im-Format "Hh" eingegeben.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|Fügt der `namedCaches`-Sammlung für einen Speichercache einen benannten Cache hinzu.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|Löscht die `namedCaches`-Sammlung für einen Speichercache.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|Entfernt einen benannten Cacheeintrag aus der `namedCaches`-Sammlung für einen Speichercache.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<memoryCache>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert.|  
  
## <a name="remarks"></a>Hinweise  
 Der Abschnitt Configuration der Datei "Web.config" darf `add`, `remove`, und `clear` Attribute für die `namedCaches` Auflistung. Jede `namedCaches` Eintrag eindeutig durch die `name` Attribut.  
  
 Sie können Instanzen von Cacheeinträgen Speicher verweisen auf die Informationen in den Konfigurationsdateien der Anwendung abrufen. Standardmäßig enthält nur die Standard-Cache-Instanz einen Eintrag in der Konfigurationsdatei. Die Standard-Cache-Instanz ist die Instanz, die von zurückgegeben wird das <xref:System.Runtime.Caching.MemoryCache.Default%2A> Eigenschaft.  
  
 Wenn Sie das Name-Attribut auf "Standard" festlegen, verwendet das Element die Standard-Memory-Cache-Instanz.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel veranschaulicht die legen Sie des Namens des Caches, der Name des Standard-Cache-Eintrags durch Festlegen der `name` Attribut auf "Standard".  
  
 Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryPercentage` -Attribut werden auf 0 (Null) festgelegt. Festlegen von dieser Attribute auf 0 (null) bedeutet, dass die-Heuristik von der <xref:System.Runtime.Caching.MemoryCache> Klasse verwendet werden. Die Cacheimplementierung vergleicht die aktuelle Arbeitsspeicherlast mit den absoluten und prozentualen Speichergrenzen alle zwei Minuten.  
  
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

- [\<MemoryCache >-Element (Cacheeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
