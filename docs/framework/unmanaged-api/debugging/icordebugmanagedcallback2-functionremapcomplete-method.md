---
title: ICorDebugManagedCallback2::FunctionRemapComplete-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type:
- apiref
ms.openlocfilehash: 6e048d03e54d4f97cd45935906ea4e4744468db9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131526"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a>ICorDebugManagedCallback2::FunctionRemapComplete-Methode
Benachrichtigt den Debugger, dass die Codeausführung zu einer neuen Version einer bearbeiteten Funktion gewechselt hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pAppDomain`  
 in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die die bearbeitete Funktion enthält.  
  
 `pThread`  
 in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, in dem der Umwandlungs-Breakpoint gefunden wurde.  
  
 `pFunction`  
 in Ein Zeiger auf ein ICorDebugFunction-Objekt, das die Version der Funktion darstellt, die derzeit auf dem Thread ausgeführt wird.  
  
## <a name="remarks"></a>Hinweise  
 Mit diesem Rückruf hat der Debugger die Möglichkeit, alle zuvor vorhandenen Steppers neu zu erstellen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
