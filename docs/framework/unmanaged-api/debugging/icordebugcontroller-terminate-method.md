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
ms.openlocfilehash: 460aeeca9d62ce91a11a24d774c8e681ed4f00ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679805"
---
# <a name="icordebugcontrollerterminate-method"></a>ICorDebugController::Terminate-Methode

Beendet den Prozess mit dem angegebenen Exitcode.  
  
> [!NOTE]
> Bei dieser Methode handelt es sich um einen Wrapper für die Win32- `TerminateProcess` Funktion. Folglich `Terminate` verwendet den Exitcode auf dieselbe Weise wie die Win32- `TerminateProcess` Funktion.  
  
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

 Wenn der Prozess beendet wird `Terminate` , wenn aufgerufen wird, sollte der Prozess mit der [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) -Methode fortgesetzt werden, damit der Debugger eine Bestätigung der Beendigung durch den [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) -oder [ICorDebugManagedCallback:: ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md) -Rückruf erhält.  
  
> [!NOTE]
> Diese Methode wird nicht von einer Anwendungsdomäne implementiert. Das heißt, es ist nicht auf der <xref:System.AppDomain> Ebene implementiert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen
