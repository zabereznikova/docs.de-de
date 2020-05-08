---
title: ICorDebugChain::GetCallee-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
ms.openlocfilehash: ba9a4e32216fd6fad285397bfc48fbc54f602b88
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894651"
---
# <a name="icordebugchaingetcallee-method"></a>ICorDebugChain::GetCallee-Methode
Ruft die Kette ab, die von dieser Kette aufgerufen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppChain`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebug-Objekts, das die aufgerufene Kette darstellt. Wenn diese Kette derzeit ausgeführt wird (d. h., wenn diese Kette nicht darauf wartet, dass eine aufgerufene Kette `ppChain` zurückgegeben wird), ist NULL.  
  
## <a name="remarks"></a>Hinweise  
 Diese Kette wartet darauf, dass die aufgerufene Kette zurückkehrt, bevor die Ausführung fortgesetzt wird. Die aufgerufene Kette kann sich in einem anderen Thread befinden, wenn Thread übergreifende Marshalling aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
