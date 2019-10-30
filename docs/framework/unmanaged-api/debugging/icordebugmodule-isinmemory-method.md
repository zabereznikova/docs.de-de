---
title: ICorDebugModule::IsInMemory-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
ms.openlocfilehash: 1384acff4ea3d1aa820b065cd2c56f649f0cbdbb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127923"
---
# <a name="icordebugmoduleisinmemory-method"></a>ICorDebugModule::IsInMemory-Methode
Ruft einen Wert ab, der angibt, ob dieses Modul nur im Arbeitsspeicher vorhanden ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pInMemory`  
 [out] `true`, wenn dieses Modul nur im Arbeitsspeicher vorhanden ist. Andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Der Common Language Runtime (CLR) unterstützt das Laden von Modulen aus unformatierten Datenströmen. Solche Module werden als *in-Memory-Module* bezeichnet und sind auf dem Datenträger nicht vorhanden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
