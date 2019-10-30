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
ms.openlocfilehash: c8cfc9cdf6580a002f6ac15080012a9e8c63be20
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129651"
---
# <a name="icordebugprocess5enumerateheap-method"></a>ICorDebugProcess5::EnumerateHeap-Methode
Ruft einen Enumerator für die Objekte im verwalteten Heap ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppObject`  
 vorgenommen Ein Zeiger auf die Adresse eines [icordebugheapenum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) -Schnittstellen Objekts, bei dem es sich um einen Enumerator für die Objekte handelt, die sich auf dem verwalteten Heap befinden.  
  
## <a name="remarks"></a>Hinweise  
 Bevor Sie die `ICorDebugProcess5::EnumerateHeap`-Methode aufrufen, sollten Sie die [ICorDebugProcess5:: getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) -Methode aufrufen und den Wert des `areGCStructuresValid` Felds des zurückgegebenen [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) -Objekts überprüfen, um sicherzustellen, dass der Garbage Collection Heap in seinem der aktuelle Zustand ist "Enumerable". Außerdem gibt die `ICorDebugProcess5::EnumerateHeap` `E_FAIL` zurück, wenn Sie zu früh an der Lebensdauer des Prozesses anfügen, bevor der Arbeitsspeicher für den verwalteten Heap zugeordnet wird.  
  
 Das [icordebugheapenum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) -Schnittstellen Objekt ist ein Standard-Enumerator, der von der ICorDebugEnum-Schnittstelle abgeleitet wird und die das Auflisten von [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) -Objekten ermöglicht. Diese Methode füllt das [icordebugheapenum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) -Auflistungs Objekt mit [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) -Instanzen auf, die Informationen zu allen Objekten bereitstellen. Die Auflistung kann auch [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) -Instanzen enthalten, die Informationen zu Objekten bereitstellen, die nicht von einem Objekt stammen, aber noch nicht von der Garbage Collector erfasst wurden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess5-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
