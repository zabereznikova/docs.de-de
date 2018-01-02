---
title: '&lt;ForcePerformanceCounterUniqueSharedMemoryReads&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 602359b713adfd4adf90d3e18f5f434d50c92ef4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltforceperformancecounteruniquesharedmemoryreadsgt-element"></a>&lt;ForcePerformanceCounterUniqueSharedMemoryReads&gt; Element
Gibt an, ob „PerfCounter.dll“ die Registrierungseinstellung „CategoryOptions“ in einer .NET Framework Version 1.1-Anwendung verwendet, um zu bestimmen, ob Leistungsindikatordaten aus kategoriespezifischem, gemeinsam genutztem Arbeitsspeicher oder aus dem globalen Arbeitsspeicher geladen werden.  
  
 \<configuration>  
\<Common Language Runtime >  
\<ForcePerformanceCounterUniqueSharedMemoryReads >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob PerfCounter.dll die registrierungseinstellung "CategoryOptions" verwendet, um zu bestimmen, ob beim Laden von Leistungsindikatordaten aus kategoriespezifische freigegebenen Speicher oder globalen Arbeitsspeicher.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|PerfCounter.dll verwendet nicht die CategoryOptions registrierungseinstellung Dies ist die Standardeinstellung.|  
|`true`|PerfCounter.dll wird die registrierungseinstellung "CategoryOptions" verwendet.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 In Versionen von .NET Framework vor der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], die Version von PerfCounter.dll, das geladen wurde zugestimmt haben, für die Laufzeit, die im Prozess geladen wurde. Wenn ein Computer sowohl .NET Framework, Version 1.1 wurde und die [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installiert ist, würde eine .NET Framework 1.1-Anwendung die .NET Framework 1.1-Version von PerfCounter.dll laden. Beginnend mit der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], die neueste installierte Version von PerfCounter.dll geladen wird. Dies bedeutet, dass eine .NET Framework 1.1-Anwendung geladen werden die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] Version von PerfCounter.dll Wenn die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] auf dem Computer installiert ist.  
  
 Beginnend mit der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], bei der Nutzung von Leistungsindikatoren überprüft PerfCounter.dll den CategoryOptions-Registrierungseintrag für jeden Anbieter, um zu bestimmen, ob von kategoriespezifische freigegebenen Speicher oder der globale freigegebene Speicher gelesen werden soll. Die .NET Framework 1.1 PerfCounter.dll Lesen dieser Registrierungseintrag nicht, da es nicht an gemeinsam genutztem Speicher kategoriespezifische bekannt ist; Er liest immer aus der globale freigegebene Speicher.  
  
 Für die Abwärtskompatibilität der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll überprüft nicht den Registrierungseintrag CategoryOptions, bei der Ausführung in einer .NET Framework 1.1-Anwendung. Globalen freigegebenen Speicher, genau wie die .NET Framework 1.1 PerfCounter.dll einfach verwendet. Sie können jedoch anweisen, die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll, überprüfen Sie die Einstellung in der Registrierung durch Aktivieren der `<forcePerformanceCounterUniqueSharedMemoryReads>` Element.  
  
> [!NOTE]
>  Aktivieren der `<forcePerformanceCounterUniqueSharedMemoryReads>` Element kann nicht garantiert, dass kategoriespezifische freigegebener Arbeitsspeicher verwendet wird. Aktivierter Einstellung `true` nur bewirkt, dass PerfCounter.dll auf die registrierungseinstellung "CategoryOptions" verweisen. Die Standardeinstellung für CategoryOptions ist die Verwendung von gemeinsam genutzten Speicher kategoriespezifische; Sie können jedoch ändern, dass CategoryOptions, um anzugeben, dass der globaler freigegebener Speicher verwendet werden soll.  
  
 Der Registrierungsschlüssel, die die Einstellung CategoryOptions enthält, ist HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< CategoryName\>\Performance. Standardmäßig wird CategoryOptions auf 3 festgelegt PerfCounter.dll weist kategoriespezifische freigegebenen Speicher verwenden. Wenn CategoryOptions auf 0 festgelegt ist, verwendet PerfCounter.dll globalen freigegebenen Speicher. Instanzdaten werden nur dann, wenn der Name des zu erstellenden Instanz identisch mit der Instanz wird wiederverwendet wird wiederverwendet. Alle Versionen werden in der Kategorie schreiben. Wenn CategoryOptions auf 1 festgelegt ist, globaler freigegebener Speicher verwendet, aber Instanzdaten können wiederverwendet werden, wenn Sie den Namen der Kategorie die gleiche Länge wie die Kategorie, die wiederverwendet wird.  
  
 Die Einstellungen, 0 und 1 können zu Speicherverlusten und das Transaktionsprotokoll der Leistungsindikator-Arbeitsspeichers führen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie angegeben wird, dass PerfCounter.dll verweisen soll, den Registrierungseintrag CategoryOptions, um festzustellen, ob kategoriespezifische freigegebener Speicher verwendet werden soll.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
