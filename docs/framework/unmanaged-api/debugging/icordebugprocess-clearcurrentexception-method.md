---
title: ICorDebugProcess::ClearCurrentException-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
ms.openlocfilehash: 37a7d8fa4439d52db3cddfff22ac6580b19af58a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128913"
---
# <a name="icordebugprocessclearcurrentexception-method"></a>ICorDebugProcess::ClearCurrentException-Methode
Löscht die aktuelle nicht verwaltete Ausnahme für den angegebenen Thread.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a>Parameter  
 `threadID`  
 in Die ID des Threads, in dem die aktuelle nicht verwaltete Ausnahme gelöscht wird.  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode auf, bevor Sie [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) aufrufen, wenn ein Thread eine nicht verwaltete Ausnahme gemeldet hat, die von der zu debuggenden Komponente ignoriert werden soll. Hierdurch werden sowohl die ausstehenden in-Band (IB)-als auch die Out-of-Band-Ereignisse (OOB) für den angegebenen Thread gelöscht. Alle OOB-Breakpoints und Einzelschritt-Ausnahmen werden automatisch gelöscht.  
  
 Verwenden Sie [ICorDebugThread2:: intercepteption TException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) , um die aktuelle verwaltete Ausnahme in einem Thread abzufangen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
