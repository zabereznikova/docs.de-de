---
title: "&lt;performanceCounters&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<perfomanceCounters>-Element"
  - "performanceCounters-Element"
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# &lt;performanceCounters&gt;-Element
Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren gemeinsam genutzt wird.  
  
## Syntax  
  
```  
<performanceCounters filemappingsize="524288" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|filemappingsize|Erforderliches Attribut.<br /><br /> Gibt die Größe des globalen Speichers \(in Bytes\) an, der von den Leistungsindikatoren gemeinsam genutzt wird.  Standardwert: 524288.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`Configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt das Stammelement für den ASP.NET\-Konfigurationsabschnitt an.|  
  
## Hinweise  
 Leistungsindikatoren veröffentlichen Leistungsdaten anhand einer Speicherabbilddatei oder eines gemeinsam genutzten Speicherbereichs.  Die Größe des freigegebenen Speicherbereichs bestimmt die Anzahl von Instanzen, die gleichzeitig verwendet werden können.  Bei freigegebenem Speicher kann es sich um globalen oder separaten Speicher handeln.  Globaler freigegebener Speicher wird von allen Leistungsindikatorkategorien verwendet, die mit .NET Framework, Version 1.0 oder 1.1, installiert sind.  Die mit .NET Framework, Version 2.0, installierten Leistungsindikatorkategorien verwenden separaten freigegebenen Speicher, wobei jede Leistungsindikatorkategorie über einen eigenen Speicherbereich verfügt.  
  
 Die Größe des globalen freigegebenen Speichers kann nur über eine Konfigurationsdatei festgelegt werden.  Die Standardgröße beträgt 524.288 Bytes, die maximale Größe beträgt 33.554.432 Bytes, und die minimale Größe beträgt 32.768 Bytes.  Da der globale freigegebene Speicher von allen Prozessen und Kategorien verwendet wird, wird die Größe durch den ersten Ersteller festgelegt.  Wenn Sie die Größe in der Anwendungskonfigurationsdatei festlegen, wird diese Angabe nur verwendet, wenn diese Anwendung die erste Anwendung ist, die die Ausführung der Leistungsindikatoren auslöst.  Der `filemappingsize`\-Wert sollte daher in der Datei Machine.config angegeben werden.  Einzelne Leistungsindikatoren können keinen Speicher aus dem globalen freigegebenen Speicher freigeben. Wenn eine große Anzahl von Leistungsindikatorinstanzen mit unterschiedlichen Namen erstellt wird, können diese den globalen freigegebenen Speicher daher vollständig belegen.  
  
 Für die Größe von separaten freigegebenen Speicherbereichen, wird der FileMappingSize\-Wert DWORD im Registrierungsschlüssel HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\*\<category name\>*\\Performance zuerst verwiesen, gefolgt durch den Wert, der für den weltweiten freigegebenen Arbeitsspeicher in der Konfigurationsdatei festgelegt ist.  Wenn der Wert von FileMappingSize nicht vorhanden ist, wird die Größe des separaten freigegebenen Speichers auf ein Viertel \(1\/4\) des Werts für den globalen Speicher in der Konfigurationsdatei festgelegt.  
  
## Siehe auch  
 <xref:System.Diagnostics.PerformanceCounter>   
 <xref:System.Diagnostics.PerformanceCounterCategory>   
 <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>   
 <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>