---
title: ICorDebugValue2::GetExactType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: 441d225dadbbca09ab27c8ccd70debe32f4c12da
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140255"
---
# <a name="icordebugvalue2getexacttype-method"></a>ICorDebugValue2::GetExactType-Methode
Ruft einen Schnittstellen Zeiger auf ein ICorDebugType-Objekt ab, das die <xref:System.Type> dieses Werts darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppType`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugType` Objekts, das die <xref:System.Type> des Werts darstellt, der durch dieses "ICorDebugValue2"-Objekt dargestellt wird.  
  
## <a name="remarks"></a>Hinweise  
 Die Generika unterstützende `GetExactType` Methode ersetzt sowohl die [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) -Methode als auch die [ICorDebugValue:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) -Methode, die jeweils Informationen über den Typ eines Werts zurückgeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
