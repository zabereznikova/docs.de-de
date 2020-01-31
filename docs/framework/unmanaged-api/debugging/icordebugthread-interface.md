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
ms.openlocfilehash: b227b374021136e78f7f061d235eb18eca5b9515
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791472"
---
# <a name="icordebugthread-interface"></a>ICorDebugThread-Schnittstelle
Stellt einen Thread in einem Prozess dar. Die Lebensdauer einer `ICorDebugThread`-Instanz ist identisch mit der Lebensdauer des von ihr dargestellten Threads.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[ClearCurrentException-Methode](icordebugthread-clearcurrentexception-method.md)|Diese Methode ist nicht implementiert. Verwenden Sie sie nicht.|  
|[CreateEval-Methode](icordebugthread-createeval-method.md)|Erstellt ein ICorDebugEval-Objekt, das mit diesem `ICorDebugThread`arbeitet.|  
|[CreateStepper-Methode](icordebugthread-createstepper-method.md)|Erstellt ein ICorDebug-Stepper-Objekt, das das schrittweise durchlaufen des aktiven Frames in diesem `ICorDebugThread`ermöglicht.|  
|[EnumerateChains-Methode](icordebugthread-enumeratechains-method.md)|Ruft einen Schnittstellen Zeiger auf einen ICorDebug-chainenum-Enumerator ab, der alle Stapel Ketten in diesem `ICorDebugThread`enthält.|  
|[GetActiveChain-Methode](icordebugthread-getactivechain-method.md)|Ruft einen Schnittstellen Zeiger auf die aktive ICorDebug-Kette in diesem `ICorDebugThread`ab.|  
|[GetActiveFrame-Methode](icordebugthread-getactiveframe-method.md)|Ruft einen Schnittstellen Zeiger auf den aktiven ICorDebug-Frame auf diesem `ICorDebugThread`ab.|  
|[GetAppDomain-Methode](icordebugthread-getappdomain-method.md)|Ruft einen Schnittstellen Zeiger auf die Anwendungsdomäne ab, in der dieser `ICorDebugThread` derzeit ausgeführt wird.|  
|[GetCurrentException-Methode](icordebugthread-getcurrentexception-method.md)|Ruft einen Schnittstellen Zeiger auf ein ICorDebugValue-Objekt ab, das eine Ausnahme darstellt, die zurzeit von verwaltetem Code ausgelöst wird.|  
|[GetDebugState-Methode](icordebugthread-getdebugstate-method.md)|Ruft einen CorDebugThreadState-Wert ab, der den aktuellen Debugzustand dieses `ICorDebugThread`beschreibt.|  
|[GetHandle-Methode](icordebugthread-gethandle-method.md)|Ruft das aktuelle Handle für den aktiven Teil dieses `ICorDebugThread`ab.|  
|[GetID-Methode](icordebugthread-getid-method.md)|Ruft den aktuellen Betriebssystem Bezeichner des aktiven Teils dieses `ICorDebugThread`ab.|  
|[GetObject-Methode](icordebugthread-getobject-method.md)|Ruft einen Schnittstellen Zeiger auf den Common Language Runtime (CLR)-Thread ab.|  
|[GetProcess-Methode](icordebugthread-getprocess-method.md)|Ruft einen Schnittstellen Zeiger auf den Prozess ab, dessen-`ICorDebugThread` ein Teil bildet.|  
|[GetRegisterSet-Methode](icordebugthread-getregisterset-method.md)|Ruft einen Schnittstellen Zeiger auf den diesem `ICorDebugThread`zugeordneten Register Satz ab.|  
|[GetUserState-Methode](icordebugthread-getuserstate-method.md)|Ruft eine bitweise Kombination von CorDebugUserState-Werten ab, die den aktuellen Zustand dieses `ICorDebugThread`beschreiben.|  
|[SetDebugState-Methode](icordebugthread-setdebugstate-method.md)|Legt eine bitweise Kombination von `CorDebugThreadState`-Werten fest, die den Debugzustand dieses `ICorDebugThread`beschreiben.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
