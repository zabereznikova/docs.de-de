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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 223989d883c421be228fb3d6a608643a5246c060
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763702"
---
# <a name="icordebugmoduleisinmemory-method"></a>ICorDebugModule::IsInMemory-Methode
Ruft einen Wert, der angibt, ob dieses Modul nur im Arbeitsspeicher vorhanden ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pInMemory`  
 [out] `true` Wenn dieses Modul nur im Speicher vorhanden ist, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Die common Language Runtime (CLR) unterstützt das Laden der Module von unformatierte Bytedatenströme. Solcher Module heißen *in-Memory-Module* und sind nicht auf dem Datenträger vorhanden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
