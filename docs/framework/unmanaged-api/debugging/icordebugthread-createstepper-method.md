---
title: ICorDebugThread::CreateStepper-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
ms.openlocfilehash: a74d32478bc88ee634fa5ff9b61ac2059bc8e302
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379717"
---
# <a name="icordebugthreadcreatestepper-method"></a>ICorDebugThread::CreateStepper-Methode
Erstellt ein ICorDebugStepper-Objekt, mit dem der aktive Frame dieses ICorDebugThread schrittweise durchlaufen werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppStepper`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugStepper` Objekts, das das schrittweise durchlaufen des aktiven Frames dieses Threads ermöglicht.  
  
## <a name="remarks"></a>Hinweise  
 Der aktive Frame kann nicht verwalteter Code sein.  
  
 Die- `ICorDebugStepper` Schnittstelle muss verwendet werden, um die tatsächliche Schritt Ausführung auszuführen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
