---
title: ICorDebugThread2::GetTaskID-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type:
- apiref
ms.openlocfilehash: d5f2838007504e56ad44614a6778083be046629f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140073"
---
# <a name="icordebugthread2gettaskid-method"></a>ICorDebugThread2::GetTaskID-Methode
Ruft den Bezeichner der Aufgabe ab, die auf diesem Thread ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pTaskId`  
 vorgenommen Ein Zeiger auf den Bezeichner der Aufgabe, die auf dem Thread ausgeführt wird, der durch dieses ICorDebugThread2-Objekt dargestellt wird.  
  
## <a name="remarks"></a>Hinweise  
 Ein Task kann nur auf dem Thread ausgeführt werden, wenn der Thread einer Verbindung zugeordnet ist. `GetTaskID` gibt in `pTaskId` 0 (null) zurück, wenn der Thread keiner Verbindung zugeordnet ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
