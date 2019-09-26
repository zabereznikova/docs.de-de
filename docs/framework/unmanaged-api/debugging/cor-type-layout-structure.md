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
ms.openlocfilehash: 6bd274b1eb14532629580e777288317186544912
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274164"
---
# <a name="cor_type_layout-structure"></a>COR_TYPE_LAYOUT-Struktur
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
|`parentID`|Der Bezeichner des übergeordneten Typs für diesen Typ. Dabei handelt es sich um <xref:System.Object?displayProperty=nameWithType>die NULL-Typ-ID (ttoken1 = 0, Token2 = 0), wenn die Typ-ID entspricht.|  
|`objectSize`|Die Basis Größe eines Objekts dieses Typs. Dies ist die Gesamtgröße für Objekte, die keine Variablen groß sind.|  
|`numFields`|Die Anzahl der Felder, die in Objekten dieses Typs enthalten sind.|  
|`boxOffset`|Wenn dieser Typ ein Boxing ist, der Anfangs Offset der Felder eines Objekts. Dieses Feld ist nur für Werttypen, z. b. primitive und Strukturen, gültig.|  
|`type`|Der CorElementType, zu dem dieser Typ gehört.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `numFields` größer als 0 (null) ist, können Sie die [ICorDebugProcess5:: gettypeer Fields](icordebugprocess5-gettypefields-method.md) -Methode aufrufen, um Informationen zu den Feldern in diesem Typ zu erhalten. Wenn `type` , `ELEMENT_TYPE_STRING` oderist`ELEMENT_TYPE_SZARRAY`, ist die Größe von Objekten dieses Typs variabel, und Sie können die [COR_TYPEID](cor-typeid-structure.md) -Struktur an die [ICorDebugProcess5:: getarraylayout](icordebugprocess5-getarraylayout-method.md) -Methode übergeben. `ELEMENT_TYPE_ARRAY`  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
