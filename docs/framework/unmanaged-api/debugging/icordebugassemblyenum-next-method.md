---
title: ICorDebugAssemblyEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum::Next method
helpviewer_keywords:
- ICorDebugAssemblyEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: b3e7d0c2-3baa-4ef8-8e3f-b865cf252940
topic_type:
- apiref
ms.openlocfilehash: 155354b335caf83c466c8d9d6711f36c7efc9298
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894811"
---
# <a name="icordebugassemblyenumnext-method"></a>ICorDebugAssemblyEnum::Next-Methode
Ruft die angegebene Anzahl von Assemblys aus der Auflistung ab, beginnend bei der aktuellen Cursorposition.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `celt`  
 in Die Anzahl der abzurufenden Assemblys.  
  
 `values`  
 vorgenommen Ein Array von Zeigern, von denen jedes auf ein ICorDebug-Objekt verweist, das eine Assembly darstellt.  
  
 `pceltFetched`  
 vorgenommen Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Assemblys. Dieser Wert kann NULL sein, `celt` wenn ein Wert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
