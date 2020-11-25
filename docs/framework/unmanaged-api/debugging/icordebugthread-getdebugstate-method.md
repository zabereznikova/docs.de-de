---
title: ICorDebugThread::GetDebugState-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
ms.openlocfilehash: 746fef3629e6573d7dfe47d5a3fcf9ee9a1d4250
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728042"
---
# <a name="icordebugthreadgetdebugstate-method"></a>ICorDebugThread::GetDebugState-Methode

Ruft den aktuellen Debugzustand dieses ICorDebugThread-Objekts ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pState`  
 vorgenommen Ein Zeiger auf eine bitweise Kombination von CorDebugThreadState-Enumerationswerten, die den aktuellen Debugzustand dieses Threads beschreibt.  
  
## <a name="remarks"></a>Hinweise  

 Wenn der Prozess aktuell beendet ist, `pState` stellt den Debugzustand dar, der für diesen Thread vorhanden wäre, wenn der Prozess fortgesetzt werden soll, und nicht den tatsächlichen aktuellen Zustand dieses Threads.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
