---
title: COR_ARRAY_LAYOUT-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_ARRAY_LAYOUT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_ARRAY_LAYOUT
helpviewer_keywords: COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 02ddd87cfaf16990ff487dfe27f30a2493cb9a01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
|`elementSize`|Die Größe jedes Elements.|  
|`countOffset`|Der Offset, der die Anzahl der Elemente im Array.|  
|`rankSize`|Die Größe der Rang in Bytes.|  
|`numRanks`|Die Anzahl der Ränge im Array.|  
|`rankOffset`|Der Offset, an dem die Ränge starten.|  
  
## <a name="remarks"></a>Hinweise  
 Die `rankSize` Feld gibt die Größe der Rang in ein mehrdimensionales Array. Für eindimensionale Arrays als auch präzise ist.  
  
 Der Wert der `numRanks` ist 1 für ein eindimensionales Array und `N` für ein mehrdimensionales Array des `N` Dimensionen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
