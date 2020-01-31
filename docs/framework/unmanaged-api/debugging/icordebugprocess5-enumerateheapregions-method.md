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
ms.openlocfilehash: 8070b0693b5718ad8b4cbeb9bf5792cb7f4a0a85
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792406"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a>ICorDebugProcess5::EnumerateHeapRegions-Methode
Ruft einen Enumerator für die Speicherbereiche des verwalteten Heaps ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ppRegions`  
 vorgenommen Ein Zeiger auf die Adresse eines [icordebugheapsegmentenum](icordebugheapsegmentenum-interface.md) -Schnittstellen Objekts, bei dem es sich um einen Enumerator für die Speicherbereiche handelt, in denen-Objekte im verwalteten Heap gespeichert sind.  
  
## <a name="remarks"></a>Hinweise  
 Bevor Sie die `ICorDebugProcess5::EnumerateHeapRegions`-Methode aufrufen, sollten Sie die [ICorDebugProcess5:: getgcheapinformation](icordebugprocess5-getgcheapinformation-method.md) -Methode aufrufen und den Wert des `areGCStructuresValid` Felds des zurückgegebenen [COR_HEAPINFO](cor-heapinfo-structure.md) Objekts überprüfen, um sicherzustellen, dass der Garbage Collection Heap im aktuellen Zustand aufzählbar ist. Außerdem gibt die `ICorDebugProcess5::EnumerateHeapRegions`-Methode `E_FAIL` zurück, wenn Sie die Lebensdauer des Prozesses zu früh anfügen, bevor Speicherbereiche erstellt werden.  
  
 Mit dieser Methode werden alle Speicherbereiche aufgelistet, die möglicherweise verwaltete Objekte enthalten, aber es wird nicht garantiert, dass sich verwaltete Objekte tatsächlich in diesen Regionen befinden. Das [icordebugheapsegmentenum](icordebugheapsegmentenum-interface.md) -Auflistungs Objekt kann leere oder reservierte Speicherbereiche enthalten.  
  
 Das [icordebugheapsegmentenum](icordebugheapsegmentenum-interface.md) -Schnittstellen Objekt ist ein Standard-Enumerator, der von der ICorDebugEnum-Schnittstelle abgeleitet wird, die es Ihnen ermöglicht, [COR_SEGMENT](cor-segment-structure.md) Objekte aufzuzählen. Jedes [COR_SEGMENT](cor-segment-structure.md) Objekt stellt Informationen zum Speicherbereich eines bestimmten Segments zusammen mit der Generierung der Objekte in diesem Segment bereit.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess5-Schnittstelle](icordebugprocess5-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
