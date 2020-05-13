---
title: ICorDebugThread::GetID-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type:
- apiref
ms.openlocfilehash: d01936481ec139757566d5b96cb95ea887cb8c20
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378057"
---
# <a name="icordebugthreadgetid-method"></a>ICorDebugThread::GetID-Methode
Ruft den aktuellen Betriebssystem Bezeichner des aktiven Teils dieses ICorDebugThread ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pdwThreadId`  
 vorgenommen Der Bezeichner des Threads.  
  
## <a name="remarks"></a>Hinweise  
 Der Bezeichner des Betriebssystems kann sich möglicherweise während der Ausführung eines Prozesses ändern und kann einen anderen Wert für verschiedene Teile des Threads aufweisen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
