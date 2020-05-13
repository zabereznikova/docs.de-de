---
title: ICorDebugFunction2::GetJMCStatus-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 56dc5f87b32b3aaa0bfbb69541d5a01ae26606ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213232"
---
# <a name="icordebugfunction2getjmcstatus-method"></a>ICorDebugFunction2::GetJMCStatus-Methode
Ruft einen Wert ab, der angibt, ob die Funktion, die durch dieses ICorDebugFunction2-Objekt dargestellt wird, als Benutzercode gekennzeichnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pbIsJustMyCode`  
 vorgenommen Ein Zeiger auf einen booleschen Wert `true` , der ist, wenn diese Funktion als Benutzercode gekennzeichnet ist, andernfalls ist der Wert `false` .  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Funktion, die von diesem dargestellt `ICorDebugFunction2` wird, nicht deentschlbelt werden kann, ist `pbIsJustMyCode` immer `false` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
