---
title: COR_HEAPINFO-Struktur
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
ms.openlocfilehash: 37659262695b63a6dd6390c62c4bb7e04fdadca4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179307"
---
# <a name="cor_heapinfo-structure"></a>COR_HEAPINFO-Struktur
Liefert allgemeine Informationen zum Garbage Collection-Heap, auch zu dessen Aufzählbarkeit.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;
    DWORD pointerSize;
    DWORD numHeaps;  
    BOOL concurrent;
    CorDebugGCType gcType;
} COR_HEAPINFO;  
```  
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`areGCStructuresValid`|`true`wenn Garbage Collection-Strukturen gültig sind und der Heap aufgezählt werden kann; andernfalls `false`.|  
|`pointerSize`|Die Größe von Zeigern auf die Zielarchitektur in Bytes.|  
|`numHeaps`|Die Anzahl der logischen Garbage Collection-Heaps im Prozess.|  
|`concurrent`|`TRUE`wenn die gleichzeitige (Hintergrund-)Garbage Collection aktiviert ist; andernfalls `FALSE`.|  
|`gcType`|Ein Member der [CorDebugGCType-Enumeration,](cordebuggctype-enumeration.md) der angibt, ob der Garbage Collector auf einer Arbeitsstation oder einem Server ausgeführt wird.|  
  
## <a name="remarks"></a>Bemerkungen  
 Eine Instanz `COR_HEAPINFO` der Struktur wird zurückgegeben, indem die [ICorDebugProcess5::GetGCHeapInformation-Methode](icordebugprocess5-getgcheapinformation-method.md) aufgerufen wird.  
  
 Bevor Sie Objekte auf dem Garbage Collection-Heap aufzählen, müssen Sie das `areGCStructuresValid` Feld immer überprüfen, um sicherzustellen, dass sich der Heap in einem aufzählbaren Zustand befindet. Weitere Informationen finden Sie in der [ICorDebugProcess5::GetGCHeapInformation-Methode.](icordebugprocess5-getgcheapinformation-method.md)  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
