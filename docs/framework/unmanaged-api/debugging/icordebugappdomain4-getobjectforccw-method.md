---
title: ICorDebugAppDomain4::GetObjectForCCW-Methode
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: a175a6b6c91c284348580e1d9dc9ef0c5f5fc5df
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895118"
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
 vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalue-Objekts, das das verwaltete Objekt darstellt, das dem angegebenen CCW-Zeiger entspricht.  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugAppDomain4-Schnittstelle](icordebugappdomain4-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
