---
title: ICorDebugComObjectValue::GetCachedInterfacePointers-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfacePointers
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdbec0101de269b3d5b09e750d552c993a0198ab
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748480"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a>ICorDebugComObjectValue::GetCachedInterfacePointers-Methode
Ruft den unformatierten Schnittstellenzeiger auf den aktuellen Runtime callable Wrapper (RCW) zwischengespeichert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a>Parameter  
 `bIInspectableOnly`  
 [in] Ein Wert, der angibt, ob die Methode nur Windows-Runtime-Schnittstellen zurückgibt (`IInspectable` Schnittstellen) oder alle COM-Schnittstellen, die von den Runtime callable Wrapper (RCW) zwischengespeichert werden.  
  
 `celt`  
 [in] Die Anzahl der Objekte, deren Adressen sind, abgerufen werden sollen.  
  
 `pceltFetched`  
 [out] Ein Zeiger auf die Anzahl der `CORDB_ADDRESS` Rückgabewerte, die tatsächlich `ptrs`.  
  
 `ptrs`  
 Ein Zeiger auf die Startadresse eines Arrays von `CORDB_ADDRESS` zwischengespeicherte Werte, die die Adressen der Objekte der Benutzeroberfläche.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugComObjectValue-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
