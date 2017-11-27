---
title: COR_TYPE_LAYOUT-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_TYPE_LAYOUT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_TYPE_LAYOUT
helpviewer_keywords: COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fc23e33abf47d19792c25d36a62bf95a098ee7a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="cortypelayout-structure"></a>COR_TYPE_LAYOUT-Struktur
Bietet Informationen zum Layout eines Objekts im Speicher.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`parentID`|Der Bezeichner des übergeordneten Typs auf diesen Typ. Dieser Wert ist, die NULL-Typ-Id (ttoken1 = 0, token2 = 0), wenn die Typ-Id entspricht <xref:System.Object?displayProperty=nameWithType>.|  
|`objectSize`|Die Grundgröße eines Objekts dieses Typs. Hierbei handelt es sich um die Gesamtgröße für große Objekte nicht-Variable.|  
|`numFields`|Die Anzahl der Felder in der Objekte dieses Typs enthalten.|  
|`boxOffset`|Wenn dieser Typ geschachtelt ist, offset am Anfang der Felder eines Objekts verhindern. Dieses Feld gilt nur für Werttypen wie z. B. primitive Typen und Strukturen.|  
|`type`|Die CorElementType, zu dem dieser Typ gehört.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `numFields` ist größer als 0 (null), können Sie rufen die [icordebugprocess5:: Gettypefields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) Methode zum Abrufen von Informationen zu den Feldern in diesen Typ. Wenn `type` ist `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, oder `ELEMENT_TYPE_SZARRAY`, die Größe der Objekte dieses Typs wird die Variable und Sie können übergeben der [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) -Struktur in der [icordebugprocess5:: Getarraylayout ](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
