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
ms.openlocfilehash: 5157c62f2719a9d62608750cd122561807197494
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418293"
---
# <a name="icordebugmoduleisdynamic-method"></a>ICorDebugModule::IsDynamic-Methode
Ruft einen Wert, der angibt, ob dieses Modul dynamisch ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pDynamic`  
 [out] `true` ist dieses Modul dynamisch ist, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Ein dynamisches Modul kann neue Klassen hinzufügen und löschen vorhandene Klassen, selbst wenn das Modul geladen wurde. Die [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) Rückrufe informieren Sie den Debugger, wenn eine Klasse hinzugefügt oder gelöscht wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
