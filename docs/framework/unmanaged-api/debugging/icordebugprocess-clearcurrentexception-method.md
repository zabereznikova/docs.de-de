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
ms.openlocfilehash: 4cfacb7f3303947ec8b11362fde82649687889d8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792664"
---
# <a name="icordebugprocessclearcurrentexception-method"></a>ICorDebugProcess::ClearCurrentException-Methode
Löscht die aktuelle nicht verwaltete Ausnahme für den angegebenen Thread.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a>Parameters  
 `threadID`  
 in Die ID des Threads, in dem die aktuelle nicht verwaltete Ausnahme gelöscht wird.  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode auf, bevor Sie [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) aufrufen, wenn ein Thread eine nicht verwaltete Ausnahme gemeldet hat, die von der zu debuggenden Komponente ignoriert werden soll. Hierdurch werden sowohl die ausstehenden in-Band (IB)-als auch die Out-of-Band-Ereignisse (OOB) für den angegebenen Thread gelöscht. Alle OOB-Breakpoints und Einzelschritt-Ausnahmen werden automatisch gelöscht.  
  
 Verwenden Sie [ICorDebugThread2:: intercepteption TException](icordebugthread2-interceptcurrentexception-method.md) , um die aktuelle verwaltete Ausnahme in einem Thread abzufangen.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
