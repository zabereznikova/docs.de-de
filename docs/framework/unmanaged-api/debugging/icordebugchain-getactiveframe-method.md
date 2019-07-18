---
title: ICorDebugChain::GetActiveFrame-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c79f3b3b976b83eb99f8aa26d38a1fe316de471a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744998"
---
# <a name="icordebugchaingetactiveframe-method"></a>ICorDebugChain::GetActiveFrame-Methode
Ruft das aktive (d. h. die letzte) Frame in der Kette.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppFrame`  
 [out] Ein Zeiger auf die Adresse eines ICorDebugFrame-Objekts, das den aktiven darstellt (d. h. die letzte) Frame in der Kette.  
  
## <a name="remarks"></a>Hinweise  
 Wenn kein verwalteter Stapelrahmen verfügbar ist, `ppFrame` wird festgelegt auf Null.  
  
 Wenn der aktive Frame nicht verfügbar ist, wird der Aufruf erfolgreich und `ppFrame` NULL. Aktiven Frames sind nicht verfügbar für Ketten durch CHAIN_ENTER_UNMANAGED initiiert wurden, und für einige Ketten durch CHAIN_CLASS_INIT initiiert wurden. Finden Sie unter der CorDebugChainReason-Enumeration.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
