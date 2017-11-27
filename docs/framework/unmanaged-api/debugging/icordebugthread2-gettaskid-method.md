---
title: ICorDebugThread2::GetTaskID-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread2.GetTaskID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e2d5a845b7047949618bed4176e6d24fee43c14
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthread2gettaskid-method"></a>ICorDebugThread2::GetTaskID-Methode
Ruft den Bezeichner des Tasks in diesem Thread ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pTaskId`  
 [out] Ein Zeiger auf den Bezeichner der Aufgabe, die Ausführung für den Thread, der von diesem ICorDebugThread2-Objekt dargestellt.  
  
## <a name="remarks"></a>Hinweise  
 Eine Aufgabe kann nur auf dem Thread ausgeführt werden, wenn der Thread eine Verbindung zugeordnet ist. `GetTaskID`Gibt NULL zurück, `pTaskId` , wenn der Thread nicht mit einer Verbindung verknüpft ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
