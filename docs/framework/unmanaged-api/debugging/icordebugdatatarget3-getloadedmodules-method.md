---
title: ICorDebugDataTarget3::GetLoadedModules-Methode
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
ms.openlocfilehash: d4c22146422085daa4dc9d90ae5b3735a12500c2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793556"
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
  
## <a name="parameters"></a>Parameters  
 `cRequestedModules`  
 [in] Die Anzahl der Module, für die Informationen angefordert werden.  
  
 `pcFetchedModules`  
 [out] Ein Zeiger auf die Anzahl der Module, zu denen Informationen zurückgegeben wurden.  
  
 `pLoadedModules`  
 vorgenommen Ein Zeiger auf ein Array von [icordebugloadedmodule](icordebugloadedmodule-interface.md) -Objekten, die Informationen über geladene Module bereitstellen.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugDataTarget3-Schnittstelle](icordebugdatatarget3-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
