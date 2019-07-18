---
title: ExceptionThrown_V1-ETW-Ereignis
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd322d25d91bb277a4c817594c968c28a6d61d68
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723016"
---
# <a name="exception-thrownv1-etw-event"></a>ExceptionThrown_V1-ETW-Ereignis
Dieses Ereignis erfasst Informationen über die ausgelösten Ausnahmen.  
  
 Die folgende Tabelle zeigt das Schlüsselwort, unter dem das Ereignis ausgelöst wird, und die Ebene des Ereignisses. (Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`ExceptionKeyword` (0x8000)|Warnung (2)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|event|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|80|Eine verwaltete Ausnahme wird ausgelöst.|  
  
 In der folgenden Tabelle finden Sie die Ereignisdaten.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|Ausnahmetyp|win:UnicodeString|Typ der Ausnahme, z.B. `System.NullReferenceException`.|  
|Ausnahmemeldung|win:UnicodeString|Tatsächliche Ausnahmemeldung.|  
|EIPCodeThrow|win:Pointer|Anweisungszeiger an der Stelle, an der die Ausnahme aufgetreten ist.|  
|ExceptionHR|win:UInt32|Ausnahme [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException (siehe [CLR-ETW-Ereignisse](../../../docs/framework/performance/clr-etw-events.md) in der Dokumentation zu Visual Basic).<br /><br /> 0x02: IsNestedException.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: IsCorruptedStateException (gibt an, dass der Prozessstatus fehlerhaft ist, finden Sie unter [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) auf MSDN).<br /><br /> 0 x 10: IsCLSCompliant (eine Ausnahme, die abgeleitet <xref:System.Exception> CLS-kompatibel ist, andernfalls ist es nicht CLS-kompatibel).|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
## <a name="see-also"></a>Siehe auch

- [CLR-ETW-Ereignisse](../../../docs/framework/performance/clr-etw-events.md)
