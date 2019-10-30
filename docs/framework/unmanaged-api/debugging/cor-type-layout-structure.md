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
ms.openlocfilehash: 12c594f157c803d5fc179e09a8ca6c0ef40f3f44
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099024"
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
|`parentID`|Der Bezeichner des übergeordneten Typs für diesen Typ. Dabei handelt es sich um die NULL-Typ-ID (ttoken1 = 0, Token2 = 0), wenn die Typ-ID <xref:System.Object?displayProperty=nameWithType>entspricht.|  
|`objectSize`|Die Basis Größe eines Objekts dieses Typs. Dies ist die Gesamtgröße für Objekte, die keine Variablen groß sind.|  
|`numFields`|Die Anzahl der Felder, die in Objekten dieses Typs enthalten sind.|  
|`boxOffset`|Wenn dieser Typ ein Boxing ist, der Anfangs Offset der Felder eines Objekts. Dieses Feld ist nur für Werttypen, z. b. primitive und Strukturen, gültig.|  
|`type`|Der CorElementType, zu dem dieser Typ gehört.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `numFields` größer als 0 (null) ist, können Sie die [ICorDebugProcess5:: gettypeer Fields](icordebugprocess5-gettypefields-method.md) -Methode aufrufen, um Informationen zu den Feldern in diesem Typ zu erhalten. Wenn `type` `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`oder `ELEMENT_TYPE_SZARRAY`ist, ist die Größe von Objekten dieses Typs variabel, und Sie können die [COR_TYPEID](cor-typeid-structure.md) -Struktur an die [ICorDebugProcess5:: getarraylayout](icordebugprocess5-getarraylayout-method.md) -Methode übergeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
