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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68df19120f2e0b45e73f9d5e137afc8a5e7ac513
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987154"
---
# <a name="icordebugthreadgetdebugstate-method"></a>ICorDebugThread::GetDebugState-Methode
Ruft den aktuellen Debugzustand dieses ICorDebugThread-Objekts ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pState`  
 [out] Ein Zeiger auf eine bitweise Kombination der Werte der CorDebugThreadState-Enumeration, die den aktuellen Debugzustand dieses Threads beschreibt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Prozess gerade beendet wird, `pState` den Debugzustand, der für diesen Thread vorhanden wäre, würde der Vorgang fortgesetzt werden, wird nicht den aktuellen Zustand dieses Threads darstellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
