---
title: ICorDebugThread2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d21c221bba3ac668924003f96580bb660229ad7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963006"
---
# <a name="icordebugthread2-interface"></a>ICorDebugThread2-Schnittstelle
Dient als logische Erweiterung der ICorDebugThread-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetActiveFunctions-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|Ruft ein Array von COR_ACTIVE_FUNCTION-Instanzen ab, die Daten über die aktiven Funktionen in den Frames eines Threads enthalten.|  
|[GetConnectionID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|Ruft einen Verbindungs Bezeichner für `ICorDebugThread2`dieses ab.|  
|[GetTaskID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|Ruft einen Aufgaben Bezeichner für `ICorDebugThread2`dieses ab.|  
|[GetVolatileOSThreadID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|Ruft den Thread Bezeichner des Betriebssystems `ICorDebugThread2`für diesen ab.|  
|[InterceptCurrentException-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|Ermöglicht einem Debugger das Abfangen der aktuellen Ausnahme in einem Thread.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
