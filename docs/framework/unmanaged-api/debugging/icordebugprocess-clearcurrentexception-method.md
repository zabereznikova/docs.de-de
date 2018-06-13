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
ms.openlocfilehash: d2515e21ec00bd656eafd21a092a27304f7b1769
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419015"
---
# <a name="icordebugprocessclearcurrentexception-method"></a>ICorDebugProcess::ClearCurrentException-Methode
Löscht die aktuellen nicht verwalteten Ausnahme für den angegebenen Thread.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
#### <a name="parameters"></a>Parameter  
 `threadID`  
 [in] Die ID des Threads, die auf dem aktuelle nicht verwalteten Ausnahme gelöscht wird.  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode vor dem Aufruf [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) Wenn ein Thread eine nicht verwaltete Ausnahme, die von der zu debuggenden Komponente ignoriert werden sollen gemeldet wurde. Hiermit löschen Sie die ausstehenden in-Band-(IB) und die Out-of-Band (OOB) Ereignisse auf den angegebenen Thread. Alle OOB-Haltepunkte und einstufiger Ausnahmen werden automatisch gelöscht.  
  
 Verwendung [ICorDebugThread2:: InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) verwaltet Sie zum Abfangen von des aktuellen Ausnahme in einem Thread.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
