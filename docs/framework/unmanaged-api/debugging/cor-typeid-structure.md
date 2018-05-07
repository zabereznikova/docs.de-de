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
ms.openlocfilehash: 3d4e07fb3d0988838fde662f4bb7d4719cc2d50f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
 Die `COR_TYPEID` Struktur zurückgegeben wird, um eine Anzahl von debugging-Methoden, die Informationen zu Objekten, das speicherbereinigt werden soll. Sie können dann als Argument an anderen Debuggen-Methoden übergeben werden, die zusätzliche Informationen zu dem Element bereitstellen. Z. B. durch aufzählen einer [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) -Objekt, Sie können einzelne abrufen [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Objekte, die einzelnen Objekte im verwalteten Heap darstellen. Sie können dann übergeben der `COR_TYPEID` Wert aus der `COR_HEAPOBJECT.type` -Feld der [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) Methode, um ein ICorDebugType abzurufen, die zu dem Objekt bereitstellt.  
  
 Ein `COR_TYPEID` -Objekt ist dazu gedacht, nicht transparent sein. Die einzelne Felder sollten nicht zugegriffen oder bearbeitet werden sollen. Die alleinige Verwendung wird als ein Bezeichner, der als bereitgestellt wird ein `out` Parameter im Aufruf einer Methode und diese kann wiederum weitere Methoden zum Bereitstellen zusätzlicher Informationen übergeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
