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
ms.openlocfilehash: 5774b40178ce0d7c2ef5d063a37b9011fc2630df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127948"
---
# <a name="icordebugmoduleisdynamic-method"></a>ICorDebugModule::IsDynamic-Methode
Ruft einen Wert ab, der angibt, ob dieses Modul dynamisch ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pDynamic`  
 [out] `true`, wenn dieses Modul dynamisch ist. Andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Ein dynamisches Modul kann neue Klassen hinzufügen und vorhandene Klassen löschen, auch nachdem das Modul geladen wurde. Die [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) -und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) -Rückrufe benachrichtigen den Debugger, wenn eine Klasse hinzugefügt oder gelöscht wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
