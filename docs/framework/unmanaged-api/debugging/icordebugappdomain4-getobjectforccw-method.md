---
title: ICorDebugAppDomain4::GetObjectForCCW-Methode
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ab4905c55a1395e9ae5cba8343e6b832622005d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737642"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a>ICorDebugAppDomain4::GetObjectForCCW-Methode
Ruft ein verwaltetes Objekt über einen Zeiger des COM Callable Wrapper (CCW) ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ccwPointer`  
 [in] Zeiger des COM Callable Wrapper (CCW).  
  
 `ppManagedObject`  
 [out] Ein Zeiger auf die Adresse eines "ICorDebugValue"-Objekts, das das verwaltete Objekt, das entspricht dem angegebenen CCW-Zeiger darstellt.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugAppDomain4-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
