---
title: "Stack ETW Event | Microsoft Docs"
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
  - "stack event [.NET Framework]"
  - "ETW, stack event (CLR)"
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# Stack ETW Event
Das Stapelereignis sollte in Verbindung mit anderen Ereignissen verwendet werden, um nach dem Auslösen eines Ereignisses Stapelüberwachungen zu generieren.  Es wird protokolliert, wann der Laufzeitanbieter aktiviert wird.  Dies ist ein sehr häufiges Ereignis, da es immer dann ausgelöst wird, wenn ein anderes Laufzeitereignis ausgelöst wird.  Aus diesem Grund empfiehlt es sich, dass Sie dieses Ereignis mit Bedacht verwenden.  
  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene. \(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).\)  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|------------------------------------------------|-----------|  
|`StackKeyword` \(0x40000000\)|LogAlways\(0\)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen.  
  
|Ereignis|Ereignis\-ID|Auslöser|  
|--------------|------------------|--------------|  
|`CLRStackWalk`|82|In Verbindung mit anderen Ereignissen, um nach einem Ereignis Stapelüberwachungen zu generieren.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten.  
  
|Feldname|Datentyp|**Beschreibung**|  
|--------------|--------------|----------------------|  
|ClrInstanceID|win:Uint16|Eindeutiger Laufzeitbezeichner.|  
|Reserved1|win:UInt8|Reserviert.|  
|Reserved2|win:UInt8|Reserviert.|  
|FrameCount|win:UInt32|Die Anzahl von Rahmen in der Stapelüberwachung.|  
|Stapel|win:Pointer|Spalten von Anweisungszeigern.|  
  
## Siehe auch  
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)