---
title: ICorDebugModuleEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b052aac7a71308486676aa688fd5ad655c2015f3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765292"
---
# <a name="icordebugmoduleenumnext-method"></a>ICorDebugModuleEnum::Next-Methode
Ruft die Anzahl der "ICorDebugModule"-Instanzen, die anhand des `celt` aus der Enumeration, die an der aktuellen Position ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `celt`  
 [in] Die Anzahl der `ICorDebugModule` Instanzen abgerufen werden sollen.  
  
 `modules`  
 [out] Ein Array von Zeigern, die jeweils auf eine `ICorDebugModule` Objekt.  
  
 `pceltFetched`  
 [out] Zeiger auf die Anzahl der `ICorDebugModule` Instanzen, die tatsächlich zurückgegeben. Dieser Wert kann null sein, wenn `celt` ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
