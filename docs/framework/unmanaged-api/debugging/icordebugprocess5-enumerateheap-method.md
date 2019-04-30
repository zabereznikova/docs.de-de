---
title: ICorDebugProcess5::EnumerateHeap-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b404b7762e085eb44f0bd3b448fcee9eab9a3c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948784"
---
# <a name="icordebugprocess5enumerateheap-method"></a>ICorDebugProcess5::EnumerateHeap-Methode
Ruft einen Enumerator für die Objekte ab, auf dem verwalteten Heap.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppObject`  
 [out] Ein Zeiger auf die Adresse des ein [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) Schnittstellenobjekt, das einen Enumerator für die Objekte, die auf dem verwalteten Heap gespeichert sind.  
  
## <a name="remarks"></a>Hinweise  
 Vor dem Aufruf der `ICorDebugProcess5::EnumerateHeap` -Methode, die Sie aufrufen sollten die [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) Methode, und untersuchen Sie den Wert des der `areGCStructuresValid` Feld des zurückgegebenen [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Objekt, um sicherzustellen, dass die Garbage Collection-Heap im aktuellen Zustand aufzählbar ist. Darüber hinaus die `ICorDebugProcess5::EnumerateHeap` gibt `E_FAIL` Wenn Sie zu früh während der Lebensdauer des Prozesses, bevor Speicher anfügen, für der verwaltete Heap zugeordnet ist.  
  
 Die [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) -Schnittstellenobjekt wird einen Standardenumerator, die von der ICorDebugEnum-Schnittstelle, die Sie zum Aufzählen kann abgeleitet [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Objekte. Diese Methode füllt den [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) -Auflistungsobjekts mit [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen, die Informationen zu allen Objekten bereitstellen. Die Auflistung kann auch enthalten [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) -Instanzen, die Informationen über Objekte bereitzustellen, die nicht von einem Stamm verfügen Objekt aber noch nicht vom Garbage Collector erfasst wurden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess5-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
