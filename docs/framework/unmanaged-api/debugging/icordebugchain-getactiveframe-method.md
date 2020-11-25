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
ms.openlocfilehash: daecd216b4d7e9c23336b8956c13735549be901b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730135"
---
# <a name="icordebugchaingetactiveframe-method"></a>ICorDebugChain::GetActiveFrame-Methode

Ruft den aktiven Frame (d. h. den aktuellen) Frame in der Kette ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppFrame`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebug-Frame-Objekts, das den aktiven Frame (d. h. den aktuellen) Frame in der Kette darstellt.  
  
## <a name="remarks"></a>Hinweise  

 Wenn kein verwalteter Stapel Rahmen verfügbar ist, `ppFrame` wird auf NULL festgelegt.  
  
 Wenn der aktive Frame nicht verfügbar ist, wird der-Vorgang erfolgreich ausgeführt und ist `ppFrame` NULL. Aktive Frames sind nicht für Ketten verfügbar, die aufgrund von CHAIN_ENTER_UNMANAGED initiiert wurden, und für einige Ketten, die aufgrund CHAIN_CLASS_INIT initiiert wurden. Weitere Informationen finden Sie in der Cordebug-Enumeration.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
