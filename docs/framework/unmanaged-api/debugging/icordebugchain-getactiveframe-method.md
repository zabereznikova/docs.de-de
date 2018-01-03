---
title: ICorDebugChain::GetActiveFrame-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetActiveFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7498e031b74bd904b908342b663e4421432e6d95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchaingetactiveframe-method"></a>ICorDebugChain::GetActiveFrame-Methode
Ruft den aktiven (d. h. die letzte) Frame in der Kette.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppFrame`  
 [out] Ein Zeiger auf die Adresse eines ICorDebugFrame-Objekts, das den aktiven darstellt (d. h. die letzte) Frame in der Kette.  
  
## <a name="remarks"></a>Hinweise  
 Wenn kein verwalteter Stapelrahmen verfügbar ist, wird `ppFrame` ist festgelegt auf Null.  
  
 Wenn der aktive Frame nicht verfügbar ist, wird der Aufruf erfolgreich und `ppFrame` wird null sein. Aktive Frames werden nicht für Ketten durch CHAIN_ENTER_UNMANAGED initiiert wurden, und einige Ketten durch CHAIN_CLASS_INIT initiiert wurden. Finden Sie unter CorDebugChainReason-Enumeration.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
