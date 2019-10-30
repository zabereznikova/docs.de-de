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
ms.openlocfilehash: 4f6dbe8c17bd6a91078b87a87c1055fbf4977a88
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132301"
---
# <a name="cor_typeid-structure"></a>COR_TYPEID-Struktur
Enthält einen Typbezeichner.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`token1`|Das erste Token.|  
|`token2`|Das zweite Token.|  
  
## <a name="remarks"></a>Hinweise  
 Die `COR_TYPEID` Struktur wird von einer Reihe von Debugmethoden zurückgegeben, die Informationen zu Objekten bereitstellen, die für die Garbage Collection freigegeben werden. Sie kann dann als Argument an andere Debugmethoden weitergegeben werden, die zusätzliche Informationen über dieses Element bereitstellen. Beispielsweise können Sie durch das Auflisten eines [icordebugheapenum](icordebugheapenum-interface.md) -Objekts einzelne [COR_HEAPOBJECT](cor-heapobject-structure.md) -Objekte abrufen, die einzelne Objekte im verwalteten Heap darstellen. Anschließend können Sie den `COR_TYPEID` Wert aus dem Feld `COR_HEAPOBJECT.type` an die [ICorDebugProcess5:: gettyps](icordebugprocess5-gettypefortypeid-method.md) -Methode übergeben, um ein ICorDebugType-Objekt abzurufen, das Typinformationen über das Objekt bereitstellt.  
  
 Ein `COR_TYPEID`-Objekt ist als nicht transparent vorgesehen. Auf die einzelnen Felder sollte nicht zugegriffen werden oder Sie können nicht bearbeitet werden. Die einzige Verwendung ist ein Bezeichner, der in einem Methoden aufrufals `out`-Parameter bereitgestellt wird und wiederum an andere Methoden übergeben werden kann, um zusätzliche Informationen bereitzustellen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
