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
ms.openlocfilehash: 43408486fec9cd50222eed08ec2d3397bc11bc18
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134620"
---
# <a name="icordebuggcreferenceenumnext-method"></a>ICorDebugGCReferenceEnum::Next-Methode
Ruft die angegebene Anzahl von [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) -Instanzen ab, die Informationen über Objekte enthalten, für die eine Garbage Collection durchgeführt wird.  
  
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
 vorgenommen Ein Array von Zeigern, von denen jedes auf ein [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) -Objekt verweist, das den Stamm eines Objekts darstellt, für das eine Garbage Collection durchgeführt werden soll.  
  
 pceltFetched  
 vorgenommen Ein Zeiger auf die Anzahl der [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) -Objekte, die tatsächlich in `roots`zurückgegeben werden. Dieser Wert kann `null` sein, wenn `celt` 1 ist.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugGCReferenceEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
