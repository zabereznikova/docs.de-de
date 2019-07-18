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
ms.openlocfilehash: 82648714c375998e9daa1bb59cd9ebd9802b5794
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993940"
---
# <a name="icordebugthread2-interface"></a>ICorDebugThread2-Schnittstelle
Fungiert als logische Erweiterung von der ICorDebugThread-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetActiveFunctions-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|Ruft ein Array von COR_ACTIVE_FUNCTION-Instanzen, die Daten über die aktiven Funktionen in den Rahmen eines Threads enthalten.|  
|[GetConnectionID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|Ruft einen Verbindungsbezeichner für diese `ICorDebugThread2`.|  
|[GetTaskID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|Ruft einen Aufgabenbezeichner für diese `ICorDebugThread2`.|  
|[GetVolatileOSThreadID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|Ruft den Bezeichner des Threads für diese `ICorDebugThread2`.|  
|[InterceptCurrentException-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|Können Sie einen Debugger an die aktuelle Ausnahme in einem Thread abfangen.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
