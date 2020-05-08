---
title: ICorDebugChainEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type:
- apiref
ms.openlocfilehash: 2d075820df534e08bdf4c2b75d36f6a60f979662
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894091"
---
# <a name="icordebugchainenumnext-method"></a>ICorDebugChainEnum::Next-Methode
Ruft die angegebene Anzahl von ICorDebug-Ketten Instanzen ab der aktuellen Position aus der-Enumeration ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `celt`  
 in Die Anzahl der `ICorDebugChain` abzurufenden Instanzen.  
  
 `chains`  
 vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugChain` Objekt verweist, das eine Kette darstellt.  
  
 `pceltFetched`  
 vorgenommen Ein Zeiger auf die Anzahl der `ICorDebugChain` tatsächlich zurückgegebenen Instanzen. Dieser Wert kann NULL sein, `celt` wenn ein Wert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
