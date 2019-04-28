---
title: ICorDebugManagedCallback2::FunctionRemapOpportunity-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14291ced9a606cc0b2a3792c2157b7bc2a3460a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756220"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a>ICorDebugManagedCallback2::FunctionRemapOpportunity-Methode
Benachrichtigt den Debugger, dass die codeausführung einen Sequenzpunkt in einer früheren Version einer bearbeiteten Funktion erreicht hat.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pAppDomain`  
 [in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne, die mit der bearbeiteten Funktion darstellt.  
  
 `pThread`  
 [in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, auf dem die neuzuordnung Breakpoint erreicht wurde.  
  
 `pOldFunction`  
 [in] Ein Zeiger auf ein ICorDebugFunction-Objekt, das die Version der Funktion darstellt, die derzeit auf dem Thread ausgeführt wird.  
  
 `pNewFunction`  
 [in] Ein Zeiger auf ein ICorDebugFunction-Objekt, das die neueste Version der Funktion darstellt.  
  
 `oldILOffset`  
 [in] Der Microsoft intermediate Language (MSIL)-Offset des Anweisungszeigers in der alten Version der Funktion.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Rückruf ermöglicht dem Debugger, neu zuzuordnen, den Anweisungszeiger der richtigen Position in der neuen Version der angegebenen Funktion durch Aufrufen der [ICorDebugILFrame2:: RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) Methode. Wenn der Debugger nicht aufruft `RemapFunction` vor dem Aufruf der [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) -Methode, die Laufzeit wird weiterhin der alte Code ausgeführt und wird ausgelöst, eine andere `FunctionRemapOpportunity` Rückruf am nächsten Sequenz.  
  
 Für jeden Frame, der eine ältere Version der angegebenen Funktion ausgeführt wird, bis der Debugger S_OK zurückgibt, wird dieser Rückruf aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
