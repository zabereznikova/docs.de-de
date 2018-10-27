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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e404228cbc6efb81ed90c135358b1832ddcd8954
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185364"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a>ICorDebugModule3::CreateReaderForInMemorySymbols-Methode
Erstellt einen Debug-Symbolreader für ein dynamisches Modul.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
#### <a name="parameters"></a>Parameter  
 riid  
 [in] Die IID der COM-Schnittstelle zurückgegeben werden soll. Dies ist normalerweise ein [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).  
  
 ppObj  
 [out] Zeiger auf einen Zeiger auf die zurückgegebene Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Wurde erfolgreich erstellt. den Reader.  
  
 CORDBG_E_MODULE_LOADED_FROM_DISK  
 Das Modul ist es sich nicht um ein im Arbeitsspeicher oder dynamischen Modul.  
  
 CORDBG_E_SYMBOLS_NOT_AVAILABLE  
 Symbole nicht von der Anwendung bereitgestellt haben, oder es sind noch nicht verfügbar.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Erstellen des Readers nicht möglich.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode kann auch sein verwendet, um ein Symbol Reader-Objekt zu (nicht dynamisch) im Arbeitsspeicher-Modulen zu erstellen, aber nur, wenn die Symbole zuerst zur Verfügung stehen (angegeben durch die [UpdateModuleSymbols-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) Rückruf).  
  
 Diese Methode gibt eine neue Readerinstanz zurück, jedes Mal, wenn sie aufgerufen wird (z. B. [CComPtrBase:: CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)). Aus diesem Grund sollte der Debugger Zwischenspeicherung des Ergebnisses und fordern Sie eine neue Instanz nur, wenn die zugrunde liegenden Daten geändert haben können (d. h. bei einer [LoadClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) -Rückruf empfangen wird).  
  
 Dynamische Module müssen keine verfügbaren Symbole aus, bis der erste Typ geladen wurde (wie durch die [LoadClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) Rückruf).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugRemoteTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
