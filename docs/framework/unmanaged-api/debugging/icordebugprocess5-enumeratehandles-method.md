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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6552bde30bf3363f1a5a25788fba99e473975c7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64616278"
---
# <a name="icordebugprocess5enumeratehandles-method"></a>ICorDebugProcess5::EnumerateHandles-Methode
Ruft einen Enumerator für die Objekt-Handles in einem Prozess ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a>Parameter  
 `types`  
 [in] Eine bitweise Kombination von [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) Werte, der angibt, den Typ des Handles in die Auflistung eingeschlossen werden sollen.  
  
 `ppENum`  
 [out] Ein Zeiger auf die Adresse einer [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) , einen Enumerator für die Objekte, das speicherbereinigt werden soll.  
  
## <a name="remarks"></a>Hinweise  
 `EnumerateHandles` ist eine Hilfsfunktion, die Überprüfung der Handletabelle unterstützt. Es ähnelt der [icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) -Methode, außer dass statt Auffüllen einer [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) Auflistung mit allen Objekten, das speicherbereinigt werden soll es enthält nur Objekte, die Handles aus der Handletabelle verfügen.  
  
 Die `types` Parameter gibt die Typen von Handles in die Auflistung eingeschlossen werden sollen. `types` die folgenden drei Elemente von möglich die [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) Enumeration:  
  
- `CorHandleStrongOnly` (Handles auf zuverlässige Verweise nur).  
  
- `CorHandleWeakOnly` (um nur schwache Verweise Handles).  
  
- `CorHandleAll` (alle Handles).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
