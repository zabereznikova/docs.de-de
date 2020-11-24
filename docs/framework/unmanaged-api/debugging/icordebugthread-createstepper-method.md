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
ms.openlocfilehash: dcaa5adc41a9e451b123b088dd900f01d9161689
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688275"
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
