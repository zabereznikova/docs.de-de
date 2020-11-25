---
title: COR_ARRAY_LAYOUT-Struktur
ms.date: 03/30/2017
api_name:
- COR_ARRAY_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ARRAY_LAYOUT
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type:
- apiref
ms.openlocfilehash: 2ca6c89a671c4d7882e7cefdb820d07ac5636530
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727405"
---
# <a name="cor_array_layout-structure"></a>COR_ARRAY_LAYOUT-Struktur

Bietet Informationen zum Layout eines Arrayobjekts im Speicher.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct COR_ARRAY_LAYOUT {  
    COR_TYPEID componentID;  
    CorElementType componentType;  
    ULONG32 firstElementOffset;  
    ULONG32 elementSize;  
    ULONG32 countOffset;
    ULONG32 rankSize;
    ULONG32 numRanks;
    ULONG32 rankOffset;
} COR_ARRAY_LAYOUT;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`componentID`|Der Bezeichner des Objekt Typs, der im Array enthalten ist.|  
|`componentType`|Ein CorElementType-Enumerationswert, der angibt, ob die Komponente ein Garbage Collection Verweis, eine Wert Klasse oder ein primitiver ist.|  
|`firstElementOffset`|Der Offset zum ersten Element im Array.|  
|`elementSize`|Die Größe der einzelnen Elemente.|  
|`countOffset`|Der Offset für die Anzahl der Elemente im Array.|  
|`rankSize`|Die Größe des Rangs in Bytes.|  
|`numRanks`|Die Anzahl der Ränge im Array.|  
|`rankOffset`|Der Offset, an dem die Ränge gestartet werden.|  
  
## <a name="remarks"></a>Hinweise  

 Das- `rankSize` Feld gibt die Größe eines Rang in einem mehrdimensionalen Array an. Dies gilt auch für eindimensionale Arrays.  
  
 Der Wert von `numRanks` ist 1 für ein eindimensionales Array und `N` für ein mehrdimensionales Array von `N` Dimensionen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
