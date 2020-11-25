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
ms.openlocfilehash: 5400350e1c489ec4c2ff3cddf83a4f1a8a0c7947
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726599"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`areGCStructuresValid`|`true` , wenn Garbage Collection Strukturen gültig sind und der Heap aufgelistet werden kann. andernfalls `false` .|  
|`pointerSize`|Die Größe von Zeigern in der Zielarchitektur in Byte.|  
|`numHeaps`|Die Anzahl logischer Garbage Collection Heaps im Prozess.|  
|`concurrent`|`TRUE` , wenn die gleichzeitige (Background-) Garbage Collection aktiviert ist. andernfalls `FALSE` .|  
|`gcType`|Ein Member der [cordebuggctype](cordebuggctype-enumeration.md) -Enumeration, der angibt, ob der Garbage Collector auf einer Arbeitsstation oder einem Server ausgeführt wird.|  
  
## <a name="remarks"></a>Hinweise  

 Eine Instanz der- `COR_HEAPINFO` Struktur wird durch Aufrufen der [ICorDebugProcess5:: getgcheapinformation](icordebugprocess5-getgcheapinformation-method.md) -Methode zurückgegeben.  
  
 Vor dem Auflisten von Objekten auf dem Garbage Collection Heap muss immer das Feld überprüft werden, `areGCStructuresValid` um sicherzustellen, dass sich der Heap in einem Aufzähl Bare-Zustand befindet. Weitere Informationen finden Sie unter der [ICorDebugProcess5:: getgcheapinformation](icordebugprocess5-getgcheapinformation-method.md) -Methode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
