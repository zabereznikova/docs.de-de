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
ms.openlocfilehash: 96e3a90bcb7700915bfd3618d7bae40c0ff64a75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678596"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a>ICorDebugThread2::InterceptCurrentException-Methode

Ermöglicht einem Debugger das Abfangen der aktuellen Ausnahme in diesem Thread.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pFrame`  
 in Ein Zeiger auf ein ICorDebug Frame-Element, das den aktiven Stapel Rahmen darstellt.  
  
## <a name="remarks"></a>Hinweise  

 Die `InterceptCurrentException` -Methode kann zwischen einem Ausnahme Rückruf ([ICorDebugManagedCallback:: Exception](icordebugmanagedcallback-exception-method.md) oder [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md)) und dem zugeordneten Aufruf von [ICorDebugController:: Continue](icordebugcontroller-continue-method.md)aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
