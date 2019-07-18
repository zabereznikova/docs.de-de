---
title: ICorDebugModule::IsDynamic-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsDynamic
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db5d07d2b9a295a5cd21b4d4af954503b8bd7a8b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763668"
---
# <a name="icordebugmoduleisdynamic-method"></a>ICorDebugModule::IsDynamic-Methode
Ruft einen Wert, der angibt, ob dieses Modul dynamisch ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pDynamic`  
 [out] `true` Wenn dieses Modul, dynamische, andernfalls ist `false`.  
  
## <a name="remarks"></a>Hinweise  
 Ein dynamisches Modul kann neue Klassen hinzufügen und löschen vorhandene Klassen aus, auch wenn das Modul geladen wurde. Die [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) -Rückrufe informieren Sie den Debugger, wenn eine Klasse hinzugefügt oder gelöscht wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
