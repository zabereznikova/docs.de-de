---
title: ICorDebugManagedCallback::UpdateModuleSymbols-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UpdateModuleSymbols
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type:
- apiref
ms.openlocfilehash: 1f5b413ffbbc8fccbea38f23d8c87d40e010dd37
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130614"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a>ICorDebugManagedCallback::UpdateModuleSymbols-Methode
Benachrichtigt den Debugger, dass die Symbole für ein Common Language Runtime Modul geändert wurden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pAppDomain`  
 in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem Modul darstellt, in dem sich die Symbole geändert haben.  
  
 `pModule`  
 in Ein Zeiger auf ein ICorDebugModule-Objekt, das das Modul darstellt, in dem die Symbole geändert wurden.  
  
 `pSymbolStream`  
 in Ein Zeiger auf ein Win32-com-`IStream` Objekt, das die geänderten Symbole enthält.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode bietet die Möglichkeit, die Debugger-Ansicht der Symbole eines Moduls zu aktualisieren, indem [ISymUnmanagedReader:: UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) oder [ISymUnmanagedReader:: ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)aufgerufen wird.  
  
 Dieser Rückruf kann mehrmals für dasselbe Modul auftreten.  
  
 Ein Debugger sollte versuchen, nicht gebundene Breakpoints auf Quell Ebene zu binden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
