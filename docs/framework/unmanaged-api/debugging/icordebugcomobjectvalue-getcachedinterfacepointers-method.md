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
ms.openlocfilehash: c1e2b557a5e5794c50986b1af8ec39faba845cc9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125518"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a>ICorDebugComObjectValue::GetCachedInterfacePointers-Methode
Ruft die unformatierten Schnittstellen Zeiger ab, die auf dem aktuellen Runtime Callable Wrapper (RCW) zwischengespeichert werden.  
  
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
 in Ein Wert, der angibt, ob die Methode nur Windows-Runtime Schnittstellen (`IInspectable` Schnittstellen) oder alle COM-Schnittstellen zurückgibt, die vom Runtime Callable Wrapper (RCW) zwischengespeichert werden.  
  
 `celt`  
 in Die Anzahl der Objekte, deren Adressen abgerufen werden sollen.  
  
 `pceltFetched`  
 vorgenommen Ein Zeiger auf die Anzahl der `CORDB_ADDRESS` Werte, die tatsächlich in `ptrs`zurückgegeben werden.  
  
 `ptrs`  
 Ein Zeiger auf die Startadresse eines Arrays von `CORDB_ADDRESS`-Werten, die die Adressen von zwischengespeicherten Schnittstellen Objekten enthalten.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugComObjectValue-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
