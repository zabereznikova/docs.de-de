---
title: '&lt;MemoryCache&gt; -Element (Cacheeinstellungen)'
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: cdf7d0e5605bde42d092492ea1b16d712984c182
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083911"
---
# <a name="ltmemorycachegt-element-cache-settings"></a>&lt;MemoryCache&gt; -Element (Cacheeinstellungen)
Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert. Die <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> -Klasse definiert ein [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) -Element, das Sie zum Konfigurieren des Caches verwenden können. Mehrere Instanzen der <xref:System.Runtime.Caching.MemoryCache> -Klasse können in einer einzigen Anwendung verwendet werden. Jedes `memoryCache` -Element in der Konfigurationsdatei kann Einstellungen für eine benannte <xref:System.Runtime.Caching.MemoryCache> -Instanz enthalten.  
  
 \<configuration>  
\<system.runtime.caching>  
\<memoryCache>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<memoryCache>   
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>   
</memoryCache>  
```  
  
## <a name="type"></a>Typ  
 <xref:System.Runtime.Caching.MemoryCache> -Klasse.  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|Die maximale Arbeitsspeichergröße in Megabyte, auf die eine Instanz eines <xref:System.Runtime.Caching.MemoryCache> -Objekts anwachsen kann. Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> -Klasse Autosize-Heuristik als Standard verwendet wird.|  
|`Name`|Der Name der Cachekonfiguration.|  
|`PhysicalMemoryLimitPercentage`|Der Prozentsatz des physischen Arbeitsspeichers, der vom Cache verwendet werden kann. Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> -Klasse Autosize-Heuristik als Standard verwendet wird.|  
|`PollingInterval`|Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind. Der Wert wird im Format „HH:MM:SS“ eingegeben.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Enthält eine Sammlung von Konfigurationseigenschaften für die `namedCache` -Instanz.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.runtime.caching>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|Enthält Typen, mit denen Sie Zwischenspeichern der Ausgabe in Anwendungen, die in [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]integriert sind, implementieren können.|  
  
## <a name="remarks"></a>Hinweise  
 Die <xref:System.Runtime.Caching.MemoryCache> -Klasse ist eine konkrete Implementierung der abstrakten <xref:System.Runtime.Caching.ObjectCache> -Klasse. Instanzen der <xref:System.Runtime.Caching.MemoryCache> -Klasse können mit Konfigurationsinformationen von Anwendungskonfigurationsdateien versorgt werden. Der Abschnitt [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) -Konfiguration enthält eine `namedCaches` -Konfigurationssammlung.  
  
 Wenn ein speicherbasierendes Cacheobjekt initialisiert wird, versucht es zuerst, einen `namedCaches` -Eintrag zu finden, der dem Namen in dem Parameter entspricht, der an den Speichercache-Konstruktor übergeben wird. Wenn ein `namedCaches` -Eintrag gefunden wird, werden Abruf- und Speicher-Management-Informationen aus der Konfigurationsdatei abgerufen.  
  
 Der Initialisierungsprozess bestimmt dann mithilfe der optionalen Sammlung von Name-Wert-Paaren mit Konfigurationsinformationen im Konstruktor, ob Konfigurationseinträge überschrieben wurden. Wenn Sie einen oder mehrere der folgenden Werte in der Name-Wert-Paar-Sammlung übergeben, überschreiben diese Werte Informationen aus der Konfigurationsdatei:  
  
-   <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
-   <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
-   <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie der Name des <xref:System.Runtime.Caching.MemoryCache> -Objekts durch Setzen der `name` -Attribute auf „Standard“ auf den Cache-Standardobjektnamen festgelegt wird.  
  
 Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryLimitPercentage` -Attribut werden auf 0 (Null) festgelegt. Werden diese Attribute auf 0 (Null) festgelegt, wird die <xref:System.Runtime.Caching.MemoryCache> -Heuristik zum automatischen Anpassen als Standard verwendet. Die Cacheimplementierung sollte die aktuelle Auslastung des Arbeitsspeichers alle zwei Minuten mit den absoluten und prozentualen Speichergrenzen vergleichen.  
  
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
- <xref:System.Runtime.Caching.MemoryCache>
- [\<System.Runtime.Caching >-Element (Cacheeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)
- [\<NamedCaches >-Element (Cacheeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
