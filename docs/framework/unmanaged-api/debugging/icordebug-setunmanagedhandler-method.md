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
ms.openlocfilehash: 36d314211d95dff6648753f5d550a2cfd402a918
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134047"
---
# <a name="icordebugsetunmanagedhandler-method"></a>ICorDebug::SetUnmanagedHandler-Methode
Gibt das Ereignishandlerobjekt für nicht verwaltete Ereignisse an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pCallback`  
 in Ein Zeiger auf ein [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) -Objekt, das den Ereignishandler für nicht verwaltete Ereignisse darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Das Ereignishandlerobjekt für nicht verwaltete Ereignisse muss nach einem Aufruf von [ICorDebug:: Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) und vor allen Aufrufen von [ICorDebug:: deateprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) oder [ICorDebug::D ebugactiveprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)festgelegt werden. Allerdings müssen Sie für Legacy Zwecke das Ereignishandlerobjekt nicht für nicht verwaltete Ereignisse festlegen, bis das erste systemeigene Debugereignis ausgelöst wird. Insbesondere, wenn `ICorDebug::CreateProcess` das CREATE_SUSPENDED-Flag festgelegt hat, können systemeigene Debugereignisse erst weitergeleitet werden, wenn der Haupt Thread fortgesetzt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
