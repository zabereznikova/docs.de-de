---
title: ICorDebugAppDomain4::GetObjectForCCW-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d459c9ea807114c4f63995ba8fbbb288ea5463b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain4getobjectforccw-method"></a>ICorDebugAppDomain4::GetObjectForCCW-Methode
Ruft ein verwaltetes Objekt über einen Zeiger des COM Callable Wrapper (CCW) ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ccwPointer`  
 [in] Zeiger des COM Callable Wrapper (CCW).  
  
 `ppManagedObject`  
 [out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugValue", die das verwaltete Objekt, das entspricht dem angegebenen CCW-Zeiger darstellt.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugAppDomain4-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
