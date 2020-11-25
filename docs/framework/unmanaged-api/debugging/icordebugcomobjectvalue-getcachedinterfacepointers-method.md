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
ms.openlocfilehash: c3120a0dd859f581e6356fc260043cb83250ae9e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724831"
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
 in Ein Wert, der angibt, ob die Methode nur Windows-Runtime Schnittstellen ( `IInspectable` Schnittstellen) oder alle COM-Schnittstellen zurückgibt, die vom Runtime Callable Wrapper (RCW) zwischengespeichert werden.  
  
 `celt`  
 in Die Anzahl der Objekte, deren Adressen abgerufen werden sollen.  
  
 `pceltFetched`  
 vorgenommen Ein Zeiger auf die Anzahl der `CORDB_ADDRESS` Werte, die tatsächlich in zurückgegeben werden `ptrs` .  
  
 `ptrs`  
 Ein Zeiger auf die Startadresse eines Arrays von- `CORDB_ADDRESS` Werten, die die Adressen von zwischengespeicherten Schnittstellen Objekten enthalten.  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugComObjectValue-Schnittstelle](icordebugcomobjectvalue-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
