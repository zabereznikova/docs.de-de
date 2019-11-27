---
title: ExceptionThrown_V1-ETW-Ereignis
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f0e968053c87319bf90bf3de0f21d750ec899ab
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447632"
---
# <a name="exception-thrown_v1-etw-event"></a>ExceptionThrown_V1-ETW-Ereignis
Dieses Ereignis erfasst Informationen über die ausgelösten Ausnahmen.  
  
 Die folgende Tabelle zeigt das Schlüsselwort, unter dem das Ereignis ausgelöst wird, und die Ebene des Ereignisses. (Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)  
  
|Schlüsselwort zum Auslösen des Ereignisses|Level|  
|-----------------------------------|-----------|  
|`ExceptionKeyword` (0x8000)|Warnung (2)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|80|Eine verwaltete Ausnahme wird ausgelöst.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|Ausnahmetyp|win:UnicodeString|Typ der Ausnahme, z.B. `System.NullReferenceException`.|  
|Ausnahmemeldung|win:UnicodeString|Tatsächliche Ausnahmemeldung.|  
|EIPCodeThrow|win:Pointer|Anweisungszeiger an der Stelle, an der die Ausnahme aufgetreten ist.|  
|ExceptionHR|win:UInt32|Ausnahme [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException (siehe [CLR ETW Events (CLR-ETW-Ereignisse)](clr-etw-events.md) in der Visual Basic-Dokumentation).<br /><br /> 0x02: IsNestedException.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: isbeschätedstateexception (gibt an, dass der Prozessstatus beschädigt ist, siehe [Behandlung von Ausnahmen für beschädigte](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)Zustände).<br /><br /> 0x10: IsCLSCompliant (eine Ausnahme, die von <xref:System.Exception> ableitet, ob eine CLS-Kompatibilität vorliegt, andernfalls ist sie nicht CLS-kompatibel).|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
## <a name="see-also"></a>Siehe auch

- [CLR ETW Events (CLR-ETW-Ereignisse)](clr-etw-events.md)
