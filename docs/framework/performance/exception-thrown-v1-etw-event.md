---
title: "Exception Thrown_V1 ETW Event | Microsoft Docs"
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
  - "ExceptionThrown_V1 event [.NET Framework]"
  - "ETW, ExceptionThrown_V1 event (CLR)"
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
caps.latest.revision: 6
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 6
---
# Exception Thrown_V1 ETW Event
Dieses Ereignis erfasst Informationen zu den Ausnahmen, die ausgelöst werden.  
  
 In der folgenden Tabelle werden das Schlüsselwort, unter dem das Ereignis ausgelöst wird, sowie die Ebene des Ereignisses angezeigt. \(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).\)  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|------------------------------------------------|-----------|  
|`ExceptionKeyword` \(0x8000\)|Warnung \(2\)|  
  
 Die folgende Tabelle zeigt Ereignisinformationen.  
  
|Ereignis|Ereignis\-ID|Auslöser|  
|--------------|------------------|--------------|  
|`ExceptionThrown_V1`|80|Eine verwaltete Ausnahme wird ausgelöst.|  
  
 Die folgende Tabelle zeigt Ereignisdaten.  
  
|Feldname|Datentyp|**Beschreibung**|  
|--------------|--------------|----------------------|  
|Ausnahmetyp|win:UnicodeString|Typ der Ausnahme; z. B. `System.NullReferenceException`.|  
|Ausnahmemeldung|win:UnicodeString|Tatsächliche Ausnahmemeldung.|  
|EIPCodeThrow|win:Pointer|Anweisungszeiger, für die Stelle, an der die Ausnahme aufgetreten ist.|  
|ExceptionHR|win:UInt32|Ausnahme [HRESULT](http://go.microsoft.com/fwlink/?LinkId=179679).|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException \(siehe [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) in der Visual Basic\-Dokumentation\).<br /><br /> 0x02: IsNestedException.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: IsCorruptedStateException \(gibt an, dass der Prozesszustand fehlerhaft ist; finden Sie unter [Behandlung von beschädigten Zustands\-Ausnahmen](http://go.microsoft.com/fwlink/?LinkId=179681) auf MSDN\).<br /><br /> 0x10: IsCLSCompliant \(eine Ausnahme, die von <xref:System.Exception> abgeleitet wird, ist CLS\-kompatibel; andernfalls ist sie nicht CLS\-kompatibel\).|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
## Siehe auch  
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)