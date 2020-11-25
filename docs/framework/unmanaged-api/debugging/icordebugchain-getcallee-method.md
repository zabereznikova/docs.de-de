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
ms.openlocfilehash: a28da34cd3080826f346b8957aa6ba38258b924f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730122"
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
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebug-Objekts, das die aufgerufene Kette darstellt. Wenn diese Kette derzeit ausgeführt wird (d. h., wenn diese Kette nicht darauf wartet, dass eine aufgerufene Kette zurückgegeben wird), ist `ppChain` NULL.  
  
## <a name="remarks"></a>Hinweise  

 Diese Kette wartet darauf, dass die aufgerufene Kette zurückkehrt, bevor die Ausführung fortgesetzt wird. Die aufgerufene Kette kann sich in einem anderen Thread befinden, wenn Thread übergreifende Marshalling aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
