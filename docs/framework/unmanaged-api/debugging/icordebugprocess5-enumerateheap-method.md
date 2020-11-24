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
ms.openlocfilehash: 22ab29f8a204a4b27dafdefcd3652cc3dcf9769c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671134"
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
 vorgenommen Ein Zeiger auf die Adresse eines [icordebugheapenum](icordebugheapenum-interface.md) -Schnittstellen Objekts, bei dem es sich um einen Enumerator für die Objekte handelt, die sich auf dem verwalteten Heap befinden.  
  
## <a name="remarks"></a>Hinweise  

 Bevor Sie die- `ICorDebugProcess5::EnumerateHeap` Methode aufrufen, sollten Sie die [ICorDebugProcess5:: getgcheapinformation](icordebugprocess5-getgcheapinformation-method.md) -Methode aufrufen und den Wert des- `areGCStructuresValid` Felds des zurückgegebenen [COR_HEAPINFO](cor-heapinfo-structure.md) Objekts überprüfen, um sicherzustellen, dass der Garbage Collection Heap im aktuellen Zustand aufzählbar ist. Außerdem gibt den Wert `ICorDebugProcess5::EnumerateHeap` zurück `E_FAIL` , wenn Sie zu früh an der Lebensdauer des Prozesses anfügen, bevor der Speicher für den verwalteten Heap zugeordnet wird.  
  
 Das [icordebugheapenum](icordebugheapenum-interface.md) -Schnittstellen Objekt ist ein Standard-Enumerator, der von der ICorDebugEnum-Schnittstelle abgeleitet wird und die es Ihnen ermöglicht, [COR_HEAPOBJECT](cor-heapobject-structure.md) Objekte aufzuzählen. Diese Methode füllt das [icordebugheapenum](icordebugheapenum-interface.md) -Auflistungs Objekt mit [COR_HEAPOBJECT](cor-heapobject-structure.md) -Instanzen auf, die Informationen zu allen Objekten bereitstellen. Die Auflistung kann auch [COR_HEAPOBJECT](cor-heapobject-structure.md) Instanzen enthalten, die Informationen zu Objekten bereitstellen, die nicht von einem Objekt stammen, aber noch nicht vom Garbage Collector erfasst wurden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugProcess5-Schnittstelle](icordebugprocess5-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
