---
title: ICorDebug::SetUnmanagedHandler-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49567bc354ddad56311268bef0a367b8896f2ab8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475670"
---
# <a name="icordebugsetunmanagedhandler-method"></a>ICorDebug::SetUnmanagedHandler-Methode
Gibt das Ereignishandlerobjekt für nicht verwaltete Ereignisse an.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pCallback`  
 [in] Ein Zeiger auf ein [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) -Objekt, das den Ereignishandler für nicht verwaltete Ereignisse darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Der Ereignishandler Objekt für nicht verwaltete Ereignisse müssen festgelegt werden, nach einem Aufruf von [ICorDebug:: Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) und vor allen Aufrufen von [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) oder [ICorDebug:: DebugActiveProcess ](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md). Allerdings werden für Legacyzwecke müssen nicht legen Sie das Ereignishandlerobjekt für nicht verwaltete Ereignisse, bis das erste systemeigenen Debug-Ereignis ausgelöst wird. Insbesondere wenn `ICorDebug::CreateProcess` wurde festgelegt des CREATE_SUSPENDED-Flags, systemeigenen Debug-Ereignisse nicht verteilt werden, bis der Haupt-Thread fortgesetzt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
