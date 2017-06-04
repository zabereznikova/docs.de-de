---
title: "Runtime Information ETW Events | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "runtime information events [.NET Framework]"
  - "ETW, runtime information events"
ms.assetid: 68b4edbc-7f3b-45f6-ab75-4fd066d6af9a
caps.latest.revision: 6
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 6
---
# Runtime Information ETW Events
Mit diesen ETW\-Ereignissen werden Informationen über die Laufzeit protokolliert, einschließlich SKU, Versionsnummer, der Methode, mit der die Laufzeit aktiviert wurde, die Befehlszeilenparameter, mit denen sie gestartet wurde, die GUID \(sofern zutreffend\) und andere relevante Informationen.  Wenn innerhalb eines Prozesses mehrere Laufzeiten ausgeführt werden, können die Laufzeiten anhand der Informationen aus diesen Ereignissen \(die ClrInstanceID\) eindeutig bestimmt werden.  
  
 Die folgende Tabelle zeigt die beiden Laufzeitinformationsereignisse.  Die Ereignisse können unter jedem Schlüsselwort oder jeder Maske ausgelöst werden. \(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).\)  
  
|Ereignis|Ereignis\-ID|Anbieter|**Beschreibung**|  
|--------------|------------------|--------------|----------------------|  
|`RuntimeInformationEvent`|187|CLRRuntime|Wird ausgelöst, wenn eine Laufzeit geladen wird.|  
|`RuntimeInformationDCStart`|187|CLRRundown|Listet die Laufzeiten auf, die geladen werden.|  
  
 Die folgende Tabelle zeigt Ereignisdaten.  
  
|Feldname|Datentyp|**Beschreibung**|  
|--------------|--------------|----------------------|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
|SKU|win:UInt16|1 – Desktop\-CLR.<br /><br /> 2 – CoreCLR.|  
|BclVersion – Hauptversion|win:UInt16|Hauptversion von "mscorlib.dll".|  
|BclVersion – Nebenversion|win:UInt16|Nebenversionsnummer von "mscorlib.dll".|  
|BclVersion – Buildnummer|win:UInt16|Buildnummer von "mscorlib.dll".|  
|BclVersion – QFE|win:UInt16|Hotfixversionsnummer von mscorlib.dll.|  
|VMVersion – Hauptversion|win:UInt16|Version von "clr.dll" oder "coreclr.dll", abhängig von der SKU.|  
|VMVersion – Nebenversion|win:UInt16|Nebenversion von "clr.dll" oder "coreclr.dll", abhängig vom SKU.|  
|VMVersion – Buildnummer|win:UInt16|Buildnummer von "clr.dll" oder "coreclr.dll".|  
|VMVersion – QFE|win:UInt16|Hotfixversionsnummer von clr.dll oder coreclr.dll.|  
|StartupFlags|win:UInt32|In mscoree.h definierte Startflags.|  
|StartupMode|win:UInt8|0x01 – Verwaltete ausführbare Datei.<br /><br /> 0x02 – Gehostete CLR.<br /><br /> 0x04 – Interop unter C\+\+\-Verwaltung.<br /><br /> 0x08 – COM\-aktiviert.<br /><br /> 0x10 – Andere.|  
|CommandLine|win:UnicodeString|Nicht NULL nur, wenn StartupMode\=0x01.|  
|ComObjectGUID|win:GUID|Nicht NULL nur, wenn StartupMode\=0x08.|  
|RuntimeDLLPath|win:UnicodeString|Pfad zur CLR\-DLL\-Datei, die in den Prozess geladen wurde.|  
  
## Siehe auch  
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)