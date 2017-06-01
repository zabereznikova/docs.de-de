---
title: "Contention ETW Events | Microsoft Docs"
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
  - "contention events [.NET Framework]"
  - "ETW, contention events (CLR)"
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Contention ETW Events
Konfliktereignisse werden ausgelöst, wenn bei von der Laufzeit verwendeten <xref:System.Threading.Monitor?displayProperty=fullName>\-Sperren oder systemeigenen Sperren ein Konflikt vorliegt.  Konflikte treten auf, wenn ein Thread auf eine Sperre wartet, während ein anderer Thread die Sperre besitzt.  
  
 Die folgende Tabelle zeigt das Schlüsselwort, unter dem Konfliktereignisse ausgelöst werden, und die Ebene der Ereignisse. \(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).\)  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|------------------------------------------------|-----------|  
|`ContentionKeyword` \(0x4000\)|Informationen \(4\)|  
  
 Die folgende Tabelle zeigt Ereignisinformationen.  
  
|Ereignis|Ereignis\-ID|Auslöser|  
|--------------|------------------|--------------|  
|`ContentionStart_V1`|81|Konfliktbeginn.  Das Ereignis enthält nicht die Spindauer, bevor ein Thread auf das Abrufen einer Sperre wartet, es wird erst ausgelöst, wenn der Thread mit dem Warten auf das Abrufen einer Sperre beginnt.|  
|`ContentionStop`|81|Konfliktende.|  
  
 Die folgende Tabelle zeigt Ereignisdaten.  
  
|Feldname|Datentyp|**Beschreibung**|  
|--------------|--------------|----------------------|  
|Flags|win:UInt8|0 für verwaltet, 1 für systemeigen.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR.|  
  
## Siehe auch  
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)