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
ms.openlocfilehash: a7a8d96548704f223f05826af79a4e227bdfab06
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379831"
---
# <a name="icordebugthread2-interface"></a>ICorDebugThread2-Schnittstelle
Dient als logische Erweiterung der ICorDebugThread-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetActiveFunctions-Methode](icordebugthread2-getactivefunctions-method.md)|Ruft ein Array von COR_ACTIVE_FUNCTION-Instanzen ab, die Daten über die aktiven Funktionen in den Frames eines Threads enthalten.|  
|[GetConnectionID-Methode](icordebugthread2-getconnectionid-method.md)|Ruft einen Verbindungs Bezeichner für dieses ab `ICorDebugThread2` .|  
|[GetTaskID-Methode](icordebugthread2-gettaskid-method.md)|Ruft einen Aufgaben Bezeichner für dieses ab `ICorDebugThread2` .|  
|[GetVolatileOSThreadID-Methode](icordebugthread2-getvolatileosthreadid-method.md)|Ruft den Thread Bezeichner des Betriebssystems für diesen ab `ICorDebugThread2` .|  
|[InterceptCurrentException-Methode](icordebugthread2-interceptcurrentexception-method.md)|Ermöglicht einem Debugger das Abfangen der aktuellen Ausnahme in einem Thread.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](debugging-interfaces.md)
