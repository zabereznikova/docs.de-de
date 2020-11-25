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
ms.openlocfilehash: f98118f9206d9ccd7dc9dc9a943500c7b4cd676a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732657"
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

 Ein Thread wird als aktiv betrachtet, nachdem der [ICorDebugManagedCallback:: aliatethread](icordebugmanagedcallback-createthread-method.md) -Rückruf gesendet wurde und bevor der [ICorDebugManagedCallback:: ExitThread](icordebugmanagedcallback-exitthread-method.md) -Rückruf gesendet wurde. Ein verwalteter Thread verfügt möglicherweise nicht unbedingt über verwaltete Frames auf dem Stapel. Threads können auch vor dem Rückruf [ICorDebugManagedCallback:: forateprocess](icordebugmanagedcallback-createprocess-method.md) aufgezählt werden. Die Enumeration ist natürlich leer.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen
