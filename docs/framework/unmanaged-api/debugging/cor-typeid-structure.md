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
ms.openlocfilehash: 5eeb5aef7edaa23385190a309144e1477da741e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697440"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`token1`|Das erste Token.|  
|`token2`|Das zweite Token.|  
  
## <a name="remarks"></a>Hinweise  

 Die `COR_TYPEID` Struktur wird von einer Reihe von Debugmethoden zurückgegeben, die Informationen zu Objekten bereitstellen, die für die Garbage Collection freigegeben werden. Sie kann dann als Argument an andere Debugmethoden weitergegeben werden, die zusätzliche Informationen über dieses Element bereitstellen. Beispielsweise können Sie durch das Auflisten eines [icordebugheapenum](icordebugheapenum-interface.md) -Objekts einzelne [COR_HEAPOBJECT](cor-heapobject-structure.md) Objekte abrufen, die einzelne Objekte im verwalteten Heap darstellen. Sie können dann den `COR_TYPEID` Wert aus dem `COR_HEAPOBJECT.type` Feld an die [ICorDebugProcess5:: gettyetfortypeid](icordebugprocess5-gettypefortypeid-method.md) -Methode übergeben, um ein ICorDebugType-Objekt abzurufen, das Typinformationen über das Objekt bereitstellt.  
  
 Ein-Objekt ist als nicht transparent `COR_TYPEID` vorgesehen. Auf die einzelnen Felder sollte nicht zugegriffen werden oder Sie können nicht bearbeitet werden. Die einzige Verwendung ist ein Bezeichner, der als- `out` Parameter in einem Methoden Aufrufwert bereitgestellt wird und der wiederum an andere Methoden übergeben werden kann, um zusätzliche Informationen bereitzustellen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
