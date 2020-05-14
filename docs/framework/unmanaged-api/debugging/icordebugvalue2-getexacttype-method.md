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
ms.openlocfilehash: dcec97bac2aefc8db1f9351f1dacb0f36fc0d2a0
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396800"
---
# <a name="icordebugvalue2getexacttype-method"></a>ICorDebugValue2::GetExactType-Methode
Ruft einen Schnittstellen Zeiger auf ein ICorDebugType-Objekt ab, das den <xref:System.Type> dieses Werts darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppType`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugType` Objekts, das die des Werts darstellt, der <xref:System.Type> durch dieses "ICorDebugValue2"-Objekt dargestellt wird.  
  
## <a name="remarks"></a>Bemerkungen  
 Die Generika-kompatible `GetExactType` Methode ersetzt sowohl die [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) -Methode als auch die [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) -Methode, die jeweils Informationen über den Typ eines Werts zurückgeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
