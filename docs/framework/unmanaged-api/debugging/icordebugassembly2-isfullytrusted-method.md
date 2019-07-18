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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d231595ab2c7b41d1a24f654e9785b90b34ac780
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744503"
---
# <a name="icordebugassembly2isfullytrusted-method"></a>ICorDebugAssembly2::IsFullyTrusted-Methode
Ruft einen Wert, der angibt, ob die Assembly volle Vertrauenswürdigkeit von der Laufzeit-Sicherheitssystem erteilt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pbFullyTrusted`  
 [out] `true` Wenn die Assembly volle Vertrauenswürdigkeit von der Laufzeit-Sicherheitssystem; erteilt wurde, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode gibt, dass ein CORDBG_E_NOTREADY-HRESULT zurück, wenn die Sicherheitsrichtlinie für die Assembly noch nicht aufgelöst, d. h., wenn kein Code in der Assembly wurde noch ausgeführt wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
