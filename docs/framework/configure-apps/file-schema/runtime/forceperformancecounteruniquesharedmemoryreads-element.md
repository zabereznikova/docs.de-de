---
title: <forcePerformanceCounterUniqueSharedMemoryReads>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 719448ba3de2aca0621fc17b9fadbdd3b8588f2e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178241"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a>\<forcePerformanceCounterUniqueSharedMemoryReads>-Element

Gibt an, ob „PerfCounter.dll“ die Registrierungseinstellung „CategoryOptions“ in einer .NET Framework Version 1.1-Anwendung verwendet, um zu bestimmen, ob Leistungsindikatordaten aus kategoriespezifischem, gemeinsam genutztem Arbeitsspeicher oder aus dem globalen Arbeitsspeicher geladen werden.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob PerfCounter.dll die Registrierungs Einstellung categoryoptions verwendet, um zu bestimmen, ob Leistungsdaten aus dem kategoriespezifischen gemeinsam genutzten oder globalen Arbeitsspeicher geladen werden sollen.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|PerfCounter.dll verwendet nicht die Registrierungs Einstellung categoryoptions, dies ist die Standardeinstellung.|  
|`true`|PerfCounter.dll verwendet die Registrierungs Einstellung categoryoptions.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  

 In Versionen der .NET Framework vor dem .NET Framework 4 entsprach die Version von PerfCounter.dll, die geladen wurde, der Laufzeit, die in den Prozess geladen wurde. Wenn auf einem Computer sowohl der .NET Framework Version 1,1 als auch .NET Framework 2,0 installiert war, würde eine .NET Framework 1,1-Anwendung die .NET Framework 1,1-Version PerfCounter.dll laden. Ab .NET Framework 4 wird die neueste installierte Version von PerfCounter.dll geladen. Dies bedeutet, dass eine .NET Framework 1,1-Anwendung die .NET Framework 4-Version von PerfCounter.dll lädt, wenn die .NET Framework 4 auf dem Computer installiert ist.  
  
 Ab der .NET Framework 4 prüft PerfCounter.dll bei der Nutzung von Leistungsindikatoren den Registrierungs Eintrag categoryoptions für jeden Anbieter, um zu bestimmen, ob er aus dem kategoriespezifischen freigegebenen Arbeitsspeicher oder dem globalen gemeinsam genutzten Speicher lesen soll. Der .NET Framework 1,1 PerfCounter.dll liest diesen Registrierungs Eintrag nicht, da er keinen kategoriespezifischen freigegebenen Arbeitsspeicher kennt. Er liest immer aus dem globalen gemeinsam genutzten Speicher.  
  
 Aus Gründen der Abwärtskompatibilität überprüft der .NET Framework 4-PerfCounter.dll den Registrierungs Eintrag categoryoptions nicht, wenn er in einer .NET Framework 1,1-Anwendung ausgeführt wird. Es verwendet einfach den globalen gemeinsam genutzten Speicher, genau wie die .NET Framework 1,1 PerfCounter.dll. Sie können jedoch die .NET Framework 4-PerfCounter.dll anweisen, die Registrierungs Einstellung durch Aktivieren des-Elements zu überprüfen `<forcePerformanceCounterUniqueSharedMemoryReads>` .  
  
> [!NOTE]
> Das Aktivieren des `<forcePerformanceCounterUniqueSharedMemoryReads>` -Elements garantiert nicht, dass kategoriespezifischer gemeinsam genutzter Arbeitsspeicher verwendet wird. Wenn die Einstellung aktiviert ist, `true` bewirkt dies nur PerfCounter.dll, dass auf die Registrierungs Einstellung categoryoptions verwiesen wird. Die Standardeinstellung für categoryoptions ist die Verwendung des kategoriespezifischen freigegebenen Speichers. Sie können jedoch categoryoptions ändern, um anzugeben, dass der globale gemeinsame Arbeitsspeicher verwendet werden soll.  
  
 Der Registrierungsschlüssel, der die Einstellung categoryoptions enthält, ist HKEY_LOCAL_MACHINE \system\currentcontrolset\services \\<CategoryName \> \Performance. Standardmäßig ist "categoryoptions" auf "3" festgelegt, was PerfCounter.dll anweist, kategoriespezifischen freigegebenen Arbeitsspeicher zu verwenden. Wenn categoryoptions auf 0 festgelegt ist, PerfCounter.dll den globalen gemeinsam genutzten Arbeitsspeicher verwendet. Instanzdaten werden nur dann wieder verwendet, wenn der Name der Instanz, die erstellt wird, mit der Instanz identisch ist, die wieder verwendet wird. Alle Versionen können in die Kategorie schreiben. Wenn categoryoptions auf 1 festgelegt ist, wird der globale freigegebene Speicher verwendet, aber Instanzdaten können wieder verwendet werden, wenn der Kategoriename dieselbe Länge wie die wiederverwendbare Kategorie hat.  
  
 Die Einstellungen 0 und 1 können zu Speicher Verlusten und zum Auffüllen des Leistungs Zählers führen.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass PerfCounter.dll auf den Registrierungs Eintrag categoryoptions verweisen soll, um zu bestimmen, ob der Kategoriespezifische freigegebene Speicher verwendet werden soll.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
