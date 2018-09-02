---
title: ExceptionThrown_V1-ETW-Ereignis
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 865b7b16d5807bd9161855f453128a63c84eab96
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43400821"
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
|ExceptionFlags|win:UInt16|0x01: HasInnerException (siehe [CLR ETW Events (CLR-ETW-Ereignisse)](../../../docs/framework/performance/clr-etw-events.md) in der Visual Basic-Dokumentation).<br /><br /> 0x02: IsNestedException.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: IsCorruptedStateException (gibt an, dass der Prozessstatus fehlerhaft ist, siehe [Handling Corrupted State Exceptions (Behandeln beschädigter Statusausnahmen)](https://go.microsoft.com/fwlink/?LinkId=179681) auf MSDN).<br /><br /> 0x10: IsCLSCompliant (eine Ausnahme, die von <xref:System.Exception> ableitet, ob eine CLS-Kompatibilität vorliegt, andernfalls ist sie nicht CLS-kompatibel).|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
## <a name="see-also"></a>Siehe auch  
 [CLR-ETW-Ereignisse](../../../docs/framework/performance/clr-etw-events.md)
