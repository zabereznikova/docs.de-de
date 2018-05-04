---
title: '&lt;Hinzufügen&gt; -Element für &lt;NamedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d65dfd9a1560f2657f48b327277b64ab77014b47
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltnamedcachesgt"></a>&lt;Hinzufügen&gt; -Element für &lt;NamedCaches&gt;
Fügt eine `namedCache` Eintrags, der die `namedCaches` Auflistung für einen Arbeitsspeichercache.  
  
 \<system.runtime.caching>  
\<memoryCache>  
\<NamedCaches >  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Typ  
 `None`  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|-|-|  
|`CacheMemoryLimitMegabytes`|Ein Ganzzahlwert, der die maximal zulässige Größe (in Megabytes) angibt, die einer Instanz von einer <xref:System.Runtime.Caching.MemoryCache> anwachsen kann. Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> Klasse Automatisches Anpassen der Größe Heuristik werden standardmäßig verwendet.|  
|`Name`|Der Name des Caches.|  
|`PhysicalMemoryLimitPercentage`|Eine ganze Zahl zwischen 0 und 100, die den maximalen Prozentsatz des Arbeitsspeichers physisch installierten Computer angibt, die vom Cache genutzt werden können. Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> Klasse Automatisches Anpassen der Größe Heuristik werden standardmäßig verwendet.|  
|`PollingInterval`|Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind. Dieser Wert wird im Format "Hh" eingegeben.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 `None`  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Enthält eine Auflistung von Konfigurationseinstellungen für die benannte <xref:System.Runtime.Caching.MemoryCache> Instanzen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `add` -Element fügt einen Eintrag in einen der `namedCaches` Auflistung für einen Arbeitsspeichercache. Können Sie die [deaktivieren](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) Element vor der Verwendung der `add` Element sicher, dass es keine anderen sind benannte Caches in der Auflistung. Dieses Element kann in der Datei "Machine.config" und in der Datei "Web.config" verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Einstellungen für den standardmäßigen definiert `namedCache` Eintrags, der die `namedCaches` Auflistung für einen Arbeitsspeichercache.  
  
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
 [\<NamedCaches >-Element (Cacheeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
