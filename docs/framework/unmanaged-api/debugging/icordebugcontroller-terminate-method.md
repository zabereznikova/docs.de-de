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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4c8dd8795fc3699176490ea0bb9b2e999038afb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749064"
---
# <a name="icordebugcontrollerterminate-method"></a>ICorDebugController::Terminate-Methode
Beendet den Prozess mit den angegebenen Exitcode.  
  
> [!NOTE]
>  Diese Methode ist ein Wrapper für die Win32- `TerminateProcess` Funktion. Daher `Terminate` verwendet den Exitcode in der gleichen Weise wie die Win32 `TerminateProcess` Funktion wird verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `exitCode`  
 [in] Ein numerischer Wert, der den Exitcode. Die gültigen numerischen Werte sind in Winbase.h definiert.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Prozess, wenn beendet wird `Terminate` ist aufgerufen wird, der Prozess weiter mithilfe der [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) Methode, damit der Debugger die Bestätigung für die Beendigung über empfängt die [ ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) oder [ICorDebugManagedCallback:: ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) Rückruf.  
  
> [!NOTE]
>  Diese Methode wird von einer Anwendungsdomäne nicht implementiert. D. h. es ist nicht auf implementiert die <xref:System.AppDomain> Ebene.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
