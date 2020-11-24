---
title: ICorDebugValueEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
ms.openlocfilehash: e1c8d94a90092b1497267c78d5fadf5a6e6de707
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684329"
---
# <a name="icordebugvalueenumnext-method"></a>ICorDebugValueEnum::Next-Methode

Ruft die angegebene Anzahl von "ICorDebug Value"-Instanzen aus der-Enumeration ab, beginnend bei der aktuellen Position.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `celt`  
 in Die Anzahl der `ICorDebugValue` abzurufenden Instanzen.  
  
 `values`  
 vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugValue` Objekt verweist.  
  
 `pceltFetched`  
 vorgenommen Ein Zeiger auf die Anzahl der `ICorDebugValue` tatsächlich zurückgegebenen Instanzen. Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen
