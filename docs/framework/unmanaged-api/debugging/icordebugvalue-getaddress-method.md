---
title: ICorDebugValue::GetAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
ms.openlocfilehash: 467ba53f90081f0c3499fb22acab96b5e380a3f4
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395845"
---
# <a name="icordebugvaluegetaddress-method"></a>ICorDebugValue::GetAddress-Methode
Ruft die Adresse dieses ICorDebugValue-Objekts ab, das gerade gedebuggt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pAddress`  
 vorgenommen Zeiger auf ein- `CORDB_ADDRESS` Objekt, das die Adresse dieses Wert Objekts angibt.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn der Wert nicht verfügbar ist, wird 0 (null) zurückgegeben. Dies kann vorkommen, wenn der Wert mindestens teilweise in Registern oder in einem Garbage Collector handle () gespeichert ist `GCHandle` .  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
