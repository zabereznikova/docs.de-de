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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dd233643bd18b60b7d6176c34ee57e4061daf7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740658"
---
# <a name="corheapinfo-structure"></a>COR_HEAPINFO-Struktur
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
|`areGCStructuresValid`|`true` Wenn der Garbage Collection-Strukturen sind gültig und der Heap aufgelistet werden kann; andernfalls `false`.|  
|`pointerSize`|Die Größe in Byte von Zeigern auf der Zielarchitektur.|  
|`numHeaps`|Die Anzahl der logischen speicherbereinigung heaps im Prozess.|  
|`concurrent`|`TRUE` Wenn die gleichzeitige Garbagecollection (Hintergrund) aktiviert ist. andernfalls `FALSE`.|  
|`gcType`|Ein Mitglied der [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) Enumeration, der angibt, ob der Garbage Collection auf einer Arbeitsstation oder einem Server ausgeführt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz von der `COR_HEAPINFO` Struktur wird zurückgegeben, indem die [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) Methode.  
  
 Sie müssen immer überprüfen, vor der Enumeration von Objekten auf dem Garbage Collection-Heap, der `areGCStructuresValid` Feld, um sicherzustellen, dass der Heap aufzählbar ist. Weitere Informationen finden Sie unter den [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
