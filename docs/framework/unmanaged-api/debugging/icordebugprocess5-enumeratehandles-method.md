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
ms.openlocfilehash: 291b384d6f0c8c1404b380c653693ec65fcfc960
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213412"
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
 in Eine bitweise Kombination von [corgkreferencetype](corgcreferencetype-enumeration.md) -Werten, die den Typ der Handles angibt, die in der Auflistung enthalten sein sollen.  
  
 `ppENum`  
 vorgenommen Ein Zeiger auf die Adresse eines [ICorDebug](icordebuggcreferenceenum-interface.md) -Enumerationsobjekts, bei dem es sich um einen Enumerator für die Objekte handelt, für die eine Garbage Collection durchgeführt werden soll.  
  
## <a name="remarks"></a>Hinweise  
 `EnumerateHandles`ist eine Hilfsfunktion, die die Überprüfung der Handle-Tabelle unterstützt. Die Methode ähnelt der [ICorDebugProcess5:: enumerategkreferences](icordebugprocess5-enumerategcreferences-method.md) -Methode, mit der Ausnahme, dass Sie keine [icordebuggkreferenceenumerationsauflistung](icordebuggcreferenceenum-interface.md) mit allen Objekten auffüllen, die für die Garbage Collection freigegeben werden sollen. Sie enthält nur Objekte, die über Handles aus der Handle-Tabelle verfügen.  
  
 Der- `types` Parameter gibt die Handle-Typen an, die in die Auflistung eingeschlossen werden sollen. `types`kann eines der folgenden drei Member der [corgkreferencetype](corgcreferencetype-enumeration.md) -Enumeration sein:  
  
- `CorHandleStrongOnly`(nur Handles zu starken verweisen).  
  
- `CorHandleWeakOnly`(nur Handles für schwache Verweise).  
  
- `CorHandleAll`(alle Handles).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
