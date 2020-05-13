---
title: ICorDebugThread::GetHandle-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
ms.openlocfilehash: 16aafa439fc81c3606f98ca2ba860316ec46e0db
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379740"
---
# <a name="icordebugthreadgethandle-method"></a>ICorDebugThread::GetHandle-Methode
Ruft das aktuelle Handle für den aktiven Teil dieses ICorDebugThread ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `phThreadHandle`  
 vorgenommen Ein Zeiger auf einen hThread, der das Handle des aktiven Teils dieses Threads ist.  
  
## <a name="remarks"></a>Hinweise  
 Das Handle kann sich ändern, wenn der Prozess ausgeführt wird, und unterscheidet sich möglicherweise für verschiedene Teile des Threads.  
  
 Dieses Handle gehört der Debug-API an. Der Debugger sollte ihn vor der Verwendung duplizieren.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
