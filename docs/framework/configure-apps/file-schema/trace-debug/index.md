---
title: "Schema f&#252;r Ablaufverfolgungs- und Debugeinstellungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Konfigurationsschema [.NET Framework], Ablaufverfolgungs- und Debugeinstellungen"
  - "Konfigurationsabschnitte [.NET Framework]"
  - "Konfigurationseinstellungen [.NET Framework], Debuggen"
  - "Konfigurationseinstellungen [.NET Framework], Ablaufverfolgung"
  - "Elemente [.NET Framework], Ablaufverfolgungs- und Debugeinstellungen"
  - "Schemakonfigurationseinstellungen"
  - "Ablaufverfolgungslistener, Ablaufverfolgungs- und Debugeinstellungsschema"
  - "Ablaufverfolgung [.NET Framework], Ablaufverfolgungs- und Debugeinstellungsschema"
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Schema f&#252;r Ablaufverfolgungs- und Debugeinstellungen
Die Ablaufverfolgungs\- und Debugeinstellungen geben die Ablaufverfolgungslistener, die Meldungen sammeln, speichern und weiterleiten, sowie die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.  
  
 In der folgenden Tabelle wird die Funktion der einzelnen Elemente für Ablaufverfolgungs\- und Debugeinstellungen beschrieben.  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|Fügt der `Listeners`\-Auflistung für eine Ablaufverfolgungsquelle einen Listener hinzu.|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|Fügt der `Listeners`\-Auflistung einen Listener hinzu.|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-sharedlisteners.md)|Fügt der `sharedListeners`\-Auflistung einen Listener hinzu.|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|Gibt die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.|  
|[\<assert\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|Legt fest, ob ein Meldungsfeld angezeigt wird, wenn die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>\-Methode aufgerufen wird; gibt darüber hinaus den Namen der Datei an, in die Meldungen geschrieben werden.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|Löscht die `Listeners`\-Auflistung für eine Ablaufverfolgungsquelle.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|Löscht die `Listeners`\-Auflistung für die Ablaufverfolgung.|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|Fügt einem Listener in der `Listeners`\-Auflistung für eine Ablaufverfolgungsquelle einen Filter hinzu.|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|Fügt einem Listener in der `Listeners`\-Auflistung für eine Ablaufverfolgung einen Filter hinzu.|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|Fügt einem Listener in der `sharedListeners`\-Auflistung einen Filter hinzu.|  
|[\<listeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|Gibt die Listener für die `Listeners`\-Auflistung für eine Ablaufverfolgungsquelle an.|  
|[\<listeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Gibt Listener für die `Listeners`\-Auflistung für eine Ablaufverfolgung an.|  
|[\<performanceCounters\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren gemeinsam genutzt wird.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|Entfernt einen Listener aus der `Listeners`\-Auflistung für eine Ablaufverfolgung.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|Entfernt einen Listener aus der `Listeners`\-Auflistung für eine Ablaufverfolgungsquelle.|  
|[\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|Enthält Listener, auf die jedes source\- bzw. trace\-Element verweisen kann.|  
|[\<sources\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|Enthält Ablaufverfolgungsquellen, die Ablaufverfolgungsmeldungen initiieren.|  
|[\<source\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|Gibt eine Ablaufverfolgungsquelle an, die Ablaufverfolgungsmeldungen initiiert.|  
|[\<switches\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|Enthält Ablaufverfolgungsschalter und die Ebene, auf die die Ablaufverfolgungsschalter festgelegt werden.|  
|[\<system.diagnostics\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/system-diagnostics-element.md)|Gibt die Ablaufverfolgungslistener, die Meldungen sammeln, speichern und weiterleiten, sowie die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.|  
|[\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|Enthält Listener, die Verfolgungsmeldungen sammeln, speichern und weiterleiten.|  
  
## Siehe auch  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.Debug>   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)