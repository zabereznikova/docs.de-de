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
ms.openlocfilehash: 5165ef081aad849c11747807d8cc76b2df0a6c74
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729316"
---
# <a name="icordebugthread-interface"></a>ICorDebugThread-Schnittstelle

Stellt einen Thread in einem Prozess dar. Die Lebensdauer einer `ICorDebugThread`-Instanz ist identisch mit der Lebensdauer des von ihr dargestellten Threads.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[ClearCurrentException-Methode](icordebugthread-clearcurrentexception-method.md)|Diese Methode ist nicht implementiert. Verwenden Sie sie nicht.|  
|[CreateEval-Methode](icordebugthread-createeval-method.md)|Erstellt ein ICorDebugEval-Objekt, das auf diesem ausgeführt wird `ICorDebugThread` .|  
|[CreateStepper-Methode](icordebugthread-createstepper-method.md)|Erstellt ein ICorDebug-Stepper-Objekt, das das schrittweise durchlaufen des aktiven Frames in diesem ermöglicht `ICorDebugThread` .|  
|[EnumerateChains-Methode](icordebugthread-enumeratechains-method.md)|Ruft einen Schnittstellen Zeiger auf einen ICorDebug-chainenum-Enumerator ab, der alle Stapel Ketten in diesem enthält `ICorDebugThread` .|  
|[GetActiveChain-Methode](icordebugthread-getactivechain-method.md)|Ruft einen Schnittstellen Zeiger auf die aktive ICorDebug-Kette für dieses ab `ICorDebugThread` .|  
|[GetActiveFrame-Methode](icordebugthread-getactiveframe-method.md)|Ruft einen Schnittstellen Zeiger auf den aktiven ICorDebug-Frame für dieses ab `ICorDebugThread` .|  
|[GetAppDomain-Methode](icordebugthread-getappdomain-method.md)|Ruft einen Schnittstellen Zeiger auf die Anwendungsdomäne ab, in der diese `ICorDebugThread` gerade ausgeführt wird.|  
|[GetCurrentException-Methode](icordebugthread-getcurrentexception-method.md)|Ruft einen Schnittstellen Zeiger auf ein ICorDebugValue-Objekt ab, das eine Ausnahme darstellt, die zurzeit von verwaltetem Code ausgelöst wird.|  
|[GetDebugState-Methode](icordebugthread-getdebugstate-method.md)|Ruft einen CorDebugThreadState-Wert ab, der den aktuellen Debugzustand dieses beschreibt `ICorDebugThread` .|  
|[GetHandle-Methode](icordebugthread-gethandle-method.md)|Ruft das aktuelle Handle für den aktiven Teil dieses ab `ICorDebugThread` .|  
|[GetID-Methode](icordebugthread-getid-method.md)|Ruft den aktuellen Betriebssystem Bezeichner des aktiven Teils dieses ab `ICorDebugThread` .|  
|[GetObject-Methode](icordebugthread-getobject-method.md)|Ruft einen Schnittstellen Zeiger auf den Common Language Runtime (CLR)-Thread ab.|  
|[GetProcess-Methode](icordebugthread-getprocess-method.md)|Ruft einen Schnittstellen Zeiger auf den Prozess ab, zu dem dieses-Element `ICorDebugThread` gehört.|  
|[GetRegisterSet-Methode](icordebugthread-getregisterset-method.md)|Ruft einen Schnittstellen Zeiger auf den Register Satz ab, der diesem zugeordnet ist `ICorDebugThread` .|  
|[GetUserState-Methode](icordebugthread-getuserstate-method.md)|Ruft eine bitweise Kombination von CorDebugUserState-Werten ab, die den aktuellen Zustand dieses beschreiben `ICorDebugThread` .|  
|[SetDebugState-Methode](icordebugthread-setdebugstate-method.md)|Legt eine bitweise Kombination von- `CorDebugThreadState` Werten fest, die den Debugzustand dieses beschreiben `ICorDebugThread` .|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
