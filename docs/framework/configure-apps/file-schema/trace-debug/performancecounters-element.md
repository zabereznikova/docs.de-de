---
title: '&lt;PerformanceCounters&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <perfomanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 64afd62c6eeca7bce14e331fdc65fccfa3d02bce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltperformancecountersgt-element"></a>&lt;PerformanceCounters&gt; Element
Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren freigegeben wird.  
  
 \<configuration>  
\<System.Diagnostics >  
\<PerformanceCounters >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<performanceCounters filemappingsize="524288" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|FileMappingSize|Erforderliches Attribut.<br /><br /> Gibt die Größe in Bytes, der dem globalen Arbeitsspeicher-Leistungsindikatoren gemeinsam genutzt wird. Der Standard ist 524288.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`Configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.|  
  
## <a name="remarks"></a>Hinweise  
 Leistungsindikatoren werden eine im Speicher abgebildete Datei oder shared Memory verwenden, um Leistungsdaten zu veröffentlichen.  Die Größe des freigegebenen Speicherbereichs bestimmt, wie viele Instanzen gleichzeitig verwendet werden können.  Es gibt zwei Arten von freigegebenem Arbeitsspeicher: globale freigegebene Speicher und separater freigegebener Arbeitsspeicher.  Der globale freigegebene Speicher wird von allen Leistungsindikatorkategorien, die mit .NET Framework, Version 1.0 oder 1.1 installiert.  Leistungsindikatorkategorien, die mit .NET Framework, Version 2.0 installiert verwenden separaten freigegebenen Arbeitsspeicher mit jeder Leistungsindikatorkategorie mit ihren eigenen Arbeitsspeicher.  
  
 Die Größe der globale freigegebene Speicher kann nur mit einer Konfigurationsdatei festgelegt werden.  Die Standardgröße ist 524.288, die maximale Größe beträgt 33.554.432 Bytes und die minimale Größe beträgt 32.768 Byte.  Da der globale freigegebene Speicher von allen Prozessen und Kategorien gemeinsam verwendet wird, gibt der erste Ersteller die Größe an.  Wenn Sie die Größe in der Anwendungskonfigurationsdatei definieren, wird nur diese Größe verwendet, wenn die Anwendung die erste Anwendung, die bewirkt, die Leistungsindikatoren dass ausgeführt.  Aus diesem Grund den richtigen Speicherort zum Angeben der `filemappingsize` Wert ist die Datei "Machine.config".  Speicher in der globale freigegebene Speicher kann nicht von einzelnen Leistungsindikatoren, sodass freigegeben werden, der globaler freigegebener Speicher ausgeschöpft ist, wenn eine große Anzahl von Leistungsindikatorinstanzen mit unterschiedlichen Namen erstellt werden.  
  
 Der FileMappingSize DWORD-Wert in der Registrierung Schlüssel für die Größe der separater freigegebener Arbeitsspeicher, HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<Kategorienamen >*\Performance verwiesen wird zuerst dann, durch den Wert für die globale freigegebene Speicher in der Konfigurationsdatei angegeben. Wenn der FileMappingSize-Wert ist nicht vorhanden, und klicken Sie dann auf ein Viertel die Größe separater freigegebener Arbeitsspeicher festgelegt ist (1/4) die globale Einstellung in der Konfigurationsdatei.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Diagnostics.PerformanceCounter>  
 <xref:System.Diagnostics.PerformanceCounterCategory>  
 <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>  
 <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
