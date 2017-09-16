---
title: ETW-Konfliktereignisse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
caps.latest.revision: 7
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 931a3f7d5cbc441a3cae2b7359d129dff02afd44
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="contention-etw-events"></a>ETW-Konfliktereignisse
Konfliktereignisse werden immer dann ausgelöst, wenn es Konflikte bei <xref:System.Threading.Monitor?displayProperty=fullName>-Sperren oder nativen Sperren gibt, die von der Laufzeit verwendet werden. Konflikte treten auf, wenn ein Thread auf eine Sperre wartet, während ein anderer Thread die Sperre besitzt.  
  
 Die folgende Tabelle zeigt das Schlüsselwort, unter dem Konfliktereignisse ausgelöst werden, und die Ebene der Ereignisse. (Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`ContentionKeyword` (0x4000)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`ContentionStart_V1`|81|Konflikt startet. Dieses Ereignis enthält die Spinzeit vor dem Abruf einer Sperre eines Threads nicht. Dies wird nur ausgelöst, wenn der Thread darauf wartet, eine Sperre abzurufen.|  
|`ContentionStop`|81|Konflikt endet.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|Flags|win:UInt8|0 für verwaltet. 1 für nativ.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR.|  
  
## <a name="see-also"></a>Siehe auch  
 [CLR-ETW-Ereignisse](../../../docs/framework/performance/clr-etw-events.md)

