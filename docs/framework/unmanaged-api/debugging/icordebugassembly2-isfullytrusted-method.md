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
ms.openlocfilehash: dd82709064fe7f7d912d93f4b3f0248769f02b9e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894885"
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
 vorgenommen `true` , wenn der Assembly vom Lauf Zeit Sicherheitssystem volle Vertrauenswürdigkeit gewährt wurde. andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode gibt ein HRESULT von CORDBG_E_NOTREADY zurück, wenn die Sicherheitsrichtlinie für die Assembly noch nicht aufgelöst wurde, d. h., wenn noch kein Code in der Assembly ausgeführt wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
