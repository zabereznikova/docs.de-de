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
ms.openlocfilehash: f66ef88646c314502dcb610cec8ce822cab1fca2
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379281"
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
