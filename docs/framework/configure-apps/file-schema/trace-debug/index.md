---
title: Schema für Ablaufverfolgungs- und Debugeinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- tracing [.NET Framework], trace and debug settings schema
- configuration schema [.NET Framework], trace and debug settings
- configuration settings [.NET Framework], tracing
- schema configuration settings
- configuration settings [.NET Framework], debugging
- trace listeners, trace and debug settings schema
- configuration sections [.NET Framework]
- elements [.NET Framework], trace and debug settings
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
ms.openlocfilehash: 037d08b33e9aa6a64d236b36ebcf821b604b03df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "69927116"
---
# <a name="trace-and-debug-settings-schema"></a>Schema für Ablaufverfolgungs- und Debugeinstellungen
Ablaufverfolgungs- und Debugeinstellungen geben Ablaufverfolgungslistener an, die Nachrichten sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.  
  
 Die folgende Tabelle beschreibt die Funktion jedes Elements der Ablaufverfolgungs- und Debugeinstellungen.  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-source.md)|Fügt einen Listener zu der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.|  
|[\<add>](add-element-for-listeners-for-trace.md)|Fügt einen Listener zu der `Listeners`-Sammlung hinzu.|  
|[\<add>](add-element-for-sharedlisteners.md)|Fügt einen Listener zu der `sharedListeners`-Sammlung hinzu.|  
|[\<add>](add-element-for-switches.md)|Gibt die Ebene an, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|[\<assert>](assert-element.md)|Gibt an, ob ein Meldungsfeld angezeigt wird, wenn Sie die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-Methode aufrufen. Außerdem wird der Name der Datei angegeben, in die die Meldung geschrieben werden soll.|  
|[\<clear>](clear-element-for-listeners-for-source.md)|Löscht die `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.|  
|[\<clear>](clear-element-for-listeners-for-trace.md)|Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.|  
|[\<filter>](filter-element-for-add-for-listeners-for-source.md)|Fügt einen Filter zu einem Listener in der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle hinzu.|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|Fügt einen Filter zu einem Listener in der `Listeners`-Sammlung für die Ablaufverfolgung hinzu.|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|Fügt einen Filter zu einem Listener in der `sharedListeners`-Sammlung hinzu.|  
|[\<listeners>](listeners-element-for-source.md)|Gibt Listener für die `Listeners`-Sammlung für eine Ablaufverfolgungsquelle an.|  
|[\<listeners>](listeners-element-for-trace.md)|Gibt die Listener für die `Listeners`-Sammlung für die Ablaufverfolgung an.|  
|[\<performanceCounters>](performancecounters-element.md)|Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren freigegeben wird.|  
|[\<remove>](remove-element-for-listeners-for-trace.md)|Entfernt einen Listener aus der `Listeners`-Sammlung für die Ablaufverfolgung.|  
|[\<remove>](remove-element-for-listeners-for-source.md)|Entfernt einen Listener aus der `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.|  
|[\<sharedListeners>](sharedlisteners-element.md)|Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.|  
|[\<sources>](sources-element.md)|Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.|  
|[\<source>](source-element.md)|Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.|  
|[\<switches>](switches-element.md)|Enthält Ablaufverfolgungsschalter und die Ebene, für die diese festgelegt sind.|  
|[\<system.diagnostics>](system-diagnostics-element.md)|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|[\<trace>](trace-element.md)|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.Debug>
- [Konfigurationsdateischema](../index.md)
