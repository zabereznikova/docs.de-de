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
ms.openlocfilehash: c9e2dc95bf78d95e5d608a8ce6e9462345c20a07
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788734"
---
# <a name="icordebugeval-interface"></a>ICorDebugEval-Schnittstelle

Stellt Methoden bereit, mit denen der Debugger Code innerhalb des Kontexts des gedebuggten Codes ausführen kann.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[Abort-Methode](icordebugeval-abort-method.md)|Bricht die Berechnung ab, die von diesem `ICorDebugEval` Objekt gerade durchgeführt wird.|  
|[CallFunction-Methode](icordebugeval-callfunction-method.md)|Richtet einen Rückruf für die angegebene Funktion ein. (Veraltet in der .NET Framework Version 2,0; verwenden Sie stattdessen [ICorDebugEval2:: CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) .)|  
|[CreateValue-Methode](icordebugeval-createvalue-method.md)|Ruft einen Schnittstellen Zeiger auf ein ICorDebugValue-Objekt des angegebenen Typs mit einem Anfangswert von 0 (null) oder NULL ab. (Veraltet im .NET Framework 2,0; verwenden Sie stattdessen [ICorDebugEval2:: foratevaluefortype](icordebugeval2-createvaluefortype-method.md) .)|  
|[GetResult-Methode](icordebugeval-getresult-method.md)|Ruft einen Schnittstellen Zeiger auf einen `ICorDebugValue` ab, der die Ergebnisse der Auswertung enthält.|  
|[GetThread-Methode](icordebugeval-getthread-method.md)|Ruft einen Schnittstellen Zeiger auf den "ICorDebugThread" ab, in dem diese Auswertung ausgeführt wird oder ausgeführt wird.|  
|[IsActive-Methode](icordebugeval-isactive-method.md)|Ruft einen Wert ab, der angibt, ob dieses `ICorDebugEval` Objekt gerade ausgeführt wird.|  
|[NewArray-Methode](icordebugeval-newarray-method.md)|Ordnet ein neues Array vom angegebenen Elementtyp und den angegebenen Dimensionen zu. (Veraltet im .NET Framework 2,0; verwenden Sie stattdessen [ICorDebugEval2:: NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) .)|  
|[NewObject-Methode](icordebugeval-newobject-method.md)|Ordnet eine neue Objektinstanz zu und ruft die angegebene Konstruktormethode auf. (Veraltet im .NET Framework 2,0; verwenden Sie stattdessen [ICorDebugEval2:: NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) .)|  
|[NewObjectNoConstructor-Methode](icordebugeval-newobjectnoconstructor-method.md)|Ordnet eine neue Objektinstanz des angegebenen Typs zu, ohne zu versuchen, eine Konstruktormethode aufzurufen. (Veraltet im .NET Framework 2,0; verwenden Sie stattdessen [ICorDebugEval2:: NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) .)|  
|[NewString-Methode](icordebugeval-newstring-method.md)|Ordnet ein neues String-Objekt mit dem angegebenen Inhalt zu.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICorDebugEval`-Objekt wird im Kontext eines bestimmten Threads erstellt, der zum Ausführen der Auswertungen verwendet wird. Alle Objekte und Typen, die in einer bestimmten Auswertung verwendet werden, müssen sich in derselben Anwendungsdomäne befinden. Diese Anwendungsdomäne muss nicht mit der aktuellen Anwendungsdomäne des Threads identisch sein. Auswertungen können eingebettet werden.  
  
 Die Vorgänge der Auswertung werden erst ausgeführt, wenn der Debugger [ICorDebugController:: Continue](icordebugcontroller-continue-method.md)aufruft und dann einen [ICorDebugManagedCallback:: EvalComplete](icordebugmanagedcallback-evalcomplete-method.md) -Rückruf empfängt. Wenn Sie die Evaluierungs Funktion verwenden müssen, ohne dass andere Threads ausgeführt werden dürfen, anhalten Sie die Threads mithilfe von [ICorDebugController:: SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) oder [ICorDebugController:: beenden](icordebugcontroller-stop-method.md) , bevor Sie [ICorDebugController:: Continue](icordebugcontroller-continue-method.md)aufrufen.  
  
 Da Benutzercode ausgeführt wird, während die Auswertung ausgeführt wird, können alle Debugereignisse auftreten, einschließlich Klassen Ladevorgängen und Breakpoints. Der Debugger empfängt die Rückrufe für diese Ereignisse wie üblich. Der Status der Auswertung wird im Rahmen der Überprüfung des normalen Programmstatus angezeigt. Die Stapel Kette ist eine `CHAIN_FUNC_EVAL` Kette (siehe die "CorDebugStepReason"-Enumeration und die [ICorDebugChain:: geverrat](icordebugchain-getreason-method.md) -Methode). Die vollständige Debugger-API wird weiterhin wie gewohnt ausgeführt.  
  
 Wenn eine Deadlocksituation oder unendliche Schleifen Situation auftritt, wird der Benutzercode möglicherweise nie beendet. In einem solchen Fall müssen Sie [ICorDebugEval:: Abort](icordebugeval-abort-method.md) aufrufen, bevor Sie das Programm fortsetzen.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
