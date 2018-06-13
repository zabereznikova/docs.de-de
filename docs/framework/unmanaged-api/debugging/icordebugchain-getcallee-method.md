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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f050a3d9d37e43713c40896fb162bcf9932c6512
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403369"
---
# <a name="icordebugchaingetcallee-method"></a>ICorDebugChain::GetCallee-Methode
Ruft die Kette, die durch diese Kette aufgerufen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppChain`  
 [out] Ein Zeiger auf die Adresse eines ICorDebugChain-Objekts, das die aufgerufene Kette darstellt. Wenn diese Kette zurzeit ausgeführt wird (d. h., wenn diese Kette nicht für eine aufgerufene Kette zurückzugebenden wartet), `ppChain` wird null sein.  
  
## <a name="remarks"></a>Hinweise  
 Diese Kette wartet für die aufgerufene Kette zurückgegeben werden, bevor sie die Ausführung fortsetzt. Die aufgerufene Kette möglicherweise in einem anderen Thread im Fall von threadübergreifende Aufrufe.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
