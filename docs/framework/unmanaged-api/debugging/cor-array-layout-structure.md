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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6fee91146e99ba1f63ecafcbbdaae9d42675848
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731139"
---
# <a name="corarraylayout-structure"></a>COR_ARRAY_LAYOUT-Struktur
Bietet Informationen zum Layout eines Arrayobjekts im Speicher.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
|Member|Beschreibung|  
|------------|-----------------|  
|`componentID`|Der Bezeichner des Typs von Objekten, die das Array enthält.|  
|`componentType`|Ein Wert der CorElementType-Enumeration, der angibt, ob die Komponente eine Garbage Collection-Verweis, eine Wertklasse oder ein primitiver Typ ist.|  
|`firstElementOffset`|Der Offset, der das erste Element im Array.|  
|`elementSize`|Die Größe der einzelnen Elemente.|  
|`countOffset`|Der Offset, der die Anzahl der Elemente im Array.|  
|`rankSize`|Die Größe des den Rang, wird in Bytes.|  
|`numRanks`|Die Anzahl der Ränge in das Array.|  
|`rankOffset`|Der Offset, an dem die Ränge starten.|  
  
## <a name="remarks"></a>Hinweise  
 Die `rankSize` Feld gibt die Größe der Rang in ein mehrdimensionales Array. Es ist für eindimensionale Arrays auch präzise.  
  
 Der Wert des `numRanks` ist 1 für ein eindimensionales Array und `N` für ein mehrdimensionales Array des `N` Dimensionen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
