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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95a00e8646589e7897636c1698b7c2647cd233fd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771804"
---
# <a name="icordebugthreadcreatestepper-method"></a>ICorDebugThread::CreateStepper-Methode
Erstellt ein ICorDebugStepper-Objekt, die schrittweise Ausführung des aktiven Frames dieses ICorDebugThread ermöglicht.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppStepper`  
 [out] Ein Zeiger auf die Adresse einer `ICorDebugStepper` -Objekt, das schrittweise Ausführung des aktiven Frames dieses Threads ermöglicht.  
  
## <a name="remarks"></a>Hinweise  
 Des aktiven Frames möglicherweise nicht verwaltetem Code.  
  
 Die `ICorDebugStepper` Schnittstelle muss für die schrittweise Ausführung verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
