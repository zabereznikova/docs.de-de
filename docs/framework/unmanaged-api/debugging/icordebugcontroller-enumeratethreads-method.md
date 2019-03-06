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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a4bb4072c574edeac1c531978fac75595c252e0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481598"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a>ICorDebugController::EnumerateThreads-Methode
Ruft einen Enumerator für die aktiv verwalteten Threads im Prozess ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppThreads`  
 [out] Ein Zeiger auf die Adresse des "ICorDebugThreadEnum"-Objekts, das einen Enumerator für alle verwalteten Threads darstellt, die im Prozess aktiv sind.  
  
## <a name="remarks"></a>Hinweise  
 Ein Thread wird als aktiv betrachtet, nachdem die [ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) Rückruf wurde gesendet wurden und vor der [ICorDebugManagedCallback:: ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) Rückruf wurde gesendet wurden . Ein verwalteter Thread kann nicht verwalteter Frames auf seinen Stapel unbedingt. Threads aufgelistet werden können, sogar vor dem [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) Rückruf. Die Enumeration wird auf natürliche Weise leer sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

