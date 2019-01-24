---
title: ICorDebugChain-Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0bb716f1ad4087642a76dc84266ec6d3f46c1ae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571203"
---
# <a name="icordebugchain-interface1"></a>ICorDebugChain-Schnittstelle1
Stellt ein Segment einer physikalischen oder logischen Aufrufliste dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumerateFrames-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|Ruft einen Enumerator, der alle verwalteten Stapelrahmen in der Kette, enthält der letzten Frame ab.|  
|[GetActiveFrame-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|Ruft das aktive (d. h. die letzte) Frame in der Kette.|  
|[GetCallee-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|Ruft die Zertifikatskette, die von dieser Kette aufgerufen wurde.|  
|[GetCaller-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|Ruft die Zertifikatskette, die dieser Kette aufgerufen.|  
|[GetContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|Nicht implementiert.|  
|[GetNext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|Ruft die nächste Kette von Frames für den Thread ab.|  
|[GetPrevious-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|Ruft die vorherige Kette von Frames für den Thread ab.|  
|[GetReason-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|Ruft den Grund für die Entstehung dieser Aufrufkette ab.|  
|[GetRegisterSet-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|Ruft ab, das Register, die für den aktiven Teil des dieser Kette festgelegt.|  
|[GetStackRange-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|Ruft den Adressbereich des Stack-Segments für diese Kette ab.|  
|[GetThread-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|Ruft den physischen Thread, die, den diese Kette von Aufrufen ist, Teil ab.|  
|[IsManaged-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|Ruft einen Wert, der angibt, ob dieser Kette auf verwalteten Code ausgeführt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die Stapelrahmen in einer Kette zusammenhängenden Stapelspeicher belegt und den gleichen Thread und Kontext. Eine Kette kann entweder Ketten verwaltetem oder nicht verwalteten Code darstellen. Ein leeres `ICorDebugChain` Instanz darstellt, eine Kette von nicht verwaltetem Code.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
