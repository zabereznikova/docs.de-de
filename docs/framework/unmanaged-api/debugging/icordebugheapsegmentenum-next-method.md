---
title: ICorDebugHeapSegmentEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
ms.openlocfilehash: 6398fa2962b347a260e23e4fed8cf272a2916a9e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704616"
---
# <a name="icordebugheapsegmentenumnext-method"></a>ICorDebugHeapSegmentEnum::Next-Methode

Ruft die angegebene Anzahl von [COR_SEGMENT](cor-segment-structure.md) Instanzen ab, die Informationen über die Speicherbereiche des verwalteten Heaps enthalten.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameter  

 celt  
 in Die Anzahl der abzurufenden Segmente.  
  
 Segmente  
 vorgenommen Ein Array von Zeigern, von denen jedes auf ein [COR_SEGMENT](cor-segment-structure.md) Objekt verweist, das Informationen zu einem Speicherbereich im verwalteten Heap bereitstellt.  
  
 pceltFetched  
 vorgenommen Ein Zeiger auf die Anzahl der [COR_SEGMENT](cor-segment-structure.md) -Objekte, die tatsächlich in zurückgegeben werden `segments` . Dieser Wert kann `null` sein, wenn `celt` 1 ist.  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugHeapSegmentEnum-Schnittstelle](icordebugheapsegmentenum-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
