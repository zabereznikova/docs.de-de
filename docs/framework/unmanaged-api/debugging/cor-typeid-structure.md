---
title: COR_TYPEID-Struktur
ms.date: 03/30/2017
api_name:
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b905d3b5de39057cba384ea7bca917bc3476623f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700649"
---
# <a name="cortypeid-structure"></a>COR_TYPEID-Struktur
Enthält einen Typbezeichner.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`token1`|Das erste Token.|  
|`token2`|Das zweite-Token.|  
  
## <a name="remarks"></a>Hinweise  
 Die `COR_TYPEID` Struktur wird zurückgegeben, um eine Anzahl von debugging-Methoden, die Informationen zu Objekten, das speicherbereinigt werden soll. Sie können dann als Argument an andere debugging-Methoden übergeben werden, die zusätzliche Informationen zu diesem Element bereitstellen. Z. B. durch die Enumeration eine [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) Objekt ist, können Sie einzelne abrufen [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Objekte, die einzelnen Objekte im verwalteten Heap darstellen. Anschließend können Sie übergeben die `COR_TYPEID` Wert aus der `COR_HEAPOBJECT.type` Feld der [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) Methode zum Abrufen eines ICorDebugType-Objekts, das Informationen über das Objekt bereitstellt.  
  
 Ein `COR_TYPEID` Objekt ist nicht transparent sein soll. Die einzelnen Felder sollten nicht zugegriffen oder bearbeitet werden. Die alleinige Verwendung ist ein Bezeichner, der als bereitgestellt wird ein `out` Parameter im Aufruf einer Methode und diese kann wiederum übergeben werden andere Methoden, um zusätzliche Informationen bereitzustellen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
