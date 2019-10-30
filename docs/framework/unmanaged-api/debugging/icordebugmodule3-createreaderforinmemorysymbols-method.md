---
title: ICorDebugModule3::CreateReaderForInMemorySymbols-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule3.CreateReaderForInMemorySymbols
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type:
- apiref
ms.openlocfilehash: 2655151d34275b1b0fdc5d0903dd57fcea646014
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137303"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a>ICorDebugModule3::CreateReaderForInMemorySymbols-Methode
Erstellt einen debugsymbolreader für ein dynamisches Modul.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a>Parameter  
 riid  
 in Die IID der zurück zugebende com-Schnittstelle. In der Regel ist dies eine [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).  
  
 ppobj  
 vorgenommen Zeiger auf einen Zeiger auf die zurückgegebene Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Der Reader wurde erfolgreich erstellt.  
  
 CORDBG_E_MODULE_LOADED_FROM_DISK  
 Das Modul ist kein in-Memory-oder dynamisches Modul.  
  
 CORDBG_E_SYMBOLS_NOT_AVAILABLE  
 Es wurden keine Symbole von der Anwendung bereitgestellt oder sind noch nicht verfügbar.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Der Reader kann nicht erstellt werden.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode kann auch verwendet werden, um ein Symbol Reader-Objekt für in-Memory-Module (nicht dynamisch) zu erstellen, aber erst nach der ersten Verfügbarkeit der Symbole (angegeben durch den [UpdateModuleSymbols-Methoden](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) Rückruf).  
  
 Diese Methode gibt jedes Mal, wenn Sie aufgerufen wird, eine neue Reader-Instanz zurück (z. b. [CComPtrBase:: cokreateinstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)). Daher sollte der Debugger das Ergebnis Zwischenspeichern und eine neue Instanz nur dann anfordern, wenn sich die zugrunde liegenden Daten möglicherweise geändert haben (d. h., wenn ein [LoadClass-Methoden](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) Rückruf empfangen wird).  
  
 Für dynamische Module sind keine Symbole verfügbar, bis der erste Typ geladen wurde (wie durch den [LoadClass-Methoden](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) Rückruf angegeben).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 4,5, 4, 3,5 SP1  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRemoteTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
