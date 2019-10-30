---
title: ICorDebugValue3::GetSize64-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
ms.openlocfilehash: 72a1b6fdc40f3169500d8cf3b3028315106ecc69
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140230"
---
# <a name="icordebugvalue3getsize64-method"></a>ICorDebugValue3::GetSize64-Methode
Ruft die Größe des [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) -Objekts in Bytes ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a>Parameter  
 Psize  
 vorgenommen Ein Zeiger auf die Größe dieses-Objekts in Bytes.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Typ dieses Werts ein Referenztyp ist, gibt diese Methode die Größe des Zeigers anstelle der Größe des-Objekts zurück.  
  
 Die `ICorDebugValue3::GetSize`-Methode unterscheidet sich von der [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) -Methode im Typ des Ausgabe Parameters. Der Output-Parameter in [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)ist eine `ULONG32`. in `ICorDebugValue3::GetSize`handelt es sich um eine `ULONG64`. Dadurch kann die [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) -Schnittstelle die Größe von Arrays melden, die größer als 2 GB sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugValue3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
