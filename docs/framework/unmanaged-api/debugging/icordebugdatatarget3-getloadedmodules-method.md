---
title: ICorDebugDataTarget3::GetLoadedModules-Methode
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
ms.openlocfilehash: 6ee2215e2b3e3bd911158b3fc801361fc4e22db1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136690"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a>ICorDebugDataTarget3::GetLoadedModules-Methode
Ruft eine Liste der Module ab, die bisher geladen wurden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cRequestedModules`  
 [in] Die Anzahl der Module, für die Informationen angefordert werden.  
  
 `pcFetchedModules`  
 [out] Ein Zeiger auf die Anzahl der Module, zu denen Informationen zurückgegeben wurden.  
  
 `pLoadedModules`  
 vorgenommen Ein Zeiger auf ein Array von [icordebugloadedmodule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) -Objekten, die Informationen über geladene Module bereitstellen.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugDataTarget3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
