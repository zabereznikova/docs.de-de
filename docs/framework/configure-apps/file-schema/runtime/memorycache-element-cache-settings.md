---
title: <memoryCache>-Element (Cacheeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 94c21e0408b7616bf0c8a24267b72bfa7cc3aaa0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153983"
---
# <a name="memorycache-element-cache-settings"></a>\<memoryCache> Element (Cache-Einstellungen)
Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert. Die <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> -Klasse definiert ein [memoryCache](memorycache-element-cache-settings.md) -Element, das Sie zum Konfigurieren des Caches verwenden können. Mehrere Instanzen der <xref:System.Runtime.Caching.MemoryCache> -Klasse können in einer einzigen Anwendung verwendet werden. Jedes `memoryCache` -Element in der Konfigurationsdatei kann Einstellungen für eine benannte <xref:System.Runtime.Caching.MemoryCache> -Instanz enthalten.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<memoryCache>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<memoryCache>
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>
</memoryCache>  
```  
  
## <a name="type"></a>type  
 <xref:System.Runtime.Caching.MemoryCache> -Klasse.  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|Die maximale Arbeitsspeichergröße in Megabyte, auf die eine Instanz eines <xref:System.Runtime.Caching.MemoryCache> -Objekts anwachsen kann. Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> -Klasse Autosize-Heuristik als Standard verwendet wird.|  
|`Name`|Der Name der Cachekonfiguration.|  
|`PhysicalMemoryLimitPercentage`|Der Prozentsatz des physischen Arbeitsspeichers, der vom Cache verwendet werden kann. Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> -Klasse Autosize-Heuristik als Standard verwendet wird.|  
|`PollingInterval`|Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind. Der Wert wird im Format „HH:MM:SS“ eingegeben.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Enthält eine Sammlung von Konfigurationseigenschaften für die `namedCache` -Instanz.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Konfiguration>](../configuration-element.md)|Gibt das Stammelement in jeder Konfigurationsdatei an, die von der Common Language Runtime und .NET Framework-Anwendungen verwendet wird.|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|Enthält Typen, mit denen Sie ausgabezwischenspeichern in Anwendungen implementieren können, die in .NET Framework integriert sind.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die <xref:System.Runtime.Caching.MemoryCache> -Klasse ist eine konkrete Implementierung der abstrakten <xref:System.Runtime.Caching.ObjectCache> -Klasse. Instanzen der <xref:System.Runtime.Caching.MemoryCache> -Klasse können mit Konfigurationsinformationen von Anwendungskonfigurationsdateien versorgt werden. Der Abschnitt [memoryCache](memorycache-element-cache-settings.md) -Konfiguration enthält eine `namedCaches` -Konfigurationssammlung.  
  
 Wenn ein speicherbasierendes Cacheobjekt initialisiert wird, versucht es zuerst, einen `namedCaches` -Eintrag zu finden, der dem Namen in dem Parameter entspricht, der an den Speichercache-Konstruktor übergeben wird. Wenn ein `namedCaches` -Eintrag gefunden wird, werden Abruf- und Speicher-Management-Informationen aus der Konfigurationsdatei abgerufen.  
  
 Der Initialisierungsprozess bestimmt dann mithilfe der optionalen Sammlung von Name-Wert-Paaren mit Konfigurationsinformationen im Konstruktor, ob Konfigurationseinträge überschrieben wurden. Wenn Sie einen oder mehrere der folgenden Werte in der Name-Wert-Paar-Sammlung übergeben, überschreiben diese Werte Informationen aus der Konfigurationsdatei:  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie <xref:System.Runtime.Caching.MemoryCache> Sie den Namen des Objekts `name` auf den Standard-Cacheobjektnamen festlegen, indem Sie das Attribut auf "Standard" festlegen.  
  
 Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryLimitPercentage` -Attribut werden auf 0 (Null) festgelegt. Werden diese Attribute auf 0 (Null) festgelegt, wird die <xref:System.Runtime.Caching.MemoryCache> -Heuristik zum automatischen Anpassen als Standard verwendet. Die Cacheimplementierung sollte die aktuelle Auslastung des Arbeitsspeichers alle zwei Minuten mit den absoluten und prozentualen Speichergrenzen vergleichen.  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.Caching.MemoryCache>
- [\<system.runtime.caching> Element (Cache-Einstellungen)](system-runtime-caching-element-cache-settings.md)
- [\<namedCaches> Element (Cache-Einstellungen)](namedcaches-element-cache-settings.md)
