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
ms.openlocfilehash: b6fd3682290c9752125aed7b9663c6704ade25de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132333"
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
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`areGCStructuresValid`|`true`, wenn Garbage Collection Strukturen gültig sind und der Heap aufgelistet werden kann. Andernfalls `false`.|  
|`pointerSize`|Die Größe von Zeigern in der Zielarchitektur in Byte.|  
|`numHeaps`|Die Anzahl logischer Garbage Collection Heaps im Prozess.|  
|`concurrent`|`TRUE`, wenn die gleichzeitige (Hintergrund-) Garbage Collection aktiviert ist. Andernfalls `FALSE`.|  
|`gcType`|Ein Member der [cordebuggctype](cordebuggctype-enumeration.md) -Enumeration, der angibt, ob der Garbage Collector auf einer Arbeitsstation oder einem Server ausgeführt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz der `COR_HEAPINFO` Struktur wird durch Aufrufen der [ICorDebugProcess5:: getgcheapinformation](icordebugprocess5-getgcheapinformation-method.md) -Methode zurückgegeben.  
  
 Vor dem Auflisten von Objekten auf dem Garbage Collection Heap müssen Sie immer das `areGCStructuresValid` Feld überprüfen, um sicherzustellen, dass sich der Heap in einem Aufzähl Bare-Zustand befindet. Weitere Informationen finden Sie unter der [ICorDebugProcess5:: getgcheapinformation](icordebugprocess5-getgcheapinformation-method.md) -Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
