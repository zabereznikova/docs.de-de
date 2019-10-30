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
ms.openlocfilehash: 33b1afca0b7b662cb7f922e20ba0d6d614c319f2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085034"
---
# <a name="icordebugeval-interface"></a>ICorDebugEval-Schnittstelle

Stellt Methoden bereit, mit denen der Debugger Code innerhalb des Kontexts des gedebuggten Codes ausführen kann.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Abort-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md)|Bricht die Berechnung ab, die von diesem `ICorDebugEval` Objekt gerade durchgeführt wird.|  
|[CallFunction-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)|Richtet einen Rückruf für die angegebene Funktion ein. (Veraltet in der .NET Framework Version 2,0; verwenden Sie stattdessen [ICorDebugEval2:: CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) .)|  
|[CreateValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)|Ruft einen Schnittstellen Zeiger auf ein ICorDebugValue-Objekt des angegebenen Typs mit einem Anfangswert von 0 (null) oder NULL ab. (Veraltet im .NET Framework 2,0; verwenden Sie stattdessen [ICorDebugEval2:: foratevaluefortype](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) .)|  
|[GetResult-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getresult-method.md)|Ruft einen Schnittstellen Zeiger auf einen `ICorDebugValue` ab, der die Ergebnisse der Auswertung enthält.|  
|[GetThread-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getthread-method.md)|Ruft einen Schnittstellen Zeiger auf den "ICorDebugThread" ab, in dem diese Auswertung ausgeführt wird oder ausgeführt wird.|  
|[IsActive-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-isactive-method.md)|Ruft einen Wert ab, der angibt, ob dieses `ICorDebugEval` Objekt gerade ausgeführt wird.|  
|[NewArray-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newarray-method.md)|Ordnet ein neues Array vom angegebenen Elementtyp und den angegebenen Dimensionen zu. (Veraltet im .NET Framework 2,0; verwenden Sie stattdessen [ICorDebugEval2:: NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) .)|  
|[NewObject-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobject-method.md)|Ordnet eine neue Objektinstanz zu und ruft die angegebene Konstruktormethode auf. (Veraltet im .NET Framework 2,0; verwenden Sie stattdessen [ICorDebugEval2:: NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) .)|  
|[NewObjectNoConstructor-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobjectnoconstructor-method.md)|Ordnet eine neue Objektinstanz des angegebenen Typs zu, ohne zu versuchen, eine Konstruktormethode aufzurufen. (Veraltet im .NET Framework 2,0; verwenden Sie stattdessen [ICorDebugEval2:: NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) .)|  
|[NewString-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newstring-method.md)|Ordnet ein neues String-Objekt mit dem angegebenen Inhalt zu.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICorDebugEval`-Objekt wird im Kontext eines bestimmten Threads erstellt, der zum Ausführen der Auswertungen verwendet wird. Alle Objekte und Typen, die in einer bestimmten Auswertung verwendet werden, müssen sich in derselben Anwendungsdomäne befinden. Diese Anwendungsdomäne muss nicht mit der aktuellen Anwendungsdomäne des Threads identisch sein. Auswertungen können eingebettet werden.  
  
 Die Vorgänge der Auswertung werden erst ausgeführt, wenn der Debugger [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)aufruft und dann einen [ICorDebugManagedCallback:: EvalComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md) -Rückruf empfängt. Wenn Sie die Evaluierungs Funktionalität verwenden müssen, ohne dass andere Threads ausgeführt werden dürfen, halten Sie die Threads mithilfe von [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) oder [ICorDebugController:: beenden](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md) vor dem Aufrufen [von an. Icorentbugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).  
  
 Da Benutzercode ausgeführt wird, während die Auswertung ausgeführt wird, können alle Debugereignisse auftreten, einschließlich Klassen Ladevorgängen und Breakpoints. Der Debugger empfängt die Rückrufe für diese Ereignisse wie üblich. Der Status der Auswertung wird im Rahmen der Überprüfung des normalen Programmstatus angezeigt. Die Stapel Kette ist eine `CHAIN_FUNC_EVAL` Kette (siehe die "CorDebugStepReason"-Enumeration und die [ICorDebugChain:: geverrat](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) -Methode). Die vollständige Debugger-API wird weiterhin wie gewohnt ausgeführt.  
  
 Wenn eine Deadlocksituation oder unendliche Schleifen Situation auftritt, wird der Benutzercode möglicherweise nie beendet. In einem solchen Fall müssen Sie [ICorDebugEval:: Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md) aufrufen, bevor Sie das Programm fortsetzen.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
