---
title: ICorDebugThread2::InterceptCurrentException-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.InterceptCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::InterceptCurrentException
helpviewer_keywords:
- InterceptCurrentException method [.NET Framework debugging]
- ICorDebugThread2::InterceptCurrentException method [.NET Framework debugging]
ms.assetid: 536d2357-1b97-49e0-a10c-c860aed74e6e
topic_type:
- apiref
ms.openlocfilehash: c25a03ef5bbba18da31787c911f83a1348badd4b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791452"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a>ICorDebugThread2::InterceptCurrentException-Methode
Ermöglicht einem Debugger das Abfangen der aktuellen Ausnahme in diesem Thread.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pFrame`  
 in Ein Zeiger auf ein ICorDebug Frame-Element, das den aktiven Stapel Rahmen darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die `InterceptCurrentException`-Methode kann zwischen einem Ausnahme Rückruf ([ICorDebugManagedCallback:: Exception](icordebugmanagedcallback-exception-method.md) oder [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md)) und dem zugeordneten Aufruf von [ICorDebugController:: Continue](icordebugcontroller-continue-method.md)aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
