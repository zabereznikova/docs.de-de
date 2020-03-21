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
ms.openlocfilehash: ca2d00611a7530dfb0d1c2a27123947bdf69820d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179352"
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
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`componentID`|Der Bezeichner des Objekttyps, den das Array enthält.|  
|`componentType`|Ein CorElementType-Enumerationswert, der angibt, ob es sich bei der Komponente um einen Garbage Collection-Verweis, eine Wertklasse oder einen Primitiv handelt.|  
|`firstElementOffset`|Der Offset zum ersten Element im Array.|  
|`elementSize`|Die Größe jedes Elements.|  
|`countOffset`|Der Offset zur Anzahl der Elemente im Array.|  
|`rankSize`|Die Größe des Rangs in Bytes.|  
|`numRanks`|Die Anzahl der Ränge im Array.|  
|`rankOffset`|Der Offset, bei dem die Ränge beginnen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das `rankSize` Feld gibt die Größe eines Rangs in einem mehrdimensionalen Array an. Es ist auch für eindimensionale Arrays genau.  
  
 Der Wert `numRanks` von ist 1 für `N` ein eindimensionales Array `N` und für ein mehrdimensionales Array von Dimensionen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
