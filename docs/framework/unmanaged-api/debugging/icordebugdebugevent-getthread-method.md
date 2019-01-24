---
title: ICorDebugDebugEvent::GetThread-Methode
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51d674159b33cad1a77a82e39b9f11a38c98cbd3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687400"
---
# <a name="icordebugdebugeventgetthread-method"></a>ICorDebugDebugEvent::GetThread-Methode
Ruft den Thread auf, auf dem das Ereignis aufgetreten ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 ppThread  
 [out] Ein Zeiger auf die Adresse des ein ICorDebugThread-Objekt, das den Thread darstellt, auf dem das Ereignis aufgetreten ist.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebugDebugEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
