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
ms.openlocfilehash: 79743b78ea3d19bab4756b580d2feddd07e0a23b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744983"
---
# <a name="icordebugchaingetcallee-method"></a>ICorDebugChain::GetCallee-Methode
Ruft die Zertifikatskette, die von dieser Kette aufgerufen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppChain`  
 [out] Ein Zeiger auf die Adresse des ICorDebugChain-Objekts, das die aufgerufene Kette darstellt. Wenn diese Kette zurzeit ausgeführt wird (d.h., wenn dieser Kette nicht für eine aufgerufene Kette zurückzugebenden wartet), `ppChain` NULL.  
  
## <a name="remarks"></a>Hinweise  
 Diese Kette wird gewartet, für die aufgerufene Kette zurückgegeben wird, bevor sie die Ausführung fortsetzt. Die aufgerufene Kette möglicherweise auf einem anderen Thread im Fall von threadübergreifende gemarshallte Aufrufe.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
