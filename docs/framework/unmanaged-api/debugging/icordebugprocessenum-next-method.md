---
title: ICorDebugProcessEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type:
- apiref
ms.openlocfilehash: 6aee88452819a4aabe2a29971ce86079ef7f0008
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732501"
---
# <a name="icordebugprocessenumnext-method"></a>ICorDebugProcessEnum::Next-Methode

Ruft die angegebene Anzahl von ICorDebugProcess-Instanzen aus der-Enumeration ab, beginnend bei der aktuellen Position.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `celt`  
 in Die Anzahl der `ICorDebugProcess` abzurufenden Instanzen.  
  
 `processes`  
 vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugProcess` Objekt verweist, das einen Prozess darstellt.  
  
 `pceltFetched`  
 vorgenommen Ein Zeiger auf die Anzahl der `ICorDebugProcess` tatsächlich zurückgegebenen Instanzen. Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
