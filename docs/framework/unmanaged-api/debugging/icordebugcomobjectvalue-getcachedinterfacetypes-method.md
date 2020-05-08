---
title: ICorDebugComObjectValue::GetCachedInterfaceTypes-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type:
- apiref
ms.openlocfilehash: 6b02657012870de4d0f888f6c05b115b25073fa2
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892831"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a>ICorDebugComObjectValue::GetCachedInterfaceTypes-Methode
Stellt einen Enumerator für die Schnittstellentypen bereit, in die das aktuelle-Objekt umgewandelt oder verwendet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a>Parameter  
 `bIInspectableOnly`  
 in Ein Wert, der angibt, ob die Methode nur Windows-Runtime Schnittstellen`IInspectable` (Schnittstellen) oder alle COM-Schnittstellen zurückgibt, die vom Runtime Callable Wrapper (RCW) zwischengespeichert werden.  
  
 `ppInterfacesEnum`  
 vorgenommen Ein Zeiger auf die Adresse eines icordebugtypeenumerators, der Zugriff auf ICorDebugType-Objekte bereitstellt, die zwischengespeicherte Schnittstellentypen darstellen, `bIInspectableOnly`die nach gefiltert sind.  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugComObjectValue-Schnittstelle](icordebugcomobjectvalue-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
