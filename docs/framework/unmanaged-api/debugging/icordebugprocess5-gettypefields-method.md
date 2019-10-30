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
ms.openlocfilehash: 0045285a3da22f468c2426bb3b9c4ae7e3e1d7c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132671"
---
# <a name="icordebugprocess5gettypefields-method"></a>ICorDebugProcess5::GetTypeFields-Methode
Stellt Informationen zu den Feldern bereit, die zu einem-Typ gehören.  
  
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
 in Der Bezeichner des Typs, dessen Feldinformationen abgerufen werden.  
  
 `celt`  
 in Die Anzahl der [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) -Objekte, deren Feldinformationen abgerufen werden sollen.  
  
 `fields`  
 vorgenommen Ein Array von [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) -Objekten, die Informationen zu den Feldern bereitstellen, die zum Typ gehören.  
  
 `pceltNeeded`  
 vorgenommen Ein Zeiger auf die Anzahl der in `fields`enthaltenen [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) -Objekte.  
  
## <a name="remarks"></a>Hinweise  
 Der `celt`-Parameter, der die Anzahl der Felder angibt, deren Feldinformationen die Methode zum Auffüllen von `fields`verwendet, sollte dem Wert des Felds `COR_TYPE_LAYOUT::numFields` entsprechen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess5-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
