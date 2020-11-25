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
ms.openlocfilehash: d1d057d38e16503175138c6ec978eb6c1f12bc6d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722335"
---
# <a name="icordebugvalue3getsize64-method"></a>ICorDebugValue3::GetSize64-Methode

Ruft die Größe des [ICorDebugValue3](icordebugvalue3-interface.md) -Objekts in Bytes ab.  
  
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
  
 Die- `ICorDebugValue3::GetSize` Methode unterscheidet sich von der [ICorDebugValue:: GetSize](icordebugvalue-getsize-method.md) -Methode im Typ des Ausgabe Parameters. In [ICorDebugValue:: GetSize](icordebugvalue-getsize-method.md)ist der Ausgabeparameter ein `ULONG32` `ICorDebugValue3::GetSize` . in ist es ein `ULONG64` . Dadurch kann die [ICorDebugValue3](icordebugvalue3-interface.md) -Schnittstelle die Größe von Arrays melden, die größer als 2 GB sind.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugValue3-Schnittstelle](icordebugvalue3-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
