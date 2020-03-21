---
title: ICorDebugProcess5::GetTypeFields-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
ms.openlocfilehash: 29006eba3d3a523fd24a461207ab12222a639782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178590"
---
# <a name="icordebugprocess5gettypefields-method"></a>ICorDebugProcess5::GetTypeFields-Methode
Enthält Informationen zu den Feldern, die zu einem Typ gehören.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `id`  
 [in] Der Bezeichner des Typs, dessen Feldinformationen abgerufen werden.  
  
 `celt`  
 [in] Die Anzahl der [COR_FIELD](cor-field-structure.md) Objekte, deren Feldinformationen abgerufen werden sollen.  
  
 `fields`  
 [out] Ein Array [COR_FIELD](cor-field-structure.md) von COR_FIELD-Objekten, die Informationen zu den Feldern bereitstellen, die zum Typ gehören.  
  
 `pceltNeeded`  
 [out] Ein Zeiger auf die [COR_FIELD](cor-field-structure.md) Anzahl der `fields`COR_FIELD In .  
  
## <a name="remarks"></a>Bemerkungen  
 Der `celt` Parameter, der die Anzahl der Felder angibt, deren Feldinformationen die Methode zum Auffüllen `fields`verwendet, sollte dem Wert des `COR_TYPE_LAYOUT::numFields` Felds entsprechen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugProcess5-Schnittstelle](icordebugprocess5-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
