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
ms.openlocfilehash: 815dc63a2dedecc613506b0f98702f58d6e7bd04
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783792"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a>ICorDebugController::EnumerateThreads-Methode
Ruft einen Enumerator für die aktiven verwalteten Threads im Prozess ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ppThreads`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugThreadEnum-Objekts, das einen Enumerator für alle verwalteten Threads darstellt, die im Prozess aktiv sind.  
  
## <a name="remarks"></a>Hinweise  
 Ein Thread wird als aktiv betrachtet, nachdem der [ICorDebugManagedCallback:: aliatethread](icordebugmanagedcallback-createthread-method.md) -Rückruf gesendet wurde und bevor der [ICorDebugManagedCallback:: ExitThread](icordebugmanagedcallback-exitthread-method.md) -Rückruf gesendet wurde. Ein verwalteter Thread verfügt möglicherweise nicht unbedingt über verwaltete Frames auf dem Stapel. Threads können auch vor dem Rückruf [ICorDebugManagedCallback:: forateprocess](icordebugmanagedcallback-createprocess-method.md) aufgezählt werden. Die Enumeration ist natürlich leer.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
