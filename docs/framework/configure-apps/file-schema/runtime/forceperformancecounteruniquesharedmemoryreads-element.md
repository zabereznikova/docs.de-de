---
title: <forcePerformanceCounterUniqueSharedMemoryReads>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 742b444c445ba67d6977b622e615a6a8f591826e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154139"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a>\<forcePerformanceCounterUniqueSharedMemoryReads> Element
Gibt an, ob „PerfCounter.dll“ die Registrierungseinstellung „CategoryOptions“ in einer .NET Framework Version 1.1-Anwendung verwendet, um zu bestimmen, ob Leistungsindikatordaten aus kategoriespezifischem, gemeinsam genutztem Arbeitsspeicher oder aus dem globalen Arbeitsspeicher geladen werden.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob PerfCounter.dll die Registrierungseinstellung CategoryOptions verwendet, um zu bestimmen, ob Leistungsindikatordaten aus kategoriespezifischem freigegebenem Speicher oder globalem Speicher geladen werden sollen.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|value|Beschreibung|  
|-----------|-----------------|  
|`false`|PerfCounter.dll verwendet nicht die KategorieOptions-Registrierungseinstellung Dies ist die Standardeinstellung.|  
|`true`|PerfCounter.dll verwendet die Registrierungseinstellung CategoryOptions.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  
 In Versionen von .NET Framework vor .NET Framework 4 entsprach die geladene Version von PerfCounter.dll der Laufzeit, die im Prozess geladen wurde. Wenn auf einem Computer sowohl die .NET Framework Version 1.1 als auch die .NET Framework 2.0-Anwendung installiert wäre, würde eine .NET Framework 1.1-Anwendung die .NET Framework 1.1-Version von PerfCounter.dll laden. Ab .NET Framework 4 wird die neueste installierte Version von PerfCounter.dll geladen. Dies bedeutet, dass eine .NET Framework 1.1-Anwendung die .NET Framework 4-Version von PerfCounter.dll lädt, wenn .NET Framework 4 auf dem Computer installiert ist.  
  
 Ab .NET Framework 4 überprüft PerfCounter.dll beim Verwenden von Leistungsindikatoren den Registrierungseintrag CategoryOptions für jeden Anbieter, um zu ermitteln, ob er aus kategoriespezifischem freigegebenem Speicher oder globalem freigegebenem Speicher gelesen werden soll. Der .NET Framework 1.1 PerfCounter.dll liest diesen Registrierungseintrag nicht, da er nicht über kategoriespezifischen freigegebenen Speicher informiert ist. es liest immer aus dem globalen freigegebenen Speicher.  
  
 Aus Gründen der Abwärtskompatibilität überprüft .NET Framework 4 PerfCounter.dll den Registrierungseintrag CategoryOptions nicht, wenn er in einer .NET Framework 1.1-Anwendung ausgeführt wird. Es verwendet einfach globalen freigegebenen Speicher, genau wie .NET Framework 1.1 PerfCounter.dll. Sie können jedoch die .NET Framework 4 PerfCounter.dll anweisen, `<forcePerformanceCounterUniqueSharedMemoryReads>` die Registrierungseinstellung zu überprüfen, indem Sie das Element aktivieren.  
  
> [!NOTE]
> Das `<forcePerformanceCounterUniqueSharedMemoryReads>` Aktivieren des Elements garantiert nicht, dass kategoriespezifischer freigegebener Speicher verwendet wird. Einstellung aktiviert, um `true` nur zu bewirken, dass PerfCounter.dll auf die Registrierungseinstellung CategoryOptions verweist. Die Standardeinstellung für CategoryOptions ist die Verwendung kategoriespezifischer gemeinsam genutzter Speicher. Sie können jedoch CategoryOptions ändern, um anzugeben, dass globaler freigegebener Speicher verwendet werden soll.  
  
 Der Registrierungsschlüssel, der die KategorieOptions-Einstellung enthält, lautet\\ HKEY_LOCAL_MACHINE-System-CurrentControlSet-Dienste<kategorieName\>. Standardmäßig ist CategoryOptions auf 3 festgelegt, was PerfCounter.dll anweist, kategoriespezifischen freigegebenen Speicher zu verwenden. Wenn CategoryOptions auf 0 gesetzt ist, verwendet PerfCounter.dll globalen freigegebenen Speicher. Instanzdaten werden nur wiederverwendet, wenn der Name der erstellten Instanz mit der wiederverwendeten Instanz identisch ist. Alle Versionen können in die Kategorie schreiben. Wenn CategoryOptions auf 1 festgelegt ist, wird globaler freigegebener Speicher verwendet, instanziierte Daten können jedoch wiederverwendet werden, wenn der Kategoriename die gleiche Länge wie die wiederverwendete Kategorie hat.  
  
 Die Einstellungen 0 und 1 können zu Speicherverlusten und dem Auffüllen des Leistungsindikatorspeichers führen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie angeben, dass PerfCounter.dll auf den Registrierungseintrag CategoryOptions verweisen soll, um zu bestimmen, ob kategoriespezifischer freigegebener Speicher verwendet werden soll.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Schema der Konfigurationsdatei](../index.md)
