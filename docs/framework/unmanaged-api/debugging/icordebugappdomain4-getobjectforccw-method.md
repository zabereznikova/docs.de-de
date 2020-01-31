---
title: ICorDebugAppDomain4::GetObjectForCCW-Methode
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 50f46394c809321f0bd256e4c8d75b76fc7c2c70
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784849"
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
  
## <a name="parameters"></a>Parameters  
 `ccwPointer`  
 [in] Zeiger des COM Callable Wrapper (CCW).  
  
 `ppManagedObject`  
 vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalue-Objekts, das das verwaltete Objekt darstellt, das dem angegebenen CCW-Zeiger entspricht.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugAppDomain4-Schnittstelle](icordebugappdomain4-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
