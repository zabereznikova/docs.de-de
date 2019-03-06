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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 900fece1dd29f73f77b85ff08e4deff1396f8aaf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484510"
---
# <a name="icordebugthreadgethandle-method"></a>ICorDebugThread::GetHandle-Methode
Ruft das aktuelle Handle für den aktiven Teil des ICorDebugThread ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `phThreadHandle`  
 [out] Ein Zeiger auf einen HTHREAD, der das Handle des aktiven Teils des Threads ist.  
  
## <a name="remarks"></a>Hinweise  
 Das Handle kann sich ändern, während der Prozess ausgeführt wird, und für die verschiedenen Teile des Threads kann abweichen.  
  
 Dieses Handle ist im Besitz der Debuggen-API. Der Debugger sollte es vor der Verwendung duplizieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
