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
ms.openlocfilehash: a6d26924773e6ad505975402ec3ace150d02cc3a
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894617"
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
  
 Wenn diese Kette spontan aufgerufen wurde (wie es der Fall wäre, wenn diese Kette oder der Debugger die Aufruf Stapel initialisiert hat `ppChain` ), ist NULL.  
  
## <a name="remarks"></a>Hinweise  
 Die aufrufende Kette kann sich in einem anderen Thread befinden, wenn der Aufruf über Threads hinweg gemarshallt wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
