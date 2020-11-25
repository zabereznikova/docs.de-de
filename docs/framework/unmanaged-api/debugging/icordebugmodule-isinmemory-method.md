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
ms.openlocfilehash: 637cac67e73d38aca0fdc5eaeae5405c4a859aa3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709816"
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
 [out] `true` , wenn dieses Modul nur im Arbeitsspeicher vorhanden ist. andernfalls `false` .  
  
## <a name="remarks"></a>Hinweise  

 Der Common Language Runtime (CLR) unterstützt das Laden von Modulen aus unformatierten Datenströmen. Solche Module werden als *in-Memory-Module* bezeichnet und sind auf dem Datenträger nicht vorhanden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen
