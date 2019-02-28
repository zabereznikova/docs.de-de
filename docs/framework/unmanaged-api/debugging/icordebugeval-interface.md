---
title: ICorDebugEval-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval
helpviewer_keywords:
- ICorDebugEval interface [.NET Framework debugging]
ms.assetid: 3a5c9815-832d-47e1-b7f7-bbba135d7cf1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16beff67b4ef918afeb07ce4734fb8d2945e93c8
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977200"
---
# <a name="icordebugeval-interface"></a>ICorDebugEval-Schnittstelle

Stellt Methoden bereit, mit denen der Debugger Code innerhalb des Kontexts des gedebuggten Codes ausführen kann.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Abort-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md)|Bricht die Berechnung dieses `ICorDebugEval` Objekt gerade ausführt.|  
|[CallFunction-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)|Richtet einen Aufruf der angegebenen Funktion. (In .NET Framework, Version 2.0 veraltet; verwenden Sie [ICorDebugEval2:: CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) stattdessen.)|  
|[CreateValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)|Ruft einen Schnittstellenzeiger auf ein Objekt "ICorDebugValue" des angegebenen Typs mit einem Anfangswert von 0 (null) oder Null ab. (In .NET Framework 2.0 veraltet; verwenden Sie [ICorDebugEval2:: CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) stattdessen.)|  
|[GetResult-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getresult-method.md)|Ruft einen Schnittstellenzeiger auf ein `ICorDebugValue` , die die Ergebnisse der Auswertung enthält.|  
|[GetThread-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getthread-method.md)|Ruft einen Schnittstellenzeiger auf das "ICorDebugThread", in denen diese Auswertung wird ausgeführt, oder ausgeführt wird.|  
|[IsActive-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-isactive-method.md)|Ruft einen Wert, der angibt, ob dies `ICorDebugEval` Objekt wird gerade ausgeführt.|  
|[NewArray-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newarray-method.md)|Ordnet ein neues Array mit den angegebenen Elementtyp und Dimensionen an. (In .NET Framework 2.0 veraltet; verwenden Sie [ICorDebugEval2:: NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) stattdessen.)|  
|[NewObject-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobject-method.md)|Reserviert eine neue Objektinstanz, und der angegebene Konstruktor-Methode aufgerufen. (In .NET Framework 2.0 veraltet; verwenden Sie [ICorDebugEval2:: NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) stattdessen.)|  
|[NewObjectNoConstructor-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobjectnoconstructor-method.md)|Weist eine neue Objektinstanz des angegebenen Typs, ohne zu versuchen, eine Konstruktormethode aufrufen. (In .NET Framework 2.0 veraltet; verwenden Sie [ICorDebugEval2:: NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) stattdessen.)|  
|[NewString-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newstring-method.md)|Ordnet ein neues Zeichenfolgenobjekt mit dem angegebenen Inhalt.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICorDebugEval` Objekt im Kontext eines bestimmten Threads, die zum Ausführen der auswertungen erstellt wird. Alle Objekte und Typen, die in einer bestimmten Auswertung verwendet, müssen innerhalb der gleichen Anwendungsdomäne befinden. Dieser Anwendungsdomäne muss nicht identisch mit der aktuellen Anwendungsdomäne des Threads sein. Evaluierungen können geschachtelt werden.  
  
 Die Vorgänge der Auswertung nicht vollständig bis der Debugger ruft [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md), und klicken Sie dann empfängt eine [ICorDebugManagedCallback:: EvalComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md) Rückruf. Wenn benötigten die Evaluierungsfunktion zu verwenden, ohne die Ausführung anderer Threads zugelassen, Threads anhalten, indem Sie entweder [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) oder [ICorDebugController:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)vor dem Aufruf [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).  
  
 Da Benutzercode ausgeführt wird, wenn die Auswertung ausgeführt wird, können jeder Debug-Ereignisse auftreten, einschließlich Klasse lädt und Haltepunkte. Der Debugger wird wie üblich, für diese Ereignisse Rückrufe ausgegeben. Der Status der Überprüfung werden im Rahmen der Überprüfung des Zustands normales Programm angezeigt. Die Stapelkette werden eine `CHAIN_FUNC_EVAL` Kette (finden Sie unter "CorDebugStepReason"-Enumeration und die [ICorDebugChain:: GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) Methode). Die vollständige Debugger-API wird weiterhin wie gewohnt.  
  
 Wenn ein Deadlock oder eine Endlosschleife eintritt, kann der Code des Benutzer nie abgeschlossen. In diesem Fall müssen Sie aufrufen [ICorDebugEval:: Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md) vor dem Fortsetzen des Programms.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch



- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
