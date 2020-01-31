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
ms.openlocfilehash: bc6543b46200dd611e13bdf55aabfabd8302e70a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793336"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a>ICorDebugManagedCallback2::FunctionRemapOpportunity-Methode
Benachrichtigt den Debugger, dass die Codeausführung einen Sequenz Punkt in einer älteren Version einer bearbeiteten Funktion erreicht hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pAppDomain`  
 in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die die bearbeitete Funktion enthält.  
  
 `pThread`  
 [in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, auf dem die neuzuordnung Breakpoint erreicht wurde.  
  
 `pOldFunction`  
 in Ein Zeiger auf ein ICorDebugFunction-Objekt, das die Version der Funktion darstellt, die derzeit auf dem Thread ausgeführt wird.  
  
 `pNewFunction`  
 in Ein Zeiger auf ein ICorDebugFunction-Objekt, das die neueste Version der Funktion darstellt.  
  
 `oldILOffset`  
 in Der MSIL-Offset (Microsoft Intermediate Language) des Anweisungs Zeigers in der alten Version der Funktion.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Rückruf ermöglicht dem Debugger die erneute Zuordnung des Anweisungs Zeigers zu seiner ordnungsgemäßen Position in der neuen Version der angegebenen Funktion durch Aufrufen der [ICorDebugILFrame2:: RemapFunction](icordebugilframe2-remapfunction-method.md) -Methode. Wenn der Debugger `RemapFunction` vor dem Aufrufen der [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) -Methode nicht aufruft, wird der alte Code von der Laufzeit weiterhin ausgeführt, und es wird ein weiterer `FunctionRemapOpportunity` Rückruf am nächsten Sequenz Punkt ausgelöst.  
  
 Dieser Rückruf wird für jeden Frame aufgerufen, der eine ältere Version der angegebenen Funktion ausführt, bis der Debugger S_OK zurückgibt.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback2-Schnittstelle](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
