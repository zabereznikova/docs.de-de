---
title: ICorDebugChain-Schnittstelle
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
ms.openlocfilehash: 8baf3567e4ae188f88ad3a2df157cffab3f597ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125797"
---
# <a name="icordebugchain-interface"></a>ICorDebugChain-Schnittstelle

Stellt ein Segment einer physikalischen oder logischen Aufrufliste dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumerateFrames-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|Ruft einen Enumerator ab, der alle verwalteten Stapel Rahmen in der Kette enthält, beginnend mit dem letzten Frame.|  
|[GetActiveFrame-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|Ruft den aktiven Frame (d. h. den aktuellen) Frame in der Kette ab.|  
|[GetCallee-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|Ruft die Kette ab, die von dieser Kette aufgerufen wurde.|  
|[GetCaller-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|Ruft die Kette ab, die diese Kette aufgerufen hat.|  
|[GetContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|Nicht implementiert.|  
|[GetNext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|Ruft die nächste Rahmen Kette für den Thread ab.|  
|[GetPrevious-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|Ruft die vorherige Rahmen Kette für den Thread ab.|  
|[GetReason-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|Ruft den Grund für die Entstehung dieser aufrufenden Kette ab.|  
|[GetRegisterSet-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|Ruft den Register Satz für den aktiven Teil dieser Kette ab.|  
|[GetStackRange-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|Ruft den Adressbereich des Stapel Segments für diese Kette ab.|  
|[GetThread-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|Ruft den physischen Thread ab, zu dem diese rufkette gehört.|  
|[IsManaged-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|Ruft einen Wert ab, der angibt, ob diese Kette verwalteten Code ausgeführt.|  
  
## <a name="remarks"></a>Hinweise  
 Die Stapel Rahmen in einer Kette belegen zusammenhängenden Stapel Speicher und verwenden denselben Thread und Kontext. Eine Kette kann entweder verwaltete oder nicht verwaltete Code Ketten darstellen. Eine leere `ICorDebugChain` Instanz stellt eine nicht verwaltete Codekette dar.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
