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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0fc0dd03abc1adb8eeea76a1053fb4d58de4ecf8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419831"
---
# <a name="icordebugvaluegettype-method"></a>ICorDebugValue::GetType-Methode
Ruft den primitiven Typ dieses Objekts "ICorDebugValue" ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pType`  
 [out] Ein Zeiger auf einen Wert von "CorElementType"-Enumeration, die den Werttyp angibt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn das Objekt einen komplexen Typ für die Laufzeit ist, kann dieses Typs untersucht werden, über die entsprechenden Unterklasse von der `ICorDebugValue` Schnittstelle. Z. B. "ICorDebugObjectValue", die erbt `ICorDebugValue`, stellt einen komplexen Typ dar.  
  
 Die `GetType` und [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) Methoden geben jeweils Informationen über den Typ eines Werts zurück. Sie werden sowohl von der Generika-bewusste abgelöst [ICorDebugValue2:: GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 
