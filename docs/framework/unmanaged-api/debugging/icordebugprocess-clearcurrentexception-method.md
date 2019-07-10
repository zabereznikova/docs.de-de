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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ad7dd3ae0e547933fdf7d579116dccc62ae579c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766147"
---
# <a name="icordebugprocessclearcurrentexception-method"></a>ICorDebugProcess::ClearCurrentException-Methode
Löscht die aktuelle nicht verwaltete Ausnahme für den angegebenen Thread.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a>Parameter  
 `threadID`  
 [in] Die ID des Threads auf dem die aktuelle nicht verwaltete Ausnahme wird gelöscht.  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode vor dem Aufruf [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) ein Thread hat eine nicht verwaltete Ausnahme, die von der zu debuggenden Komponente ignoriert werden soll wenn gemeldet. Hierdurch wird die ausstehenden in-Band-(IB) und die Out-of-Band (OOB)-Ereignisse auf den angegebenen Thread gelöscht. Alle OOB-Haltepunkte und Schritt für Schritt Ausnahmen werden automatisch gelöscht.  
  
 Verwendung [ICorDebugThread2:: InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) verwaltet sie abgefangen wird die aktuelle Ausnahme in einem Thread.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
