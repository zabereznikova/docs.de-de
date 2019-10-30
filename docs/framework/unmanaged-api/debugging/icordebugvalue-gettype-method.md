---
title: ICorDebugValue::GetType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
ms.openlocfilehash: 284a74823b01305f8c6e025f70bb9209c8607b7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137076"
---
# <a name="icordebugvaluegettype-method"></a>ICorDebugValue::GetType-Methode
Ruft den primitiven Typ dieses ICorDebugValue-Objekts ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pType`  
 vorgenommen Ein Zeiger auf einen Wert der "CorElementType"-Enumeration, der den Typ des Werts angibt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn das Objekt ein komplexer Lauf Zeittyp ist, kann dieser Typ durch die entsprechenden Unterklassen der `ICorDebugValue`-Schnittstelle überprüft werden. Beispielsweise stellt "ICorDebugObjectValue", der von `ICorDebugValue`erbt, einen komplexen Typ dar.  
  
 Die Methoden `GetType` und [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) geben Informationen über den Typ eines Werts zurück. Beide werden durch die Generics-Aware [ICorDebugValue2:: GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) -Methode abgelöst.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
