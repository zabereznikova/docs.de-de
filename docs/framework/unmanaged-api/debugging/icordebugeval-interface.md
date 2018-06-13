---
title: ICorDebugEval Schnittstelle1
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
ms.openlocfilehash: 3ceda938798ba03a9f178776c4cd9439456182c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423035"
---
# <a name="icordebugeval-interface1"></a>ICorDebugEval Schnittstelle1
Stellt Methoden bereit, mit denen der Debugger Code innerhalb des Kontexts des gedebuggten Codes ausführen kann.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Abort-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md)|Bricht der Berechnung dieses `ICorDebugEval` Objekt wird derzeit ausgeführt.|  
|[CallFunction-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)|Richtet einen Aufruf der angegebenen Funktion. (Veraltet in .NET Framework, Version 2.0; verwenden Sie [ICorDebugEval2:: CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) stattdessen.)|  
|[CreateValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)|Ruft einen Schnittstellenzeiger auf ein "ICorDebugValue"-Objekt des angegebenen Typs mit einem Anfangswert von 0 (null) oder Null ab. (In .NET Framework 2.0 veraltet; verwenden Sie [ICorDebugEval2:: CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) stattdessen.)|  
|[GetResult-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getresult-method.md)|Ruft einen Schnittstellenzeiger auf eine `ICorDebugValue` , die die Ergebnisse der Auswertung enthält.|  
|[GetThread-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getthread-method.md)|Ruft einen Schnittstellenzeiger auf die "ICorDebugThread", in dem diese Auswertung ausgeführt wird, oder werden ausgeführt.|  
|[IsActive-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-isactive-method.md)|Ruft einen Wert, der angibt, ob dies `ICorDebugEval` Objekt wird zurzeit ausgeführt.|  
|[NewArray-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newarray-method.md)|Ordnet ein neues Array mit den angegebenen Elementtyp und Dimensionen an. (In .NET Framework 2.0 veraltet; verwenden Sie [ICorDebugEval2:: NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) stattdessen.)|  
|[NewObject-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobject-method.md)|Ordnet eine neue Objektinstanz und ruft die Methode des angegebenen Konstruktors. (In .NET Framework 2.0 veraltet; verwenden Sie [ICorDebugEval2:: NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) stattdessen.)|  
|[NewObjectNoConstructor-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobjectnoconstructor-method.md)|Ordnet eine neue Objektinstanz des angegebenen Typs, ohne zu versuchen, eine Konstruktormethode aufrufen. (In .NET Framework 2.0 veraltet; verwenden Sie [ICorDebugEval2:: NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) stattdessen.)|  
|[NewString-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newstring-method.md)|Ordnet ein neues Zeichenfolgenobjekt mit dem angegebenen Inhalt.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `ICorDebugEval` objekterstellung im Kontext eines bestimmten Threads, die verwendet wird, um die auswertungen auszuführen. Alle Objekte und Typen, die in einer bestimmten Auswertung verwendet, müssen in derselben Anwendungsdomäne befinden. Diese Anwendungsdomäne muss nicht identisch mit der aktuellen Anwendungsdomäne des Threads sein. Evaluierungsversionen können geschachtelt werden.  
  
 Die Auswertung Vorgänge werden abgeschlossen, bis der Debugger ruft [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md), und dann empfängt eine [ICorDebugManagedCallback:: EvalComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md) Rückruf. Wenn Sie die Evaluation-Funktionen zu verwenden, ohne die Ausführung anderer Threads zugelassen möchten, halten Sie die Threads mithilfe entweder [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) oder [ICorDebugController:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)vor dem Aufruf [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).  
  
 Da Benutzercode ausgeführt wird, wenn die Auswertung ausgeführt wird, können alle Debug-Ereignisse auftreten, einschließlich Klasse lädt und Haltepunkte. Der Debugger wird Rückrufe, wie gewohnt für diese Ereignisse zu empfangen. Der Status der Auswertung wird als Teil der Überprüfung der normalen Programmstatus betrachtet werden. Die Stapelkette werden eine `CHAIN_FUNC_EVAL` Kette (finden Sie unter "CorDebugStepReason"-Enumeration und die [ICorDebugChain:: GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) Methode). Die vollständige Debugger-API wird zwar weiterhin wie gewohnt ausgeführt.  
  
 Wenn ein Deadlock oder eine Endlosschleife eintritt, kann der Benutzercode nie abgeschlossen. In diesem Fall rufen Sie [ICorDebugEval:: Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md) vor dem Fortsetzen des Programms.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
    
    
    
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
