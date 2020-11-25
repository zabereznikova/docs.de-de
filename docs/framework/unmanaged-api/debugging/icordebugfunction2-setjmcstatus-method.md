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
ms.openlocfilehash: 55f219b5b834f365b87440e69bfa7d2c4e519235
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696090"
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
  
|HRESULT|BESCHREIBUNG|  
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
