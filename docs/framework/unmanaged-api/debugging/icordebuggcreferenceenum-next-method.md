---
title: ICorDebugGCReferenceEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
ms.openlocfilehash: e55c53b9610dcadee92ba9871bf52e3dacb5796b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726235"
---
# <a name="icordebuggcreferenceenumnext-method"></a>ICorDebugGCReferenceEnum::Next-Methode

Ruft die angegebene Anzahl von [COR_GC_REFERENCE](cor-gc-reference-structure.md) Instanzen ab, die Informationen über Objekte enthalten, für die eine Garbage Collection durchgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameter  

 celt  
 in Die Anzahl der Stämme, die abgerufen werden sollen.  
  
 Basis  
 vorgenommen Ein Array von Zeigern, von denen jedes auf ein [COR_GC_REFERENCE](cor-gc-reference-structure.md) Objekt verweist, das den Stamm eines Objekts darstellt, für das eine Garbage Collection durchgeführt werden soll.  
  
 pceltFetched  
 vorgenommen Ein Zeiger auf die Anzahl der [COR_GC_REFERENCE](cor-gc-reference-structure.md) -Objekte, die tatsächlich in zurückgegeben werden `roots` . Dieser Wert kann `null` sein, wenn `celt` 1 ist.  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugGCReferenceEnum-Schnittstelle](icordebuggcreferenceenum-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
