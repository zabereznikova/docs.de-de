---
title: ICorDebugThread-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
ms.openlocfilehash: c7333f4210d0a2ec4ff71a0fac0ea00068fecc57
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133494"
---
# <a name="icordebugthread-interface"></a>ICorDebugThread-Schnittstelle
Stellt einen Thread in einem Prozess dar. Die Lebensdauer einer `ICorDebugThread`-Instanz ist identisch mit der Lebensdauer des von ihr dargestellten Threads.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ClearCurrentException-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|Diese Methode ist nicht implementiert. Verwenden Sie sie nicht.|  
|[CreateEval-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|Erstellt ein ICorDebugEval-Objekt, das mit diesem `ICorDebugThread`arbeitet.|  
|[CreateStepper-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|Erstellt ein ICorDebug-Stepper-Objekt, das das schrittweise durchlaufen des aktiven Frames in diesem `ICorDebugThread`ermöglicht.|  
|[EnumerateChains-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|Ruft einen Schnittstellen Zeiger auf einen ICorDebug-chainenum-Enumerator ab, der alle Stapel Ketten in diesem `ICorDebugThread`enthält.|  
|[GetActiveChain-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|Ruft einen Schnittstellen Zeiger auf die aktive ICorDebug-Kette in diesem `ICorDebugThread`ab.|  
|[GetActiveFrame-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|Ruft einen Schnittstellen Zeiger auf den aktiven ICorDebug-Frame auf diesem `ICorDebugThread`ab.|  
|[GetAppDomain-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|Ruft einen Schnittstellen Zeiger auf die Anwendungsdomäne ab, in der dieser `ICorDebugThread` derzeit ausgeführt wird.|  
|[GetCurrentException-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|Ruft einen Schnittstellen Zeiger auf ein ICorDebugValue-Objekt ab, das eine Ausnahme darstellt, die zurzeit von verwaltetem Code ausgelöst wird.|  
|[GetDebugState-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|Ruft einen CorDebugThreadState-Wert ab, der den aktuellen Debugzustand dieses `ICorDebugThread`beschreibt.|  
|[GetHandle-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|Ruft das aktuelle Handle für den aktiven Teil dieses `ICorDebugThread`ab.|  
|[GetID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|Ruft den aktuellen Betriebssystem Bezeichner des aktiven Teils dieses `ICorDebugThread`ab.|  
|[GetObject-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|Ruft einen Schnittstellen Zeiger auf den Common Language Runtime (CLR)-Thread ab.|  
|[GetProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|Ruft einen Schnittstellen Zeiger auf den Prozess ab, dessen-`ICorDebugThread` ein Teil bildet.|  
|[GetRegisterSet-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|Ruft einen Schnittstellen Zeiger auf den diesem `ICorDebugThread`zugeordneten Register Satz ab.|  
|[GetUserState-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|Ruft eine bitweise Kombination von CorDebugUserState-Werten ab, die den aktuellen Zustand dieses `ICorDebugThread`beschreiben.|  
|[SetDebugState-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|Legt eine bitweise Kombination von `CorDebugThreadState`-Werten fest, die den Debugzustand dieses `ICorDebugThread`beschreiben.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
