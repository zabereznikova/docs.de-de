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
ms.openlocfilehash: 45b1d0c0a3199227ab644ba8732198dd14b1cb4c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792999"
---
# <a name="icordebugmoduleisdynamic-method"></a>ICorDebugModule::IsDynamic-Methode
Ruft einen Wert ab, der angibt, ob dieses Modul dynamisch ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pDynamic`  
 [out] `true`, wenn dieses Modul dynamisch ist. Andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Ein dynamisches Modul kann neue Klassen hinzufügen und vorhandene Klassen löschen, auch nachdem das Modul geladen wurde. Die [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) -und [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) -Rückrufe benachrichtigen den Debugger, wenn eine Klasse hinzugefügt oder gelöscht wurde.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
