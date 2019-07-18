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
ms.openlocfilehash: 0baabbb736365b138d1754e68070207b4310bf57
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762462"
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
 [out] Ein Zeiger auf eine bitweise Kombination der Werte der CorDebugThreadState-Enumeration, die den aktuellen Debugzustand dieses Threads beschreibt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Prozess gerade beendet wird, `pState` den Debugzustand, der für diesen Thread vorhanden wäre, würde der Vorgang fortgesetzt werden, wird nicht den aktuellen Zustand dieses Threads darstellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
