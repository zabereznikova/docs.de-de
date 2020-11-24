---
title: ICorDebugThread::CreateEval-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
ms.openlocfilehash: 1c0037530ae4f40be5bef4da8f398afe5f2bbb91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688288"
---
# <a name="icordebugthreadcreateeval-method"></a>ICorDebugThread::CreateEval-Methode

Erstellt ein ICorDebugEval-Objekt, das die Funktionalität dieses ICorDebugThread sammelt und verfügbar macht.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppEval`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugEval` Objekts, das die Funktionalität dieses Threads sammelt und verfügbar macht.  
  
## <a name="remarks"></a>Hinweise  

 Das Auswertungs Objekt überträgt eine neue Kette im Thread, bevor die Berechnung durchgeführt wird. Dadurch wird die derzeit auf dem Thread ausgeführte Berechnung unterbrochen, bis die Auswertung abgeschlossen ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
