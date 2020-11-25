---
title: ICorDebugChain::GetCaller-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
ms.openlocfilehash: 0f616b3bae48a972c0fc8935c35add7d844a7364
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730109"
---
# <a name="icordebugchaingetcaller-method"></a>ICorDebugChain::GetCaller-Methode

Ruft die Kette ab, die diese Kette aufgerufen hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppChain`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugChain-Objekts, das die aufrufende Kette darstellt.  
  
 Wenn diese Kette spontan aufgerufen wurde (wie es der Fall wäre, wenn diese Kette oder der Debugger die Aufruf Stapel initialisiert hat), ist `ppChain` NULL.  
  
## <a name="remarks"></a>Hinweise  

 Die aufrufende Kette kann sich in einem anderen Thread befinden, wenn der Aufruf über Threads hinweg gemarshallt wurde.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
