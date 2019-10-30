---
title: ICorDebugProcess5::EnumerateHeapRegions-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeapRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type:
- apiref
ms.openlocfilehash: 3ab4da3fcf43731587dae6f3a8e82ea48c5ee1ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129643"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a>ICorDebugProcess5::EnumerateHeapRegions-Methode
Ruft einen Enumerator für die Speicherbereiche des verwalteten Heaps ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppRegions`  
 vorgenommen Ein Zeiger auf die Adresse eines [icordebugheapsegmentenum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) -Schnittstellen Objekts, bei dem es sich um einen Enumerator für die Speicherbereiche handelt, in denen-Objekte im verwalteten Heap gespeichert sind.  
  
## <a name="remarks"></a>Hinweise  
 Bevor Sie die `ICorDebugProcess5::EnumerateHeapRegions`-Methode aufrufen, sollten Sie die [ICorDebugProcess5:: getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) -Methode aufrufen und den Wert des `areGCStructuresValid` Felds des zurückgegebenen [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) -Objekts überprüfen, um sicherzustellen, dass der Garbage Collection Heap in seinem der aktuelle Zustand ist "Enumerable". Außerdem gibt die `ICorDebugProcess5::EnumerateHeapRegions`-Methode `E_FAIL` zurück, wenn Sie die Lebensdauer des Prozesses zu früh anfügen, bevor Speicherbereiche erstellt werden.  
  
 Mit dieser Methode werden alle Speicherbereiche aufgelistet, die möglicherweise verwaltete Objekte enthalten, aber es wird nicht garantiert, dass sich verwaltete Objekte tatsächlich in diesen Regionen befinden. Das [icordebugheapsegmentenum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) -Auflistungs Objekt kann leere oder reservierte Speicherbereiche enthalten.  
  
 Das [icordebugheapsegmentenum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) -Schnittstellen Objekt ist ein Standard-Enumerator, der von der ICorDebugEnum-Schnittstelle abgeleitet wird und die das Auflisten von [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) -Objekten ermöglicht. Jedes [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) -Objekt stellt Informationen zum Speicherbereich eines bestimmten Segments zusammen mit der Generierung der Objekte in diesem Segment bereit.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess5-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
