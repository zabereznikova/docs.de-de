---
title: <forcePerformanceCounterUniqueSharedMemoryReads>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29fbe951b955c97e39ebaf80885729a45c1a3fd7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927398"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a>\<forceperformancecounteruniquesharedmemoryreads > Element
Gibt an, ob „PerfCounter.dll“ die Registrierungseinstellung „CategoryOptions“ in einer .NET Framework Version 1.1-Anwendung verwendet, um zu bestimmen, ob Leistungsindikatordaten aus kategoriespezifischem, gemeinsam genutztem Arbeitsspeicher oder aus dem globalen Arbeitsspeicher geladen werden.  
  
 \<configuration>  
\<Lauf Zeit >  
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
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob PerfCounter. dll die categoryoptions-Registrierungs Einstellung verwendet, um zu bestimmen, ob Leistungsdaten aus dem kategoriespezifischen freigegebenen oder globalen Arbeitsspeicher geladen werden sollen.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|PerfCounter. dll verwendet nicht die Registrierungs Einstellung categoryoptions, dies ist die Standardeinstellung.|  
|`true`|PerfCounter. dll verwendet die Registrierungs Einstellung categoryoptions.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 In Versionen der .NET Framework vor dem .NET Framework 4 entsprach die Version von PerfCounter. dll, die geladen wurde, der Laufzeit, die in den Prozess geladen wurde. Wenn auf einem Computer sowohl der .NET Framework Version 1,1 als auch der .NET Framework 2,0 installiert war, würde eine .NET Framework 1,1-Anwendung die .NET Framework Version 1,1 von PerfCounter. dll laden. Beginnend mit dem .NET Framework 4 wird die neueste installierte Version von "PerfCounter. dll" geladen. Dies bedeutet, dass eine .NET Framework 1,1-Anwendung die .NET Framework 4-Version von "PerfCounter. dll" lädt, wenn die .NET Framework 4 auf dem Computer installiert ist.  
  
 Beginnend mit dem .NET Framework 4 überprüft PerfCounter. dll bei der Nutzung von Leistungsindikatoren den Registrierungs Eintrag categoryoptions für jeden Anbieter, um zu bestimmen, ob er aus dem kategoriespezifischen freigegebenen Arbeitsspeicher oder dem globalen gemeinsam genutzten Speicher lesen soll. Der .NET Framework 1,1 PerfCounter. dll liest diesen Registrierungs Eintrag nicht, da er keinen kategoriespezifischen freigegebenen Arbeitsspeicher kennt. Er liest immer aus dem globalen gemeinsam genutzten Speicher.  
  
 Aus Gründen der Abwärtskompatibilität überprüft das .NET Framework 4 PerfCounter. dll den Registrierungs Eintrag categoryoptions nicht, wenn er in einer .NET Framework 1,1-Anwendung ausgeführt wird. Es verwendet einfach den globalen gemeinsam genutzten Speicher, genau wie die .NET Framework 1,1 PerfCounter. dll. Sie können jedoch die .NET Framework 4 PerfCounter. dll anweisen, die Registrierungs Einstellung durch Aktivieren des `<forcePerformanceCounterUniqueSharedMemoryReads>` -Elements zu überprüfen.  
  
> [!NOTE]
> Das aktivieren `<forcePerformanceCounterUniqueSharedMemoryReads>` des-Elements garantiert nicht, dass kategoriespezifischer gemeinsam genutzter Arbeitsspeicher verwendet wird. Wenn die Einstellung `true` aktiviert ist, verweist PerfCounter. dll nur auf die Registrierungs Einstellung categoryoptions. Die Standardeinstellung für categoryoptions ist die Verwendung des kategoriespezifischen freigegebenen Speichers. Sie können jedoch categoryoptions ändern, um anzugeben, dass der globale gemeinsame Arbeitsspeicher verwendet werden soll.  
  
 Der Registrierungsschlüssel, der die Einstellung categoryoptions enthält,\\ist HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services < CategoryName\>\Performance. Standardmäßig ist "categoryoptions" auf "3" festgelegt, was PerfCounter. dll anweist, kategoriespezifischen freigegebenen Arbeitsspeicher zu verwenden. Wenn categoryoptions auf 0 festgelegt ist, verwendet PerfCounter. dll globalen gemeinsam genutzten Arbeitsspeicher. Instanzdaten werden nur dann wieder verwendet, wenn der Name der Instanz, die erstellt wird, mit der Instanz identisch ist, die wieder verwendet wird. Alle Versionen können in die Kategorie schreiben. Wenn categoryoptions auf 1 festgelegt ist, wird der globale freigegebene Speicher verwendet, aber Instanzdaten können wieder verwendet werden, wenn der Kategoriename dieselbe Länge wie die wiederverwendbare Kategorie hat.  
  
 Die Einstellungen 0 und 1 können zu Speicher Verlusten und zum Auffüllen des Leistungs Zählers führen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie angeben können, dass "PerfCounter. dll" auf den Registrierungs Eintrag "categoryoptions" verweisen soll, um zu bestimmen, ob der kategorisierte Speicher verwendet werden soll.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
