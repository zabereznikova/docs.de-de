---
title: ICorDebugProcess5::EnumerateHandles-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
ms.openlocfilehash: e0e68dba1f4d9ac5fa618aa842b823dcc046e70e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129681"
---
# <a name="icordebugprocess5enumeratehandles-method"></a>ICorDebugProcess5::EnumerateHandles-Methode
Ruft einen Enumerator für Objekt Handles in einem Prozess ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a>Parameter  
 `types`  
 in Eine bitweise Kombination von [corgkreferencetype](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) -Werten, die den Typ der Handles angibt, die in der Auflistung enthalten sein sollen.  
  
 `ppENum`  
 vorgenommen Ein Zeiger auf die Adresse eines [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) -Enumerationsobjekts, bei dem es sich um einen Enumerator für die Objekte handelt, für die eine Garbage Collection durchgeführt werden soll.  
  
## <a name="remarks"></a>Hinweise  
 `EnumerateHandles` ist eine Hilfsfunktion, die die Überprüfung der Handle-Tabelle unterstützt. Sie ähnelt der [ICorDebugProcess5:: enumerategkreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) -Methode, mit dem Unterschied, dass Sie keine [icordebuggkreferenceenumerationsauflistung](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) mit allen Objekten auffüllen, die für die Garbage Collection freigegeben werden sollen. Sie enthält nur Objekte, die über Handles aus verfügen. die Handle-Tabelle.  
  
 Der `types`-Parameter gibt die Handle-Typen an, die in die Auflistung eingeschlossen werden sollen. `types` kann eines der folgenden drei Member der [corgkreferencetype](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) -Enumeration sein:  
  
- `CorHandleStrongOnly` (nur Handles zu starken verweisen).  
  
- `CorHandleWeakOnly` (nur Handles für schwache Verweise).  
  
- `CorHandleAll` (alle Handles).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
