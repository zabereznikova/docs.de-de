---
title: ICorDebugModule3::CreateReaderForInMemorySymbols-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule3.CreateReaderForInMemorySymbols
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fbab155e783d3b5e40da466fef56633317c67042
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
 [in] Die IID der COM-Schnittstelle zurück. Dies ist normalerweise ein [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).  
  
 ppObj  
 [out] Zeiger auf einen Zeiger auf die zurückgegebene Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Den Reader erstellt.  
  
 CORDBG_E_MODULE_LOADED_FROM_DISK  
 Das Modul ist kein im Arbeitsspeicher oder dynamisches Modul.  
  
 CORDBG_E_SYMBOLS_NOT_AVAILABLE  
 Symbole nicht zur Verfügung gestellt wurden von der Anwendung, oder es sind noch nicht verfügbar.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Erstellen den Reader nicht möglich.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode kann auch sein verwendet zum Erstellen eines Symbols Reader-Objekts für Module im Arbeitsspeicher (nicht dynamisch), jedoch nur, nachdem zuerst die Symbole verfügbar sind (angegeben durch die [UpdateModuleSymbols-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) Rückruf).  
  
 Jedes Mal, wenn sie aufgerufen wird, gibt diese Methode eine neue Readerinstanz (z. B. [CComPtrBase:: CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)). Aus diesem Grund sollte der Debugger cache das Ergebnis und fordern Sie eine neue Instanz nur, wenn die zugrunde liegenden Daten geändert haben, können (d. h. bei einem [LoadClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) Rückruf empfangen wird).  
  
 Dynamische Module müssen keine verfügbaren Symbole, bis der erste Typ geladen wurde (durch die [LoadClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) Rückruf).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugRemoteTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
