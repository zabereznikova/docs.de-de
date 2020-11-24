---
title: ICorDebugProcess5::GetGCHeapInformation-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
ms.openlocfilehash: 43054a71445193bae7a74e0ed6785cccd1d02dc2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670991"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a>ICorDebugProcess5::GetGCHeapInformation-Methode

Stellt allgemeine Informationen über den Garbage Collection Heap bereit, einschließlich dessen, ob er derzeit Aufzähl Bar ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pHeapInfo`  
 vorgenommen Ein Zeiger auf einen [COR_HEAPINFO](cor-heapinfo-structure.md) Wert, der allgemeine Informationen über den Garbage Collection Heap bereitstellt.  
  
## <a name="remarks"></a>Hinweise  

 Die- `ICorDebugProcess5::GetGCHeapInformation` Methode muss aufgerufen werden, bevor der Heap oder einzelne Heap Regionen aufgelistet werden, um sicherzustellen, dass die Garbage Collection Strukturen im Prozess aktuell gültig sind. Der Garbage Collection Heap kann nicht durchlaufen werden, während eine Sammlung ausgeführt wird. Andernfalls kann die-Enumeration Garbage Collection Strukturen erfassen, die ungültig sind.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugProcess5-Schnittstelle](icordebugprocess5-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
