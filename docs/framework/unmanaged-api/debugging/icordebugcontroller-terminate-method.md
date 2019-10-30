---
title: ICorDebugController::Terminate-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
ms.openlocfilehash: fb8cfb2d1c5902ecd0d5858ef21ba48b65b12506
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125334"
---
# <a name="icordebugcontrollerterminate-method"></a>ICorDebugController::Terminate-Methode
Beendet den Prozess mit dem angegebenen Exitcode.  
  
> [!NOTE]
> Bei dieser Methode handelt es sich um einen Wrapper für die Win32-`TerminateProcess` Funktion. Folglich verwendet `Terminate` den Exitcode auf die gleiche Weise, wie die Win32-`TerminateProcess` Funktion Sie verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `exitCode`  
 in Ein numerischer Wert, der der Exitcode ist. Die gültigen numerischen Werte werden in Winbase. h definiert.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Prozess beendet wird, wenn `Terminate` aufgerufen wird, sollte der Prozess mit der [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) -Methode fortgesetzt werden, damit der Debugger eine Bestätigung der Beendigung durch [ICorDebugManagedCallback erhält: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) -oder [ICorDebugManagedCallback:: ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) -Rückruf.  
  
> [!NOTE]
> Diese Methode wird nicht von einer Anwendungsdomäne implementiert. Das heißt, es ist nicht auf <xref:System.AppDomain> Ebene implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
