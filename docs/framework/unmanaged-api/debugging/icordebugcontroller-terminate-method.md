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
ms.openlocfilehash: 851a127c117b826c271dd021c41cfdb36045a1ff
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783752"
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
  
## <a name="parameters"></a>Parameters  
 `exitCode`  
 in Ein numerischer Wert, der der Exitcode ist. Die gültigen numerischen Werte werden in Winbase. h definiert.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Prozess beendet wird, wenn `Terminate` aufgerufen wird, sollte der Prozess mit der [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) -Methode fortgesetzt werden, damit der Debugger eine Bestätigung der Beendigung durch den [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) -oder [ICorDebugManagedCallback:: ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md) -Rückruf erhält.  
  
> [!NOTE]
> Diese Methode wird nicht von einer Anwendungsdomäne implementiert. Das heißt, es ist nicht auf <xref:System.AppDomain> Ebene implementiert.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
