---
title: <add>-Element für <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: fd6668a551663470a97b07ff131710dbe92a91f5
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659034"
---
# <a name="add-element-for-namedcaches"></a>\<Fügen Sie >- \<Element für NamedCaches hinzu >
Fügt der `namedCache` `namedCaches` -Auflistung einen Eintrag für einen Speicher Cache hinzu.  
  
 \<system.runtime.caching>  
\<memoryCache>  
\<namedCaches>  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<namedCaches>  
    <add name="Default" />  
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
|`CacheMemoryLimitMegabytes`|Ein ganzzahliger Wert, der die maximal zulässige Größe (in Megabyte) angibt, auf die <xref:System.Runtime.Caching.MemoryCache> eine Instanz eines anwachsen kann. Der Standardwert ist 0 (null), was <xref:System.Runtime.Caching.MemoryCache> bedeutet, dass die Automatisches Anpassen-Heuristik der Klasse standardmäßig verwendet wird.|  
|`Name`|Der Name des Caches.|  
|`PhysicalMemoryLimitPercentage`|Ein ganzzahliger Wert zwischen 0 und 100, der den maximalen Prozentsatz des physisch installierten Computer Arbeitsspeichers angibt, der vom Cache genutzt werden kann. Der Standardwert ist 0 (null), was <xref:System.Runtime.Caching.MemoryCache> bedeutet, dass die Automatisches Anpassen-Heuristik der Klasse standardmäßig verwendet wird.|  
|`PollingInterval`|Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind. Dieser Wert wird im Format "hh: mm: SS" eingegeben.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 `None`  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Enthält eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.|  
  
## <a name="remarks"></a>Hinweise  
 Das `add` -Element fügt der `namedCaches` -Auflistung einen Eintrag für einen Speicher Cache hinzu. Sie können das [Clear](clear-element-for-namedcaches.md) -Element verwenden, bevor Sie `add` das-Element verwenden, um sicherzustellen, dass keine anderen benannten Caches in der Auflistung vorhanden sind. Dieses Element kann in der Datei "Machine. config" und in der Datei "Web. config" verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie Einstellungen für den `namedCache` Standardeintrag für `namedCaches` die-Auflistung für einen Speicher Cache definieren.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [\<NamedCaches > Element (Cache Einstellungen)](namedcaches-element-cache-settings.md)
