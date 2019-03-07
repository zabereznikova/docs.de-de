---
title: ICorDebugFunction2::SetJMCStatus-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49ced1b4be888c7550c3927d1b319ab2f0bef086
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501005"
---
# <a name="icordebugfunction2setjmcstatus-method"></a>ICorDebugFunction2::SetJMCStatus-Methode
Markiert die Funktion, die von dieser ICorDebugFunction2 dargestellt für nur mein Code schrittweise ausführen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `bIsJustMyCode`  
 [in] Legen Sie auf `true` , markieren Sie die Funktion als Benutzercode; legen Sie andernfalls auf `false`.  
  
## <a name="return-values"></a>Rückgabewerte  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|Die Funktion wurde erfolgreich markiert.|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|Die Funktion konnte nicht als Benutzercode gekennzeichnet werden, da es nicht gedebuggt werden kann.|  
  
## <a name="remarks"></a>Hinweise  
 Eine zugeordnetem nur mein Code wird nicht benutzerseitiger Code überspringen. Benutzercode muss es sich um eine Teilmenge der debugfähiger Code sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
