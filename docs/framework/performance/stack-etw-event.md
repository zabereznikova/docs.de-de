---
title: ETW-Stapelereignis
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 073622c22b957975ed799cf5b3bc3826473114b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33396353"
---
# <a name="stack-etw-event"></a>ETW-Stapelereignis
Das Stapelereignis sollte in Verbindung mit anderen Ereignissen verwendet werden, um Stapelüberwachungen zu generieren, nachdem ein Ereignis ausgelöst wird. Es wird protokolliert, wann der Laufzeitanbieter aktiviert ist. Dieses Ereignis hat eine hohe Frequenz, da es ausgelöst wird, wenn ein anderes Laufzeitereignis ausgelöst wird. Aus diesem Grund wird empfohlen, dass Sie dieses Ereignis mit Vorsicht verwenden.  
  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an. (Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`StackKeyword` (0x40000000)|LogAlways(0)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|82|In Verbindung mit anderen Ereignissen zum Generieren von Stapelüberwachungen nach einem Ereignis.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|ClrInstanceID|win:UInt16|URI.|  
|Reserved1|win:UInt8|Reserviert.|  
|Reserved2|win:UInt8|Reserviert.|  
|FrameCount|win:UInt32|Die Anzahl von Frames in der Stapelüberwachung.|  
|Stapel|win:Pointer|Anweisungszeigerspalten.|  
  
## <a name="see-also"></a>Siehe auch  
 [CLR-ETW-Ereignisse](../../../docs/framework/performance/clr-etw-events.md)
