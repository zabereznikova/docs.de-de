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
ms.openlocfilehash: 7da12554ba1db9a467aa03c01bfb3b584125b129
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213191"
---
# <a name="icordebugfunction2setjmcstatus-method"></a>ICorDebugFunction2::SetJMCStatus-Methode
Markiert die durch dieses ICorDebugFunction2 dargestellte Funktion für nur eigenen Code schrittweise.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `bIsJustMyCode`  
 in Legen Sie auf fest, `true` um die Funktion als Benutzercode zu markieren; andernfalls legen Sie auf fest `false` .  
  
## <a name="return-values"></a>Rückgabewerte  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|Die Funktion wurde erfolgreich gekennzeichnet.|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|Die Funktion konnte nicht als Benutzercode gekennzeichnet werden, da Sie nicht deentschlbelt werden kann.|  
  
## <a name="remarks"></a>Hinweise  
 Ein nur eigenen Code Stepper überspringt Nichtbenutzer Code. Der Benutzercode muss eine Teilmenge des debugfähigen Codes sein.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
