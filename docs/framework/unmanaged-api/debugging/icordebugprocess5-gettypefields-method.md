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
ms.openlocfilehash: 644b5ed751caaf1809250244b37badc8037b0f57
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792351"
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
  
## <a name="parameters"></a>Parameters  
 `id`  
 in Der Bezeichner des Typs, dessen Feldinformationen abgerufen werden.  
  
 `celt`  
 in Die Anzahl der [COR_FIELD](cor-field-structure.md) -Objekte, deren Feldinformationen abgerufen werden sollen.  
  
 `fields`  
 vorgenommen Ein Array von [COR_FIELD](cor-field-structure.md) -Objekten, die Informationen zu den Feldern bereitstellen, die zum Typ gehören.  
  
 `pceltNeeded`  
 vorgenommen Ein Zeiger auf die Anzahl von [COR_FIELD](cor-field-structure.md) -Objekten, die in `fields`enthalten sind.  
  
## <a name="remarks"></a>Hinweise  
 Der `celt`-Parameter, der die Anzahl der Felder angibt, deren Feldinformationen die Methode zum Auffüllen von `fields`verwendet, sollte dem Wert des Felds `COR_TYPE_LAYOUT::numFields` entsprechen.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess5-Schnittstelle](icordebugprocess5-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
