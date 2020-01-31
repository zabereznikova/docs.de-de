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
ms.openlocfilehash: 7ae06d825565faff70b0c8be2ccbee5228737e41
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791103"
---
# <a name="icordebugvalue3getsize64-method"></a>ICorDebugValue3::GetSize64-Methode
Ruft die Größe des [ICorDebugValue3](icordebugvalue3-interface.md) -Objekts in Bytes ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a>Parameters  
 Psize  
 vorgenommen Ein Zeiger auf die Größe dieses-Objekts in Bytes.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Typ dieses Werts ein Referenztyp ist, gibt diese Methode die Größe des Zeigers anstelle der Größe des-Objekts zurück.  
  
 Die `ICorDebugValue3::GetSize`-Methode unterscheidet sich von der [ICorDebugValue:: GetSize](icordebugvalue-getsize-method.md) -Methode im Typ des Ausgabe Parameters. Der Output-Parameter in [ICorDebugValue:: GetSize](icordebugvalue-getsize-method.md)ist eine `ULONG32`. in `ICorDebugValue3::GetSize`handelt es sich um eine `ULONG64`. Dadurch kann die [ICorDebugValue3](icordebugvalue3-interface.md) -Schnittstelle die Größe von Arrays melden, die größer als 2 GB sind.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugValue3-Schnittstelle](icordebugvalue3-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
