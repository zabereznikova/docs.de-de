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
ms.openlocfilehash: a3cd62384ad87d072cd715d23d0e9ee9dac23270
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396738"
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
  
## <a name="remarks"></a>Bemerkungen  
 Wenn das-Objekt ein komplexer Lauf Zeittyp ist, kann dieser Typ durch die entsprechenden Unterklassen der- `ICorDebugValue` Schnittstelle überprüft werden. Beispielsweise stellt "ICorDebugObjectValue", der von erbt `ICorDebugValue` , einen komplexen Typ dar.  
  
 `GetType`Mit der-Methode und der [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) -Methode werden jeweils Informationen über den Typ eines Werts zurückgegeben. Beide werden durch die Generics-Aware [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md) -Methode abgelöst.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
