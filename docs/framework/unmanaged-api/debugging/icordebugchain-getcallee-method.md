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
ms.openlocfilehash: ed5a7657affde335acf79952d77bbdb7ac42c7a0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490462"
---
# <a name="icordebugchaingetcallee-method"></a>ICorDebugChain::GetCallee-Methode
Ruft die Zertifikatskette, die von dieser Kette aufgerufen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
