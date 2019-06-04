---
title: <forcePerformanceCounterUniqueSharedMemoryReads>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26fed0a10b9a25f25a580c7ac9a468cbedeb3671
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489475"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a>\<forcePerformanceCounterUniqueSharedMemoryReads> Element
Gibt an, ob „PerfCounter.dll“ die Registrierungseinstellung „CategoryOptions“ in einer .NET Framework Version 1.1-Anwendung verwendet, um zu bestimmen, ob Leistungsindikatordaten aus kategoriespezifischem, gemeinsam genutztem Arbeitsspeicher oder aus dem globalen Arbeitsspeicher geladen werden.  
  
 \<configuration>  
\<runtime>  
\<forcePerformanceCounterUniqueSharedMemoryReads>  
  
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
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob "PerfCounter.dll" die registrierungseinstellung CategoryOptions verwendet, um zu ermitteln, ob Leistungsindikatordaten aus kategoriespezifischem, gemeinsam genutzten Speicher oder globalen Arbeitsspeicher zu laden.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|"PerfCounter.dll" verwendet nicht die CategoryOptions Registrierung durch Festlegen dieses Werts ist die Standardeinstellung.|  
|`true`|"PerfCounter.dll" wird die registrierungseinstellung CategoryOptions verwendet.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Entsprach in Versionen von .NET Framework vor .NET Framework 4 wird die Version von "PerfCounter.dll", das geladen wurde, an die Laufzeit, die im Prozess geladen wurde. Bei ein Computer sowohl .NET Framework, Version 1.1 und [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installiert haben, eine .NET Framework 1.1-Anwendung lädt die .NET Framework 1.1-Version von "PerfCounter.dll". Ab .NET Framework 4, wird die neueste installierte Version von "PerfCounter.dll" geladen. Dies bedeutet, dass eine .NET Framework 1.1-Anwendung die .NET Framework 4-Version von "PerfCounter.dll" geladen werden, wenn .NET Framework 4 auf dem Computer installiert ist.  
  
 Ab .NET Framework 4, bei der Nutzung von Leistungsindikatoren, überprüft "PerfCounter.dll" CategoryOptions Registrierungseintrag für jeden Anbieter, um zu bestimmen, ob er aus kategoriespezifischem, gemeinsam genutzten Speicher oder der globale freigegebene Speicher lesen soll. Die .NET Framework 1.1 PerfCounter.dll Lesen dieses Registrierungseintrags nicht, da es nicht an gemeinsam genutztem Speicher kategoriespezifische bekannt ist; Es liest aus der globale freigegebene Speicher.  
  
 Um Abwärtskompatibilität zu gewährleisten überprüft der .NET Framework 4 "PerfCounter.dll" nicht den Registrierungseintrag "CategoryOptions", wenn in einer .NET Framework 1.1-Anwendung ausgeführt wird. Sie verwendet einfach globalen freigegebenen Speicher, genau wie die .NET Framework 1.1 "PerfCounter.dll". Sie können jedoch anweisen, die .NET Framework 4 PerfCounter.dll, überprüfen Sie die registrierungseinstellung durch Aktivieren der `<forcePerformanceCounterUniqueSharedMemoryReads>` Element.  
  
> [!NOTE]
>  Aktivieren der `<forcePerformanceCounterUniqueSharedMemoryReads>` Element garantiert nicht, dass kategoriespezifische gemeinsam genutzten Speicher verwendet werden. Aktivierter Einstellung `true` bewirkt nur, dass "PerfCounter.dll", um auf die registrierungseinstellung CategoryOptions zu verweisen. Die Standardeinstellung für CategoryOptions ist die Verwendung von gemeinsam genutzten Speicher kategoriespezifische; Sie können jedoch ändern, dass CategoryOptions, um anzugeben, dass der globaler freigegebener Speicher verwendet werden soll.  
  
 Der Registrierungsschlüssel, der die Einstellung der CategoryOptions enthält ist HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< "CategoryName"\>\Performance. Standardmäßig wird CategoryOptions auf 3 festgelegt "PerfCounter.dll" weist kategoriespezifische freigegebenen Speicher verwenden. Wenn CategoryOptions auf 0 festgelegt ist, wird "PerfCounter.dll" globalen freigegebenen Speicher verwendet. Instanzdaten werden wiederverwendet werden, nur, wenn der Name des zu erstellenden Instanz mit der Instanz, die wiederverwendet werden identisch ist. Alle Versionen werden in der Kategorie "" schreiben. Wenn CategoryOptions auf 1 festgelegt ist, globaler freigegebener Speicher wird verwendet, aber Instanzdaten wiederverwendet werden können, den Namen der Kategorie ist die gleiche Länge wie der Kategorie, die wiederverwendet werden.  
  
 Die Einstellungen, 0 und 1 können der schnell an Größe zunimmt Leistungsindikator-Arbeitsspeichers zu Speicherverlusten führen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie angeben, dass "PerfCounter.dll" verweisen soll, den Registrierungseintrag CategoryOptions, um festzustellen, ob kategoriespezifische gemeinsam genutzten Speicher verwendet werden soll.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
