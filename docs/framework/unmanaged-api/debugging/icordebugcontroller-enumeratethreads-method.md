---
title: ICorDebugController::EnumerateThreads-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugController.EnumerateThreads
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type:
- apiref
ms.openlocfilehash: 291f6c05171b5e507afaa70537aafdc9002a506e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125407"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a>ICorDebugController::EnumerateThreads-Methode
Ruft einen Enumerator für die aktiven verwalteten Threads im Prozess ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppThreads`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugThreadEnum-Objekts, das einen Enumerator für alle verwalteten Threads darstellt, die im Prozess aktiv sind.  
  
## <a name="remarks"></a>Hinweise  
 Ein Thread wird als aktiv betrachtet, nachdem der [ICorDebugManagedCallback:: aliatethread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) -Rückruf gesendet wurde und bevor der [ICorDebugManagedCallback:: ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) -Rückruf gesendet wurde. Ein verwalteter Thread verfügt möglicherweise nicht unbedingt über verwaltete Frames auf dem Stapel. Threads können auch vor dem Rückruf [ICorDebugManagedCallback:: forateprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) aufgezählt werden. Die Enumeration ist natürlich leer.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
