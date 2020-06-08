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
ms.openlocfilehash: c0381cf924e44e581c8b275c9750cacba045cf1b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501780"
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
 in Ein Zeiger auf ein Win32-com- `IStream` Objekt, das die geänderten Symbole enthält.  
  
## <a name="remarks"></a>Bemerkungen  
 Diese Methode bietet die Möglichkeit, die Debugger-Ansicht der Symbole eines Moduls zu aktualisieren, indem [ISymUnmanagedReader:: UpdateSymbolStore](../diagnostics/isymunmanagedreader-updatesymbolstore-method.md) oder [ISymUnmanagedReader:: ReplaceSymbolStore](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md)aufgerufen wird.  
  
 Dieser Rückruf kann mehrmals für dasselbe Modul auftreten.  
  
 Ein Debugger sollte versuchen, nicht gebundene Breakpoints auf Quell Ebene zu binden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
