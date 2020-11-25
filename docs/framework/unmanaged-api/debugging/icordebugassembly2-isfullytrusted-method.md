---
title: ICorDebugAssembly2::IsFullyTrusted-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
ms.openlocfilehash: 8a2a6be0db76f5ee2c7fa67c2038e0a5c845bd0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719709"
---
# <a name="icordebugassembly2isfullytrusted-method"></a>ICorDebugAssembly2::IsFullyTrusted-Methode

Ruft einen Wert ab, der angibt, ob dem Lauf Zeit Sicherheitssystem volle Vertrauenswürdigkeit für die Assembly gewährt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pbFullyTrusted`  
 [out] `true` , wenn der Assembly vom Lauf Zeit Sicherheitssystem volle Vertrauenswürdigkeit gewährt wurde. andernfalls `false` .  
  
## <a name="remarks"></a>Hinweise  

 Diese Methode gibt ein HRESULT von CORDBG_E_NOTREADY zurück, wenn die Sicherheitsrichtlinie für die Assembly noch nicht aufgelöst wurde, d. h., wenn noch kein Code in der Assembly ausgeführt wurde.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
