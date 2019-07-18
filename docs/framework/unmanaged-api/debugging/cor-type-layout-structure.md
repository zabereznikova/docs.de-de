---
title: COR_TYPE_LAYOUT-Struktur
ms.date: 03/30/2017
api_name:
- COR_TYPE_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPE_LAYOUT
helpviewer_keywords:
- COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1793547cfc0d9637352b62ff47beee41e9f5ac5c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740506"
---
# <a name="cortypelayout-structure"></a>COR_TYPE_LAYOUT-Struktur
Bietet Informationen zum Layout eines Objekts im Speicher.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
|`parentID`|Der Bezeichner des übergeordneten Typs auf diesen Typ. Dadurch werden die NULL-Typ-Id (ttoken1 = 0 "," token2 = 0) Wenn die Typ-Id entspricht <xref:System.Object?displayProperty=nameWithType>.|  
|`objectSize`|Die Grundgröße eines Objekts dieses Typs. Dies ist die Gesamtgröße für große Objekte nicht-Variable.|  
|`numFields`|Die Anzahl der Felder, die in der Objekte dieses Typs enthalten.|  
|`boxOffset`|Wenn dieser Typ geschachtelt ist, offset am Anfang der Felder eines Objekts aus. Dieses Feld gilt nur für Werttypen wie z. B. primitive Typen und Strukturen.|  
|`type`|Die CorElementType, zu dem dieser Typ gehört.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `numFields` ist größer als 0 (null), rufen Sie die [icordebugprocess5:: Gettypefields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) Methode zum Abrufen von Informationen zu den Feldern in dieser Art. Wenn `type` ist `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, oder `ELEMENT_TYPE_SZARRAY`, die Größe der Objekte dieses Typs ist, Variablen und können Sie übergeben die [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) -Struktur in der [icordebugprocess5:: Getarraylayout ](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
