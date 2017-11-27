---
title: '&lt;NamedCaches&gt; Element (Cacheeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bdafddcb05dd50f059c9f6804573beec085a4a2a
ms.sourcegitcommit: d0f7646d67db5809cf43ff1d27b399a4020e8ee2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2017
---
# <a name="ltnamedcachesgt-element-cache-settings"></a>&lt;NamedCaches&gt; Element (Cacheeinstellungen)
Gibt eine Auflistung von Konfigurationseinstellungen für die benannte <xref:System.Runtime.Caching.MemoryCache> Instanzen. Die <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> -Eigenschaft verweist auf die Auflistung der Konfigurationseinstellungen von einer oder mehreren `namedCaches` Elemente der Konfigurationsdatei.  
  
 \<configuration>  
\<System.Runtime.Caching >  
\<MemoryCache >  
\<NamedCaches >  
  
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
|`cacheMemoryLimitMegabytes`|Ein Ganzzahlwert, der die maximale zulässige Größe in Megabyte angibt, die einer Instanz von einer <xref:System.Runtime.Caching.MemoryCache> anwachsen kann. Der Standardwert ist 0, was bedeutet, der Heuristik Automatisches Anpassen der Größe dass der <xref:System.Runtime.Caching.MemoryCache> Klasse werden standardmäßig verwendet.|  
|`name`|Der Name des Caches.|  
|`physicalMemoryLimitPercentage`|Eine ganze Zahl zwischen 0 und 100, die den maximalen Prozentsatz des Arbeitsspeichers physisch installierten Computer angibt, die vom Cache genutzt werden können. Der Standardwert ist 0, was bedeutet, der Heuristik Automatisches Anpassen der Größe dass der <xref:System.Runtime.Caching.MemoryCache> Klasse werden standardmäßig verwendet.|  
|`pollingInterval`|Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind. Dieser Wert wird im Format "Hh" eingegeben.|  
  
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
 Der Arbeitsspeicher Cache-Konfigurationsabschnitt der Datei "Web.config" darf `add`, `remove`, und `clear` Attribute für die `namedCaches` Auflistung. Jede `namedCaches` Eintrag eindeutig identifiziert wird, durch die `name` Attribut.  
  
 Sie können Instanzen von Arbeitsspeichercacheeinträgen durch Verweisen auf die Informationen in den Anwendungskonfigurationsdateien abrufen. Standardmäßig enthält nur die standardmäßige Instanz einen Eintrag in der Konfigurationsdatei an. Die Cache-Standardinstanz ist die Instanz, die von zurückgegeben wird die <xref:System.Runtime.Caching.MemoryCache.Default%2A> Eigenschaft.  
  
 Wenn Sie das Name-Attribut auf "Default" festgelegt, verwendet das Element die Arbeitsspeicher-Cache Standardinstanz an.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie für den Standardnamen des Cache Eintrag den Namen des Caches festzulegen, durch Festlegen der `name` Attribut "Default".  
  
 Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryPercentage` -Attribut werden auf 0 (Null) festgelegt. Diese Attribute auf 0 (null) festlegen bedeutet, dass der Heuristik Automatisches Anpassen der Größe der <xref:System.Runtime.Caching.MemoryCache> Klasse verwendet werden. Der Cacheimplementierung vergleicht die aktuelle Arbeitsspeicherlast gegen die absolute und Prozentsätzen basierenden Arbeitsspeichergrenze alle zwei Minuten.  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\<MemoryCache >-Element (Cacheeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
